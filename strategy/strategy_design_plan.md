# UK Multi-Bagger Factor Strategy: Design Plan

**Date:** 2026-02-07
**Evidence labels used throughout:**
- **[DATA SUPPORTS]** -- Directly from academic evidence with specific citations
- **[REASONABLE ASSUMPTION]** -- Logical extension of validated evidence
- **[SPECULATIVE]** -- Going beyond what evidence supports; flagged honestly

---

## 1. Strategy Overview

This is a **UK small-cap quality-value-momentum factor strategy** that systematically targets cheap, profitable, trending small companies. It is not a multibagger identification system -- no factor screen can reliably predict which specific stocks will deliver 5-10x returns. Instead, the strategy increases exposure to the population from which multibaggers are drawn, while generating steady factor-driven alpha from the broader portfolio.

The strategy has two components:

1. **Core Factor Portfolio (80% of capital):** A disciplined, semi-annually rebalanced portfolio of 16-24 UK small-cap stocks selected by three well-validated factors: gross profitability (GP/Assets), valuation (EV/EBITDA), and momentum (12-1 month). This component targets 1-3% net annual alpha over a UK small-cap benchmark through systematic factor exposure. FCF yield is used as a secondary quality check.

2. **Conviction Hold Carve-out (20% of capital):** 4-6 positions drawn from the Core Portfolio that exhibit the strongest fundamentals and clearest compounding potential. Once designated as conviction holds, these positions are **exempt from factor-based rebalancing** and are held until the business thesis breaks. This is where multibagger compounding can occur -- if it occurs at all.

The approach is rooted in validated findings from Novy-Marx (2013), Bermejo et al. (2021), Asness et al. (2013), and Bessembinder (2018), with directional support from Yartseva (2025), adapted for the structural realities of UK equity markets.

**[DATA SUPPORTS]** The strategy is grounded in a statistical reality: 57.4% of all stocks underperform Treasury bills over their lifetimes, and only 2-4% of stocks drive virtually all net market wealth creation (Bessembinder 2018, 2023). This means that any stock-picking strategy faces terrible base rates. The only empirically validated way to improve those odds is to systematically tilt toward the factor characteristics that the wealth-creating minority disproportionately exhibits -- high profitability, reasonable valuation, and positive price trends -- while maintaining sufficient diversification to have a meaningful probability of owning the rare winners.

**[HONEST LIMITATION]** The UK market is smaller and less liquid than the US, with fewer extreme outcomes. The strategy must contend with UK-specific frictions: 0.5% stamp duty on Main Market transactions, AIM spreads that are 5-10x wider than FTSE 100, a declining number of listed companies, and persistent fund outflows from UK equities. No UK-specific backtest of this strategy has been conducted. The expected performance characteristics are extrapolated from US and European studies in different market segments. These constraints and evidence gaps are embedded into every design decision below.

---

## 2. Universe Definition

### 2.1 Eligible Securities

**Market:** London Stock Exchange -- both Main Market (Premium and Standard segments) and AIM.

**[DATA SUPPORTS]** Multi-baggers overwhelmingly start as small caps. Yartseva (2025) found a median starting market cap of $348m for US multibaggers. Stockopedia's UK-specific evidence identifies a starting range of GBP 50m-350m. Chris Mayer (2018) found median starting market cap of approximately $500m for 100-baggers.

**Market capitalisation range:** GBP 30m to GBP 1,000m at time of entry.
- **Lower bound (GBP 30m):** Below this level, AIM stocks become severely illiquid (Board, Villa & Wells 1998 documented that the majority of AIM stocks trade infrequently with clustered trading days). Spreads can reach 20-40% in volatile periods, which would consume multiple years of expected factor premiums. GBP 30m provides a minimal liquidity floor while still capturing the small-cap universe where multibaggers originate.
- **Upper bound (GBP 1,000m):** Allows inclusion of the upper end of the multibagger starting range. Stocks are permitted to grow beyond this threshold after purchase (this is desirable -- it means the thesis is working).

**Liquidity filters:**
- Minimum median daily traded value: GBP 25,000 over the trailing 60 trading days. **[REASONABLE ASSUMPTION]** This ensures a GBP 20,000 position (typical for a GBP 500,000-1,000,000 portfolio) can be built over 1-2 trading days without exceeding 50% of daily volume. For larger portfolios, this threshold must scale upward.
- Maximum bid-ask spread: 5% median over trailing 20 trading days. **[REASONABLE ASSUMPTION]** This eliminates the most illiquid AIM stocks where round-trip transaction costs would exceed 10%, erasing several years of expected alpha.
- Minimum free float: 25%. Stocks with lower free float have unpredictable liquidity and are susceptible to manipulation.

**Exclusions:**
- Financial companies (banks, insurance, REITs, investment trusts) -- their balance sheet structures make gross profitability and free cash flow metrics non-comparable. **[DATA SUPPORTS]** Fama-French factor models standardly exclude financials for this reason.
- Companies in administration, receivership, or with going-concern qualifications in their most recent audit.
- Shell companies, SPACs, and companies with less than 2 full years of trading history and financial reporting. **[DATA SUPPORTS]** Gerakos, Lang & Maffett (2013) showed AIM IPO firms exhibit significant post-IPO underperformance; requiring 2 years of data avoids the worst of IPO-related distortions.
- Companies with negative revenue in the most recent fiscal year (pre-revenue biotechs, exploration-stage miners with no sales).

### 2.2 Universe Size Estimate

**[REASONABLE ASSUMPTION]** Based on current UK market structure:
- Total Main Market companies: approximately 1,100
- Total AIM companies: approximately 679 (2025 figure; down from 1,694 at 2007 peak)
- After applying market cap range (GBP 30m-1,000m): approximately 600-800 companies
- After liquidity filters (minimum traded value, maximum spread): approximately 350-500 companies
- After exclusions (financials, shells, pre-revenue): approximately 250-400 companies

This universe will shrink during bear markets (lower market caps, reduced liquidity) and expand during bull markets. The declining trend in UK listings (20% reduction over 5 years) means the universe is likely to contract over time, which is a structural headwind for the strategy. **[DATA SUPPORTS]** This contraction is documented fact, not projection.

---

## 3. Factor Selection and Justification

### 3.1 Primary Factors (Must-Have)

These factors have strong empirical support across multiple independent studies, multiple markets, and multiple time periods. They are the non-negotiable quality gates.

**Note on evidence standard:** Only factors with multi-source validation (at least two independent studies, at least one including UK or European data) qualify as primary. Factors supported by a single study -- regardless of reported effect size -- are classified as secondary or excluded.

#### Factor 1: Gross Profitability (GP/Assets)

