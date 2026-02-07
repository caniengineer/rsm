# Validated Factors for UK Small-Cap Quality-Value-Momentum Strategy

> Factors are classified into three tiers based on the strength and breadth of their evidence:
>
> - **Core Factors (Tier A):** Multi-source validation, multi-market evidence including UK/Europe, t > 3.0 or equivalent. Used as primary scoring factors.
> - **Secondary Factors (Tier B):** Partial multi-source support or strong single-source evidence with directional corroboration. Used as quality checks and tiebreakers.
> - **Excluded Factors (Tier C):** Single-study findings without independent replication. Documented for transparency but not used in the scoring model until replicated.
>
> **Evidence standard for Core status:** At least two independent academic studies, at least one including UK or European data, with a plausible economic mechanism.

---

## 1. Gross Profitability (GP/Assets) — TIER A (Core)

**Title:** Gross Profit-to-Assets (GPA)
**Source:** Novy-Marx (2013), Bermejo et al. (2021), Cotter & McGeever (2018), Hanauer & Huber (2016), Foye (2018)
**Key Insight:** Gross Profit / Total Assets is the most robust profitability metric internationally. It captures the economic engine of a business before management can obscure it through accounting choices on SG&A, depreciation, or one-off items. In Europe, GPA delivers a Fama-French 3-factor alpha of 4.23% per annum (t = 10.88). In the UK specifically, profitability remains robust when other anomalies decay post-publication (Cotter & McGeever 2018).
**Measurable Signal:** GPA = (Revenue - Cost of Goods Sold) / Total Assets. Use the most recent annual report. Rank universe; require above 40th percentile as minimum quality threshold.
**Evidence Strength:** Very strong. Multiple independent sources, multiple markets (19+ countries), multiple decades, UK-specific persistence confirmed. This is the most defensible factor in the strategy.
**Composite Score Weight:** 30%
**Where it Works:** US and European equities broadly. Strongest in small caps where information asymmetry is highest.
**Where it Fails:** Asset-light business models (software, platforms) show extremely high GPA reflecting business model rather than mispricing. Financial companies have meaningless COGS lines. GPA does not capture capital allocation quality.
**Open Questions:** Whether trailing-three-year average GPA is more stable. Whether GPA improvement (delta-GPA) adds incremental information.

---

## 2. Valuation (EV/EBITDA) — TIER A (Core)

**Title:** Enterprise Value-to-EBITDA
**Source:** Bermejo et al. (2021), Harvey, Liu & Zhu (2016), DMS long-run UK data, Yartseva (2025)
**Key Insight:** Value is one of two factors surviving the harshest multiple-testing corrections globally (Harvey et al. 2016). EV/EBITDA is the strongest value metric in European data (Bermejo et al. 2021). Long-run UK evidence shows 10.8% vs 7.8% for high vs low yield over 117 years (DMS).
**Measurable Signal:** EV/EBITDA = (Market Cap + Total Debt - Cash) / EBITDA. Lower is cheaper. Rank universe; require below 60th percentile (not in the most expensive 40%).
**Evidence Strength:** Strong. Value (HML) survives the 0.1% significance threshold. Long-run UK evidence robust. EV/EBITDA outperforms P/E, P/B, and P/CF in Bermejo et al.'s European tests.
**Composite Score Weight:** 25%
**Where it Works:** Globally, across US and European markets. Effect strongest in small caps.
**Where it Fails:** Prolonged drawdowns (2017-2020 in the US). Sectors with intangible-heavy business models appear perpetually expensive on book value measures. Negative EBITDA renders the ratio meaningless. Financial companies excluded.
**Open Questions:** Whether intangible-adjusted measures improve signal. Relative weighting vs B/M in a composite.

---

## 3. Momentum (12-1 Month) — TIER A (Core)

