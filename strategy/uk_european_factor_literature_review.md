# Literature Review: Empirical UK & European Factor Studies
## Focus: Small/Mid-Cap Equities and Extreme Return Outcomes

**Date compiled:** 2026-02-07
**Evidence labels used throughout:**
- **[DIRECT EVIDENCE]** - from specific papers with citations
- **[RELATED EVIDENCE]** - from closely related research
- **[INFERENCE]** - reasonable inference from available evidence
- **[STYLIZED FACT]** - widely accepted but hard to pin to single paper

---

## 1. Which Factors Work in UK Equities? Evidence Strength Ratings

### Summary Table

| Factor | Evidence in UK | Estimated Premium | Robustness | Key Concern |
|---|---|---|---|---|
| **Size (SMB)** | Mixed | ~2% p.a. (post-correction) | Weak post-publication | Survivorship bias, reversal post-1990s |
| **Value (HML)** | Strong | ~3-5% p.a. (long-run) | Moderate | Weakened recently; stronger in small caps |
| **Momentum (WML)** | Strong | ~0.85% per month (developed ex-US) | Strong but crash-prone | Crash risk in bear-market recoveries |
| **Profitability (RMW)** | Strong | ~3.6% p.a. (Europe) | High | Gross profitability >> ROE internationally |
| **Investment (CMA)** | Moderate | ~0.17-0.29% per month (Europe) | Moderate | Weaker than profitability; debated origins |
| **Quality (composite)** | Strong | ~4.7% p.a. (QMJ global) | High | Time-varying; outperforms in crises |

**[DIRECT EVIDENCE]** Cotter & McGeever (2018) studied nine anomalies in UK stocks from 1990-2013 and found diminished statistical significance for most anomalies over time. However, **firm profitability and stock turnover remained robust** throughout the sample period. Momentum and return reversal significance declined markedly.

**[DIRECT EVIDENCE]** Foye (2018) tested the Fama-French five-factor model in the UK and found that a respecified model using **gross profit rather than operating profit** provides an improved description of UK equity returns, though neither the value nor investment premiums were consistently priced across different test portfolios.

**[DIRECT EVIDENCE]** Gregory, Tharyan & Christidis (2013) constructed UK-equivalent Fama-French and Carhart factors, providing the foundational UK factor dataset hosted at the University of Exeter Xfi Centre.

---

## 2. Size Premium in UK

### Does It Exist?

**[DIRECT EVIDENCE]** Vidal-Garcia & Vidal (2022), "The Size Effect on the London Stock Exchange" (SSRN): Analysed FTSE All-Share, FTSE 250, and FTSE Small Cap indices from 1990-2023. Found a size premium of **approximately 2% per annum** for FTSE 250 and FTSE Small Cap indices after partially correcting risk measurement using monthly data. Returns of smaller indices were higher but not systematically so.

**[DIRECT EVIDENCE]** Dimson, Marsh & Staunton (DMS) long-run dataset (1900-present): The UK small-cap premium has been historically significant -- **even more pronounced than in the US**. From 1926-2023, US small caps outperformed larger caps by 2.1% p.a., compounding to 9.7x terminal value difference. The UK premium was documented as even larger historically.

**[DIRECT EVIDENCE]** UK small caps outperformed in 78% of 10-year rolling periods and 99% of 30-year rolling periods since January 1955 (DMS Yearbook data).

### Post-Publication Reversal

**[DIRECT EVIDENCE]** Dimson & Marsh (1999), "Murphy's Law and Market Anomalies," *Journal of Portfolio Management*: After the UK size premium was documented and disseminated, **the historical small-cap premium of ~6% was replaced by a small-cap discount of approximately 6%**. This is one of the starkest examples of anomaly reversal post-publication in the academic literature.

**[DIRECT EVIDENCE]** The small cap premium reversed in international markets during the 1990s (DMS Yearbook). Despite this, DMS conclude they "can see no case for underweighting smaller companies" given the long-run evidence.

### Survivorship Bias Issues

**[DIRECT EVIDENCE]** DMS chose their indexes specifically to **avoid survivorship bias**, with all returns including reinvested income. They showed that some historical indexes overstate long-term performance because they are contaminated by survivorship bias, and that long-term stock returns in most countries are seriously overestimated due to a focus on periods known with hindsight to have been successful.