- **Academic source:** Novy-Marx (2013) -- "The Other Side of Value," tested in 19 developed international markets. Bermejo et al. (2021) found FF3 alpha of 4.23% in Europe (t=10.88). Cotter & McGeever (2018) found profitability remains robust in UK even as other anomalies decay post-publication. Hanauer & Huber (2016) confirmed in 49 countries.
- **Measurement formula:** (Revenue - Cost of Goods Sold) / Total Assets.
- **Threshold:** Above the 40th percentile of the eligible universe.
- **Evidence strength:** Very strong. The most robust profitability metric internationally; confirmed to survive in UK specifically when other anomalies vanish. Multiple independent sources, multiple markets, multiple decades.
- **Why it works:** Captures the economic engine of a business before management can obscure it through accounting choices. Complementary to value -- profitable stocks and cheap stocks are different sets of stocks (Novy-Marx 2013).

#### Factor 2: Valuation (EV/EBITDA)

- **Academic source:** Bermejo et al. (2021) -- EV/EBITDA is the strongest European value metric. Harvey, Liu & Zhu (2016) -- Value (HML) survives the 0.1% significance threshold. DMS long-run UK data: 10.8% vs 7.8% for high vs low yield over 117 years.
- **Measurement formula:** Enterprise Value / EBITDA, where Enterprise Value = Market Cap + Total Debt - Cash. Lower values indicate cheaper stocks.
- **Threshold:** EV/EBITDA below the 60th percentile of the eligible universe (not in the most expensive 40%).
- **Evidence strength:** Strong. Value is one of two factors surviving the harshest multiple-testing corrections globally. Long-run UK evidence is robust. EV/EBITDA is the strongest value metric in European data.
- **Why EV/EBITDA rather than P/E or P/B:** EV/EBITDA is capital-structure neutral and less distorted by accounting choices than P/E. It outperforms P/E, P/B, and P/CF in Bermejo et al.'s European tests.

#### Factor 3: Momentum (12-1 month)

- **Academic source:** Bermejo et al. (2021) -- strongest pure factor in Europe (Sharpe 0.80). Liu, Strong & Xu (1999) -- confirmed momentum profits in UK equities. Asness, Moskowitz & Pedersen (2013) -- momentum confirmed in UK specifically. Harvey, Liu & Zhu (2016) -- MOM survives the 0.1% significance threshold.
- **Measurement formula:** Total return over the prior 12 months excluding the most recent month (standard Jegadeesh-Titman measure).
- **Threshold:** Positive 12-1 month return (above zero). Used as a confirmation signal, not a hard ranking factor.
- **Evidence strength:** Strong across multiple studies and markets. **Important caveats:** absent in UK data before 1977 (Hon & Tonks 2003), subject to severe crash risk during bear-market recoveries (Daniel & Moskowitz 2016), and declining significance in recent UK data (Cotter & McGeever 2018).
- **Why positive-only rather than top-decile:** For a semi-annually rebalanced small-cap strategy, momentum serves primarily to avoid "falling knives" (stocks in structural decline) rather than to chase recent winners. The crash risk of aggressive momentum tilts is amplified in concentrated small-cap portfolios.

### 3.2 Secondary Factors (Enhancement)

These factors enhance scoring but are applied as tiebreakers and gradients, not hard gates. A stock can enter the portfolio without maximising on these.

#### Factor 4: Free Cash Flow Yield (FCF/P)

- **Academic source:** Fama & French (2018) -- cash-based operating profitability dominates accrual measures. Yartseva (2025) reports FCF yield as the strongest predictor in the multibagger sample (coefficient 46-82), though this is a single unreplicated US study.
- **Measurement formula:** Free Cash Flow / Market Capitalisation, where FCF = Operating Cash Flow - Capital Expenditures.
- **Threshold:** Positive FCF required (hard gate). Within positive-FCF stocks, higher FCF yield improves composite score.
- **Evidence strength:** Moderate. Cash-based profitability is well-supported broadly (Fama & French 2018). The specific claim that FCF yield predicts *extreme* returns rests on Yartseva alone. Coefficient instability (46-82 across specifications) is a concern.
- **Role in strategy:** Quality check ensuring companies generate real cash, not just accounting profits. Complements GP/Assets by capturing the cash flow dimension of profitability.

#### Factor 5: Small Cap Size (within eligible universe)

- **Academic source:** Multibaggers start small by mathematical necessity. Fama-French SMB premium is larger in profitable small caps. UK size premium reversed post-publication (Dimson & Marsh 1999).
- **Measurement:** Market capitalisation at time of screening. Within the eligible universe (GBP 30m-1,000m), smaller stocks receive a modest scoring bonus.
- **Threshold:** Scoring gradient. Stocks below GBP 200m receive the highest size score; GBP 200m-500m moderate; GBP 500m-1,000m lowest.
- **Evidence strength:** Mixed. Size is a universe filter (where to look), not a return predictor (what to buy). The raw size premium is unreliable in the UK. Within the quality-filtered universe, smaller stocks may have wider information asymmetry, but this is an assumption.

### 3.3 Factors Excluded from Core Model (Insufficient Evidence)

The following factors were considered but excluded from the scoring model due to insufficient independent validation. They may be reinstated if replicated in UK/European data.

#### Excluded: Investment-EBITDA Growth Interaction

- **Academic source:** Yartseva (2025) only. No independent replication in any market.
- **Why excluded:** Single-study finding with "100% of cases" claim that is a statistical red flag. Papanastasopoulos (2017) European evidence on asset growth anomalies contradicts the interaction pattern. The interaction term is inherently susceptible to look-ahead bias and overfitting in a 150-variable, 464-stock sample.
- **What would change this:** Independent replication in UK or European small-cap data using survivorship-free datasets.
- **Retained as heuristic:** Investors may note whether a company's asset growth is matched by earnings growth. This is good investment sense, but it should not be a scored factor in a systematic model until replicated.

#### Excluded: Contrarian Momentum (Near 52-Week Lows)

- **Academic source:** Yartseva (2025) only. Contradicts the standard momentum literature.
- **Why excluded:** Single-study finding that directly conflicts with the well-validated 12-1 momentum factor. Including both standard momentum and contrarian momentum creates logical incoherence. The contrarian signal may identify value traps rather than future multibaggers if not paired with perfect fundamental judgment.
- **What would change this:** Independent validation of contrarian momentum as a predictor of extreme positive returns in a multi-market study.

#### Excluded: Interest Rate Regime Overlay

