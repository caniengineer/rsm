# Literature Review: Academic Evidence for UK Small-Cap Factor Strategy

**Compiled:** 2026-02-07
**Purpose:** Structured synthesis of mandatory source papers and supporting evidence
**Evidence Labels:**
- **[CORE]** — From mandatory source papers
- **[SUPPORTING]** — From closely related academic work
- **[WEAK/SPECULATIVE]** — Limited evidence or inference

---

## Paper 1: Yartseva (2025) — "The Alchemy of Multibagger Stocks"

**Title:** The Alchemy of Multibagger Stocks: An Empirical Investigation of Factors That Drive Outperformance
**Source:** CAFE Working Paper No. 33, Birmingham City University
**Key Insight:** Multi-bagger stocks (10x+ returns) can be partially predicted by a specific set of fundamental, technical, and macroeconomic factors — but many commonly assumed predictors (earnings growth, debt, dividends) are statistically insignificant.

### Research Question
What characteristics predict stocks that achieve 10x+ returns, and can a model outperform Fama-French five factors for this specific subset?

### Dataset
- 464 multibagger stocks on NYSE/NASDAQ, 2009-2024
- 11,600 company-year observations, 150+ variables tested
- In-sample: 2000-2022; Out-of-sample: 2023-2024
- 24 stocks in the sample achieved 100x+ returns
- Inclusion rule: stock must hit 10x AND stay above 9x (persistence requirement)

### Methodology
- Stage 1: Fama-French portfolio sorts (3×3×2×2: size × value × profitability × investment)
- Stage 2: Arellano-Bond GMM dynamic panel estimation to address endogeneity
- Diagnostics: Modified Wald test (heteroscedasticity), Wooldridge test (autocorrelation)
- Model selection: AIC and SBC criteria

### Key Findings

| Factor | Direction | Coefficient Range | Evidence |
|--------|-----------|------------------|----------|
| **FCF Yield (FCF/P)** | Positive | 46-82 | [CORE] Strongest predictor |
| **Small Size** | Positive | Significant | [CORE] Median start: $348m |
| **High B/M (Value)** | Positive | +34.7% excess (high) vs +12.8% (low) | [CORE] Non-linear |
| **Profitability** | Positive | Significant | [CORE] Level matters, not growth |
| **Investment when EBITDA-supported** | Positive | -4.7 to -22.8 (when NOT supported) | [CORE] Conditional |
| **Near 52-week lows** | Positive | Significant | [CORE] Contrarian |
| **Rising interest rates** | Negative | -7.9 to -12.1 | [CORE] Macro regime |

**Non-Significant Factors (Rejected):**
Earnings growth (all forms), dividends, debt levels, share buybacks, analyst coverage, Altman Z-scores, R&D/FCF ratio.

### Multibagger Starting Profile (2009 Medians)
| Metric | Value |
|--------|-------|
| Market cap | $348m |
| Revenue | $702m |
| Price-to-Sales | 0.6 |
| Price-to-Book | 1.1 |
| Forward P/E | 11.3 |
| Gross margin | 34.8% |
| Operating margin | 3.9% |
| ROE | 9.0% |

### Limitations
- **Survivorship bias**: Only successful 10x stocks studied; false-positive rate unknown
- **US-only**: NYSE/NASDAQ; not tested on UK/European data
- **Bull market period**: 2009-2024 is predominantly a rising market
- **Coefficient instability**: FCF yield ranges 46-82 across specifications
- **Short OOS window**: Only 2 years of out-of-sample validation
- **FF5 intercept of 83**: Large unexplained component remains

### Limitations and Status

**This paper is used as SUPPORTING evidence only, not as a primary evidence source.** It is a single, non-peer-reviewed working paper that has not been independently replicated. The strategy no longer depends on any Yartseva-exclusive findings. Factors with weight in the scoring model (GP/Assets, FCF Yield, EV/EBITDA, Momentum) all have multiple independent replications from other sources.

### Relevance to Multi-baggers
This is the ONLY paper that directly studies multi-bagger characteristics empirically. All other evidence is indirect (factor premiums for average returns, not extreme outcomes). The distinction matters: factors that predict mean outperformance may not predict right-tail outcomes.

---

## Paper 2: Harvey, Liu & Zhu (2016) — "...and the Cross-Section of Expected Returns"

