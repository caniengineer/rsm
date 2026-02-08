# UK Small-Cap Quality-Value-Momentum Factor Strategy: Design Plan

**Date:** 2026-02-07
**Revised:** Post-audit, incorporating all improvements from independent strategy review
**Evidence labels used throughout:**
- **[DATA SUPPORTS]** -- Directly from academic evidence with specific citations
- **[REASONABLE ASSUMPTION]** -- Logical extension of validated evidence
- **[SPECULATIVE]** -- Going beyond what evidence supports; flagged honestly

---

## 1. Strategy Overview

This strategy systematically tilts a UK small-cap portfolio toward the factor characteristics that academic research has shown to predict above-average cross-sectional returns: high gross profitability, strong free cash flow generation, moderate valuation, and positive price momentum. The approach is grounded in validated findings from Novy-Marx (2013), Bermejo et al. (2021), Harvey, Liu & Zhu (2016), Asness et al. (2013), and Bessembinder (2018), adapted for the structural realities of UK equity markets.

**[DATA SUPPORTS]** The strategy addresses a statistical reality: 57.4% of all stocks underperform Treasury bills over their lifetimes, and only 2-4% of stocks drive virtually all net market wealth creation (Bessembinder 2018, 2023). The only empirically validated way to improve those odds is to systematically tilt toward the factor characteristics that the wealth-creating minority disproportionately exhibits — high profitability, reasonable valuation, and positive price trends — while maintaining sufficient diversification to have a meaningful probability of owning the rare winners.

**What this strategy is:** A quality-value-momentum factor tilt that maximises exposure to the population from which extreme winners emerge. Its edge, if it has one, comes from (a) avoiding the 57% of stocks that destroy wealth via profitability and FCF gates, (b) harvesting documented factor premiums (estimated 0-1% net annually in base case), and (c) providing diversified small-cap exposure that gives incidental exposure to potential compounders through portfolio breadth, not selection skill.

**What this strategy is not:** A stock-picking system that can identify which specific stocks will deliver extreme returns. The evidence base predicts average cross-sectional factor returns, not which individual stocks will be in the right tail of the return distribution.

**[REASONABLE ASSUMPTION]** The UK market is smaller and less liquid than the US, with different sector composition (less technology, more resources and financials), a declining number of listed companies, and UK-specific frictions: 0.5% stamp duty on Main Market transactions, AIM spreads that are 5-10x wider than FTSE 100, and persistent fund outflows from UK equities. These constraints are embedded into every design decision below.

---

## 2. Universe Definition

### 2.1 Eligible Securities

**Market:** London Stock Exchange -- both Main Market (Premium and Standard segments) and AIM.

**Market capitalisation range:** GBP 50m to GBP 1,000m at time of entry.
- **Lower bound (GBP 50m):** Below this level, AIM stocks become severely illiquid with spreads of 5-10% or more (Board, Villa & Wells 1998). Data quality also degrades materially for the smallest stocks. **[DATA SUPPORTS]**
- **Upper bound (GBP 1,000m):** Captures the small-cap universe where factor premia are largest (Fama-French SMB premium is 0.37% per month in small stocks vs 0.11% in large stocks). Stocks are permitted to grow beyond this threshold after purchase.

**Liquidity filters:**
- Minimum median daily traded value: GBP 50,000 over the trailing 60 trading days. **[REASONABLE ASSUMPTION]** This ensures positions of GBP 3,000-4,000 (typical for a GBP 100,000 portfolio with 25-35 positions) can be built within 1-2 trading days without exceeding 10% of daily volume.
- Maximum bid-ask spread: 3% median over trailing 20 trading days. **[REASONABLE ASSUMPTION]** A 5% round-trip spread alone consumes approximately 2 years of expected factor premium. The tighter 3% cap reduces the upper bound of cost drag.
- Minimum free float: 25%.
- Minimum trading history: 3 years of continuous listing and financial reporting.

**AIM exposure cap:** Maximum 60% of portfolio value in AIM-listed stocks. **[REASONABLE ASSUMPTION]** While AIM's stamp duty exemption makes it attractive for higher-turnover strategies, excessive AIM concentration creates aggregate liquidity risk. Main Market stocks offer superior liquidity and data quality.