**[RELATED EVIDENCE]** Failing to account for delisted stocks can overstate returns by 1-4% annually. CRSP data shows annualised returns of 7.4% in survivorship-free datasets versus 9.0% in survivorship-biased ones (1926-2001), a 1.6% gap. This is especially relevant for AIM, where high attrition rates amplify delisting bias.

**[INFERENCE]** Given AIM's shrinkage from ~1,694 companies (2007 peak) to just 679 (2025), any backtest of UK small-cap strategies that fails to include delisted companies will materially overstate returns.

---

## 3. Momentum in UK

### Strength of Evidence

**[DIRECT EVIDENCE]** Liu, Strong & Xu (1999), "The Profitability of Momentum Investing," *Journal of Business Finance & Accounting*: Demonstrated momentum profits using weekly UK stock prices over January 1977 to December 1996. Controlling for systematic risk, size, price, book-to-market ratio, or cash earnings-to-price ratio did not eliminate momentum profits. Concluded the momentum effect derives from **market underreaction to firm-specific information**.

**[DIRECT EVIDENCE]** Hon & Tonks (2003), "Momentum in the UK Stock Market," *Journal of Multinational Financial Management*: Using the largest set of individual UK securities examined to date (1955-96), found profitable momentum strategies in the sub-sample 1977-96, consistent with Liu et al. (1999), but **momentum was not present in the earlier 1955-76 period**, implying it may not be a permanent feature of the UK market.

**[DIRECT EVIDENCE]** Asness, Moskowitz & Pedersen (2013), "Value and Momentum Everywhere": Constructed profitable momentum strategies across multiple asset classes including **UK equities** specifically. Monthly WML portfolio returns across Developed ex-USA markets averaged ~0.85% per month.

**[DIRECT EVIDENCE]** Rouwenhorst (1998) confirmed out-of-sample momentum in many European countries, with magnitudes comparable to Jegadeesh & Titman (1993) US findings.

### Crash Risk

**[DIRECT EVIDENCE]** Daniel & Moskowitz (2016), "Momentum Crashes," *Journal of Financial Economics*: 14 of the 15 worst momentum returns occurred when the past two-year market return was negative and the contemporaneous market return was positive (i.e., **bear market recoveries**). This pattern was confirmed across **US, UK, Europe, Japan**, and multiple asset classes.

The crash mechanism: past loser stocks surge during bear market recoveries due to their high betas in up-markets during bear states, creating option-like payoffs that devastate the short side of momentum strategies.

**[DIRECT EVIDENCE]** Higher ex-ante market variance is associated with more negative momentum strategy betas and lower future returns to momentum. This relationship is **statistically significant in the UK**.

**[DIRECT EVIDENCE]** A dynamic momentum strategy scaling exposure based on forecasts of mean and variance approximately **doubles the alpha and Sharpe ratio** of a static momentum strategy (Daniel & Moskowitz, 2016).

### Implementation Challenges

**[RELATED EVIDENCE]** Liu et al. (2022/2023) proposed generalised risk-adjusted momentum (GRJMOM) to mitigate the negative impact of high-volatility stocks on momentum. This approach was validated across **UK stocks**, commodities, global equity indices, and fixed income markets.

**[INFERENCE]** Momentum strategies require frequent rebalancing (3-12 month horizons), which amplifies transaction costs in illiquid UK small caps. The combination of stamp duty (0.5% on Main Market), wide bid-ask spreads on AIM, and market impact costs makes pure momentum strategies expensive to implement in the smallest UK stocks.

---

## 4. Quality / Profitability in UK

### Which Metrics Work Best?

**[DIRECT EVIDENCE]** Novy-Marx (2013), "The Other Side of Value," *Journal of Financial Economics*: **Gross profitability (gross profits-to-assets)** has roughly the same power as book-to-market in predicting cross-sectional returns. Tested in 19 developed international markets (July 1990 - October 2009) with similar results, confirming pervasiveness.

**[DIRECT EVIDENCE]** Dimensional Fund Advisors, "Dimensions of Equity Returns in Europe" (2015): Covering 15 European markets over 1982-2014, the **average annual profitability premium in Europe was 3.6%**.