- **Academic source:** Yartseva (2025) -- rising rates reduce multibagger returns by 8-12pp. US-specific finding using Federal Funds Rate.
- **Why excluded:** Single-study finding. Bank of England transmission mechanism differs from the Fed. Regime-dependent factor timing is notoriously unreliable and adds complexity without proven benefit. The strategy should work across rate environments or not at all.

### 3.4 Screening Overlays

These are binary pass/fail screens applied after factor scoring to eliminate stocks with specific red flags. They are informed by evidence but serve primarily as risk management.

#### Overlay A: Low Share Dilution

- **Source:** Cotter & McGeever (2018) -- net equity issuance anomaly documented in UK. Stockopedia UK multibagger checklist identifies low share issuance as a criterion.
- **Screen:** Net shares outstanding growth over trailing 12 months must be less than 5%. Companies issuing large amounts of equity are diluting existing shareholders and often doing so to fund unprofitable growth.
- **Evidence strength:** Moderate. Well-documented anomaly but secondary to the primary factors.

#### Overlay B: Minimum Revenue Trajectory

- **Source:** Stockopedia UK -- trailing sales growth > 10% identified as multibagger characteristic. Yartseva (2025) -- profitability and growth interaction matters.
- **Screen:** Trailing 12-month revenue growth > 0% (positive, not necessarily >10%). **[REASONABLE ASSUMPTION]** The 10% threshold from Stockopedia is from a small sample of top winners. Requiring simply positive revenue growth eliminates declining businesses without being so restrictive that the universe becomes too small.
- **Evidence strength:** Moderate. Revenue growth is supportive evidence rather than a primary predictor. Notably, Yartseva found earnings growth has NO predictive value under statistical scrutiny -- but revenue growth was not specifically tested.

#### Overlay C: Avoid Excessive Leverage

- **Source:** Stockopedia UK -- net gearing < 30% identified for multibaggers. However, Yartseva (2025) found debt levels were NOT statistically significant predictors of multibagger returns.
- **Screen:** Net Debt / EBITDA < 4x. This is a loose constraint, not a strict low-debt requirement. **[REASONABLE ASSUMPTION]** The screen exists to avoid companies at risk of financial distress (which would prevent them from compounding returns over 5-7 years), not because low debt itself predicts multibagger returns.
- **Evidence strength:** Weak as a direct predictor. Strong as a survival filter (companies that go bankrupt cannot be multibaggers).

---

## 4. Factor Combination Logic

### 4.1 Iterative Filtering Approach (Bermejo-inspired)

This is the primary implementation methodology. It applies sequential hard filters to narrow the universe, then scores the survivors.

**Step 1: Universe Construction**
- Apply all universe filters from Section 2 (market cap, liquidity, exclusions).
- Expected output: 250-400 stocks.

**Step 2: Profitability Gate**
- Require Gross Profitability (GP/Assets) in the top 60% of the universe (above the 40th percentile).
- Rationale: **[DATA SUPPORTS]** Cotter & McGeever (2018) found profitability is the most robust anomaly in UK equities. This gate eliminates the least profitable companies, where the asset growth anomaly is most dangerous (Papanastasopoulos 2017).
- Expected output: approximately 150-240 stocks.

**Step 3: Cash Flow Gate**
- Require positive Free Cash Flow (Operating Cash Flow > Capital Expenditures) over the trailing 12 months.
- AND require FCF Yield (FCF/Market Cap) in the top 50% of the post-Step 2 universe.
- Rationale: **[DATA SUPPORTS]** Yartseva (2025) identifies FCF yield as the strongest single predictor. Requiring positive FCF eliminates cash-burning companies that may show accounting profits but are not generating real cash.
- Expected output: approximately 75-120 stocks.

**Step 4: Valuation Filter**
- Require EV/EBITDA below the 70th percentile of the post-Step 3 universe (i.e., not in the most expensive 30%).
- Rationale: **[DATA SUPPORTS]** Yartseva's non-linear value effect shows the biggest penalty comes from being expensive, not from failing to be extremely cheap. This filter removes overvalued stocks without demanding deep value.
- Expected output: approximately 50-85 stocks.

**Step 5: Composite Scoring**
- Score remaining stocks on secondary factors (Section 4.2 below) and rank.
- Select top 20-30 stocks for the portfolio.

### 4.2 Composite Scoring

For the composite score applied in Step 5, each surviving stock receives a score from 0-100 based on:

| Factor | Weight | Justification |
|---|---|---|
| Gross Profitability (GP/Assets rank) | 30% | Most robust international factor; survives UK post-publication decay (Novy-Marx 2013, Cotter & McGeever 2018) |
| EV/EBITDA (cheaper = higher score) | 25% | Strongest European value metric (Bermejo 2021); survives harshest multiple-testing (Harvey et al. 2016) |
| Momentum (12-1 month return) | 20% | Strongest pure European factor (Bermejo 2021); confirmed in UK (Liu et al. 1999) |
| FCF Yield (rank within survivors) | 15% | Cash-based quality check (Fama & French 2018); directional support from Yartseva (2025) |
| Size (smaller = higher score) | 10% | Modest tilt toward smaller companies where information asymmetry is wider |

**Weight justification:** Weights reflect the strength and breadth of evidence, not reported effect sizes from any single study. Gross profitability receives the highest weight because it has the broadest validation (19+ countries, multiple decades, UK-specific persistence). Value receives the second-highest weight because HML is one of two factors surviving the most extreme multiple-testing corrections. Momentum receives moderate weight because of crash risk and declining UK significance. FCF yield is secondary because its specific link to extreme returns rests on a single unreplicated study. Size receives the lowest weight because the raw size premium has reversed in the UK.

**Penalty adjustments:**
- Negative 12-1 month momentum: -10 points.
- Net shares outstanding growth > 5%: -10 points.
- Negative free cash flow: excluded at Step 3 (hard gate), so this should not arise.

### 4.3 AND vs OR Logic

**Hard AND conditions (ALL must be met for inclusion):**
1. Universe eligibility (market cap, liquidity, exclusions) -- AND
2. Gross Profitability above 40th percentile of universe -- AND
3. Positive free cash flow over trailing 12 months -- AND
4. FCF Yield above 50th percentile of post-profitability universe -- AND
5. EV/EBITDA below 70th percentile of post-FCF universe

**[DATA SUPPORTS]** The AND logic on profitability and cash flow is justified by Novy-Marx's finding that gross profitability has roughly the same predictive power as book-to-market, and Yartseva's finding that FCF yield is the strongest single predictor. These are non-negotiable quality gates.