**Title:** ...and the Cross-Section of Expected Returns
**Source:** Review of Financial Studies, 29(1): 5-68
**Key Insight:** The traditional t > 2.0 significance threshold is insufficient given 316+ factors tested on overlapping data. A minimum of t > 3.0 is required; most published factors are likely false discoveries.

### Research Question
What statistical hurdle should new factors meet, given the cumulative data mining since 1967?

### Dataset
- 316 factors catalogued from 250+ published papers and 63 working papers
- Spanning 1967-2012

### Methodology
- Three multiple testing corrections: Bonferroni (FWER), Holm (FWER), BHY (FDR)
- Allows for correlation among tests and missing data
- Estimates that 71% of tried tests are never published

### Key Findings
- **Only 9 of 313 variables survive |t| > 3.0**
- **158 of 296 published "significant" factors are likely false discoveries (53%)**
- Bonferroni benchmark reaches 3.78 by 2012, projected to 4.00 by 2032
- BHY-adjusted threshold: t > 3.18

### Factors That Survive
[CORE] Value (HML) and Momentum (MOM) pass even the 0.1% threshold — these are among the most robust factors in the literature.

### Implications for Strategy
- **Any factor we use must have t > 3.0** (or strong economic rationale + multiple independent replications)
- Combining weak factors amplifies noise, not signal
- Start with a small number of highly robust factors
- Independent factors (value + momentum, negatively correlated) add genuine diversification

### Related Evidence
- **McLean & Pontiff (2016)**: 26% lower out-of-sample, 58% lower post-publication, 93% lower after costs [SUPPORTING]
- **Hou, Xue & Zhang (2020)**: 65% of 452 anomalies fail even t > 1.96 when microcaps excluded; 82% fail t > 2.78 [SUPPORTING]
- **Jensen, Kelly & Pedersen (2023)**: Pushback — factors cluster into 13 themes, 10 significant; replication rate >50% in 11 of 13 themes; false discovery rate estimated at only ~1% [SUPPORTING]
- **Chen & Zimmermann (2022)**: 98% of 161 significant characteristics reproduce with t > 1.96 [SUPPORTING]

### Evidence Quality Hierarchy (Derived)
| Tier | Criteria | Action |
|------|----------|--------|
| **Tier 1: Gold Standard** | t > 3.0, economic theory, global OOS, survives replication | Use as primary drivers |
| **Tier 2: Strong** | t > 3.0, some theory, limited OOS | Use with caution |
| **Tier 3: Suspect** | 2.0 < t < 3.0, possibly data-mined | Avoid as primary drivers |
| **Tier 4: Rejected** | t < 2.0, fails replication | Do not use |

---

## Paper 3: Bermejo et al. (2021) — European Factor Investing

**Title:** Factor investing: A stock selection methodology for the European equity market
**Source:** Heliyon, 7(10): e08168
**Key Insight:** Iterative multi-factor combinations (value → profitability → momentum) dramatically outperform single-factor strategies in European large-caps, achieving Sharpe ratios up to 0.94.

### Research Question
Can systematic multi-factor portfolios outperform benchmarks in European equities using value, profitability, and momentum?

### Dataset
- 600 largest European companies by market cap (29 countries including UK)
- July 1991 – July 2019 (28 years)
- 17,400 observations, 1,830 companies, 19 sectors
- UK estimated at ~20-25% of universe weight

### Methodology
- 8 factor metrics: 4 value (BTM, PER, EVEBIT, EVEBITDA), 3 profitability (GPA, ROC_Green, ROC_Det), 1 momentum (12-1)
- 40 strategies: Pure (8), Mixed (16), Iterative/Conditional (16)
- Iterative: Top quintile by value → top 50% by profitability → top 50% by momentum = 30 stocks
- Annual rebalancing (June 30), long-only, equal-weighted

### Key Findings by Factor

**Momentum (12-1):** Strongest pure factor. Final index 25.49, annualised 11.56%, Sharpe 0.80, FF3 alpha 1.54% (t=2.62). [CORE]

**GPA (Gross Profit/Assets):** Highest FF3 alpha as pure strategy: 4.23% (t=10.88). Z-score impact: 4.68% per standard deviation. [CORE]

**EVEBITDA:** Strongest value metric. Final index 25.21, annualised 11.21%. [CORE]

**Best Iterative Strategy:** EVEBITDA|ROC_Det|MOM — Sharpe 0.94, Jensen's alpha 5.65%, FF3 alpha 2.42% (t=5.96), beta 87.08%. [CORE]