**[DIRECT EVIDENCE]** Hanauer & Huber (2016): Investigated profitability measures in 49 countries (July 1989 - June 2016). Critical finding: **all profitability definitions besides ROE are robustly priced outside the US**. ROE appears weaker internationally (including Europe/UK) compared to gross profitability, operating profitability, and cash-based measures.

**[DIRECT EVIDENCE]** Novy-Marx & Medhat (2025), "Profitability Retrospective: What Have We Learned?": Profitability **subsumes all quality factors**, explaining the performance of strategies marketed as "quality" -- none of the quality factors generated significant positive alpha relative to profitability.

**[DIRECT EVIDENCE]** Fama & French (2018), "Choosing Factors": Cash-based operating profitability **dominates** their operating profitability measure.

**[DIRECT EVIDENCE]** NBIM Discussion Note (2015): Sharpe ratios of **0.7 for cash flow over assets** and **0.9 for gross profitability** were found for global unadjusted factors. Quality premiums perform particularly well in crises and underperform in booms.

### Hierarchy of Profitability Measures (Best to Worst for UK/Europe)

1. **Gross profitability (GP/Assets)** -- strongest cross-sectional predictor
2. **Cash-based operating profitability** -- dominates accrual-based measures
3. **Operating profitability** -- robust but slightly weaker than gross
4. **ROE** -- weakest internationally; marginally significant in cross-section

**[INFERENCE]** For UK small/mid-cap stock selection, gross profitability (revenue minus COGS, scaled by total assets) is the academically preferred quality metric. ROE, while widely used in industry quality indices (e.g., MSCI Quality), is the least reliable predictor of future returns outside the US.

---

## 5. Investment Discipline in UK (Asset Growth Anomaly)

**[DIRECT EVIDENCE]** Cooper, Gulen & Scallise (2008) first documented the asset growth anomaly: stocks in the highest asset-growth decile underperformed the lowest by **7.3% annually** in the US.

**[DIRECT EVIDENCE]** Papanastasopoulos (2017), *Economics Letters*: The asset growth anomaly exists in European capital markets, but is **more pronounced across loss-making firms** and significantly dampened by including profitable firms. Hedge strategy returns for loss firms were nearly **2x higher than for profit firms**. Evidence leans toward mispricing rather than risk-based explanations.

**[DIRECT EVIDENCE]** A study in *The European Journal of Finance* (2022) found the asset growth anomaly exists in Europe at the aggregate level, with evidence relatively consistent with a **risk-based explanation** at the aggregate level -- contradicting the mispricing view from Papanastasopoulos.

**[DIRECT EVIDENCE]** Fama-French CMA (Conservative Minus Aggressive) factor: Mean monthly return ranged from 0.17% to 0.29% across global and European portfolios. **Statistically significant in the Global and Europe portfolio sets.** Premium is larger in small stocks (0.37% per month) vs. large stocks (0.11% per month).

**[DIRECT EVIDENCE]** Titman, Wei & Xie (NBER Working Paper): The negative abnormal capital investment/return relation is stronger for firms with greater investment discretion (higher cash flows, lower debt ratios). This suggests aggressive capital allocators with financial flexibility are most likely to destroy value through overinvestment.

**[DIRECT EVIDENCE]** Koh (2024), *Economics Letters*: The negative relation between asset growth and future stock returns is **most pronounced in firms with both high financing constraints and high profitability**, supporting a rational (q-theory) channel.

**[INFERENCE]** For UK small/mid-cap investing, the investment discipline signal is best used as a **screening overlay** rather than a standalone factor -- avoid companies aggressively expanding assets without commensurate EBITDA growth, especially loss-making firms. The premium is stronger in small caps and interacts with profitability.

**NOTE:** The Investment-EBITDA interaction term from Yartseva (2025) has been removed from the strategy. This section documents the standalone asset growth anomaly evidence, which remains relevant as a screening overlay. The specific interaction term (requiring EBITDA growth to match asset growth) is a single-study finding with no independent replication and is treated as unvalidated.

---

## 6. UK Market Structure: AIM vs Main Market

### Market Segments