**Title:** Price Momentum (12-minus-1)
**Source:** Bermejo et al. (2021), Harvey, Liu & Zhu (2016), Liu, Strong & Xu (1999), Asness, Moskowitz & Pedersen (2013), Daniel & Moskowitz (2016)
**Key Insight:** Classical 12-1 momentum (buy past winners, skip the most recent month) is the strongest pure factor in European data (Sharpe 0.80, FF3 alpha 1.54%, t = 2.62) and one of only two factors to survive the harshest multiple-testing thresholds globally (Harvey et al. 2016). Used as a trend-confirmation signal to avoid "falling knives."
**Measurable Signal:** 12-1 Momentum = (Price today / Price 12 months ago) - 1, excluding the most recent month. Require positive (above zero) as a minimum gate.
**Evidence Strength:** Strong across multiple independent studies, multiple markets. Important caveats: absent in UK data before 1977 (Hon & Tonks 2003), subject to severe crash risk during bear-market recoveries (Daniel & Moskowitz 2016), declining significance in recent UK data (Cotter & McGeever 2018).
**Composite Score Weight:** 20%
**Where it Works:** US and European equities broadly. Strongest in mid-to-large caps with high liquidity.
**Where it Fails:** Momentum crashes during bear-market recoveries (14 of 15 worst returns when trailing 2-year market return negative and contemporaneous return positive). Absent in UK data 1955-76. Post-2012 alpha decay in Europe.
**Note on contrarian momentum:** Yartseva (2025) found that for multibaggers specifically, stocks near 52-week lows tend to become future winners. This contradicts standard momentum. The contrarian signal has been **excluded from the scoring model** because it rests on a single study and creates logical incoherence with standard momentum. It may be relevant for Tier 2 conviction hold selection as a qualitative input, but should not be systematically scored until independently replicated.

---

## 4. Free Cash Flow Yield (FCF/P) — TIER B (Secondary)

**Title:** Free Cash Flow Yield
**Source:** Fama & French (2018) -- cash-based profitability dominates accrual measures. Yartseva (2025) -- strongest predictor in multibagger sample (coefficient 46-82), but single unreplicated US study.
**Key Insight:** FCF yield captures companies generating real cash relative to their market price. Cash flow is harder to manipulate than accrual earnings, making it a useful quality check. Positive FCF ensures the company is self-financing.
**Measurable Signal:** FCF Yield = Free Cash Flow / Market Capitalisation. FCF = Operating Cash Flow minus Capital Expenditures. TTM figures. Higher is better.
**Evidence Strength:** Moderate. Cash-based profitability is well-supported broadly (Fama & French 2018). The specific claim that FCF yield predicts *extreme* returns rests on Yartseva (2025) alone, with coefficient instability (46-82 across specifications) that is a concern.
**Composite Score Weight:** 15% (secondary to GP/Assets)
**Where it Works:** Broad equity markets. Especially useful for identifying cash-generating businesses in small caps where accounting quality varies.
**Where it Fails:** Capital-intensive turnarounds show depressed FCF. Sectors with lumpy capex cycles (mining, semiconductors) show misleading single-year FCF. FCF can be temporarily inflated by cutting capex or deferring maintenance.
**Why secondary rather than primary:** The link between FCF yield and *average* cross-sectional returns is supported by Fama & French (2018). The link to *extreme* returns (multibaggers) is supported only by Yartseva (2025), which is unreplicated, US-only, and shows coefficient instability. GP/Assets has broader and more robust evidence.

---

## 5. Small Cap Size — TIER B (Secondary / Universe Filter)

**Title:** Small Capitalisation
**Source:** Yartseva (2025) -- median starting market cap $348m. Dimson & Marsh (1999) -- UK size premium reversed post-publication. Bessembinder (2018) -- 57.4% of stocks underperform T-bills.
**Key Insight:** Multibaggers start small by mathematical necessity (a GBP 100m company reaching 10x is GBP 1bn; a GBP 50bn company reaching 10x is nearly impossible). However, the raw size premium has failed to replicate in the UK. Size is a universe filter (where to look), not a return predictor (what to buy).
**Measurable Signal:** Market capitalisation at screening date. GBP 30m-1,000m eligible range. Within the range, smaller stocks receive a modest scoring bonus (10% weight).
**Evidence Strength:** Mixed. The descriptive fact that multibaggers start small is tautological. The UK size premium reversed post-publication (+6% to -6%, Dimson & Marsh 1999). Most small caps underperform bonds (Bessembinder 2018).
**Composite Score Weight:** 10% (modest tilt only)
**Where it Works:** As a universe definition. Small caps have wider information asymmetry, which amplifies factor signals from profitability and value.
**Where it Fails:** Raw size premium reversed in UK. AIM spreads of 5-10x FTSE 100 consume any size premium. High failure rates in small caps. Survivorship bias most acute here.

---

## 6. Investment-EBITDA Growth Interaction — TIER C (Excluded)