**Exclusions:**
- Financial companies (banks, insurance, REITs, investment trusts) -- balance sheet structures make gross profitability and free cash flow metrics non-comparable. **[DATA SUPPORTS]** Fama-French factor models standardly exclude financials.
- Companies in administration, receivership, or with going-concern qualifications.
- Shell companies, SPACs, and companies with less than 3 full years of trading history.
- Companies with negative revenue in the most recent fiscal year.

### 2.2 Universe Size Estimate

**[REASONABLE ASSUMPTION]** Based on current UK market structure:
- Total Main Market + AIM companies: approximately 1,800
- After market cap range (GBP 50m-1,000m): approximately 500-700 companies
- After liquidity filters (minimum traded value, maximum spread): approximately 300-450 companies
- After exclusions (financials, shells, pre-revenue, minimum history): approximately 200-350 companies

This universe will shrink during bear markets and the ongoing UK de-equitisation trend (20% fewer listed companies in 5 years) is a structural headwind. **[DATA SUPPORTS]**

---

## 3. Factor Selection and Justification

### 3.1 Primary Factors (Must-Have Gates)

These factors have the strongest empirical support (t-statistics > 3.0, multiple independent replications) and must all be present for a stock to enter the portfolio.

#### Factor 1: Gross Profitability (GP/Assets) — Weight: 30%

- **Academic sources:** Novy-Marx (2013) — tested in 19 developed international markets. Bermejo et al. (2021) — FF3 alpha of 4.23% in Europe (t=10.88). Cotter & McGeever (2018) — remains robust in UK when other anomalies decay. Foye (2018) — confirmed that gross profitability provides the best description of UK equity returns. Novy-Marx & Medhat (2025) — profitability subsumes all quality factors.
- **Measurement formula:** (Revenue - Cost of Goods Sold) / Total Assets.
- **Threshold:** Above the 40th percentile of the eligible universe.
- **Evidence strength:** Very strong. The most robust profitability metric internationally. The single factor most resistant to post-publication decay in the UK. Receives the highest weight in the strategy because it has the deepest and widest evidence base.

#### Factor 2: Free Cash Flow Yield (FCF/P) — Weight: 20%

- **Academic sources:** Fama & French (2018) — cash-based operating profitability dominates accrual measures. Yartseva (2025) — identifies FCF yield as a strong predictor (coefficient 46-82), though from a single US study with survivorship bias. NBIM (2015) — Sharpe ratio of 0.7 for cash flow over assets globally.
- **Measurement formula:** Free Cash Flow / Market Capitalisation, where FCF = Operating Cash Flow - Capital Expenditures (trailing twelve months).
- **Threshold:** Top 50% of the eligible universe (positive FCF required as a hard gate).
- **Evidence strength:** Strong for cash-based profitability as a general predictor. The specific calibration from Yartseva is unvalidated in UK markets, hence the reduced weight (20% vs the original 30%).

#### Factor 3: Valuation (EV/EBITDA) — Weight: 20%

- **Academic sources:** Bermejo et al. (2021) — EV/EBITDA is the strongest European value metric. Harvey, Liu & Zhu (2016) — Value (HML) survives the 0.1% significance threshold. Dimson, Marsh & Staunton — long-run UK value premium of 3-5% p.a.
- **Measurement formula:** Enterprise Value / EBITDA, where EV = Market Cap + Total Debt - Cash.
- **Threshold:** EV/EBITDA below the 60th percentile of the eligible universe.
- **Evidence strength:** Strong. Value is one of the two factors surviving the most stringent multiple-testing corrections (Harvey et al. 2016). Multiple independent replications across geographies and decades.

### 3.2 Secondary Factors (Scoring Enhancement)

#### Factor 4: Price Momentum (12-1 month) — Weight: 20%

- **Academic sources:** Bermejo et al. (2021) — strongest pure factor in Europe (Sharpe 0.80, t=2.62). Liu, Strong & Xu (1999) — confirmed in UK equities 1977-1996. Asness, Moskowitz & Pedersen (2013) — documented in UK specifically. Harvey, Liu & Zhu (2016) — survives 0.1% threshold.
- **Measurement formula:** Total return over prior 12 months excluding the most recent month (standard Jegadeesh-Titman measure).
- **Threshold:** Positive 12-1 month return (above zero) used as confirmation signal.
- **Evidence strength:** Strong as a standalone factor, but with caveats. Hon & Tonks (2003) found momentum was absent in UK data 1955-1976. Daniel & Moskowitz (2016) documented severe crash risk in bear market recoveries. Applied as a scoring factor rather than hard gate to avoid excluding stocks in temporary drawdowns.