**[STYLIZED FACT]** The London Stock Exchange operates two primary equity market segments:
- **Main Market** (Premium and Standard Listing segments): Higher regulatory requirements, continuous SETS order book trading for larger stocks, stamp duty of 0.5% on transactions.
- **AIM (Alternative Investment Market)**: Launched June 1995, lighter regulation (no minimum market cap, no minimum free float), majority of stocks traded on SETSqx system, **exempt from stamp duty**.

### AIM Market Characteristics

**[DIRECT EVIDENCE]** Board, Villa & Wells (1998), LSE Financial Markets Group: A small group of AIM stocks trade frequently with minimal execution risk, but **the majority trade infrequently**, with trades often clustered around a few days. Higher market capitalisation and higher free float contribute to better liquidity. There is no "average" AIM stock -- liquidity is difficult to predict.

**[DIRECT EVIDENCE]** Stocks moving from Main Market to AIM experience a **significant increase in Amihud illiquidity and bid-ask spreads**, with a decrease in stock return volatility. Lower trading volume is attributed to fewer investors and less information flow (2021 study in *Asia-Pacific Financial Markets*).

**[DIRECT EVIDENCE]** AIM bid-ask spreads are typically **5-10x wider than FTSE 100 constituents**. It is not uncommon to see spread percentages of 20-40% during volatile periods. 80% of AIM listings use the SETSqx trading system, which lacks continuous order-book liquidity.

**[DIRECT EVIDENCE]** Gerakos, Lang & Maffett (2013): AIM-listed firms experience **greater post-IPO underperformance** than matched firms on traditionally regulated exchanges, with performance indistinguishable from US OTC Pink Sheets. Consistent with a failure of private-sector regulation.

**[DIRECT EVIDENCE]** Contrasting evidence from Khurshed, Paleari & Vismara: AIM IPO firms use the IPO as a springboard for growth **without sacrificing operating profitability** -- the first market where operating performance is not found to decline post-IPO.

### AIM Structural Decline

**[DIRECT EVIDENCE]** AIM has shrunk from ~1,694 companies at 2007 peak to just 679 companies by 2025 -- its lowest level since 2001. In 2023/24, 76 companies delisted (up 62% year-on-year). Reasons include high compliance costs (~GBP 500,000/year to maintain listing), low share price performance, and financial stress.

**[DIRECT EVIDENCE]** MiFID II paradoxically **improved** AIM research coverage (+6.3%) and liquidity, as analysts migrated from Main Market to AIM's less-populated coverage landscape, and the NOMAD system requires research production.

### Implications for Factor Investing

**[INFERENCE]** AIM stocks are the natural hunting ground for UK small-cap factor strategies, but the extreme illiquidity of the majority of AIM stocks (SETSqx-traded with wide spreads) means theoretical factor premiums are substantially eroded by implementation costs. The stamp duty exemption on AIM stocks partially offsets this, making AIM relatively more attractive for high-turnover strategies like momentum compared to Main Market small caps.

---

## 7. Extreme Returns / Multi-baggers: Academic Evidence

### Characteristics of Stocks Delivering 5x+ Returns

**[DIRECT EVIDENCE]** Yartseva (2025), "The Alchemy of Multibagger Stocks," CAFE Working Paper No. 33, Birmingham City University: Empirical analysis of **464 multibagger stocks** (10x+ returns) on major American exchanges during 2009-2024. Tested over 150 variables across 11,600 company-year observations. Key findings:

**Significant predictors of multibagger returns:**
- Small-cap size
- High value (book-to-market)
- High profitability
- High free cash flow yield
- Distinctive investment patterns linked to EBITDA growth
- Complex momentum effects with quick trend reversals
- Specific interest rate environments

**Surprisingly NON-significant:**
- Earnings growth (no predictive value under statistical scrutiny)
- Dividend policies (irrelevant)
- Debt levels (did not predict returns)
- Share buybacks, analyst coverage, Altman Z-scores (all failed statistical tests)
- R&D expense relative to free cash flow (no correlation)

**Critical finding on asset growth:** Companies that aggressively expanded assets achieved superior returns in **100% of cases** vs. conservative investors -- **but only when expansion was supported by corresponding EBITDA growth**.