**Soft OR conditions (enhance score but not required):**
- Positive momentum (12-1 month > 0%) -- enhances score but a stock with negative momentum can still enter the portfolio if it scores very highly on fundamentals. **[DATA SUPPORTS]** Yartseva found momentum has a contrarian element for multibaggers -- some future multibaggers are in temporary drawdowns. Requiring positive momentum as a hard gate would exclude potential winners in recovery phases.
- Productive investment growth (EBITDA growth >= asset growth) -- enhances score but not required. **[REASONABLE ASSUMPTION]** Some excellent companies may have stable asset bases with minimal growth, still generating excellent FCF. Requiring positive asset growth would exclude these.
- Small size (< GBP 200m) -- enhances score but larger companies in the range can still qualify.

---

## 5. Portfolio Construction

### 5.1 Two-Tier Portfolio Structure

The portfolio is split into two tiers with different management rules, resolving the tension between systematic factor rebalancing and patient compounding.

#### Tier 1: Core Factor Portfolio (80% of capital, 16-24 positions)

This is a standard semi-annually rebalanced factor portfolio. Positions are selected by composite score and managed mechanically. Average holding period is approximately 3 years. This tier generates alpha through systematic factor exposure -- cheap, profitable, trending UK small caps.

**Why 16-24 positions:** Provides sufficient diversification to manage idiosyncratic risk in UK small caps while maintaining meaningful position sizes (3.3-5.0% each). Classic portfolio theory suggests 20-30 stocks eliminates most idiosyncratic risk. The lower bound of 16 positions reflects the reduced universe size after filtering.

#### Tier 2: Conviction Hold Carve-out (20% of capital, 4-6 positions)

Positions are drawn from the Core Portfolio based on the strongest combination of: (a) highest composite factor scores, (b) qualitative assessment of business scalability and competitive position, and (c) management quality (insider ownership, capital allocation track record).

**Once designated as a conviction hold, the position is exempt from factor-based rebalancing.** It is held until one of the conviction-specific sell triggers fires (Section 6.3). This is where multibagger compounding can occur -- if a stock triples and its factor scores deteriorate (because it is no longer "cheap"), it remains in Tier 2 rather than being sold at the next rebalance.

**Why 4-6 positions:** At 20% of a GBP 500k-1m portfolio, each conviction hold is GBP 17,000-50,000. This is enough to be meaningful if a position delivers 5x+ returns (contributing 7-20% to total portfolio return) while limiting damage if any single conviction hold fails.

**Promotion criteria (Core → Conviction):**
- Stock has been held in the Core Portfolio for at least 6 months (one rebalance cycle)
- Composite factor score is in the top 25% of the portfolio
- Positive revenue growth trajectory (not just a single-year spike)
- Management owns >3% of outstanding shares
- Business model is simple and scalable (not project-dependent or commodity-dependent)

**[HONEST LIMITATION]** The conviction hold selection introduces a discretionary element that cannot be backtested. This is acknowledged. The 80/20 split limits the damage if discretionary judgment is poor.

### 5.2 Position Sizing

**Primary approach: Modified equal weight.**

- **Base allocation:** Equal weight across all holdings (approximately 3.3-5.0% each for 20-30 positions).
- **Composite score tilt:** The top-scoring third of holdings receives a 25% weight increase; the bottom-scoring third receives a 25% weight decrease. This means top-tier positions are approximately 4.2-6.3% and bottom-tier positions are approximately 2.5-3.8%.
- **Maximum position size at entry:** 7% of portfolio value. **[REASONABLE ASSUMPTION]** This prevents excessive concentration in any single thesis while allowing meaningful exposure.
- **Maximum position size during holding (after appreciation):** 15% of portfolio value. Beyond this, trim to 12%. **[SPECULATIVE]** The optimal trim threshold is not empirically determined for UK equities; 15% represents a pragmatic balance between letting winners run and managing concentration risk.

**Why equal weight as the base:**
- **[DATA SUPPORTS]** Equal-weighted portfolios systematically outperform cap-weighted portfolios because they provide greater exposure to smaller stocks, where factor premiums are larger (Fama-French SMB premium is 0.37% per month in small stocks vs 0.11% in large stocks). Since the universe is already size-filtered (GBP 30m-1,000m), equal weighting avoids the strategy simply becoming a bet on the largest stocks in the universe.

### 5.3 Sector Constraints

**Maximum sector weight: 30% at time of rebalancing.**

**[REASONABLE ASSUMPTION]** UK small-cap indices are heavily skewed toward certain sectors (industrials, consumer discretionary, technology on AIM). Without sector constraints, the factor model might concentrate in one or two sectors, creating unintended sector bets that dominate factor exposure.

**UK-specific sector considerations:**
- **Technology (AIM):** Likely to feature heavily due to high gross profitability and scalability. The 30% cap prevents over-concentration.
- **Resources (mining, oil & gas):** Excluded where pre-revenue or where profitability metrics are not comparable (commodity price dependency makes profitability cyclical rather than structural).
- **Consumer discretionary:** Likely source of UK multibaggers based on Stockopedia evidence (JD Sports, Games Workshop examples). No special restriction.
- **Healthcare/Biotech:** Most pre-revenue biotech is excluded by the positive FCF requirement. Profitable healthcare companies remain eligible.

---

## 6. Holding Period and Rebalancing

### 6.1 Holding Period Philosophy

**The two tiers have different holding philosophies. This resolves the contradiction (identified in A-10 of the assumptions document) between systematic rebalancing and patient compounding.**

#### Tier 1 (Core Factor Portfolio): Systematic rebalancing
- **Target holding period:** ~2-4 years per position (driven by factor score changes).
- **Philosophy:** Factor signals drive entry and exit. When a stock's factor scores deteriorate, it is replaced regardless of narrative or sentiment. This is a systematic strategy -- it does not require faith in any individual stock.
- **[DATA SUPPORTS]** Factor premiums are captured through portfolio turnover. Value and profitability signals are slow-moving (semi-annual measurement appropriate). Holding indefinitely on stale factor signals risks holding value traps.

#### Tier 2 (Conviction Holds): Patient compounding
- **Target holding period:** 5-10+ years, or until business thesis breaks.
- **Philosophy:** The factor screen identified the stock; now let the business compound. Factor score deterioration (e.g., rising valuation multiples as the stock appreciates) is NOT a sell trigger for Tier 2.
- **[DATA SUPPORTS]** Mayer (2018) found 100-baggers required 10+ years. Farago & Hjalmarsson (2023) showed positive skewness of individual stock returns increases dramatically with holding period. The conviction carve-out is where this evidence is applied.
- **Key discipline:** The 80/20 split means only 20% of capital is exposed to the patient-holding approach. If conviction hold judgment is poor, 80% of the portfolio is still systematically managed.

### 6.2 Rebalancing Rules

**Frequency: Semi-annual (every 6 months), with quarterly monitoring.**