#### Factor 5: Small Cap Size — Weight: 10%

- **Academic sources:** Descriptive evidence that extreme winners start small (Yartseva 2025 median $348m; Stockopedia UK GBP 50-350m; Mayer 2018 median $500m).
- **Measurement:** Market capitalisation at screening. Within the eligible universe, smaller stocks receive higher scores.
- **Evidence strength:** Mixed as a return factor. **[DATA SUPPORTS]** The UK size premium reversed post-publication (Dimson & Marsh 1999). Used as a universe definition and minor scoring tilt, not as a primary return driver. Factor premia are larger in small caps (Fama-French SMB 0.37%/month in small vs 0.11% in large), which is the actual justification.

### 3.3 Screening Overlays (Binary Pass/Fail)

#### Overlay A: Low Share Dilution
- Net shares outstanding growth over trailing 12 months must be less than 5%.
- **Source:** Cotter & McGeever (2018) — net equity issuance anomaly documented in UK.

#### Overlay B: Minimum Revenue Trajectory
- Trailing 12-month revenue growth > 0%.

#### Overlay C: Avoid Excessive Leverage
- Net Debt / EBITDA < 4x. A loose survival filter, not a scoring factor.

---

## 4. Factor Combination Logic

### 4.1 Iterative Filtering Approach (Bermejo-inspired)

**Step 1: Universe Construction**
- Apply all universe filters from Section 2.
- Expected output: 200-350 stocks.

**Step 2: Profitability Gate**
- Require Gross Profitability (GP/Assets) above the 40th percentile.
- **[DATA SUPPORTS]** Cotter & McGeever (2018) found profitability is the most robust anomaly in UK equities.
- Expected output: approximately 120-210 stocks.

**Step 3: Cash Flow Gate**
- Require positive Free Cash Flow over trailing 12 months.
- AND require FCF Yield above the 50th percentile of the post-Step 2 universe.
- Expected output: approximately 60-105 stocks.

**Step 4: Valuation Filter**
- Require EV/EBITDA below the 70th percentile of the post-Step 3 universe.
- Expected output: approximately 40-75 stocks.

**Step 5: Composite Scoring**
- Score remaining stocks and rank. Select top 25-35 for the portfolio.

### 4.2 Composite Scoring

| Factor | Weight | Justification |
|---|---|---|
| Gross Profitability (rank within survivors) | 30% | Most robust international factor (Novy-Marx 2013, Bermejo 2021, Foye 2018) |
| FCF Yield (rank within survivors) | 20% | Cash-based profitability (Fama & French 2018); reduced from 30% due to unvalidated UK calibration |
| EV/EBITDA (cheaper = higher score) | 20% | Strongest European value metric (Bermejo 2021); survives Harvey et al. 0.1% threshold |
| Momentum (12-1 month return) | 20% | Strongest European pure factor (Bermejo 2021); confirmed in UK (Liu et al. 1999) |
| Size (smaller = higher score) | 10% | Universe filter; factor premia larger in small caps |

**Penalty adjustments:**
- Negative 12-1 month momentum: -10 points.
- Net shares outstanding growth > 5%: -10 points.

### 4.3 AND vs OR Logic

**Hard AND conditions (ALL must be met):**
1. Universe eligibility (market cap, liquidity, exclusions) -- AND
2. Gross Profitability above 40th percentile -- AND
3. Positive free cash flow over trailing 12 months -- AND
4. FCF Yield above 50th percentile of post-profitability universe -- AND
5. EV/EBITDA below 70th percentile of post-FCF universe

**Soft OR conditions (enhance score but not required):**
- Positive momentum (12-1 month > 0%) -- enhances score but not a hard gate, to avoid excluding stocks in temporary drawdowns.
- Small size (< GBP 200m) -- enhances score but larger companies can qualify.

---

## 5. Portfolio Construction

