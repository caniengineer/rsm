# Independent Audit: UK Multi-Bagger Factor Strategy

**Date:** 2026-02-07
**Evaluator role:** Independent evaluation AI acting as academic peer reviewer, quantitative risk committee member, and skeptical institutional investor.
**Scope:** All research documents in `/strategy/` directory.
**Evaluation standard:** Evidence, logic, and robustness only.

---

## Executive Verdict: CONDITIONAL FAIL

The research demonstrates unusual intellectual honesty in self-criticism, particularly in the `risks_and_failure_modes.md` and `assumptions_and_unknowns.md` documents, which identify most of the same weaknesses this audit finds. That transparency is the strongest feature of the work. However, the strategy as designed suffers from a fundamental identity crisis, critical dependence on a single unvalidated working paper, multiple internal contradictions, and the absence of any UK-specific empirical validation. The strategy should not be deployed with real capital in its current form.

The verdict would change to **conditional pass** if the conditions listed in Section 7 are met.

---

## 1. Major Strengths

**1.1 Adversarial self-assessment.** The research includes its own red team. The `risks_and_failure_modes.md` assigns probability estimates to six strategy-breaking risks, all rated above 55%. The `assumptions_and_unknowns.md` identifies ten explicit assumptions and rates the joint probability of all holding at approximately 0.09%. This level of honesty is rare and commendable. Most strategy research omits or minimises its own weaknesses.

**1.2 Transparent evidence labeling.** The classification system ([CORE EVIDENCE], [REASONABLE ASSUMPTION], [SPECULATIVE], etc.) allows readers to distinguish between empirically grounded claims and extrapolations. This is above the standard found in most practitioner strategy documents.

**1.3 Correct rejection of weak factors.** The `rejected_or_weak_factors.md` correctly identifies and discards ten commonly used but empirically unsupported factors (earnings growth, dividends, debt levels, share buybacks, analyst coverage, R&D intensity, ROE, raw size premium, Altman Z-score, and the broader factor zoo). The reasoning is well-supported by evidence, particularly the reliance on Yartseva (2025) and Harvey, Liu & Zhu (2016).

**1.4 Appropriate use of Harvey, Liu & Zhu threshold.** The research correctly applies the t > 3.0 multiple-testing adjustment framework. This is a meaningful improvement over strategies that rely on conventional significance thresholds.

**1.5 UK implementation realism.** The documents demonstrate genuine awareness of UK-specific frictions: stamp duty, AIM market structure, SETSqx trading system, de-equitisation trends, and bid-ask spread magnitudes. These are not afterthoughts; they are embedded into the strategy design.

---

## 2. Critical Weaknesses

### 2.1 Foundational dependence on a single, unpublished working paper

The strategy's distinctive claims -- that FCF yield is "the single strongest predictor" of multibagger returns (coefficient 46-82), that the Investment-EBITDA interaction identifies productive investment, that earnings growth is irrelevant, and that contrarian momentum (near 52-week lows) predicts extreme returns -- all derive from a single source: Yartseva (2025), CAFE Working Paper No. 33, Birmingham City University.

This paper is:
- **Not peer-reviewed** in a ranked finance journal. It is a university centre working paper.
- **US-only** (NYSE/NASDAQ, 2009-2024).
- **Survivorship-biased by design** -- it studies only the 464 stocks that achieved 10x returns, with no control group of stocks with similar starting characteristics that failed.
- **Testing 150+ variables on 464 observations** -- a variable-to-observation ratio that creates extreme overfitting risk, regardless of the GMM methodology employed.
- **Validated out-of-sample for only 2 years** (2023-2024), in a specific market regime (post-pandemic, AI boom). Two years cannot validate a model whose thesis depends on 5-15 year holding periods.

The research acknowledges these limitations individually but does not draw the obvious aggregate conclusion: this paper is not a sufficient evidence base for a strategy. No allocation committee would approve capital deployment based on a single unreplicated working paper with a 2-year out-of-sample window.