**[DIRECT EVIDENCE]** Stockopedia, "Makings of a Multibagger" (UK-specific): Investigated top 10 UK stock-market winners over 10 years. Multi-bagger checklist:
- Small size: Market cap GBP 50m-350m
- Strong profitability: ROCE > 10%, operating margins growing
- Low debt: Net gearing < 30%, high free cash flow
- Moderate valuation: Forecast P/E < 15
- Strong growth: Trailing sales growth > 10%
- Price momentum: 1-year relative strength > 0%
- Low share issuance (avoid dilution)
- **Simple, scalable business models** (e.g., JD Sports, Games Workshop -- not world-changing innovation)

**[DIRECT EVIDENCE]** Chris Mayer (2018), *100 Baggers*: Studied 100x return companies 1962-2014. Median starting market cap ~$500m, median sales ~$170m. Required characteristics: ROE > 20%, sustainable competitive advantages, owner-operators with high insider ownership. Required **at least 10 years** of patient holding.

**[DIRECT EVIDENCE]** Farago & Hjalmarsson (2023), "Long-Horizon Stock Returns Are Positively Skewed," *Review of Finance*: At long horizons, multiplicative compounding induces **strong-to-extreme positive skewness** into individual stock returns. The skewness of 5-year returns can exceed 10; 30-year skewness can be in the millions. This is driven primarily by single-period volatility, making individual stocks far more skewed than aggregate markets.

The evidence describes characteristics that extreme winners tend to exhibit retrospectively, but does not establish prospective predictive power for identifying which specific stocks will deliver extreme returns. The strategy uses these characteristics as factor tilts to improve average cross-sectional returns, not as a stock-picking tool for extreme outcomes.

---

## 8. Bessembinder's Findings: Concentration of Wealth Creation

### US Evidence

**[DIRECT EVIDENCE]** Bessembinder (2018), "Do Stocks Outperform Treasury Bills?," *Journal of Financial Economics*, 129(3): 440-457.

Core findings:
- **57.4% of all US stocks** (since 1926) had lifetime buy-and-hold returns **below one-month Treasury bills**.
- The best-performing **4% of listed companies** explain the net gain for the entire US stock market since 1926.
- Just **5 firms** (Exxon Mobil, Apple, Microsoft, General Electric, IBM) account for 10% of total wealth creation (~$35 trillion as of 2016).
- Just **90 companies** (0.33% of all listed stocks) account for over half of total wealth creation.
- Only **4.0% of single-stock strategies** outperformed the value-weighted market.

**[DIRECT EVIDENCE]** Bessembinder (2023 update through 2022): US stock market enhanced shareholder wealth by $55.1 trillion (1926-2022), while 58.6% of individual stocks reduced rather than increased wealth. The concentration has **increased over time**: the number of firms explaining half of wealth creation fell from 90 (2016) to 83 (2019) to **72 (2022)**.

### Global / International Evidence

**[DIRECT EVIDENCE]** Bessembinder, Chen, Choi & Wei (2023), "Long-Term Shareholder Returns: Evidence from 64,000 Global Stocks," *Financial Analysts Journal*, 79(3): The top-performing **2.4% of firms** account for all of the $75.7 trillion in net global stock market wealth creation from 1990-2020.

**[DIRECT EVIDENCE]** Fang et al. (2021): In 57 countries (1996-2017), less than half of stocks outperform Treasury bills in all but two countries. **Average cross-country outperformance rate: 42.4%**, compared to 49.7% in the US -- indicating stock underperformance is **more prevalent internationally** (including Europe/UK).

### Mauboussin's Extension

**[DIRECT EVIDENCE]** Mauboussin, "Birth, Death, and Wealth Creation" (Morgan Stanley Counterpoint Global): Nearly **60% of companies failed to create value**, and just **2% created 90% of aggregate wealth**. Suggests two strategies: broad diversification or concentrated ownership of massive wealth creators.

**[INFERENCE]** For UK-focused investors, the Bessembinder/Mauboussin findings imply that: (a) most UK stocks will underperform gilts over their lifetimes; (b) a tiny fraction of UK stocks will drive almost all net returns; (c) concentrated stock-picking has very poor base-rate odds of success unless the investor has genuine skill in identifying the 2-4% of wealth creators; (d) factor-based strategies that systematically tilt toward profitability, quality, and momentum may help identify stocks more likely to be in the wealth-creating tail.

---