### 5.1 Two-Sleeve Architecture

The portfolio uses two distinct sleeves to resolve the tension between systematic factor harvesting (which requires regular rebalancing) and patient compounding (which requires holding winners indefinitely).

#### Factor Sleeve (60-70% of portfolio)

- **Positions:** 15-20 holdings.
- **Purpose:** Harvest factor premiums via quality-value-momentum tilt.
- **Rebalancing:** Semi-annual (June and December), systematic.
- **Turnover budget:** 25-35% annual one-way turnover.

#### Compounding Sleeve (30-40% of portfolio)

- **Positions:** 5-10 holdings, graduated from the Factor Sleeve.
- **Purpose:** Allow winners to compound without being sold due to valuation expansion or composite score changes.
- **Rebalancing:** None. Held indefinitely. Sold only on hard fundamental triggers (Section 7.2).

#### Graduation Criteria (Factor Sleeve -> Compounding Sleeve)

A stock graduates when ALL of the following are met:
1. Has delivered 50%+ total return since entry
2. Still passes the profitability gate (GP/Assets > 40th percentile)
3. Still FCF-positive (trailing 12 months)
4. Revenue growing year-over-year
5. No material dilution (net shares outstanding growth < 5%)

Once graduated, the stock is removed from composite score rebalancing.

### 5.2 Total Portfolio Size

**Target: 25-35 positions total** (Factor Sleeve + Compounding Sleeve).

**[DATA SUPPORTS]** Academic justification:
- Small-cap portfolios show much greater volatility reduction going from 10 to 40 stocks compared to large-cap portfolios (CFA Institute research, 2021). Peak diversification for small caps is approximately 26-50 positions.
- Bessembinder (2018) showed only 4% of stocks are wealth creators. With 30 positions and a factor-enriched hit rate of approximately 10-15%, the probability of holding at least one extreme winner is approximately 96-99%.
- **[REASONABLE ASSUMPTION]** The 3x improvement in hit rate from factor screening is an assumption, not a measured quantity.

### 5.3 Position Sizing

**Primary approach: Modified equal weight.**
- Base allocation: Equal weight across all holdings.
- Composite score tilt: Top-scoring third receives a 25% weight increase; bottom-scoring third receives a 25% weight decrease.
- Maximum position size at entry: 7% of portfolio value.
- Maximum position size during holding (after appreciation): 15% of portfolio value. Beyond this, trim to 12%.

### 5.4 Sector Constraints

**Maximum sector weight: 30% at time of rebalancing.** Prevents unintended sector concentration.

---

## 6. Holding Period and Rebalancing

### 6.1 Factor Sleeve Rebalancing

**Frequency: Semi-annual (June and December), with quarterly monitoring.**

- **Full rebalance (June and December):** Re-screen the entire universe, recalculate composite scores, and make portfolio adjustments. Aligns with UK reporting cycles.
- **Quarterly monitoring (March and September):** Review existing holdings for sell triggers. New positions generally NOT added during quarterly reviews.
- **Ad hoc review:** Triggered by profit warnings, material insider selling (>10% of holding), or suspension of trading.

### 6.2 Compounding Sleeve

**No scheduled rebalancing.** Holdings are reviewed at quarterly monitoring dates for sell triggers only (Section 7.2). No composite score recalculation.

### 6.3 Transaction Cost Budget

**[REASONABLE ASSUMPTION]** At 25-35% annual one-way turnover:
- AIM stocks: ~0% stamp duty + ~2-3% average spread cost per round trip = ~0.5-1.0% annual drag.
- Main Market stocks: ~0.5% stamp duty + ~0.5-1.0% spread cost per round trip = ~0.3-0.5% annual drag.
- **Total estimated annual transaction cost drag: 0.5-1.5% of portfolio value.**

**Hard rule:** If total all-in costs exceed **2% of portfolio value** in any calendar year, reduce turnover in the Factor Sleeve immediately (extend rebalancing to annual, raise the score threshold for replacement).

---

## 7. Sell Discipline

### 7.1 Factor Sleeve Sell Rules

A position is sold when ANY of these triggers fires:

1. **Composite score drops to bottom 30%** of eligible universe at semi-annual rebalance.
2. **Two consecutive periods of negative FCF.**
3. **GP/Assets below 30th percentile** at rebalance.
4. **Net dilution >10% in a single year.**
5. **Position hits 15% of portfolio** -- trim to 10%.

### 7.2 Compounding Sleeve Sell Rules (Only These)

1. Three consecutive quarters of negative free cash flow.
2. GP/Assets falls below 25th percentile for two consecutive semi-annual periods.
3. Net share dilution >15% in a single fiscal year.
4. Fraud, material regulatory action, or trading suspension.
5. Acquisition at a premium (take the exit).

### 7.3 When NOT to Sell (Both Sleeves)

1. **Short-term price declines:** 20-30% drawdowns if fundamentals intact. **[DATA SUPPORTS]** Selling on price weakness alone systematically eliminates the portfolio's best future performers.
2. **Sector rotation or macro noise.**
3. **Missing a single quarterly earnings estimate.**
4. **A stock doubling in year one.** **[DATA SUPPORTS]** The positive skewness of long-horizon returns (Farago & Hjalmarsson 2023) means expected value of continuing to hold a winner is significantly higher than mean-reverting it.

---

## 8. Risk Controls

### 8.1 Portfolio-Level Controls

1. **Maximum sector exposure:** 30% at time of rebalancing.
2. **AIM exposure cap:** 60% hard cap.
3. **Cash buffer:** 3-5% at all times.
4. **No portfolio-level stop-loss.** **[DATA SUPPORTS]** Portfolio stop-losses for long-only equity strategies are empirically destructive -- they lock in losses during temporary drawdowns.

### 8.2 Position-Level Controls

1. Maximum position size at entry: 7%.
2. Trim threshold: 15%, trim to 12%.
3. No averaging down into deteriorating fundamentals.

### 8.3 Momentum Crash Protection (Daniel & Moskowitz 2016)

**[DATA SUPPORTS]** 14 of 15 worst momentum returns occurred when past two-year market return was negative and contemporaneous market return was positive.

**Implementation:**
- If trailing 24-month FTSE All-Share total return is negative (bear market), reduce momentum weight in composite scoring from 20% to 5%.
- If FTSE All-Share 60-day realised volatility is above 80th percentile of its 10-year history AND trailing 24-month return is negative, set momentum weight to 0%.

### 8.4 Cost Budget and Kill Switch

**Cost Budget:** Track all-in annual costs (bid-ask spread, commissions, stamp duty, data subscriptions) as percentage of portfolio value. If costs exceed 2%, reduce turnover immediately.

**Kill Switch — binding halt triggers:**
1. Underperforms FTSE Small Cap Index by >3% annually for 3 consecutive years (net of all costs).
2. Gross profitability premium turns negative over any rolling 5-year window in UK data.
3. All-in transaction costs exceed gross factor returns for 2 consecutive years.
4. Investable universe (post-filter) drops below 40 stocks.
5. AIM loses Business Property Relief (inheritance tax advantage).

---

## 9. Expected Performance Characteristics

### 9.1 What the Data Supports

- **Factor premiums exist in UK equities.** Gross profitability premium ~3.6% p.a. in Europe (DFA 2015). Momentum ~0.85%/month developed ex-US (Asness et al. 2013). Value ~3-5% p.a. in UK long-run data (DMS). These are gross premiums before costs and post-publication decay.
- **Post-publication decay is substantial.** McLean & Pontiff (2016): factor returns decline 26% out-of-sample and 58% post-publication. Bermejo et al. (2021) noted European factor alphas approaching zero post-2012.
- **Multi-factor strategies outperform single-factor strategies.** Bermejo et al. (2021): iterative value->profitability->momentum achieves Sharpe 0.94 (in-sample, European large caps, gross of costs).
- **Transaction costs erode premiums significantly in UK small caps.** Estimated 1.5-3% annual drag including stamp duty and AIM spreads.
- **Most stocks underperform bonds.** 57.4% of stocks have lifetime returns below T-bills (Bessembinder 2018).

### 9.2 Honest Scenario Analysis

