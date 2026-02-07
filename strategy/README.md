# UK Multi-Bagger Factor Investing Strategy

**An Evidence-Based Approach to Identifying Exceptional UK Equities**

---

## Executive Summary

This research project designs an institutional-grade factor investing strategy aimed at identifying multi-bagger stocks (5x+ returns) in UK equities, grounded entirely in academic evidence from four mandatory source papers and extensive supporting literature.

### The Core Problem

Most stocks destroy value. Bessembinder (2018, 2023) demonstrates that 57.4% of all US stocks underperform Treasury bills over their lifetimes, and only 2-4% of listed companies account for virtually all net stock market wealth creation. Internationally, the picture is worse — only 42.4% of stocks outperform bills across 57 countries. This means the base rate for successful stock picking is terrible, and the base rate for identifying a multi-bagger (5-10x return) is vanishingly small.

### What the Evidence Says

After deep analysis of Yartseva (2025), Harvey, Liu & Zhu (2016), Bermejo et al. (2021), and extensive UK/European factor studies, the following evidence-led conclusions emerge:

**Factors that predict multi-bagger outcomes (strong evidence):**
1. **Free Cash Flow Yield** — The single strongest predictor (Yartseva 2025, coefficient 46-82). Combines profitability and valuation in one metric.
2. **Gross Profitability (GP/Assets)** — Most robust quality metric internationally (Novy-Marx 2013, Bermejo 2021 FF3 alpha 4.23%, t=10.88). Remains robust in UK when other anomalies decay.
3. **Small Capitalisation** — Multi-baggers overwhelmingly start small (median $348m US; GBP 50-350m UK).
4. **Moderate Valuation** — High book-to-market stocks in the multibagger universe returned +34.7% excess vs +12.8% for low-value (Yartseva). EV/EBITDA is the strongest European value metric (Bermejo).
5. **Investment-EBITDA Growth Interaction** — Aggressive asset expansion is positive ONLY when supported by corresponding EBITDA growth; otherwise returns drop 5-23% (Yartseva).
6. **Momentum** — Strongest pure factor in Europe (Sharpe 0.80, Bermejo). Confirmed in UK (Liu et al. 1999). Multi-factor combinations achieve Sharpe 0.94.

**Factors that do NOT predict multi-baggers (commonly believed but statistically insignificant):**
- Earnings growth, dividend policy, debt levels, share buybacks, analyst coverage, R&D intensity, Altman Z-scores (all: Yartseva 2025)

**Statistical rigour (Harvey, Liu & Zhu 2016):**
- Only 9 of 313 published factors survive t > 3.0 after multiple testing adjustment
- 53% of published factors are likely false discoveries
- All factors in this strategy meet or exceed the t > 3.0 threshold through multiple independent replications

### The Strategy

The strategy targets UK-listed equities (Main Market + AIM) with market caps of GBP 30m-1,000m, using an iterative screening approach inspired by Bermejo et al. (2021):