**Severity: Critical.** Remove Yartseva-specific factors (Investment-EBITDA interaction, contrarian momentum signal, specific FCF yield coefficient magnitudes) from the strategy until independent replication exists. The directional finding that multibaggers tend to be small, profitable, cash-generative, and reasonably valued is consistent with the broader literature and can stand without Yartseva-specific calibration.

### 2.2 Conflation of average factor returns with extreme-tail prediction

This is the most consequential intellectual error in the research. The strategy's stated objective is to identify multi-bagger stocks (5x-10x returns). The evidence base for the selected factors (gross profitability, value, momentum) is drawn from studies of **average cross-sectional returns** -- specifically, portfolio sort returns comparing top vs. bottom quintiles.

Predicting that the top-quintile profitability portfolio will outperform the bottom quintile by 3.6% per annum (Dimensional Fund Advisors 2015) is a categorically different statistical problem from predicting which specific stocks will deliver 5x-10x returns. The former describes a distributional shift in the mean; the latter requires predicting the far right tail of the return distribution.

The literature review states (line 70): "This is the ONLY paper that directly studies multi-bagger characteristics empirically. All other evidence is indirect (factor premiums for average returns, not extreme outcomes). The distinction matters: factors that predict mean outperformance may not predict right-tail outcomes."

This is correctly stated. But the strategy then proceeds to build a multi-bagger hunting methodology using predominantly average-return factors. The admission undermines the strategy's own premise without the research adjusting its confidence accordingly.

**Severity: Critical.** The strategy would be more honestly described as "a UK small-cap quality-value-momentum factor tilt that incidentally increases exposure to the population from which multibaggers are drawn." The multibagger framing creates expectations the factor evidence cannot support.

### 2.3 Internal contradiction: patient holding vs. annual rebalancing

The `assumptions_and_unknowns.md` document (A-10) identifies this contradiction explicitly:

> "The strategy cannot simultaneously rebalance annually based on factor signals and hold positions for 10-15 years to allow compounding. These are incompatible portfolio management approaches."

This is correct. The strategy design document specifies:
- Target holding period: 3-7 years per position (Section 6.1)
- Rebalancing: semi-annual full rebalance (Section 6.2)
- Annual turnover: 25-35% (Section 6.2)

At 30% annual turnover, the average holding period is approximately 3.3 years. This is a standard factor-rotation portfolio, not a patient multibagger compounding vehicle. The strategy will systematically sell winners that no longer score highly on the factor model (because they have appreciated beyond "cheap" valuations or their momentum has reversed), precisely when the multibagger thesis requires continued holding.

