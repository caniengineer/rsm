# UK Small-Cap Quality-Value-Momentum Factor Strategy

**An Evidence-Based Factor-Tilt Approach to UK Small-Cap Equities**

---

## Executive Summary

This research project designs a systematic factor investing strategy for UK small-cap equities, grounded in replicated academic evidence from multiple independent sources. The strategy tilts toward the factor characteristics that wealth-creating stocks disproportionately exhibit — high profitability, reasonable valuation, positive momentum, and disciplined capital allocation — while maintaining sufficient diversification to capture the rare extreme winners that drive aggregate market returns.

### The Core Problem

Most stocks destroy value. Bessembinder (2018, 2023) demonstrates that 57.4% of all US stocks underperform Treasury bills over their lifetimes, and only 2-4% of listed companies account for virtually all net stock market wealth creation. Internationally, the picture is worse — only 42.4% of stocks outperform bills across 57 countries (Fang et al. 2021). This means the base rate for successful stock picking is terrible, and any systematic approach must focus on avoiding the wealth-destroying majority while maintaining broad exposure to the wealth-creating minority.

### What the Evidence Says

After deep analysis of Harvey, Liu & Zhu (2016), Bermejo et al. (2021), Novy-Marx (2013), and extensive UK/European factor studies, the following evidence-led conclusions emerge:

**Factors with strong, replicated evidence (multiple independent studies, t > 3.0):**
1. **Gross Profitability (GP/Assets)** — Most robust quality metric internationally (Novy-Marx 2013, tested in 19 countries; Bermejo 2021 FF3 alpha 4.23%, t=10.88; Foye 2018 confirms UK respecification; Cotter & McGeever 2018 finds it remains robust when other UK anomalies decay).
2. **Free Cash Flow Yield** — Combines profitability and valuation in a single, manipulation-resistant metric (supported by Fama & French 2018 finding cash-based profitability dominates accrual measures; Yartseva 2025 identifies it as a strong predictor, though UK-specific calibration is unvalidated).
3. **Value (EV/EBITDA)** — Survives Harvey et al.'s 0.1% significance threshold. Strongest European value metric (Bermejo 2021). Long-run UK value premium of 3-5% p.a. (Dimson, Marsh & Staunton).
4. **Momentum (12-1 Month)** — Strongest pure factor in European data (Sharpe 0.80, Bermejo 2021). Confirmed in UK equities (Liu et al. 1999, Asness et al. 2013). Survives Harvey et al.'s 0.1% threshold.
5. **Small Capitalisation** — Used as a universe definition, not a return factor. The raw UK size premium reversed post-publication (Dimson & Marsh 1999), but small caps remain the universe where mispricing is largest and extreme outcomes most likely.

**Factors correctly rejected (commonly believed but statistically insignificant):**
- Earnings growth, dividend policy, debt levels, share buybacks, analyst coverage, R&D intensity, ROE, Altman Z-scores, Investment-EBITDA interaction (all: see rejected_or_weak_factors.md)

**Statistical rigour (Harvey, Liu & Zhu 2016):**
- Only 9 of 313 published factors survive t > 3.0 after multiple testing adjustment
- 53% of published factors are likely false discoveries
- Every factor in this strategy has multiple independent replications across geographies

### The Strategy

The strategy uses a two-sleeve portfolio architecture to resolve the tension between systematic factor harvesting and patient compounding:

1. **Factor Sleeve (60-70% of portfolio):** 15-20 positions, rebalanced semi-annually. Harvests quality-value-momentum factor premiums via systematic screening of UK-listed equities (Main Market + AIM) with market caps of GBP 50m-1,000m.
2. **Compounding Sleeve (30-40% of portfolio):** 5-10 positions graduated from the Factor Sleeve when they demonstrate sustained fundamental strength. Held indefinitely, sold only on hard fundamental triggers.

**Factor weights (scoring model):**

| Factor | Weight | Evidence Base |
|--------|--------|---------------|
| Gross Profitability (GP/Assets) | 30% | Novy-Marx 2013, Bermejo 2021, Foye 2018, Cotter & McGeever 2018 |
| FCF Yield | 20% | Fama & French 2018, Yartseva 2025 (reduced weight due to unvalidated UK calibration) |
| EV/EBITDA (Value) | 20% | Harvey et al. 2016, Bermejo 2021, DMS long-run UK data |
| Momentum (12-1 month) | 20% | Bermejo 2021, Asness et al. 2013, Liu et al. 1999 |
| Size (universe filter) | 10% | Descriptive only; not a standalone return factor in UK |

### Realistic Performance Expectations

| Scenario | Probability | Expected Net Alpha (vs FTSE Small Cap) |
|----------|------------|----------------------------------------|
| **Bull case** | 20-30% | +2% to +4% annually |
| **Base case** | 40-50% | 0% to +1% annually |
| **Bear case** | 30-40% | -1% to -3% annually |

**Expected value: approximately +0.3% net alpha.** This is an honest assessment: the strategy's expected value is marginally positive but within the margin of estimation error. The case for it rests on the persistence of the profitability premium, avoiding catastrophic stocks via quality gates, and the optionality of the Compounding Sleeve.

Factor premiums decline approximately 58% post-publication (McLean & Pontiff 2016). Any historical premium estimate must be discounted accordingly.

### Critical Risks and Honest Limitations