## 9. Implementation Challenges for UK Small Caps

### Transaction Costs

**[DIRECT EVIDENCE]** UK stamp duty is 0.5% on all Main Market share purchases. This is **unique among major financial centres** -- the US, Germany, and Netherlands do not impose equivalent taxes. AIM shares are **exempt** from stamp duty.

**[DIRECT EVIDENCE]** A pension fund allocating GBP 10 million to UK equities incurs GBP 50,000 in stamp duty before any return. With multiple rebalancings per year, cumulative costs become substantial.

**[DIRECT EVIDENCE]** AIM bid-ask spreads of 5-10x FTSE 100 levels, with potential for 20-40% spreads during volatility. This creates round-trip transaction costs (buy + sell) that can consume several years of expected factor premiums in the smallest stocks.

### Liquidity Constraints

**[DIRECT EVIDENCE]** For the majority of AIM stocks, immediacy risk is a significant concern -- trades are often clustered around a few days, with 80% of stocks on the SETSqx system (no continuous order book).

**[RELATED EVIDENCE]** Factor strategies with high turnover (momentum) face severe scaling constraints in UK small caps. A fund with significant AUM trading less-liquid small-value securities could take quarters or years to build positions at 2% of ADV.

**[DIRECT EVIDENCE]** FTSE SmallCap index constituents have declined 30% over 5 years, with available market cap dropping ~50%. Total outflows from UK smaller company funds totalled approximately GBP 4 billion over two years (22% of fund assets).

### Market Impact and Off-Market Trading

**[DIRECT EVIDENCE]** Stamp duty has driven a considerable and growing level of London trading **off-market and through swaps**, meaning trading volumes are regularly understated. Many funds base investment decisions on data that is consequently flawed.

### UK De-equitisation

**[DIRECT EVIDENCE]** There has been a 20% reduction in the number of listed UK companies over 5 years, combined with lower liquidity. The outflow of money from UK funds has been relentless, depressing valuations, accelerating M&A, and resulting in a dearth of IPOs.

**[INFERENCE]** The combination of stamp duty (Main Market), wide spreads (AIM), declining number of listed companies, persistent fund outflows, and off-market trading creates a challenging environment for implementing factor strategies in UK small caps. Strategies must be designed with realistic transaction cost assumptions, potentially targeting AIM stocks (stamp duty exempt) while managing the wider spread costs through patient execution.

---

## 10. Key Researchers in UK Factor Investing

### Foundational UK Factor Researchers

| Researcher | Affiliation | Key Contribution |
|---|---|---|
| **Elroy Dimson** | Cambridge Judge Business School (formerly LBS) | DMS database; long-run UK equity/size premium; survivorship bias |
| **Paul Marsh** | London Business School | DMS database; UK size effect; Murphy's Law anomaly reversal |
| **Mike Staunton** | London Business School | DMS database; Global Investment Returns Yearbook |
| **Alan Gregory** | University of Exeter (Xfi Centre) | UK Fama-French & Carhart factor construction; contrarian strategies |
| **Rajesh Tharyan** | University of Exeter | UK factor data archive (UK Data Service); FF factors for UK |
| **Angela Christidis** | University of Exeter | UK factor construction (with Gregory & Tharyan) |

### Key Contributors to UK/European Factor Evidence

| Researcher | Affiliation | Key Contribution |
|---|---|---|
| **John Cotter** | University College Dublin | Anomaly persistence/disappearance in UK stocks |
| **Niall McGeever** | UCD / Central Bank of Ireland | UK anomaly attenuation evidence |
| **James Foye** | (various) | Five-factor model testing in UK; gross profitability respecification |
| **Mark Hon** | (UK academia) | Momentum in UK stock market 1955-96 |
| **Ian Tonks** | University of Bath (formerly Bristol) | UK momentum; fund performance |
| **Weimin Liu** | (UK academia) | UK momentum profitability 1977-96 |
| **Norman Strong** | University of Manchester | UK momentum; profitability of momentum investing |
| **Xinzhong Xu** | (UK academia) | UK momentum (with Liu & Strong) |

### International Researchers with Major UK/European Impact