| Scenario | Probability | Expected Net Alpha (vs FTSE Small Cap) | What Happens |
|----------|------------|----------------------------------------|--------------|
| **Bull case** | 20-30% | +2% to +4% annually | Factor premiums persist at 50%+ of historical levels; UK small caps recover from outflows; 1-2 Compounding Sleeve positions deliver 3x+ over 7 years |
| **Base case** | 40-50% | 0% to +1% annually | Approximately matches a UK small-cap quality ETF after all costs; factor premiums offset by transaction drag |
| **Bear case** | 30-40% | -1% to -3% annually | Factor decay continues; AIM shrinks further; costs exceed premiums; strategy abandoned at year 3-5 kill switch |

**Expected value:** (0.25 x 3%) + (0.45 x 0.5%) + (0.35 x -2%) = **+0.275% net alpha.**

The strategy's expected value is marginally positive but within the margin of estimation error. The case for it rests on:
1. The profitability premium being genuinely persistent (strongest evidence)
2. Avoiding catastrophic stocks (real but hard to quantify)
3. The optionality of the Compounding Sleeve (genuine but probabilistically small)

### 9.3 What Is Speculative

- **[SPECULATIVE]** Any claim of a specific expected CAGR. Factor premiums are estimated from historical data that may not repeat.
- **[SPECULATIVE]** That factor characteristics identified in US studies transfer directly to the UK market with similar magnitudes.
- **[SPECULATIVE]** The specific factor weights in the composite score. They are informed by relative evidence strength but have not been optimised on UK data.
- **[SPECULATIVE]** Whether the AIM market will continue to exist in its current form.

---

## 10. UK-Specific Validation Roadmap

Before committing real capital, the strategy must pass through four validation phases:

### Phase 1: Historical Screen (Pre-deployment, 1-2 weeks)

Apply the revised factor gates to historical UK small-cap data via Stockopedia or SharePad (even 5-10 years). Check:
- How many stocks pass each gate at each historical rebalance date?
- What sectors dominate the filtered universe?
- Does the filtered universe look sensible and diversified?
- How stable is the filtered set between rebalance dates?

### Phase 2: Dead-Stock Audit (Pre-deployment, 1-2 weeks)

For historical screen output, manually check:
- How many filtered stocks subsequently delisted involuntarily?
- How many were acquired (and at what premium/discount)?
- How many went to zero or near-zero?
- This gives a rough false-positive rate for the gates.

### Phase 3: Paper Portfolio (12 months, concurrent)

Run the full strategy in paper form for one complete annual cycle:
- Execute mock trades at real bid-ask prices.
- Track actual execution feasibility for AIM stocks.
- Measure real spreads vs the assumed 3% cap.
- Log data availability issues.
- Record time required per rebalance cycle.

### Phase 4: Survivorship-Free Backtest (If pursuing seriously)

Commission or conduct a proper backtest using:
- LSPD (London Share Price Database) or equivalent survivorship-free data.
- Minimum 15-20 year history.
- Realistic transaction costs: 1.5-3% round-trip for AIM, 1% for Main Market.
- Must show t > 2.0 net-of-cost alpha over FTSE Small Cap Index.

**Deployment gate:** Do not commit real capital until at least Phases 1-3 are complete.

---

## 11. Implementation Roadmap

### 11.1 Data Required

| Data Item | Source Options | Update Frequency | Critical? |
|---|---|---|---|
| Market capitalisation | LSE data, Yahoo Finance, SharePad, Stockopedia | Weekly | Yes |
| Revenue, COGS, Total Assets | Company reports, SharePad, Stockopedia | Semi-annual | Yes |
| Free Cash Flow (OCF - Capex) | Cash flow statements | Semi-annual | Yes |
| EV/EBITDA | Calculated or SharePad/Stockopedia | Semi-annual | Yes |
| 12-month price return | Any price data provider | Monthly | Yes |
| Bid-ask spreads | LSE market data | Monthly median | Yes |
| Daily traded value | LSE market data | 60-day rolling median | Yes |
| Shares outstanding history | Company RNS announcements | Semi-annual | Moderate |
| Net debt | Balance sheet data | Semi-annual | Moderate |
| FTSE All-Share trailing returns and volatility | Any index provider | Monthly | For risk controls |

**Cost-effective data stack:**
- **Stockopedia (~GBP 500/year):** Pre-calculated quality, value, and momentum scores.
- **SharePad (~GBP 400/year):** Comprehensive fundamental data.
- **Free alternatives:** Yahoo Finance for prices; Companies House for accounts. These require significant manual processing.