1. **Universe**: ~250-400 eligible UK stocks after liquidity and sector filters
2. **Step 1 — Profitability Gate**: Require above-median Gross Profitability (GP/Assets)
3. **Step 2 — Valuation Filter**: Require above-median Free Cash Flow Yield AND reasonable EV/EBITDA
4. **Step 3 — Investment Discipline**: Require asset growth ≤ EBITDA growth (Yartseva's key interaction)
5. **Step 4 — Momentum Confirmation**: Require positive 12-month price momentum (skip last month)
6. **Result**: A concentrated portfolio of 20-40 stocks, rebalanced annually

**Target return profile**: Not a specific return promise — that would be speculative. Instead: systematic exposure to the factor characteristics that the wealth-creating minority of stocks disproportionately exhibits, with sufficient diversification to have a meaningful probability of owning the rare winners.

### Critical Risks and Honest Limitations

This strategy has significant risks that are documented in detail:

1. **Survivorship bias** — Yartseva studied only successful 10x stocks; the false-positive rate is unknown
2. **Base rate problem** — Even with perfect screens, only 2-4% of stocks create meaningful wealth
3. **US-to-UK translation** — All Yartseva findings are US-only; UK market structure differs materially
4. **Factor decay** — Alphas approaching zero post-2012 (Bermejo); 58% lower post-publication (McLean & Pontiff)
5. **Liquidity constraints** — AIM spreads of 5-10x FTSE 100; stamp duty 0.5% on Main Market
6. **UK de-equitisation** — 20% fewer listed companies in 5 years; persistent fund outflows

### The Final Check

*"If this strategy fails, can I clearly explain why using the papers?"*

**Yes.** The strategy would fail if:
- Survivorship bias in Yartseva overstates the predictive power of the identified factors (base-rate probability remains too low even with correct factor tilts)
- Factor premiums continue their post-2012 decay toward zero (Bermejo's documented trend)
- UK-specific implementation costs (stamp duty, AIM spreads, illiquidity) consume the gross factor premiums
- The 2009-2024 bull market period that generated Yartseva's sample is not representative of future market regimes
- Concentrated UK small-cap exposure coincides with continued de-equitisation and fund outflows

Each of these failure modes is documented, probability-assessed, and has specific monitoring triggers in the risk documentation.

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
| **[CORE EVIDENCE]** | From the four mandatory source papers |
| **[DIRECT EVIDENCE]** | From specific academic papers with citations |
| **[SUPPORTING EVIDENCE]** | From closely related research |
| **[RELATED EVIDENCE]** | From adjacent academic work |
| **[INFERENCE]** | Reasonable logical extension of evidence |
| **[SPECULATIVE]** | Beyond what evidence directly supports |
| **[DATA SUPPORTS]** | Directly supported by empirical data |
| **[REASONABLE ASSUMPTION]** | Logical extension of validated findings |

---

## Mandatory Source Papers Analysed

1. **Yartseva (2025)** — "The Alchemy of Multibagger Stocks: An Empirical Investigation of Factors That Drive Outperformance." CAFE Working Paper No. 33, Birmingham City University. *464 multibagger stocks, 150+ variables, GMM estimation.*

2. **Harvey, Liu & Zhu (2016)** — "...and the Cross-Section of Expected Returns." Review of Financial Studies, 29(1): 5-68. *316 factors, multiple testing framework, t > 3.0 threshold.*

3. **Bermejo et al. (2021)** — "Factor investing: A stock selection methodology for the European equity market." Heliyon, 7(10): e08168. *600 European large-caps, iterative multi-factor strategies, Sharpe 0.94.*

4. **UK/European Empirical Factor Studies** — Including Dimson, Marsh & Staunton (DMS database), Gregory, Tharyan & Christidis (2013), Novy-Marx (2013), Asness, Moskowitz & Pedersen (2013), Daniel & Moskowitz (2016), Bessembinder (2018, 2023), and 20+ additional papers.

---

## Key Insight Summary

| # | Insight | Source | Confidence |
|---|---------|--------|------------|
| 1 | FCF Yield is the strongest single predictor of multi-bagger returns | Yartseva 2025 | High |
| 2 | Gross Profitability (GP/Assets) is the most robust quality metric internationally | Novy-Marx 2013, Bermejo 2021 | High |
| 3 | Only 9 of 313 factors survive rigorous multiple-testing adjustment (t > 3.0) | Harvey et al. 2016 | High |
| 4 | Iterative multi-factor combinations (value→quality→momentum) achieve Sharpe 0.94 | Bermejo et al. 2021 | High |
| 5 | 57.4% of stocks underperform Treasury bills over their lifetimes | Bessembinder 2018 | High |
| 6 | Earnings growth does NOT predict multi-bagger outcomes | Yartseva 2025 | High (counterintuitive) |
| 7 | Asset growth is positive ONLY when supported by EBITDA growth | Yartseva 2025 | High |
| 8 | UK size premium reversed post-publication (+6% → -6%) | Dimson & Marsh 1999 | High |
| 9 | Factor alphas are decaying toward zero post-2012 | Bermejo 2021 | Moderate |
| 10 | UK AIM market has structural liquidity constraints (5-10x wider spreads) | Multiple sources | High |