### Factor Interactions
- 11 of 16 iterative strategies significantly outperform pure strategies
- Average Sharpe improvement: +0.12 points over pure strategies
- Value + momentum negative correlation (~-0.49 to -0.60) provides diversification
- Iterative approach filters: cheap stocks → profitable → trending up

### Limitations
- **No UK-specific breakdown** — all countries pooled
- **Large-cap only** (top 600) — cannot test small-cap effects
- **No transaction cost modelling** — gross returns only
- **Factor alphas decaying** — alphas approach zero post-2012
- **No investment/asset growth factor** tested

---

## Paper 4: UK & European Empirical Factor Studies (Multiple Sources)

### UK Factor Evidence Summary

| Factor | UK Evidence | Premium | Source |
|--------|------------|---------|--------|
| Size | Long-run +2% p.a., but reversed post-publication | Mixed | DMS; Dimson & Marsh 1999 |
| Value (yield) | 10.8% vs 7.8% for high vs low yield over 117 years | Strong (long-run) | DMS 2017 |
| Momentum | Confirmed 1977-96; absent 1955-76 | Strong post-1977 | Liu et al. 1999; Hon & Tonks 2003 |
| Profitability (GP/A) | 3.6% p.a. Europe; robust when others decay | Strong | DFA 2015; Cotter & McGeever 2018 |
| Investment (CMA) | 0.17-0.29% monthly Europe; stronger in small caps | Moderate | Fama & French 2017 |
| Quality (QMJ) | ~4.7% p.a. globally | Strong | Asness et al. |

### Profitability Metric Hierarchy (International Evidence)
1. **Gross profitability (GP/Assets)** — strongest [CORE: Novy-Marx 2013, Hanauer & Huber 2016]
2. **Cash-based operating profitability** — dominates accrual-based [SUPPORTING: Fama & French 2018]
3. **Operating profitability** — robust but slightly weaker [SUPPORTING]
4. **ROE** — weakest internationally [CORE: Hanauer & Huber 2016]

### UK Market Structure
- **Main Market**: Stamp duty 0.5%; SETS order book; higher regulation
- **AIM**: Stamp duty exempt; SETSqx for 80% of stocks; spreads 5-10x FTSE 100
- AIM shrinkage: 1,694 (2007) → 679 (2025)
- MiFID II improved AIM research coverage (+6.3%)
- UK de-equitisation: 20% fewer listed companies over 5 years

### Extreme Returns (Bessembinder Programme)
- 57.4% of US stocks underperform T-bills over their lifetimes [CORE: Bessembinder 2018]
- Top 4% of stocks explain entire US market gains [CORE]
- Top 2.4% explain all $75.7 trillion global wealth creation 1990-2020 [CORE]
- Stock underperformance more prevalent internationally (42.4%) than US (49.7%) [SUPPORTING]
- Concentration increasing over time [CORE]

### UK-Specific Multi-bagger Evidence (Stockopedia)
- Starting market cap: GBP 50m-350m
- ROCE > 10%, operating margins growing
- Net gearing < 30%, high FCF
- Forecast P/E < 15
- Trailing sales growth > 10%
- Simple, scalable business models (JD Sports, Games Workshop)
- No technology stocks in UK's top 10 performers [SUPPORTING]

---

## Paper 5: McLean & Pontiff (2016) — "Does Academic Research Destroy Stock Return Predictability?"

**Title:** Does Academic Research Destroy Stock Return Predictability?
**Source:** Journal of Finance, 71(1): 5-32
**Key Insight:** Academic publication of anomalies leads to substantial decay in factor premiums, with returns declining 26% out-of-sample and 58% post-publication. This provides critical context for all factor premium estimates used in this strategy.

### Research Question
Do stock return anomalies documented in academic research decline after publication, and if so, by how much?

### Dataset
- 97 characteristics shown to predict cross-sectional stock returns in peer-reviewed journals
- Sample period extended beyond original publication dates to measure post-publication decay

### Key Findings
- **Out-of-sample decay: 26%** — Returns to anomaly-based strategies decline by an average of 26% when tested on data not used in the original study (but prior to publication).
- **Post-publication decay: 58%** — Returns decline by an average of 58% after the academic paper documenting the anomaly is published.
- The post-publication decline is consistent with two mechanisms: (1) investors learning about mispricing and trading it away, and (2) original studies benefiting from data-mining/overfitting.
- Anomalies based on less liquid stocks (where arbitrage is harder) show smaller post-publication declines, suggesting mispricing correction is a meaningful channel.
- The findings imply that **academic factor premiums should be haircut by at least 50%** when used for forward-looking return estimates.