### 11.2 Common Mistakes to Avoid

1. **Backtesting without transaction costs.** Any backtest that excludes stamp duty, spreads, and market impact will overstate returns by 1-3% annually.
2. **Ignoring delisted stocks.** Survivorship bias is particularly severe for UK small caps. DMS documented 1.6% annual overstatement.
3. **Overweighting recent winners.** The modified equal-weight approach with trim threshold prevents this.
4. **Confusing narrative with data.** Execute mechanically based on quantitative criteria.
5. **Rebalancing too frequently.** Monthly rebalancing in UK small caps generates excessive costs.
6. **Applying US-derived thresholds directly.** UK market structure and liquidity differ materially.
7. **Ignoring stamp duty.** 0.5% on Main Market purchases adds ~0.15% annual drag at 30% turnover.

### 11.3 Why Most Investors Fail to Stick to It

**[DATA SUPPORTS]** The primary cause of strategy failure is the investor's inability to adhere to it:

1. **Tracking error regret.** This strategy will deviate significantly from benchmarks. Most investors abandon after 2-3 years of underperformance. **Solution:** Pre-commit to 5-year minimum evaluation horizon.
2. **Disposition effect.** Tendency to sell winners and hold losers. **Solution:** Follow explicit sell triggers.
3. **Narrative attachment.** **Solution:** Make sell decisions rule-based, not story-based.
4. **Illiquidity panic.** During crises, AIM stocks may be effectively untradeable. **Solution:** Position limits and cash buffer.
5. **Complexity fatigue.** **Solution:** Automate scoring via Stockopedia/spreadsheet.

---

## Appendix: Summary of Evidence Sources

| Source | Year | Key Finding Used | Evidence Type |
|---|---|---|---|
| Novy-Marx, "The Other Side of Value" | 2013 | Gross profitability premium; complementarity with value | [DATA SUPPORTS] |
| Bermejo et al. | 2021 | European factor performance; EV/EBITDA strongest; Sharpe 0.94 | [DATA SUPPORTS] |
| Harvey, Liu & Zhu, "...and the Cross-Section" | 2016 | Only 9/313 factors survive t>3.0; 53% false discoveries | [DATA SUPPORTS] |
| McLean & Pontiff | 2016 | Factor returns 26% lower OOS, 58% lower post-publication | [DATA SUPPORTS] |
| Asness, Moskowitz & Pedersen, "Value and Momentum Everywhere" | 2013 | Momentum confirmed in UK equities | [DATA SUPPORTS] |
| Daniel & Moskowitz, "Momentum Crashes" | 2016 | Crash mechanism and dynamic strategy | [DATA SUPPORTS] |
| Cotter & McGeever | 2018 | UK anomaly persistence; profitability robust | [DATA SUPPORTS] |
| Bessembinder, "Do Stocks Outperform Treasury Bills?" | 2018 | 57.4% underperformance; 4% wealth creators | [DATA SUPPORTS] |
| Dimson & Marsh, "Murphy's Law" | 1999 | UK size premium reversal | [DATA SUPPORTS] |
| Foye | 2018 | Gross profitability respecification for UK | [DATA SUPPORTS] |
| Fama & French, "Choosing Factors" | 2018 | Cash-based profitability dominates accruals | [DATA SUPPORTS] |
| Novy-Marx & Medhat | 2025 | Profitability subsumes all quality factors | [DATA SUPPORTS] |
| Farago & Hjalmarsson | 2023 | Positive skewness at long horizons | [DATA SUPPORTS] |
| Liu, Strong & Xu | 1999 | Momentum profits in UK equities 1977-1996 | [DATA SUPPORTS] |
| Hanauer & Huber | 2016 | ROE weakest profitability metric outside US | [DATA SUPPORTS] |
| Papanastasopoulos | 2017 | European asset growth anomaly | [DATA SUPPORTS] |
| Board, Villa & Wells | 1998 | AIM liquidity characteristics | [DATA SUPPORTS] |
| Yartseva, "Alchemy of Multibagger Stocks" | 2025 | Supporting evidence only (single study, US, unvalidated) | [SUPPORTING] |