1. **Post-publication factor decay** — Factor alphas approaching zero post-2012 in Europe (Bermejo 2021); 58% lower post-publication (McLean & Pontiff 2016)
2. **No UK-specific backtesting exists** — Zero historical simulations using UK data, survivorship-free databases, or realistic AIM transaction costs
3. **Survivorship bias** — Source studies examined successful stocks retrospectively; the false-positive rate is unknown
4. **Base rate problem** — Even with factor screens, only 2-4% of stocks create meaningful wealth (Bessembinder 2018)
5. **Liquidity constraints** — AIM spreads of 5-10x FTSE 100; stamp duty 0.5% on Main Market; estimated 1.5-3% annual cost drag
6. **UK de-equitisation** — 20% fewer listed companies in 5 years; persistent fund outflows

### Pre-Deployment Requirements

The strategy should NOT receive real capital until:
1. Historical screen confirms a viable filtered universe of 40+ stocks
2. Dead-stock audit shows false-positive rate below 50%
3. Paper portfolio demonstrates executable trades within the 3% spread cap
4. The investor has committed (in writing) to the kill switch criteria
5. Minimum capital of GBP 100,000 is available

### The Kill Switch

Binding commitment to halt and review if ANY of these occur:
1. Underperforms FTSE Small Cap Index by >3% annually for 3 consecutive years (net of all costs)
2. Gross profitability premium turns negative over any rolling 5-year window in UK data
3. All-in transaction costs exceed gross factor returns for 2 consecutive years
4. Investable universe (post-filter) drops below 40 stocks
5. AIM loses Business Property Relief, triggering structural decline

---

## Document Index

| File | Purpose |
|------|---------|
| [literature_review.md](literature_review.md) | Paper-by-paper synthesis with evidence mapping |
| [uk_european_factor_literature_review.md](uk_european_factor_literature_review.md) | Deep-dive UK/European empirical factor evidence |
| [validated_factors.md](validated_factors.md) | Factors accepted into the strategy with measurement formulas |
| [rejected_or_weak_factors.md](rejected_or_weak_factors.md) | Factors rejected or classified as weak with reasoning |
| [strategy_design_plan.md](strategy_design_plan.md) | Complete strategy design with implementation details |
| [risks_and_failure_modes.md](risks_and_failure_modes.md) | Adversarial risk analysis and failure mode catalogue |
| [assumptions_and_unknowns.md](assumptions_and_unknowns.md) | Explicit assumptions, evidence gaps, and unknowns |

---

## Evidence Classification System

Throughout all documents, evidence is classified as:

| Label | Meaning |
|-------|---------|
| **[CORE EVIDENCE]** | From papers with multiple independent replications and t > 3.0 |
| **[DIRECT EVIDENCE]** | From specific academic papers with citations |
| **[SUPPORTING EVIDENCE]** | From closely related research |
| **[RELATED EVIDENCE]** | From adjacent academic work |
| **[INFERENCE]** | Reasonable logical extension of evidence |
| **[SPECULATIVE]** | Beyond what evidence directly supports |
| **[DATA SUPPORTS]** | Directly supported by empirical data |
| **[REASONABLE ASSUMPTION]** | Logical extension of validated findings |

---

## Key Source Papers

1. **Harvey, Liu & Zhu (2016)** — "...and the Cross-Section of Expected Returns." Review of Financial Studies, 29(1): 5-68. *316 factors, multiple testing framework, t > 3.0 threshold.*

2. **Bermejo et al. (2021)** — "Factor investing: A stock selection methodology for the European equity market." Heliyon, 7(10): e08168. *600 European large-caps, iterative multi-factor strategies, Sharpe 0.94.*

3. **Novy-Marx (2013)** — "The Other Side of Value: The Gross Profitability Premium." Journal of Financial Economics, 108(1): 1-28. *Gross profitability tested in 19 developed international markets.*

4. **McLean & Pontiff (2016)** — "Does Academic Research Destroy Stock Return Predictability?" Journal of Finance, 71(1): 5-32. *Factor returns decline 26% out-of-sample, 58% post-publication.*

5. **UK/European Empirical Factor Studies** — Including Dimson, Marsh & Staunton (DMS database), Gregory, Tharyan & Christidis (2013), Asness, Moskowitz & Pedersen (2013), Daniel & Moskowitz (2016), Bessembinder (2018, 2023), Cotter & McGeever (2018), Foye (2018), and 20+ additional papers.

6. **Yartseva (2025)** — "The Alchemy of Multibagger Stocks." CAFE Working Paper No. 33, Birmingham City University. *464 multibagger stocks, 150+ variables. Used as supporting evidence only; not peer-reviewed, US-only, unreplicated.*

---

## Key Insight Summary

| # | Insight | Source | Confidence |
|---|---------|--------|------------|
| 1 | Gross Profitability (GP/Assets) is the most robust quality metric internationally | Novy-Marx 2013, Bermejo 2021, Foye 2018 | High |
| 2 | Only 9 of 313 factors survive rigorous multiple-testing adjustment (t > 3.0) | Harvey et al. 2016 | High |
| 3 | Factor returns decline 58% post-publication | McLean & Pontiff 2016 | High |
| 4 | Iterative multi-factor combinations (value->quality->momentum) achieve Sharpe 0.94 | Bermejo et al. 2021 | High (in-sample) |
| 5 | 57.4% of stocks underperform Treasury bills over their lifetimes | Bessembinder 2018 | High |
| 6 | UK size premium reversed post-publication (+6% to -6%) | Dimson & Marsh 1999 | High |
| 7 | Earnings growth does NOT predict extreme returns | Yartseva 2025 | High (counterintuitive) |
| 8 | UK AIM market has structural liquidity constraints (5-10x wider spreads) | Multiple sources | High |
| 9 | Base-case net alpha is approximately 0-1%, not 3-6% | Composite assessment | Moderate |
| 10 | No UK-specific backtesting of this strategy exists | N/A | Certain |
