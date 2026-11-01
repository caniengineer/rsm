# QuantaAlpha vs. our approach

**Compared against:** [QuantaAlpha/QuantaAlpha](https://github.com/QuantaAlpha/QuantaAlpha) @ `b7ceb27` (2026-06-29), arXiv [2602.07085](https://arxiv.org/abs/2602.07085)

**Our approach, as stated:** build or train an agent that is expert at backtesting. We do it by repeatedly giving it financial research papers, all about factor investing, and asking it to check whether each paper's findings hold up.

---

## 1. What QuantaAlpha actually is

QuantaAlpha mines alpha factors with an LLM. It is a fork of Microsoft **RD-Agent** with ideas from **AlphaAgent**, and it runs on **Qlib** over China A-shares (CSI 300).

**Input:** a short natural-language direction, e.g. `./run.sh "Price-Volume Factor Mining"`.

**Pipeline** (`quantaalpha/pipeline/`):

1. **Planning** (`planning.py`). The LLM expands the direction into N "orthogonal" sub-directions (2 by default).
2. **Main loop**, 5 steps (`loop.py::AlphaAgentLoop`): `factor_propose → factor_construct → factor_calculate → factor_backtest → feedback`.
   - *Propose:* the LLM writes a hypothesis. It sees the last 10 rounds of (hypothesis, code, feedback).
   - *Construct:* the LLM writes the factor as an expression in a **restricted DSL** of about 60 operators (`TS_MEAN`, `RANK`, `REGRESI`, `RSI`…). The DSL can only use `$open $high $low $close $volume $return` (`factors/prompts/prompts.yaml::function_lib_description`).
   - *Quality gates* (`factors/regulator/`): complexity limits (symbol length ≤ 200, ≤ 5 base features, free-parameter ratio ≤ 0.5), AST-subtree **redundancy** matching against a factor zoo, and an optional LLM **consistency check** of hypothesis → description → formula → expression, with auto-correction.
   - *Backtest:* the new factor plus 4 base price features go into a **LightGBM** model that predicts the 2-day return. The model output drives a **TopK-Dropout** portfolio (top 50, drop 5) on CSI 300 with costs. Inside the loop: train 2016–19 / valid 2020 / test 2021. Final reported test: 2022–2025 (`configs/backtest.yaml`).
   - *Feedback:* the LLM judges whether the result supports the hypothesis and whether it beats SOTA ("Replace Best Result: yes/no"). It is told repeatedly to simplify complex factors to avoid overfitting.
3. **Evolution** (`pipeline/evolution/`). Each loop's output is stored as a *trajectory* in a pool. Next come **mutation** rounds (the LLM writes a hypothesis "orthogonal" to a parent) and **crossover** rounds (the LLM fuses 2 parents). Parents are picked by metric (`best`, `weighted`, …).
4. **Output:** `all_factors_library.json` plus a standalone backtester and a React dashboard.

**Headline result:** on CSI 300, 2022–25, IC 0.047, ARR 4.7%, IR 0.65, MDD 11.8%. Zero-shot transfer to CSI 500 and S&P 500.

### Things the README doesn't tell you

- **"Self-evolving" does not mean the model is trained.** The LLM is frozen and called via an API. All "learning" is prompt context: the last 10 trace entries, the trajectory pool, and CoSTEER's coding-error knowledge base. `fresh_start: true` is the default, so even that context is discarded between experiments. **Nothing gets better at research over time. Only the factor list grows.**
- **The paper-ingestion path is dead code.** `pipeline/factor_from_report.py` is RD-Agent's "PDF report → classify → extract factors and LaTeX formulas → implement → backtest" loop. It imports `quantaalpha.app.qlib_rd_loop.factor`, which doesn't exist in the repo, and it isn't exposed in the CLI (`cli.py` only has `mine`, `backtest`, `health_check`). The PDF extraction prompts in `factors/loader/prompts.yaml` are still usable as a reference.
- **There is only one backtest design.** Every hypothesis goes through the same LightGBM + top-k pipeline. The agent never chooses *how* to test something.
- **Data is daily price/volume only.** No fundamentals, analyst data or long history. The DSL cannot express value, profitability, investment, accruals or size-adjusted anything.

---

## 2. Side-by-side

| | **QuantaAlpha** | **Ours** |
|---|---|---|
| Core question | "What new signal predicts returns?" (discovery) | "Does this published claim hold up?" (verification) |
| Input per iteration | LLM-generated hypothesis | A factor-investing paper with a concrete claim |
| Ground truth | None beyond the backtest metric itself | The paper's reported results: sign, spread, t-stat, alpha vs. a factor model |
| What improves over time | The **factor library** (artifact) | The **agent** (skill) |
| Learning mechanism | In-context memory, reset per run; frozen LLM | "Train": needs to be pinned down (see §5) |
| Backtest method | Fixed: LightGBM → TopK-Dropout, daily, CSI 300 | Must vary by paper: decile/quintile sorts, value vs. equal weight, NYSE breakpoints, monthly rebalance, Fama-MacBeth, spanning regressions, FF3/FF5/q-factor alphas, Newey-West t-stats |
| Factor representation | Restricted DSL (safe, dedup-able, narrow) | Needs general code, since papers define signals in arbitrary ways |
| Data | Daily OHLCV, A-shares, 2016–2025 | Needs fundamentals, point-in-time accounting, delisting returns, long US history (CRSP/Compustat-like) |
| Main failure mode | Data mining / multiple testing on a fixed split | Agent "tunes until it matches the paper" (reward hacking toward replication) |
| Output | Ranked factor JSON | A verdict per paper (replicates / partial / fails) with an audit trail of the spec and code |

---

## 3. Where we're structurally stronger

1. **We have a label, so the agent can actually be trained.** Every QuantaAlpha step is graded by "did IC go up?". That signal is noisy, non-stationary and easy to overfit. A paper gives a fixed target: did you reproduce the reported spread, sign and significance within tolerance? That is a **verifiable reward**, which is what fine-tuning, RL or even disciplined prompt-evolution needs. QuantaAlpha has nothing like it, which is probably why they never train anything.
2. **The skill transfers, not just the output.** Their factors decay. An agent that has learned *how to run a correct factor test* (breakpoints, look-ahead control, microcap filters, rebalance timing) stays useful across markets and data sets.
3. **Methodology is the product.** In factor investing, results flip on implementation details. Hou, Xue & Zhang's *Replicating Anomalies* found most anomalies fail once microcaps are handled properly. QuantaAlpha hard-codes one method. Making method selection the learned skill targets the part that actually decides outcomes.
4. **Our output is credible to an investor.** A verdict like "Paper X: replicates in 1963–2010, dies post-publication, gone after FF5" is more defensible than a black-box expression with a good IC.

## 4. Where QuantaAlpha is ahead, and what to borrow

- **It works end to end today:** data on HuggingFace, a CLI, a UI and published numbers. We have an empty repo.
- **Steal: the consistency checker** (`factors/regulator/consistency_checker.py` + `consistency_prompts.yaml`). Hypothesis → description → formula → code fidelity is *exactly* our core problem, restated as paper claim → test spec → implementation. It's a cheap first guard against the agent quietly testing something other than what the paper says.
- **Steal: complexity and redundancy gates.** AST-based dedup against a factor zoo helps us recognize "this paper's factor is just momentum, re-labelled". Complexity limits help flag over-engineered replications.
- **Steal: the paper-extraction prompts** (`factors/loader/prompts.yaml`: classify, extract factors, extract LaTeX formulas plus variable definitions). They make a reasonable v0 paper parser even though their loop is broken.
- **Steal: the structured trace memory** of (hypothesis, code, observation, feedback, decision). It's a good schema for our per-paper episode logs, and later for training data.
- **Watch: [QuantaAlpha-claw](https://github.com/QuantaAlpha/QuantaAlpha-claw).** Per the README it adds Reviewer agents, persistent factor memory and stricter walk-forward validation. That moves them toward rigor, i.e. toward our position.

## 5. Risks and open questions for us

1. **What does "train" mean?** Options, cheapest first:
   - (a) A growing skills/playbook memory curated from past replications.
   - (b) Supervised fine-tuning on successful replication traces.
   - (c) RL with reward = match to the paper's reported results.

   The choice drives the whole architecture. QuantaAlpha only does a weak, per-run version of (a).
2. **Reward hacking.** If the reward is "match the paper", the agent learns to fiddle with specs until the numbers match. Mitigations:
   - Make it **commit to a test spec before seeing results**.
   - Include **papers known not to replicate**, so "doesn't replicate" is a correct, rewarded answer.
   - Grade on held-out papers.
3. **Ground-truth sets already exist.** Use them for curriculum and evaluation rather than labelling by hand:
   - Chen & Zimmermann's *Open Source Asset Pricing* (~200+ predictors with replication code and results).
   - Jensen, Kelly & Pedersen's global factor data (*Is There a Replication Crisis in Finance?*).
   - Hou, Xue & Zhang (2020).
4. **Data is the expensive part.** Most factor-investing papers need CRSP/Compustat-style point-in-time fundamentals. QuantaAlpha sidesteps this by staying on price/volume. We can't.
5. **Natural extension: verification → discovery.** Once the agent can validate, it can extend: other markets, post-publication decay, interactions. That is QuantaAlpha's mutation/crossover, but seeded from **validated** factors rather than LLM free association. Their whole system then becomes a possible downstream stage of ours, not a competitor.

---

### One-line summary

QuantaAlpha is a **search engine for new factors**. A frozen LLM generates expressions, and one fixed backtest scores them. Ours is a **training loop for an expert tester**. Published factor-investing papers provide graded exercises, and the backtesting skill itself is what gets better. Their missing pieces (ground truth, method choice, a model that actually learns) are the core of our approach. Their working parts (consistency check, complexity/redundancy gates, paper-extraction prompts, trace schema) are worth borrowing.
