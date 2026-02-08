# Rejected or Weak Factors

> Factors below have been tested in rigorous academic studies and found to be either
> statistically insignificant, unreliable post-publication, or lacking incremental explanatory
> power for UK small-cap factor strategy screening. Including these in a screening model would add
> noise, complexity, and false confidence without improving returns.

---

## 1. Earnings Growth

**Title:** Earnings Per Share Growth as a Predictor of Future Returns
**Source:** Yartseva (2025) -- "Multibagger Stocks: Characteristics and Drivers of Returns"
**Why Rejected/Weak:** Earnings growth is NOT a significant predictor of multibagger returns in Yartseva's multivariate analysis. Despite being the most commonly cited reason retail investors buy growth stocks, past or projected earnings growth carries no statistically significant predictive power once other factors (FCF yield, value, profitability) are controlled for.
**Common Misconception:** Investors equate "growing earnings" with "good stock." The confusion arises because multibaggers do tend to grow earnings -- but this is an outcome, not a predictor. By the time earnings growth is visible in financial statements, it is already priced in. Free cash flow yield and gross profitability, which are less followed and harder to game, carry the genuine signal.
**Implications:** Do NOT screen for EPS growth, earnings surprise history, or analyst earnings growth estimates. These are outputs of a good business, not inputs to a good screen. Focus on FCF yield and GPA instead.

---

## 2. Dividend Policy

**Title:** Dividend Yield, Payout Ratio, and Dividend Growth
**Source:** Yartseva (2025)
**Why Rejected/Weak:** Dividend policy is irrelevant to multibagger identification. Whether a company pays dividends, how much it pays, or how fast it grows dividends has no predictive power for future multibagger returns. This result holds across all specifications in Yartseva's regressions.
**Common Misconception:** Dividend investing is a popular strategy with deep cultural roots (especially in the UK). The belief is that dividends signal management confidence, financial health, and shareholder alignment. While dividends may serve as consumption income for retirees, they are a drag on compounding for growth-seeking portfolios. A company paying out cash as dividends cannot reinvest that cash at high returns on capital.
**Implications:** Remove all dividend-related filters from the screening process. Do not penalise non-dividend-paying companies; they may be reinvesting in high-FCF-yield growth. Do not favour dividend aristocrats or high-yield stocks in a multibagger strategy.

---

## 3. Debt Levels

**Title:** Leverage, Debt-to-Equity, Net Debt/EBITDA
**Source:** Yartseva (2025)
**Why Rejected/Weak:** Debt levels are not predictive of multibagger returns. Neither high leverage (which some theories predict should amplify equity returns) nor low leverage (which signals financial conservatism) meaningfully predicts which stocks become multibaggers. The signal is dominated by FCF yield, profitability, and value metrics.
**Common Misconception:** Investors often use debt screens as a "safety" filter, assuming low-debt companies are safer and more likely to survive. While extreme leverage certainly increases bankruptcy risk, moderate variations in debt levels do not discriminate between future multibaggers and average stocks. The Altman Z-score finding (see below) corroborates this -- financial distress measures add nothing.
**Implications:** Do not use debt-to-equity or net-debt/EBITDA as a primary screen. If desired as a risk management guardrail, apply it only as a loose exclusion (e.g., exclude companies with net debt > 5x EBITDA) rather than as a scoring factor. The profitability gate (GP/Assets > 40th percentile) and asset growth screening overlay are better measures of whether a company's financial structure is healthy.

---

## 4. Share Buybacks

**Title:** Share Repurchase Activity
**Source:** Yartseva (2025)
**Why Rejected/Weak:** Share buyback activity is not a significant predictor of multibagger returns. Companies that repurchase shares do not systematically outperform those that do not, within the multibagger-candidate universe. This is notable because buybacks are often cited as a shareholder-friendly capital allocation signal.
**Common Misconception:** The narrative that buybacks "signal undervaluation" and "increase EPS by reducing share count" is popular among investors. While individual buyback announcements may generate short-term positive returns, the aggregate buyback signal does not distinguish future multibaggers. Many companies buy back shares at overvalued prices, and the EPS accretion effect is mechanical rather than value-creating.
**Implications:** Do not include net buyback yield or share count reduction in the factor model. If management capital allocation quality is important (and it is), the profitability gate and asset growth screening overlay (avoiding aggressive asset growth in loss-making firms) are more rigorous ways to measure it.

---

## 5. Analyst Coverage