- **Full rebalance (June and December):** Re-screen the entire universe, recalculate composite scores, and make portfolio adjustments. These months align with UK reporting cycles (many UK companies have December or June fiscal year-ends, meaning fresh annual accounts are available approximately 3-4 months later).
- **Quarterly monitoring (March and September):** Review existing holdings for sell triggers (Section 6.3) and for any acute deterioration in fundamentals. New positions are generally NOT added during quarterly reviews unless a sell has opened a slot.
- **Ad hoc review:** Triggered by profit warnings, material insider selling (>10% of holding), or suspension of trading. These override the regular schedule.

**Transaction cost budget:**
- **[REASONABLE ASSUMPTION]** Target annual one-way turnover of 25-35% of the portfolio (approximately 5-10 stocks replaced per year out of 20-30). At this turnover rate:
  - AIM stocks: approximately 0% stamp duty + approximately 2-3% average spread cost per round trip = approximately 0.5-1.0% annual frictional drag from AIM turnover.
  - Main Market stocks: approximately 0.5% stamp duty + approximately 0.5-1.0% spread cost per round trip = approximately 0.3-0.5% annual frictional drag from Main Market turnover.
  - **Total estimated annual transaction cost drag: 0.5-1.5% of portfolio value.** This is manageable relative to the expected gross alpha from factor exposure (3-5% annually from profitability alone, per Dimensional Fund Advisors 2015 European evidence).

### 6.3 Sell Discipline

#### Tier 1 (Core Factor Portfolio) sell triggers:

Any ONE of these triggers a sale:

1. **Composite score collapse:** The stock's composite score falls to the bottom 20% of the current eligible universe at a semi-annual rebalance. This is the primary mechanical sell trigger.

2. **Fundamental deterioration:** Two consecutive quarters of negative free cash flow AND gross profitability drops below the 30th percentile of the universe.

3. **Excessive dilution:** Net shares outstanding increase by more than 15% in a single fiscal year. **[DATA SUPPORTS]** Net equity issuance anomaly documented in UK by Cotter & McGeever (2018).

4. **Valuation ceiling:** EV/EBITDA exceeds the 90th percentile of the broad market. At extreme valuations, the risk/reward profile shifts unfavourably.

#### Tier 2 (Conviction Holds) sell triggers:

Conviction holds use a **narrower, fundamentals-only** sell discipline. Factor score deterioration (e.g., stock becomes "expensive" after appreciating) is NOT a sell trigger.

1. **Business thesis breaks:** Revenue declines for two consecutive fiscal years AND gross profitability drops below the 30th percentile. This is not a temporary setback; it is structural decline.

2. **Excessive dilution:** Same as Tier 1 (>15% share count increase in one year).

3. **Management red flags:** Material insider selling (>25% of holding by CEO/CFO), accounting restatements, or regulatory action.

4. **Position size limit:** If a conviction hold grows to exceed 15% of total portfolio value, trim to 12%. This is the only price-based trigger -- it manages concentration risk, not thesis deterioration.

**Demotion (Tier 2 → Tier 1):** If a conviction hold's fundamentals deteriorate but do not trigger a full sell, it can be demoted back to Tier 1 and subjected to standard factor-based rebalancing.

#### When NOT to sell (both tiers):

1. **Short-term price declines:** A 20-30% drawdown is NOT a sell signal if fundamentals remain intact.

2. **Sector rotation or macro noise:** Sector-wide selloffs that do not reflect company-specific deterioration.

3. **Missing a single quarterly earnings estimate:** Analyst estimates are unreliable for small caps.

4. **Mean-reversion temptation (especially Tier 2):** If a conviction hold doubles, the temptation to sell is strong. Resist unless a sell trigger fires. **[DATA SUPPORTS]** Positive skewness of long-horizon returns (Farago & Hjalmarsson 2023) means the expected value of holding a winner exceeds mean-reverting it.

---

## 7. Risk Controls

### 7.1 Portfolio-Level Controls

1. **Maximum sector exposure:** 30% at time of rebalancing (Section 5.3).
2. **AIM vs Main Market balance:** No hard constraint, but monitor. If AIM exposure exceeds 70% of the portfolio, review liquidity risk. **[REASONABLE ASSUMPTION]** AIM's stamp duty exemption and smaller starting capitalisations mean the strategy may naturally tilt toward AIM, but excessive AIM exposure creates aggregate liquidity risk.
3. **Cash buffer:** Maintain 3-5% cash at all times for opportunistic purchases and to avoid forced selling during drawdowns. **[SPECULATIVE]** The optimal cash buffer is not empirically determined; this is a pragmatic portfolio management choice.
4. **Maximum drawdown awareness:** No automatic stop-loss at portfolio level. **[DATA SUPPORTS]** Portfolio-level stop-losses for long-only equity strategies are empirically destructive -- they lock in losses during temporary drawdowns and miss subsequent recoveries. The entire factor framework is the risk management system; adding a portfolio stop-loss would undermine it.

### 7.2 Position-Level Controls

1. **Maximum position size at entry:** 7% of portfolio value.
2. **Trim threshold for appreciated positions:** 15% of portfolio value; trim to 12%.
3. **No averaging down:** If a position declines significantly and a partial sell trigger is approaching, do not add to the position. **[REASONABLE ASSUMPTION]** Averaging down into deteriorating fundamentals is a common behavioral trap; the strategy should either hold (if no sell trigger) or sell (if trigger hit), not increase exposure.

### 7.3 Momentum Crash Protection (Daniel & Moskowitz)

**[DATA SUPPORTS]** Daniel & Moskowitz (2016) documented that 14 of 15 worst momentum returns occurred when the past two-year market return was negative and the contemporaneous market return was positive, confirmed in UK data. They showed that a dynamic strategy scaling momentum exposure based on mean and variance forecasts approximately doubles the alpha and Sharpe ratio.

**Implementation:**
- **Monitor trailing 24-month FTSE All-Share total return.** If negative (bear market), reduce the weight of the momentum factor in composite scoring from 15% to 5%.
- **Monitor FTSE All-Share 60-day realised volatility.** If above the 80th percentile of its 10-year history AND the trailing 24-month return is negative, set momentum weight to 0% (ignore momentum entirely).
- **Rationale:** During bear market recoveries, past losers surge due to their high option-like betas, creating the momentum crash. By downweighting momentum during these periods, the strategy avoids the crash mechanism while retaining fundamental factor exposure.
- **[REASONABLE ASSUMPTION]** The specific thresholds (80th percentile volatility, 24-month lookback) are approximations of Daniel & Moskowitz's dynamic strategy, adapted for a practical semi-annual rebalancing schedule rather than continuous optimization.