### Implications for This Strategy
- All factor premium estimates from the academic literature (value, profitability, momentum, investment) should be treated as upper bounds on achievable future returns.
- Factor premiums documented from historical backtests are likely to overstate what can be captured going forward, even before transaction costs.
- Factors with strong economic rationale (risk-based explanations) may be more persistent than those driven purely by mispricing, but even risk-based factors show some post-publication decay.
- This reinforces the importance of using factors with the highest evidence quality (Tier 1 per Harvey, Liu & Zhu) and multiple independent replications, as these are most likely to retain meaningful premiums post-publication.

---

## Cross-Paper Synthesis: Evidence Mapping

### Factors → Factor Evidence for Above-Average Returns

| Factor | Increases probability of above-average returns? | Evidence |
|--------|-------------------------------------|----------|
| FCF Yield (high) | **YES — strongest signal** | Yartseva 2025 [SUPPORTING], Fama & French 2018 [CORE] |
| Gross Profitability (high) | **YES — quality gate** | Bermejo 2021, Novy-Marx 2013 [CORE] |
| Value (low P/E, high B/M, low EV/EBITDA) | **YES — non-linear effect** | Yartseva 2025 [SUPPORTING], Bermejo 2021 [CORE] |
| Small Cap Size | **YES — necessary condition** | Yartseva 2025 [SUPPORTING], Stockopedia UK [SUPPORTING] |
| Investment + EBITDA growth | **REMOVED FROM STRATEGY** — single-study finding (Yartseva 2025 only), no independent replication | Yartseva 2025 [WEAK/SPECULATIVE] |
| Momentum (standard 12-1) | **For average returns, YES** | Bermejo 2021 [CORE] |
| Contrarian momentum (near lows) | **REMOVED — single-study evidence only** | Yartseva 2025 [WEAK/SPECULATIVE] |

| Factor | Avoids losers but doesn't create winners? | Evidence |
|--------|------------------------------------------|----------|
| Investment discipline (CMA) | **Mostly — removes destroyers** | Fama-French 2017 [SUPPORTING] |
| Low share issuance | **Yes — avoids dilution** | Cotter & McGeever 2018 [SUPPORTING] |

| Factor | Works for average returns only? | Evidence |
|--------|-------------------------------|----------|
| Standard momentum (12-1) | **May not predict extreme tails** | Bessembinder: no long-horizon momentum in winners [SUPPORTING] |
| ROE | **Weakest quality metric internationally** | Hanauer & Huber 2016 [CORE] |

| Factor | Does NOT predict multi-baggers? | Evidence |
|--------|-------------------------------|----------|
| Earnings growth | **Insignificant** | Yartseva 2025 [SUPPORTING] |
| Dividend policy | **Irrelevant** | Yartseva 2025 [SUPPORTING] |
| Debt levels | **Not predictive** | Yartseva 2025 [SUPPORTING] |
| R&D intensity | **No correlation** | Yartseva 2025 [SUPPORTING] |
| Analyst coverage | **Not significant** | Yartseva 2025 [SUPPORTING] |

---

## Evidence Confidence Assessment

### What We Can State with Confidence
1. Multi-baggers start small and undervalued — this is the strongest cross-source finding
2. Profitability (measured by GP/Assets or FCF yield) is a robust and persistent factor globally
3. Most published factors are likely false discoveries — rigorous selection is essential
4. Multi-factor combinations outperform single factors (Bermejo Sharpe of 0.94 vs 0.80)
5. Factor premiums decay after publication and after accounting for costs
6. Factor premiums decline substantially post-publication (McLean & Pontiff: 58% decay)

### What Is a Reasonable Assumption
1. The iterative approach (value → quality → momentum) will work in UK small/mid-caps
2. AIM stocks with sufficient liquidity are the natural hunting ground for UK multi-baggers
3. Patient holding (3-7+ years) is required for multi-bagger outcomes

### What Is Speculative
1. Specific return targets (5x, 10x) — base rates are extremely low
2. That the 2009-2024 factor relationships will persist in different market regimes
3. That a systematic screen can reliably identify the 2-4% of stocks that create wealth
4. UK-specific coefficient magnitudes for any factor
5. That specific factor calibrations from Yartseva's US sample apply to UK markets
6. That Yartseva's US findings are directionally applicable to UK equities — this is an assumption based on partial overlap with Stockopedia UK observations, not an established fact