**Title:** Number of Analysts Covering the Stock
**Source:** Yartseva (2025)
**Why Rejected/Weak:** Analyst coverage (number of sell-side analysts following the stock) is not a significant predictor of multibagger returns. While low coverage is correlated with small-cap status (which is a valid universe filter), analyst count itself adds no incremental information beyond market capitalisation.
**Common Misconception:** The "neglected firm effect" suggests that under-followed stocks outperform because they are mispriced. This is partially true, but the effect is subsumed by the small-cap size filter. Once you control for market cap, knowing whether 2 or 5 analysts cover the stock does not help.
**Implications:** Do not screen for low analyst coverage. The small-cap universe filter ($100m-$2bn market cap) already captures the information asymmetry advantage. If anything, zero-coverage stocks may be uninvestable due to lack of financial data availability.

---

## 6. R&D Intensity (R&D/FCF or R&D/Revenue)

**Title:** Research and Development Spending Relative to Cash Flow or Revenue
**Source:** Yartseva (2025)
**Why Rejected/Weak:** R&D intensity shows no significant correlation with multibagger returns. Neither high R&D spending (innovation narrative) nor low R&D spending (capital efficiency narrative) predicts which companies become multibaggers.
**Common Misconception:** The innovation thesis holds that companies spending heavily on R&D are investing in future growth and will eventually be rewarded. While true in specific cases (biotech breakthroughs, tech platforms), the cross-sectional evidence shows that R&D spending is too noisy and heterogeneous to serve as a systematic predictor. Most R&D spending is maintenance or incremental, not transformative.
**Implications:** Do not screen for R&D intensity in either direction. For sectors where R&D is critical (biotech, semiconductors), use sector-specific fundamental analysis rather than a quantitative R&D factor. Gross profitability (GPA) already captures whether a company has a competitive moat without requiring R&D-specific data.

---

## 7. Return on Equity (ROE)

**Title:** Return on Equity as a Profitability Measure
**Source:** UK/European factor replication studies; Novy-Marx (2013) comparison of profitability metrics
**Why Rejected/Weak:** ROE is the weakest profitability metric in international tests. While it is the most commonly used measure by equity analysts and screeners, it is dominated by Gross Profit/Assets (GPA) and Operating Profitability in every cross-sectional return study conducted outside the US. ROE is mechanically inflated by leverage (high debt increases ROE without improving the business), manipulated by buybacks (reducing equity increases ROE), and distorted by one-off items that flow through net income.
**Common Misconception:** ROE is a cornerstone of the Buffett/Munger value investing framework and DuPont analysis. Its popularity stems from its intuitive appeal (returns to shareholders) and long pedigree. However, the academic evidence is clear: GPA captures the same economic information with far less noise. ROE conflates operating quality with financial engineering.
**Implications:** Replace ROE with GPA (Gross Profit / Total Assets) in all screening and scoring. If a secondary profitability check is desired, use Operating Profitability (Operating Income / Book Equity) rather than net-income-based ROE.

---

## 8. Raw Size Premium (SMB as a Return Factor)

**Title:** The Small-Minus-Big (SMB) Factor as a Standalone Alpha Source
**Source:** Dimson & Marsh (1999) -- UK size premium reversal; Bessembinder (2018) -- 57.4% of US stocks underperform T-bills; Fama & French ongoing research
**Why Rejected/Weak:** The raw size premium has failed to replicate reliably post-publication. In the UK, Dimson & Marsh (1999) documented a complete reversal of the size effect after Fama & French's 1993 publication. The median small-cap stock underperforms -- Bessembinder shows 57.4% of all US stocks (mostly small) underperform Treasury bills over their lifetime. The "size premium" in historical data was driven by a tiny number of extreme winners in the right tail, not by small stocks being systematically better.
**Common Misconception:** "Small caps outperform large caps" is one of the most deeply ingrained beliefs in investing. The confusion arises from the difference between equal-weighted and value-weighted returns, survivorship bias in historical data, and the conflation of the size universe (where multibaggers live) with size as a return predictor (which it is not).
**Implications:** Use small-cap status as a universe definition (where to fish), NOT as a scoring factor (which fish to catch). Within the small-cap universe, other factors (FCF yield, GPA, value, momentum) are the actual return drivers. Expect that most small caps will underperform; the strategy must identify the rare winners.

---

## 9. Altman Z-Score and Financial Health Measures

**Title:** Altman Z-Score, Interest Coverage, Current Ratio, and Related Financial Distress Indicators
**Source:** Yartseva (2025)
**Why Rejected/Weak:** Altman Z-scores are explicitly listed as non-significant in Yartseva's multibagger analysis. Neither high financial health (safe companies) nor low financial health (distressed companies with lottery-ticket upside) predicts multibagger status. This is consistent with the debt levels finding -- balance sheet safety metrics do not discriminate among multibagger candidates.
**Common Misconception:** Financial health screens are popular as "safety nets" to avoid companies at risk of bankruptcy. While bankruptcy avoidance is important, the Z-score is too blunt an instrument. Many future multibaggers look financially precarious during their trough (low Z-scores due to depressed earnings and high debt), and screening them out would eliminate some of the best opportunities. Conversely, high-Z-score companies are often mature and slow-growing.
**Implications:** Do not use Altman Z-score, Piotroski F-score, or similar financial health composites as screening factors. The FCF yield filter already ensures the company is generating cash, which is a more relevant survival indicator than accounting-ratio-based distress models. If bankruptcy risk needs to be managed, use a simple negative-FCF exclusion or a minimum market cap threshold rather than a composite score.