| Researcher | Affiliation | Key Contribution |
|---|---|---|
| **Robert Novy-Marx** | University of Rochester | Gross profitability premium (tested internationally incl. UK) |
| **Clifford Asness** | AQR Capital | Value and momentum everywhere (incl. UK equities) |
| **Tobias Moskowitz** | Yale/AQR | Momentum crashes (confirmed in UK) |
| **Kent Daniel** | Columbia/NBER | Momentum crashes (confirmed in UK) |
| **Hendrik Bessembinder** | Arizona State University | Wealth creation concentration (global extension) |
| **Eugene Fama** | University of Chicago | Five-factor model (international tests incl. Europe) |
| **Kenneth French** | Dartmouth | Five-factor model (international tests incl. Europe) |
| **K. Geert Rouwenhorst** | Yale | International momentum (European evidence) |
| **Sheridan Titman** | University of Texas | Capital investment/return relation; momentum (with Jegadeesh) |
| **Michael Mauboussin** | Morgan Stanley | Base rates; birth/death/wealth creation |

---

## Appendix A: Key Paper Citations

### Size Factor
1. Vidal-Garcia, J. & Vidal, M. (2022). "The Size Effect on the London Stock Exchange." SSRN Working Paper.
2. Dimson, E. & Marsh, P. (1999). "Murphy's Law and Market Anomalies." *Journal of Portfolio Management*, 25(2): 53-69.
3. Dimson, E., Marsh, P. & Staunton, M. (2002). *Triumph of the Optimists: 101 Years of Global Investment Returns*. Princeton University Press.
4. Dimson, E., Marsh, P. & Staunton, M. (annual). *Global Investment Returns Yearbook*. UBS/Credit Suisse.

### Momentum
5. Liu, W., Strong, N. & Xu, X. (1999). "The Profitability of Momentum Investing." *Journal of Business Finance & Accounting*, 26(9-10): 1043-1091.
6. Hon, M.T. & Tonks, I. (2003). "Momentum in the UK Stock Market." *Journal of Multinational Financial Management*, 13(1): 43-70.
7. Asness, C., Moskowitz, T. & Pedersen, L. (2013). "Value and Momentum Everywhere." *Journal of Finance*, 68(3): 929-985.
8. Daniel, K. & Moskowitz, T. (2016). "Momentum Crashes." *Journal of Financial Economics*, 122(2): 221-247.
9. Rouwenhorst, K.G. (1998). "International Momentum Strategies." *Journal of Finance*, 53(1): 267-284.

### Profitability / Quality
10. Novy-Marx, R. (2013). "The Other Side of Value: The Gross Profitability Premium." *Journal of Financial Economics*, 108(1): 1-28.
11. Novy-Marx, R. & Medhat, M. (2025). "Profitability Retrospective: What Have We Learned?" Working Paper.
12. Hanauer, M. & Huber, D. (2016). "The Profitability Factor: International Evidence." Working Paper.
13. NBIM (2015). "The Quality Factor." Discussion Note 3-15, Norges Bank Investment Management.

### Investment / Asset Growth
14. Cooper, M., Gulen, H. & Scallise, M. (2008). "Asset Growth and the Cross-Section of Stock Returns." *Journal of Finance*, 63(4): 1609-1651.
15. Papanastasopoulos, G. (2017). "Asset Growth Anomaly in Europe: Do Profits and Losses Matter?" *Economics Letters*, 156: 106-109.
16. Titman, S., Wei, K.C.J. & Xie, F. (2004). "Capital Investments and Stock Returns." NBER Working Paper 9951.

### UK Factor Models
17. Gregory, A., Tharyan, R. & Christidis, A. (2013). "Constructing and Testing Alternative Versions of the Fama-French and Carhart Models in the UK." *Journal of Business Finance & Accounting*, 40(1-2): 172-214.
18. Tharyan, R. (2018). "Fama-French Factors and Benchmark Portfolios for the UK." UK Data Archive, Colchester.
19. Foye, J. (2018). "Testing Alternative Versions of the Fama-French Five-Factor Model in the UK." *Risk Management*, 20(2): 167-183.
20. Cotter, J. & McGeever, N. (2018). "Are Equity Market Anomalies Disappearing? Evidence from the U.K." UCD Geary Institute Working Paper 201804.