### 7.4 Interest Rate Awareness (Monitoring Only)

Interest rates affect small-cap valuations and factor premiums. However, no evidence supports systematic factor weight adjustment based on rate regimes in UK equities. The Yartseva (2025) finding on interest rate sensitivity is US-specific and unreplicated.

**Implementation:** Monitor Bank of England base rate trajectory as context for interpreting portfolio performance. Do NOT adjust factor weights based on rate movements. If the rate environment changes materially (e.g., rates exceed 6% or fall below 1%), review the strategy's overall thesis but do not tinker with scoring weights -- this introduces discretionary timing that undermines the systematic approach.

---

## 8. Expected Performance Characteristics

### 8.1 What the Data Supports

- **Factor premiums exist in UK equities.** Gross profitability premium of approximately 3.6% annually in Europe (Dimensional Fund Advisors 2015). Momentum premium of approximately 0.85% per month in developed ex-US markets (Asness et al. 2013). Value premium of approximately 3-5% annually in UK long-run data. These are gross premiums before transaction costs.
- **Multi-factor strategies outperform single-factor strategies.** Combining profitability and value captures both sides of the "quality at a reasonable price" trade (Novy-Marx 2013 showed they are complementary -- profitable stocks and cheap stocks are different sets of stocks).
- **Multibaggers have identifiable ex-ante characteristics.** Small size, high FCF yield, high profitability, moderate valuation, and disciplined investment growth are statistically significant predictors (Yartseva 2025).
- **Most stocks underperform bonds.** 57.4% of stocks have lifetime returns below T-bills (Bessembinder 2018). Even a well-constructed factor strategy will hold many losers; the strategy succeeds if the winners more than compensate.
- **Transaction costs erode premiums significantly in UK small caps.** Stamp duty (0.5% Main Market) and AIM spreads (5-10x FTSE 100) create a meaningful drag.
- **Factor premiums have been decaying post-2012 in the UK.** Cotter & McGeever (2018) documented diminished statistical significance for most anomalies over time, though profitability remained robust.

### 8.2 What Are Reasonable Expectations (After Applying Discount)

- **[REASONABLE ASSUMPTION]** The Core Factor Portfolio (Tier 1) should deliver 1-3% annual net alpha over a UK small-cap benchmark over a full market cycle (7-10 years). This is based on historical gross premiums of 3-5% discounted by: (a) 58% post-publication decay (McLean & Pontiff 2016), (b) 1-2% annual transaction costs in UK small caps, and (c) the absence of UK-specific validation. This is deliberately conservative -- if the strategy cannot clear this lower bar, it should not be pursued.
- **[HONEST LIMITATION]** No reliable estimate exists for how many positions will deliver multibagger returns. The factor screen increases exposure to the population from which multibaggers emerge, but the enrichment factor is unknown and unquantified. Assuming any specific number of 3x+ or 5x+ winners would be speculative.
- **[REASONABLE ASSUMPTION]** The strategy will underperform in strong large-cap bull markets (when FTSE 100 mega-caps lead) and outperform when small-cap quality is rewarded. It will experience drawdowns of 30-50% during severe bear markets (UK small caps fell approximately 60% in 2008-2009).
- **[REASONABLE ASSUMPTION]** Core Portfolio turnover of 25-35% annually implies 5-10 position changes per year, which is implementable for a personal investor. Conviction holds will have near-zero planned turnover.

### 8.3 What Is Speculative

- **[SPECULATIVE]** Any claim of a specific expected CAGR (e.g., "15% annually") is speculative. Factor premiums are estimated from historical data that may not repeat. The documented factor premium decay in the UK (Cotter & McGeever 2018) could continue or accelerate.
- **[SPECULATIVE]** The assumption that factor characteristics identified in US multibaggers (Yartseva 2025) transfer directly to the UK market. The UK has a different sector composition (less technology, more resources and financials), smaller market, and different institutional investor base.
- **[SPECULATIVE]** The specific factor weights in the composite score (Section 4.2) are not calibrated from UK-specific regression analysis. They are informed by relative evidence strength but have not been optimised on UK data.
- **[SPECULATIVE]** Whether the AIM market will continue to exist in its current form. With only 679 companies and declining, structural changes (closure, merger with Main Market, regulatory changes) are plausible.
- **[SPECULATIVE]** The 5x return target over 5-7 years implies a CAGR of approximately 26-38%. Even with perfect factor exposure, this is an ambitious target that requires both factor premiums AND stock-specific compounding to deliver. The strategy improves the probability of achieving this target relative to random stock picking, but cannot guarantee it.

---

## 9. Expected Failure Modes

### 9.1 Factor Premium Disappearance

**Risk:** The factor premiums that underpin this strategy could decay further or disappear entirely in UK equities.
**Evidence:** Cotter & McGeever (2018) already documented diminished significance for most UK anomalies post-publication. The size premium reversed outright (Dimson & Marsh 1999). Only profitability has remained robust.
**Mitigation:** The strategy is most heavily weighted toward profitability and FCF yield -- the factors with the strongest theoretical underpinning and empirical persistence. If these fail, no factor strategy in UK equities is likely to work.
**Probability:** Moderate. Factor premiums have survived in some form for decades, but the magnitude is likely lower than historical estimates.

### 9.2 Liquidity Crisis

**Risk:** During market stress, AIM liquidity evaporates. Spreads widen to 20-40%, and it may become impossible to sell positions at reasonable prices.
**Evidence:** Board, Villa & Wells (1998) documented AIM's fragile liquidity. The 2020 COVID crash saw AIM liquidity deteriorate severely.
**Mitigation:** The liquidity filters in Section 2 exclude the least liquid stocks. The 3-5% cash buffer provides some cushion. The semi-annual rebalancing avoids forced selling during acute crises.
**Probability:** Certain to occur periodically. The question is severity and duration.

### 9.3 Survivor Bias in Design

**Risk:** The evidence base draws partly from studies with potential survivorship bias. AIM's high attrition rate (from 1,694 to 679 companies) means backtests that exclude delisted stocks materially overstate returns.
**Evidence:** DMS Yearbook documented 1.6% annual return overstatement from survivorship bias. Gerakos et al. (2013) showed AIM firms experience performance similar to US OTC Pink Sheets.
**Mitigation:** The profitability and FCF gates are designed to screen out the most failure-prone companies. But no screen perfectly predicts bankruptcy or value destruction.
**Probability:** High that some degree of survivorship bias contaminates the expected returns.

### 9.4 UK Market Structural Decline