---

## 10. The "Factor Zoo" (300+ Published Anomalies)

**Title:** The Vast Majority of Published Cross-Sectional Return Factors
**Source:** Harvey, Liu & Zhu (2016) -- "...and the Cross-Section of Expected Returns"; Jensen, Kelly & Pedersen (2023) -- factor taxonomy
**Why Rejected/Weak:** Of the 313+ factors catalogued in the academic literature as of 2016, Harvey, Liu & Zhu estimate that 53% are likely false discoveries -- artefacts of data mining, p-hacking, and publication bias. Only 9 factors survive a t-statistic threshold of 3.0 (the minimum the authors recommend for new discoveries). Only 2 -- Value (HML) and Momentum (MOM) -- survive the most stringent 0.1% significance threshold. Jensen, Kelly & Pedersen (2023) confirm that the 300+ factors cluster into just 13 themes, of which only 10 are statistically significant. The vast majority of individually named factors (accruals anomaly, post-earnings-announcement drift, asset growth, investment-to-assets, net stock issuance, etc.) are either subsumed by the core themes or are outright false discoveries.
**Common Misconception:** Each new factor paper seems to identify a "new anomaly" with a compelling economic story and a statistically significant backtest. Practitioners accumulate these factors in increasingly complex models, believing that more factors equal more alpha. In reality, most of these factors share the same underlying information (value, momentum, profitability, investment, size), and adding them increases overfitting risk without improving out-of-sample performance.
**Implications:** Resist the temptation to add complexity. The validated factors in this strategy (FCF yield, GPA, momentum, value, and the CMA/asset growth anomaly) cover the core themes identified by Jensen et al. Adding dozens of additional factors would increase data requirements, computational complexity, and false-positive risk without meaningful improvement. Any new candidate factor must meet the Harvey et al. threshold of t > 3.0 before inclusion.

---

## 11. Investment-EBITDA Growth Interaction

**Title:** Capital Investment Conditional on Earnings Growth (Investment-EBITDA Interaction)
**Source:** Yartseva (2025) only
**Why Rejected:**
- Single unreplicated study -- no independent validation in any market
- The "100% of cases" claim is a statistical red flag suggesting overfitting or an extremely small subsample
- Yartseva tested 150+ variables on 464 stocks, creating severe multiple testing risk (Harvey et al. 2016 would require t > 3.0)
- Not tested in UK or European data
- Papanastasopoulos (2017) found the European asset growth anomaly is more pronounced in loss-making firms -- the opposite direction from what a positive Investment-EBITDA interaction would predict
- The standalone asset growth anomaly (CMA factor) provides the relevant information without the unreplicated interaction term
**Common Misconception:** The narrative that "investment is good when supported by earnings growth" is intuitively appealing, but this specific statistical interaction has been found in only one retrospective study of winners.
**Implications:** Use the standalone CMA/asset growth anomaly as a screening overlay (avoid aggressive asset growth in loss-making firms) rather than this specific interaction term. The profitability gate (GP/Assets > 40th percentile) already filters for the quality dimension.

---

## Summary Decision Matrix

| Factor | Verdict | Reason | Alternative |
|---|---|---|---|
| Earnings Growth | Reject | Not significant (Yartseva) | FCF Yield |
| Dividend Policy | Reject | Irrelevant (Yartseva) | None needed |
| Debt Levels | Reject | Not predictive (Yartseva) | Profitability gate + asset growth overlay |
| Share Buybacks | Reject | Not significant (Yartseva) | Profitability gate + asset growth overlay |
| Analyst Coverage | Reject | Subsumed by market cap | Small-cap universe filter |
| R&D Intensity | Reject | No correlation (Yartseva) | GPA |
| ROE | Reject | Weakest profitability metric | GPA |
| Raw Size Premium | Reject as factor | Reversed post-publication | Use as universe filter only |
| Altman Z-Score | Reject | Not significant (Yartseva) | FCF > 0 as survival check |
| Factor Zoo (300+) | Reject most | 53% false discoveries | Core 5-6 validated factors |
| Investment-EBITDA Interaction | Reject | Unreplicated; overfitting risk | CMA/asset growth overlay + profitability gate |