### Extreme Returns / Wealth Creation
21. Bessembinder, H. (2018). "Do Stocks Outperform Treasury Bills?" *Journal of Financial Economics*, 129(3): 440-457.
22. Bessembinder, H. (2021). "Wealth Creation in the U.S. Public Stock Markets 1926 to 2019." *The Journal of Investing*.
23. Bessembinder, H., Chen, T.-F., Choi, G. & Wei, K.C.J. (2023). "Long-Term Shareholder Returns: Evidence from 64,000 Global Stocks." *Financial Analysts Journal*, 79(3).
24. Farago, A. & Hjalmarsson, E. (2023). "Long-Horizon Stock Returns Are Positively Skewed." *Review of Finance*, 27(2): 495-538.
25. Yartseva, A. (2025). "The Alchemy of Multibagger Stocks." CAFE Working Paper No. 33, Birmingham City University.
26. Mauboussin, M.J. "Birth, Death, and Wealth Creation." Morgan Stanley Counterpoint Global Insights.

### AIM Market / UK Market Structure
27. Board, J., Villa, A. & Wells, S. (1998). "Liquidity in the Alternative Investment Market." LSE Financial Markets Group.
28. Gerakos, J., Lang, M. & Maffett, M. (2013). "Post-Listing Performance and Private Regulation: The Experience of the AIM." *Journal of Accounting and Economics*.
29. Khurshed, A., Paleari, S. & Vismara, S. "The Operating and Share Price Performance of Initial Public Offerings: The UK Experience." SSRN.

---

## Appendix B: Synthesis -- Factor Interaction Model for UK Small/Mid-Cap Multi-bagger Identification

Based on the combined evidence, the following factor interaction framework emerges for identifying potential multi-baggers in UK small/mid-cap equities:

### Primary Factors (Strong Evidence)

1. **Profitability Gate** [DIRECT EVIDENCE]: Gross profitability (GP/Assets) is the single most robust factor internationally. Screens should require above-median gross profitability. This is the factor that Cotter & McGeever (2018) found remains robust even as other UK anomalies disappear.

2. **Size Selection** [DIRECT EVIDENCE]: Multi-baggers overwhelmingly start as small caps. Yartseva (2025), Mayer (2018), and Stockopedia all confirm starting market caps in the small-to-mid range (GBP 50m-500m equivalent). The Fama-French SMB premium is also larger in profitable small caps.

3. **Momentum Confirmation** [DIRECT EVIDENCE]: Price momentum (12-1 month) is a robust cross-sectional predictor in UK equities, but must be managed for crash risk. Use as a timing/confirmation signal rather than primary selection criterion.

### Secondary Factors (Moderate Evidence)

4. **Investment Discipline** [DIRECT EVIDENCE]: The standalone asset growth anomaly exists in Europe (Papanastasopoulos 2017). Avoid companies with aggressive asset growth, especially loss-making firms. The Yartseva-specific EBITDA interaction term has been removed from the strategy due to lack of replication.

5. **Valuation Floor** [RELATED EVIDENCE]: Moderate valuations (P/E < 15-20x) at entry improve multi-bagger odds. Extreme cheapness (deep value) is less important than reasonable price combined with quality.

### Screening Overlays

6. **Low Dilution** [RELATED EVIDENCE]: Avoid companies with excessive share issuance (net equity issuance anomaly documented in UK by Cotter & McGeever).

7. **Insider Ownership** [RELATED EVIDENCE]: Owner-operators with significant stakes (Mayer, 2018).

8. **Scalable Business Model** [RELATED EVIDENCE]: Simple, replicable models that can scale (Stockopedia UK evidence; Mauboussin intangible asset scalability).

### Risk Management

9. **Momentum Crash Protection**: Scale momentum exposure based on market variance forecasts (Daniel & Moskowitz, 2016). Reduce exposure when trailing 2-year market return is negative and volatility is elevated.

10. **Liquidity Floor**: Minimum daily traded value threshold to ensure implementability. Avoid the least liquid AIM stocks where 20-40% spreads would consume factor premiums.

11. **Diversification Insurance**: Given Bessembinder's finding that only 2-4% of stocks create net wealth, any concentrated strategy carries extreme selection risk. Maintain sufficient diversification (25-35 positions) to have meaningful probability of owning wealth creators.