**Risk:** The ongoing de-equitisation of the UK market (fewer listings, persistent outflows, declining liquidity) could mean the UK becomes an increasingly poor venue for small-cap factor investing.
**Evidence:** 20% reduction in listed companies over 5 years. GBP 4 billion in outflows from UK smaller company funds (22% of assets). Dearth of IPOs.
**Mitigation:** Limited. If the UK market continues to shrink, the investable universe will become too small for this strategy. Possible adaptation: expand to include Irish-listed or Channel Islands-listed stocks.
**Probability:** The trend is well-established. Whether it accelerates or stabilises is uncertain.

### 9.5 Concentration Risk

**Risk:** With 20-30 positions in UK small caps, a single fraud, accounting scandal, or sector collapse could materially damage returns.
**Evidence:** Bessembinder (2018) showed only 4% of stocks create net wealth. Even with factor screening, most holdings will disappoint. The strategy's success depends on a few large winners compensating for many moderate losers.
**Mitigation:** Sector diversification (30% cap), position size limits (7% at entry, 15% maximum), and the 20-30 position count.
**Probability:** High for individual position losses. The question is whether the factor screens generate sufficient winners to compensate.

### 9.6 Behavioral Failure

**Risk:** The investor fails to execute the strategy as designed -- selling winners too early, holding losers too long, panicking during drawdowns, or abandoning the strategy during a period of underperformance.
**Evidence:** Mayer (2018) found 100-baggers required 10+ years of patient holding. The behavioral literature documents extensive evidence of disposition effect (selling winners, holding losers), loss aversion, and strategy abandonment after 2-3 years of underperformance.
**Mitigation:** Clear sell rules (Section 6.3), explicit guidance on when NOT to sell, and a pre-commitment to holding periods. See Section 10.4 for further discussion.
**Probability:** Very high. This is likely the single largest risk to the strategy's real-world performance.

### 9.7 Overfitting to Yartseva's US Bull Market Sample

**Risk:** Yartseva's multibagger characteristics were identified during 2009-2024, a historically strong US bull market following the GFC. These characteristics may not generalise to UK equities in a different macroeconomic regime.
**Evidence:** The sample period coincides with near-zero interest rates, quantitative easing, and a technology-led bull market -- conditions that may not repeat.
**Mitigation:** The strategy draws on multiple evidence sources (not just Yartseva), including Novy-Marx (tested across 19 countries), Asness et al. (tested across multiple markets), and UK-specific studies. The core factors (profitability, value, momentum) have evidence spanning decades and multiple countries.
**Probability:** Moderate. The specific effect sizes from Yartseva are unlikely to replicate precisely, but the directional findings are consistent with a much broader literature.

---

## 10. Implementation Roadmap

### 10.1 Data Required

| Data Item | Source Options | Update Frequency | Critical? |
|---|---|---|---|
| Market capitalisation | LSE data, Bloomberg, Refinitiv, free sources (Yahoo Finance, Google Finance) | Daily (for screening), weekly (adequate) | Yes |
| Revenue, COGS, Total Assets | Company annual/interim reports, Refinitiv, Bloomberg, SharePad, Stockopedia | Semi-annual (aligned with reporting) | Yes |
| Free Cash Flow (Operating CF - Capex) | Cash flow statements, same sources | Semi-annual | Yes |
| EV/EBITDA | Calculated from market cap, debt, cash, EBITDA; available on SharePad, Stockopedia | Semi-annual (fundamentals), daily (price component) | Yes |
| 12-month price return | Price data from any provider | Monthly | Yes |
| Bid-ask spreads | LSE market data, Bloomberg | Monthly median | Yes |
| Daily traded value | LSE market data, Bloomberg, free sources | 60-day rolling median | Yes |
| Shares outstanding history | Company RNS announcements, Refinitiv | Semi-annual | Moderate |
| Net debt | Balance sheet data, same as above | Semi-annual | Moderate |
| EBITDA growth | Calculated from trailing EBITDA data | Semi-annual | Moderate |
| Asset growth | Calculated from trailing total assets data | Semi-annual | Moderate |
| FTSE All-Share trailing returns and volatility | Any index data provider | Monthly | For risk controls |
| Bank of England base rate | Bank of England website (free) | As announced | For regime adjustment |

**Cost-effective data stack for personal investors:**
- **Stockopedia (approximately GBP 500/year):** Pre-calculated quality, value, and momentum scores for UK equities. Covers most data requirements in one platform.
- **SharePad (approximately GBP 400/year):** Comprehensive fundamental data including free cash flow, EV/EBITDA, profitability metrics.
- **Free alternatives (for reduced data quality):** Yahoo Finance for price data; Companies House for annual accounts; LSE website for basic company information. These require significant manual processing and are not recommended for a systematic strategy.

### 10.2 Tools and Platforms

**Screening and scoring:**
- Stockopedia or SharePad for initial screening (both support custom screens with multiple factor criteria).
- Spreadsheet (Excel/Google Sheets) or Python for composite scoring and portfolio tracking.
- **[REASONABLE ASSUMPTION]** A personal investor can implement this strategy with one professional data subscription (Stockopedia or SharePad) and a spreadsheet. Institutional implementation would benefit from a proper database and automated screening pipeline.

**Execution:**
- Interactive Brokers, AJ Bell, or Hargreaves Lansdown for trade execution. Interactive Brokers offers the lowest commissions and best AIM execution through their SmartRouting system.
- Limit orders exclusively for AIM stocks (never market orders -- the wide spreads make market orders unacceptably expensive).
- Patience: for illiquid AIM stocks, plan for 1-5 days to fill a position at a reasonable price.

**Portfolio tracking:**
- Spreadsheet tracking: entry date, entry price, entry composite score, current price, current factor values, sell trigger status.
- Calendar reminders for semi-annual rebalancing (June, December) and quarterly reviews (March, September).

### 10.3 Common Mistakes to Avoid

1. **Backtesting without transaction costs.** Any backtest of this strategy that does not include realistic transaction costs (stamp duty + spreads + market impact) will overstate returns by 1-3% annually. AIM spreads alone can consume most of the expected alpha for the smallest, least liquid stocks. **[DATA SUPPORTS]** This is not hypothetical -- it is a documented reality of UK small-cap markets.

2. **Ignoring delisted stocks in backtests.** Survivorship bias is particularly severe for UK small caps, where AIM has lost over 1,000 companies since 2007. Any backtest must include the returns of companies that subsequently delisted (often at significant losses). **[DATA SUPPORTS]** DMS documented 1.6% annual overstatement from survivorship bias.

3. **Overweighting recent winners.** The temptation to increase position sizes in stocks that have already appreciated is a classic behavioral trap. The strategy's modified equal-weight approach with a 15% trim threshold is designed to prevent this.