The sell discipline (Section 6.3) attempts to reconcile this by specifying "when NOT to sell" (price declines without fundamental deterioration). But the composite score criterion (sell trigger #5: stock falls to bottom 20% at rebalance) will override patient holding for any stock whose valuation multiples expand with price appreciation.

**Severity: Major.** The strategy must choose: either it is a systematic factor-rebalancing strategy (in which case the multibagger framing is misleading) or it is a buy-and-hold compounding strategy (in which case factor-based rebalancing must be abandoned after initial selection).

### 2.4 No UK-specific backtesting has been performed

The strategy design document is detailed and implementable. But nowhere in the eight documents is there a backtest, walk-forward analysis, or even a simple historical simulation using UK data. The closest approximation is the statement that Bermejo et al. achieved Sharpe 0.94 in European data -- but that was for large-caps, not small-caps, and not UK-specifically.

For a strategy targeting UK small-cap equities:
- The UK size premium **reversed** post-publication (Dimson & Marsh 1999)
- UK momentum was **absent** before 1977 (Hon & Tonks 2003)
- Most UK anomalies show **diminished significance** (Cotter & McGeever 2018)
- Factor alphas were **approaching zero post-2012** (Bermejo et al. 2021)

Without a UK-specific backtest incorporating survivorship-free data and realistic transaction costs, the strategy's expected performance characteristics (Section 8 of the design plan) are conjectural. The stated "3-6% annual gross alpha" estimate is an extrapolation from studies conducted in different markets, different time periods, different cap ranges, and different cost environments.

**Severity: Critical.** A UK-specific backtest using survivorship-free data (LSPD or equivalent) with realistic AIM transaction costs is a prerequisite for any capital deployment.

### 2.5 The Investment-EBITDA interaction factor is almost certainly overfit

The `assumptions_and_unknowns.md` correctly classifies this factor as "WEAKLY SUPPORTED / LIKELY OVERFIT" (A-5). The evidence:

- Single source: Yartseva (2025), US only
- No independent replication in any market
- The "100% of cases" claim is a red flag -- no factor works in 100% of cases in financial markets
- The Papanastasopoulos (2017) European evidence on asset growth anomalies **contradicts** the Yartseva interaction pattern (the anomaly is stronger in loss-making firms, not profitable ones)
- The interaction term is inherently susceptible to look-ahead bias in how "EBITDA-supported" growth is defined

Despite this honest self-assessment, the factor receives a 15% weight in the composite score (Section 4.2 of the design plan) and is used as a sell trigger (trigger #2 in Section 6.3). An acknowledged likely-overfit factor should not be weighted at 15% in a scoring model.

**Severity: Major.** Remove or downweight to nominal (≤5%) until replicated in UK/European data.

---

## 3. Unsupported or Overstated Claims

### Claim 1: "All factors in this strategy meet or exceed the t > 3.0 threshold through multiple independent replications"
**Source:** README.md, line 33
**Assessment:** False. The FCF yield coefficient from Yartseva reports regression coefficients (46-82), not t-statistics. The Investment-EBITDA interaction has been tested in one study. The contrarian momentum signal (near 52-week lows) has been tested in one study. These do not meet the Harvey, Liu & Zhu standard of t > 3.0 across multiple independent tests. Only gross profitability (GP/Assets), standard 12-1 momentum, and value (HML) meet this bar.

### Claim 2: FCF yield is "the single strongest predictor of multibagger returns"
**Source:** validated_factors.md, Section 1; README line 21
**Assessment:** Overstated. It is the largest coefficient in one regression specification of one unreplicated working paper. "Largest coefficient in a single study" is not the same as "strongest predictor." The coefficient ranges from 46 to 82 across specifications -- a nearly 2x variation that undermines claims of it being a stable, dominant predictor. Furthermore, coefficient magnitude in a GMM regression depends on variable scaling; without knowing the scale of the FCF yield variable relative to other regressors, the raw coefficient is not interpretable as relative predictive power.

### Claim 3: "The strategy targets UK-listed equities... using an iterative screening approach inspired by Bermejo et al. (2021)"
**Source:** README, line 37; strategy_design_plan.md
**Assessment:** Misleading extrapolation. Bermejo et al. tested their iterative approach on the **600 largest European companies by market cap**. The proposed strategy targets companies with GBP 30m-1,000m market cap -- stocks roughly 10-100x smaller than Bermejo's universe. There is no evidence that the iterative methodology transfers to small caps, where factor behaviour, liquidity, data quality, and transaction costs are fundamentally different.

### Claim 4: "From a portfolio of 25 stocks held for 5-7 years, 2-4 positions (8-16%) might deliver 3x+ returns"
**Source:** strategy_design_plan.md, Section 8.2
**Assessment:** Speculative and ungrounded. This assumes a "factor-enriched hit rate" of 2-3x the Bessembinder base rate (4%). There is no empirical estimate of this enrichment factor for UK small caps. The research itself labels this as a "reasonable assumption" but provides no citation or calculation to support the 2-3x multiplier. Given that the base rate evidence is from US data and the factor evidence is predominantly not from UK small caps, this estimate could easily be off by an order of magnitude.

### Claim 5: "A personal investor can implement this strategy"
**Source:** strategy_design_plan.md, Section 10.2
**Assessment:** Highly questionable. The strategy requires: (a) a professional data subscription (~GBP 500-900/year), (b) the ability to calculate composite multi-factor scores across 250-400 stocks semi-annually, (c) the discipline to execute limit orders on illiquid AIM stocks over multi-day periods, (d) the psychological fortitude to hold through 30-50% drawdowns for years, and (e) at least GBP 500,000 in capital to achieve meaningful position sizes (GBP ~20,000 per position across 25 holdings) while staying within AIM daily volume constraints. This describes a sophisticated, wealthy, self-directed investor -- a small minority of any investor population.

---

## 4. Factor Validity Assessment

| Factor | Multiple independent sources? | Relates to multi-bagger outcomes specifically? | Robust in UK/similar markets? | Classification |
|--------|------|------|------|------|
| **Gross Profitability (GP/Assets)** | Yes (Novy-Marx 2013, Bermejo 2021, Cotter & McGeever 2018, Hanauer & Huber 2016) | No -- predicts average cross-sectional returns, not extreme right tail | Yes -- robust in UK even as other anomalies decay | **Strongly supported** (as average-return factor) |
| **Value (HML, EV/EBITDA)** | Yes (Fama-French, Harvey et al. 2016, Bermejo 2021, DMS long-run UK) | Partially -- Yartseva shows high B/M multibaggers outperform low B/M multibaggers, but this is within-winners, not predictive of becoming a winner | Yes -- long-run UK evidence strong, though recent weakness | **Strongly supported** (as average-return factor) |
| **Momentum (12-1)** | Yes (Liu et al. 1999, Asness et al. 2013, Bermejo 2021) | No -- Yartseva's multibagger signal is CONTRARIAN (near lows), the opposite of standard momentum | Mixed -- confirmed in UK post-1977 but absent pre-1977, declining significance | **Strongly supported** (for average returns); **contradicted** for multibagger-specific use |
| **FCF Yield** | No -- only Yartseva (2025) for multibagger prediction specifically. Related evidence from Fama & French (2018) on cash-based profitability supports it directionally | Yes -- directly tested on multibagger sample | No UK evidence whatsoever | **Weakly supported** |
| **Small Cap Size** | Yes -- as a descriptive characteristic (Yartseva, Mayer, Stockopedia) | As a precondition (tautological), not as a return predictor | No -- UK size premium reversed (Dimson & Marsh 1999) | **Supported as universe filter; unsupported as return factor** |
| **Investment-EBITDA Interaction** | No -- Yartseva (2025) only, with no replication | Yes -- directly tested on multibagger sample | No evidence in UK or Europe | **Unsupported / speculative** |
| **Contrarian momentum (near 52-week lows)** | No -- Yartseva (2025) only | Yes -- directly tested on multibagger sample | No evidence in UK or Europe | **Unsupported / speculative** |

**Summary:** Of the seven factors/signals used in the strategy, two are strongly supported for average returns (GP/Assets, Value), one is strongly supported for average returns but contradicted for multibagger use (momentum), one is weakly supported (FCF yield), one is supported only as a universe filter (size), and two are unsupported (Investment-EBITDA interaction, contrarian momentum). None of the factors have been validated for multi-bagger prediction in the UK.

---

## 5. Key Assumptions That Must Hold

For this strategy to deliver returns superior to a simple UK small-cap index fund, **all** of the following must be true simultaneously:

1. **Factor premiums persist in UK small caps net of costs.** The gross profitability premium (3.6% Europe, Dimensional 2015) must survive stamp duty, AIM spreads, and the post-publication decay documented by Cotter & McGeever (2018) and McLean & Pontiff (2016).

2. **US multibagger factor characteristics transfer to UK equities.** The Yartseva findings (US, NYSE/NASDAQ, 2009-2024) must be directionally applicable in a market with different sector composition, different regulatory structure, and different institutional investor base.

3. **Factor screens meaningfully enrich the probability of holding future multibaggers.** The assumed 2-3x enrichment of the Bessembinder base rate (from ~4% to ~10-15%) must actually materialise. There is no empirical estimate of this quantity.

4. **The investable UK small-cap universe remains large enough.** With AIM at 679 companies and shrinking, the post-filter universe of 250-400 stocks must not decline below the ~50-100 needed for the iterative screening to produce a meaningful portfolio.

5. **The investor executes mechanically for at least 5-7 years.** The behavioral risk documentation (Section 10.4 of design plan) correctly identifies this as "likely the single largest risk." A 30-50% drawdown in year 2 with no visible multibagger candidates will test any investor's commitment.

6. **Interest rates and macro regime do not shift to a structurally hostile environment.** The strategy's evidence base is calibrated to 2009-2024 conditions. A 1970s-style stagflation or a prolonged bear market is outside the model's training data.

---

## 6. Top 5 Failure Scenarios

### Scenario 1: Factor premium exhaustion in UK small caps
**Mechanism:** Post-publication factor decay continues its documented trajectory (Cotter & McGeever 2018; Bermejo et al. 2021 post-2012 decay). Gross profitability, the most robust factor, delivers 1.5% annual premium instead of 3.6%. After AIM transaction costs of 1-2%, net alpha is 0% or negative. The strategy underperforms a FTSE Small Cap index tracker by 50-100 bps annually (the fee and complexity premium the strategy imposes).
**Probability:** Moderate-high (40-60%).
**Timeline:** Evident within 3-5 years.

### Scenario 2: Prolonged UK small-cap bear market + investor abandonment
**Mechanism:** UK de-equitisation accelerates. Fund outflows from UK smaller companies (already GBP 4 billion in two years) continue. AIM shrinks below 500 companies. The strategy's small-cap bias creates persistent underperformance versus large-cap benchmarks (FTSE 100) for 5+ years. The investor, experiencing a cumulative 40-60% underperformance versus their peer group / spouse's FTSE 100 tracker, abandons the strategy at the point of maximum pessimism -- which is historically the point of maximum forward opportunity.
**Probability:** High (50-70%).
**Timeline:** Could begin immediately; abandonment most likely at year 3-5 mark.

### Scenario 3: AIM structural collapse
**Mechanism:** The UK government removes AIM's inheritance tax relief (Business Property Relief) in a future budget. This triggers a wave of forced selling from IHT-driven portfolios, depressing AIM prices. Several NOMAD sponsors exit the market due to reduced profitability. AIM delistings accelerate to 100+ per year. The investable universe shrinks below the 30-stock minimum, rendering the strategy inoperable.
**Probability:** Moderate (25-40%) for partial impact; lower (10-20%) for full collapse.
**Timeline:** Policy risk is unpredictable; could occur at any budget.

### Scenario 4: Momentum crash during concentrated small-cap exposure
**Mechanism:** A bear market (FTSE All-Share down 30%+) is followed by a sharp snapback. Past losers surge due to their high option-like betas (Daniel & Moskowitz 2016). The strategy's momentum-tilted small-cap portfolio, concentrated in 20-30 positions, experiences a 40-60% drawdown relative to the market during the recovery. The dynamic momentum scaling (Section 7.3) fires too late because it relies on trailing 24-month signals, which by definition lag the crash mechanism. Concentrated positions in illiquid AIM stocks cannot be sold at reasonable prices during the volatility.
**Probability:** Near-certain over a 15-year period. The question is timing and magnitude.
**Timeline:** Episodic; 2-4 events expected over a 15-year horizon.

### Scenario 5: The strategy is a standard factor tilt that adds no multibagger edge
**Mechanism:** The strategy is implemented faithfully. After 10 years, it has delivered returns approximately in line with a UK small-cap quality-value fund (which can be bought as an ETF for 30-50 bps annually). Zero holdings have delivered 5x+ returns. Several have been acquired at 50-100% premiums (counted as "good" returns but not multibaggers). The strategy's cost (data subscriptions, time, complexity, stamp duty, AIM spreads) exceeds the incremental return over a passive alternative. The "multibagger" framing was marketing, not substance.
**Probability:** High (50-65%).
**Timeline:** Assessment possible at year 7-10.

---

## 7. What Evidence Would Change the Verdict

The verdict would improve to **conditional pass** if the following are produced:

1. **A survivorship-free UK backtest** using LSPD (London Share Price Database) or equivalent dead-stock-inclusive data, covering at least 20 years (to span multiple regimes), with realistic AIM and Main Market transaction costs (stamp duty, measured bid-ask spreads, market impact estimates). The strategy must show **statistically significant** (t > 2.0) net-of-cost alpha over the FTSE Small Cap Index.

2. **Independent replication of the Investment-EBITDA interaction** in UK or European small-cap data. If this factor cannot be validated outside Yartseva's US sample, it should be removed.

3. **A false-positive rate estimate.** Apply the factor screen to the full historical UK small-cap universe (including delistings) at each point in time. Calculate what fraction of stocks passing the screen subsequently delivered 3x+ returns over 5 years. If the precision is below 10%, the screen is functionally random for multibagger identification and should be re-described as a factor tilt.

4. **Resolution of the holding period contradiction.** The strategy must clearly decide whether it is a factor-rebalanced portfolio (accept ~3-year average holding period, drop the multibagger narrative) or a buy-and-hold compounding vehicle (select once based on factors, then hold for 7-15 years without factor-based selling).

5. **Stress testing against UK crisis periods** (1992 ERM exit, 2000-03 tech bust, 2007-09 GFC, 2016 Brexit, 2020 COVID, 2022 gilt crisis) using UK factor data from Gregory, Tharyan & Christidis. The strategy should demonstrate it does not suffer correlated multi-factor failure during these events.

---

## 8. Detailed Assessment by Evaluation Category

### 8.1 Literature Integrity Check

**Were the cited papers correctly interpreted?**

Mostly yes, with important exceptions:

- **Harvey, Liu & Zhu (2016):** Correctly interpreted regarding the t > 3.0 threshold. However, the research then claims its own factors meet this threshold when several (FCF yield from Yartseva, Investment-EBITDA interaction) have not been tested against it.
- **Bermejo et al. (2021):** Correctly interpreted regarding iterative strategies and Sharpe ratios. However, the extrapolation from the 600 largest European companies to UK small caps is a material leap that is not adequately flagged as an assumption. Bermejo's sample is predominantly mega-cap and large-cap stocks; the smallest stock in their universe would likely be in the top 5% by market cap of the proposed strategy's universe.
- **Yartseva (2025):** Findings are reported accurately, but the research treats working paper findings as equivalent in credibility to peer-reviewed, replicated results. The coefficient instability (46-82 for FCF yield) is noted but not given sufficient weight in determining how much to rely on this single source.
- **Stockopedia evidence:** Practitioner/commercial research (not peer-reviewed) is cited alongside academic papers without sufficient demarcation. Stockopedia's "top 10 UK winners" is an anecdotal sample that does not meet any reasonable evidence threshold for strategy design.

**Were key limitations explicitly acknowledged?**

Yes -- this is a genuine strength. The research documents limitations for each paper. However, there is a pattern of acknowledging limitations in the literature review and risk documents, then proceeding to build the strategy as though those limitations do not materially affect confidence. The limitations are "noted and filed" rather than "noted and incorporated into reduced conviction."

**Were claims made beyond what the papers support?**

Yes:
- The claim that factor screens can "meaningfully" improve multibagger hit rates beyond the Bessembinder base rate is unsupported by any cited paper.
- The 2-3x enrichment factor assumed for the hit rate calculation is invented, not derived from evidence.
- The "3-6% annual gross alpha" estimate is an arithmetic combination of premiums from different studies, different markets, and different time periods. Combining premiums this way implicitly assumes independence and additivity, neither of which is established.

### 8.2 Strategy Logic Review

**Where does this strategy actually make its money?**

If the strategy generates positive alpha, it will come from:
1. **The gross profitability premium** (~3.6% gross in Europe, ~1.5-2.5% net of decay and costs). This is the most robust component.
2. **The value premium** in UK small caps (~2-4% gross historically, but weakened recently).
3. **Avoidance of the worst stocks** -- the profitability and FCF gates eliminate cash-burning, unprofitable companies that account for disproportionate losses in small-cap portfolios.

The strategy will **not** generate its money from multibagger identification. The factor screens create exposure to the population from which multibaggers emerge, but do not reliably identify specific future multibaggers. Any multibagger returns that materialise will be a function of diversification (holding 25 small-cap stocks for several years gives non-trivial probability of one becoming a multibagger) rather than factor-based selection skill.

**What must go right for it to work?**

At minimum: (a) gross profitability premium must remain positive in UK small caps, (b) transaction costs must remain below 2% annually, (c) the UK small-cap universe must remain large enough to screen (~200+ eligible stocks), and (d) the investor must execute for at least one full market cycle (7-10 years).

### 8.3 Bias and Fragility Analysis

| Bias Type | Severity | Assessment |
|-----------|----------|------------|
| **Survivorship bias** | Critical | Yartseva's methodology is inherently survivorship-biased. AIM's 60% company attrition since 2007 means any UK backtest without dead-stock data will be materially overstated. |
| **Look-ahead bias** | Major | Factor selection, combination logic, and weightings are all chosen with knowledge of what worked historically. The specific thresholds (GPA above 40th percentile, EV/EBITDA below 70th percentile) have no prior academic justification and are implicitly fitted to historical intuition. |
| **Data-snooping / factor mining** | Major | Yartseva tested 150+ variables. Even with GMM methodology, the probability of finding spurious significant relationships is high. The Harvey, Liu & Zhu framework was designed precisely to address this concern, yet the strategy selectively applies the framework (to reject factors it dislikes) while ignoring it (for Yartseva-specific factors it likes). |
| **Liquidity and capacity** | Major | The strategy may be unimplementable at any meaningful scale. A GBP 10m allocation across 30 AIM positions creates multi-day execution requirements per position, with significant market impact. |
| **Transaction costs** | Moderate-to-major | Estimated 1.5-3.0% annual drag. If gross alpha is 3-5%, costs consume 30-100% of the premium. The research's own estimate of 0.5-1.5% annual cost (Section 6.2) appears optimistic for AIM stocks. |

### 8.4 Implementation Reality Check

| Dimension | Assessment |
|-----------|------------|
| **Data availability** | Adequate for top 200-300 AIM/Main Market small caps via Stockopedia or SharePad. Degrades significantly for stocks below GBP 50m market cap. COGS data (needed for GP/Assets) may be inconsistently reported for AIM companies. FCF is not standardised and varies across data providers. |
| **Signal stability** | Profitability and value signals are reasonably stable (semi-annual measurement appropriate). Momentum signals have 3-12 month half-life, creating tension with semi-annual rebalancing. The Investment-EBITDA interaction requires year-over-year changes, which are inherently noisy for small caps with lumpy capital expenditure. |
| **Rebalancing feasibility** | Semi-annual rebalancing is feasible for a personal portfolio (GBP 500k-1m). Execution in AIM stocks requires multi-day limit order management. Institutional execution (GBP 10m+) would face severe market impact constraints. |
| **Tax drag** | CGT on rebalancing gains reduces net returns. ISA/SIPP wrappers mitigate this for UK investors but impose annual contribution limits (currently GBP 20,000 ISA). Stamp duty at 0.5% on Main Market round-trips is a permanent friction. |
| **Investor adherence** | The research correctly identifies behavioral abandonment as the single largest risk. A strategy that underperforms FTSE 100 for 3-5 consecutive years (entirely plausible for UK small-cap value) will be abandoned by most investors, including most who believe ex ante that they will not abandon it. |

---

## 9. Mandatory Final Question

**"If this strategy underperforms for 10 years, would that be surprising based on the evidence?"**

**No. 10 years of underperformance would not be surprising.**

The reasons are structural and well-documented within the research's own evidence base:

1. **Factor premiums are shrinking.** Bermejo et al. found European factor alphas approaching zero post-2012. Cotter & McGeever documented declining significance in the UK. McLean & Pontiff established a 58% post-publication decay rate. A composite multi-factor premium of 1-2% net (optimistic) creates a signal-to-noise ratio where 10 years of data is insufficient to distinguish genuine alpha from randomness. At 1.5% net alpha with 15% tracking error, the t-statistic after 10 years would be approximately 1.0 -- statistically indistinguishable from zero.

2. **UK small caps face structural headwinds.** De-equitisation, persistent fund outflows, and declining IPO activity create a hostile environment for small-cap investing regardless of factor tilts. The strategy is swimming against a structural tide that has been worsening for a decade.

3. **The size premium reversed in the UK.** Small caps as a class have a documented negative premium post-publication in the UK (Dimson & Marsh 1999). While the strategy attempts to use size as a universe filter rather than a return factor, the portfolio's inherent small-cap bias still exposes it to this negative structural force.

4. **Momentum is unstable in the UK.** It was absent before 1977, crashed during market recoveries, and its significance has been declining. A strategy weighting momentum at 15% is exposed to extended periods where this factor contributes nothing or actively detracts.

5. **The Yartseva-specific factors have no out-of-sample evidence in the UK.** If these factors are spurious (as the 150-variable, 464-stock design suggests is likely for at least some of them), they contribute noise rather than signal, and the strategy degenerates to a conventional profitability-value tilt in an increasingly crowded space.

6. **Transaction costs are a persistent headwind.** In a low-alpha environment, the compounding drag of stamp duty, AIM spreads, and rebalancing costs is meaningful. Ten years of 1-2% annual cost drag compounds to 10-20% of terminal wealth -- enough to turn modest alpha into net underperformance.

A strategy grounded in robust, high-conviction evidence with proven UK applicability might generate 10-year underperformance as a 1-in-10 or 1-in-20 event. This strategy, with its reliance on unvalidated working papers, untested UK transferability, and acknowledged post-publication factor decay, generates 10-year underperformance as a plausible base-case outcome -- perhaps 30-50% probability.

---

## Appendix: Evidence Quality Matrix

| Evidence Source | Publication Tier | Market | Cap Range | Peer Reviewed? | Replicated? | Relevance to UK Small-Cap Multibaggers |
|---|---|---|---|---|---|---|
| Yartseva (2025) | Working paper | US | All | No | No | Direct (multibaggers) but unvalidated |
| Harvey, Liu & Zhu (2016) | Top journal (RFS) | Global | All | Yes | N/A (methodological) | Framework only |
| Bermejo et al. (2021) | Mid-tier journal (Heliyon) | Europe | Large cap (top 600) | Yes | No | Indirect (average returns, wrong cap range) |
| Novy-Marx (2013) | Top journal (JFE) | US + 19 international | All | Yes | Yes (multiple) | Moderate (average returns, not UK-specific) |
| Cotter & McGeever (2018) | Working paper | UK | All | No | No | High (UK-specific factor persistence) |
| Dimson & Marsh (1999) | Strong journal (JPM) | UK | Small vs large | Yes | Yes (DMS database) | High (UK size premium reversal) |
| Liu, Strong & Xu (1999) | Strong journal (JBFA) | UK | All | Yes | Yes (Hon & Tonks 2003) | Moderate (UK momentum, pre-1996 only) |
| Daniel & Moskowitz (2016) | Top journal (JFE) | US + international | All | Yes | Yes | Moderate (momentum crash risk) |
| Bessembinder (2018) | Top journal (JFE) | US | All | Yes | Yes (global extension) | High (base rate framing) |
| Stockopedia | Commercial/practitioner | UK | Small-mid | No | No | Low (anecdotal, not systematic) |
| Mayer (2018) | Practitioner book | US | All | No | No | Low (anecdotal, US-focused) |

---

*End of audit.*