**Title:** Capital Investment Conditional on Earnings Growth
**Source:** Yartseva (2025) only. No independent replication.
**Key Insight:** Yartseva found that aggressive asset growth generates superior returns ONLY when supported by concurrent EBITDA growth. When asset growth is high but EBITDA growth is low, returns drop 5-23 percentage points. The economic intuition is sound (productive investment beats empire-building), but the statistical evidence is insufficient.
**Status: EXCLUDED from scoring model.**
**Why Excluded:**
- Single-study finding with no independent replication in any market.
- The "100% of cases" claim is a statistical red flag -- no factor works in 100% of cases.
- Papanastasopoulos (2017) European evidence on asset growth anomalies contradicts the interaction pattern (anomaly stronger in loss-making firms, not profitable ones).
- Testing 150+ variables on 464 stocks creates extreme overfitting risk for interaction terms.
- The interaction term requires judgement calls on timing (contemporaneous vs. lagged EBITDA growth) that are inherently susceptible to look-ahead bias.
**Retained as qualitative heuristic:** When evaluating Tier 2 conviction holds, investors may note whether a company's investment is matched by earnings growth. This is sensible business analysis, not a scored factor.
**What would reinstate this factor:** Independent replication in UK or European small-cap data using a survivorship-free dataset, with pre-specified measurement definitions.

---

## 7. Iterative Multi-Factor Strategy (Profitability -> Value -> Momentum) — METHODOLOGY

**Title:** Sequential Factor Layering
**Source:** Bermejo et al. (2021) -- Iterative strategy achieving Sharpe 0.94, alpha 5.65% per annum in European large-caps.
**Key Insight:** Applying factors sequentially -- screening for profitability, then filtering by valuation, then confirming momentum -- produces better risk-adjusted returns than single factors or naive composites. Each layer removes a different type of loser: profitability removes cash-burners, value removes overpriced stocks, momentum removes dead-money stocks.
**Implementation:** Step 1: GP/Assets above 40th percentile. Step 2: Positive FCF, FCF yield above median. Step 3: EV/EBITDA below 60th percentile. Step 4: Composite score using weights (GP/Assets 30%, EV/EBITDA 25%, Momentum 20%, FCF Yield 15%, Size 10%).
**Evidence Strength:** Strong for the combined approach in European large-caps (Bermejo et al. 2021). **Important caveat:** Bermejo tested on the 600 LARGEST European companies. Extrapolation to UK small caps (GBP 30m-1,000m) is an assumption, not a tested result. Post-2012 factor alpha decay noted.
**Where it Fails:** Post-2012 alpha decay. The sequential approach concentrates the portfolio aggressively (20-30 stocks), increasing idiosyncratic risk. Transaction costs from rebalancing erode alpha in illiquid small caps.

---

## Appendix: Factor Evidence Summary Table

| Factor | Tier | Weight | Primary Source | t-stat or Equivalent | Markets Validated | Independent Sources |
|---|---|---|---|---|---|---|
| GPA (Gross Profitability) | A (Core) | 30% | Novy-Marx (2013), Bermejo (2021), Cotter & McGeever (2018) | t = 10.88 (Europe) | US, Europe, UK, 19+ countries | 4+ |
| EV/EBITDA (Value) | A (Core) | 25% | Bermejo (2021), Harvey et al. (2016), DMS | Survives 0.1% threshold | US, Europe, UK, Global | 4+ |
| Momentum (12-1) | A (Core) | 20% | Bermejo (2021), Liu et al. (1999), Asness et al. (2013) | t = 2.62 / survives 0.1% | US, Europe, UK | 4+ |
| FCF Yield | B (Secondary) | 15% | Fama & French (2018), Yartseva (2025) | Coeff 46-82 (Yartseva, US only) | US, Europe (broad) | 2 (1 for extreme returns) |
| Small Cap Size | B (Universe filter) | 10% | Yartseva (2025), Dimson & Marsh (1999) | Descriptive; premium reversed in UK | US (descriptive) | N/A (tautological) |
| Inv x EBITDA Growth | C (Excluded) | 0% | Yartseva (2025) only | Significant interaction (single study) | US only | 1 (no replication) |
| Contrarian Momentum | C (Excluded) | 0% | Yartseva (2025) only | Significant in regression (single study) | US only | 1 (contradicts standard MOM) |
| Interest Rate Overlay | C (Excluded) | 0% | Yartseva (2025) only | Coeff -7.9 to -12.1 (single study) | US only (Fed Funds) | 1 |

---

## Notes on Interest Rate Sensitivity

Yartseva (2025) finds that rising interest rates reduce multibagger returns by 8-12 percentage points. This is a single-study, US-specific finding using the Federal Funds Rate. It has been **excluded from the scoring model** because: (a) the Bank of England's transmission mechanism differs from the Fed, (b) regime-dependent factor timing is unreliable and adds complexity without proven benefit, and (c) a strategy should work across rate environments or be honestly described as regime-dependent.

Interest rates are monitored as context for interpreting performance, not as a factor weight adjustment trigger.