4. **Confusing narrative with data.** A compelling management story, an exciting product, or a charismatic CEO are not factor characteristics. The strategy should be executed mechanically based on quantitative criteria, not overridden by qualitative judgments. **[REASONABLE ASSUMPTION]** Qualitative overlays can improve or destroy returns depending on skill; for most investors, mechanical execution will outperform discretionary overrides.

5. **Rebalancing too frequently.** Monthly rebalancing in UK small caps would generate excessive transaction costs and potentially trigger tax events. The semi-annual schedule is designed to balance signal freshness against trading costs.

6. **Applying US-derived thresholds directly.** Yartseva's effect sizes and thresholds are from US data. UK market structure, sector composition, and liquidity are different. The thresholds in this document have been adapted for UK conditions, but should be further calibrated with UK-specific backtesting before live implementation.

7. **Ignoring stamp duty in asset allocation.** The 0.5% stamp duty on Main Market purchases is a real and permanent friction that does not exist in US, European, or AIM markets. For a strategy with 30% annual turnover, this adds approximately 0.15% annual drag on Main Market positions. Preferring AIM stocks (stamp duty exempt) where liquidity is adequate is a rational cost-saving measure.

8. **Failing to account for AIM delisting risk.** AIM companies delist at much higher rates than Main Market companies. The positive FCF and profitability gates are the primary defense, but investors should maintain heightened awareness of regulatory and NOMAD-related risks on AIM.

### 10.4 Why Most Investors Fail to Stick to It

**[DATA SUPPORTS]** Behavioral finance research and practitioner experience consistently show that the primary cause of strategy failure is not the strategy itself but the investor's inability to adhere to it.

1. **Tracking error regret.** This strategy will deviate significantly from benchmark returns in any given year. During periods when large-cap or growth stocks lead (as in much of 2017-2024), a UK small-cap value-quality strategy will underperform, potentially for several years. Most investors abandon strategies after 2-3 years of relative underperformance. **Solution:** Pre-commit to a minimum 5-year evaluation horizon. Judge the strategy on whether it is being executed correctly, not on short-term returns.

2. **Loss aversion and the disposition effect.** The natural tendency is to sell winners (to lock in gains) and hold losers (to avoid realising losses). This strategy requires the opposite: hold winners (unless a sell trigger fires) and sell losers (when fundamentals deteriorate). **Solution:** Automate sell decisions using the explicit triggers in Section 6.3.

3. **Overconfidence in stock-specific narratives.** After buying a stock based on quantitative criteria, investors often develop an emotional attachment and a narrative about why this particular company will succeed. When the quantitative signals deteriorate, the narrative creates resistance to selling. **Solution:** Make the sell decision before seeing which stock it applies to -- establish rules and follow them.

4. **Illiquidity panic.** During market crises, AIM stocks may become effectively untradeable. Spreads widen to 20-40%, and seeing a position that cannot be sold at a reasonable price creates extreme anxiety. The temptation is to sell at any price, which is precisely when factor premiums are largest. **Solution:** Position size limits and the cash buffer provide some comfort. Accept that illiquidity is the price paid for the small-cap premium.

5. **Strategy complexity fatigue.** A multi-factor strategy with scoring, interaction effects, regime adjustments, and multiple sell triggers is cognitively demanding. Over time, investors simplify their execution (dropping factors, skipping rebalances) or abandon the strategy entirely. **Solution:** Automate as much as possible. Use a spreadsheet or platform (Stockopedia) that calculates scores automatically. Reduce the cognitive load of each decision.

6. **Survivorship bias in personal experience.** Investors remember the multibaggers they missed and forget the losers they avoided. This creates chronic dissatisfaction with any systematic approach that fails to catch every winner. **Solution:** Track the strategy's actual performance against a realistic benchmark (FTSE Small Cap Index), not against hindsight-selected winners.

---

## Appendix: Summary of Evidence Sources

| Source | Year | Key Finding Used | Evidence Type |
|---|---|---|---|
| Yartseva, "Alchemy of Multibagger Stocks" | 2025 | FCF yield strongest predictor; investment-EBITDA interaction; size and value effects | [DATA SUPPORTS] |
| Novy-Marx, "The Other Side of Value" | 2013 | Gross profitability premium; complementarity with value | [DATA SUPPORTS] |
| Bermejo et al. | 2021 | European factor performance; EV/EBITDA as strongest value metric; momentum Sharpe 0.80 | [DATA SUPPORTS] |
| Asness, Moskowitz & Pedersen, "Value and Momentum Everywhere" | 2013 | Momentum confirmed in UK equities | [DATA SUPPORTS] |
| Daniel & Moskowitz, "Momentum Crashes" | 2016 | Crash mechanism and dynamic momentum strategy | [DATA SUPPORTS] |
| Cotter & McGeever | 2018 | UK anomaly persistence; profitability remains robust | [DATA SUPPORTS] |
| Bessembinder, "Do Stocks Outperform Treasury Bills?" | 2018 | 57.4% underperformance; 4% wealth creators | [DATA SUPPORTS] |
| Dimson & Marsh, "Murphy's Law and Market Anomalies" | 1999 | UK size premium reversal post-publication | [DATA SUPPORTS] |
| Farago & Hjalmarsson, "Long-Horizon Stock Returns Are Positively Skewed" | 2023 | Extreme positive skewness at long horizons | [DATA SUPPORTS] |
| Liu, Strong & Xu | 1999 | Momentum profits in UK equities 1977-1996 | [DATA SUPPORTS] |
| Stockopedia, "Makings of a Multibagger" | Various | UK-specific multibagger characteristics | [DATA SUPPORTS] |
| Mayer, *100 Baggers* | 2018 | Characteristics of 100x return stocks; 10+ year holding period | [DATA SUPPORTS] |
| Foye | 2018 | Gross profitability respecification for UK five-factor model | [DATA SUPPORTS] |
| Hanauer & Huber | 2016 | International profitability measure comparison; ROE weakest outside US | [DATA SUPPORTS] |
| Papanastasopoulos | 2017 | European asset growth anomaly; more pronounced in loss-making firms | [DATA SUPPORTS] |
| Cooper, Gulen & Scallise | 2008 | Asset growth anomaly; 7.3% annual underperformance of high-growth decile | [DATA SUPPORTS] |
| Fama & French, "Choosing Factors" | 2018 | Cash-based profitability dominates accrual measures | [DATA SUPPORTS] |
| Board, Villa & Wells | 1998 | AIM liquidity characteristics | [DATA SUPPORTS] |
| Gerakos, Lang & Maffett | 2013 | AIM post-IPO underperformance | [DATA SUPPORTS] |
