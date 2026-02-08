# Risks and Failure Modes

**Date:** 2026-02-07 (revised post-audit)
**Purpose:** Adversarial challenge to the proposed UK small-cap quality-value-momentum factor strategy. This document is written from the perspective of a Skeptic/Risk Agent whose job is to find reasons this strategy will fail, not reasons it will succeed. Revised to reflect the post-audit improvements documented in `strategy_improvements.md`.

---

## Critical Risks (Strategy-Breaking)

These risks could individually render the strategy unviable. Any one of them, if realised, could result in sustained underperformance, permanent capital loss, or inability to execute.

---

### CR-1: Survivorship Bias Invalidates the Core Thesis

**Risk description:** The foundational study (Yartseva 2025) identified 464 stocks that *achieved* 10x returns, then examined their characteristics retrospectively. This is a textbook case of survivorship bias. The study does not, and cannot, tell us how many stocks *with identical starting characteristics* failed to deliver extreme returns. The denominator -- the population of stocks that looked the same at the starting point but went to zero or underperformed -- is entirely absent from the analysis.

**Evidence:**
- Yartseva's sample is 464 winners out of the full NYSE/NASDAQ universe. The total number of stocks listed on those exchanges over 2009-2024 exceeds 10,000. We have no data on the thousands of small-cap, high-FCF-yield, high-profitability stocks that did not deliver extreme returns.
- AIM attrition: 1,694 companies (2007) to 679 (2025). More than 1,000 companies were delisted, most due to failure, acquisition at distressed prices, or regulatory removal. Any backtest that fails to include these deletions will dramatically overstate returns.
- CRSP evidence shows survivorship bias overstates annual returns by 1.6% (7.4% vs 9.0%) in US datasets. In AIM, where failure rates are far higher, the bias could be 2-4% annually or more.
- Gerakos, Lang & Maffett (2013): AIM-listed firms experience greater post-IPO underperformance than traditionally regulated exchanges, with performance indistinguishable from US OTC Pink Sheets.

**Probability assessment:** Near-certainty (>90%). Survivorship bias is a structural feature of the Yartseva methodology, not a correctable flaw. The only question is the magnitude, not the existence, of the bias.

**Mitigation:** Partial at best. One could attempt to reconstruct the full universe including delistings using LSPD (London Share Price Database) or Refinitiv dead-stock data, but this is expensive and still subject to data quality issues. Even with survivorship-free data, the fundamental problem remains: the study was designed to describe winners, not to estimate the conditional probability of winning.

**Residual risk after mitigation:** High. Even with survivorship-free backtests, the strategy may perform materially worse than naive projections suggest.

---

### CR-2: Base Rate Neglect -- The Extreme-Return Probability is Vanishingly Low

**Risk description:** The strategy is positioned in the population from which extreme returners emerge, but the base rate for such outcomes is extremely low, and no combination of factor screens has been demonstrated to raise this probability to actionable levels.

**Evidence:**
- Bessembinder (2018, 2023): 57.4-58.6% of ALL US stocks underperform Treasury bills over their lifetimes. Only 4% of stocks explain the entire net gain of the US stock market. Only 2% create 90% of aggregate wealth.
- Fang et al. (2021): Internationally (including Europe/UK), the underperformance rate is *worse* -- average cross-country outperformance rate of only 42.4% vs 49.7% in the US.
- Even if we generously assume 5% of small-cap stocks become extreme returners over a 15-year period, and even if factor screens double the hit rate to 10%, a diversified portfolio of 25-40 stocks has a meaningful probability of containing zero such outcomes.
- Bessembinder himself states: "It's very difficult to predict ahead of time which stocks are going to end up in the right tail."

**Probability assessment:** High (70-80%). The base rate problem is mathematical. Unless the factor screens can demonstrably concentrate the portfolio in the 2-5% tail, the strategy will underperform broad market exposure on a risk-adjusted basis.

**Mitigation:** Diversification across 25-40+ positions. But this creates a tension: broader diversification reduces extreme-return exposure if you do hold one, converging toward index-like returns minus higher costs.

**Residual risk after mitigation:** High. The incidental multibagger exposure is a genuine optionality benefit, but the primary return driver must be factor premiums, not stock-picking for extreme returns.

---

### CR-3: US-to-UK Translation Failure

**Risk description:** The entire factor model is derived from US data (NYSE/NASDAQ, 2009-2024). Applying it to UK equities requires assumptions about cross-market transferability that may not hold.

**Evidence:**
- Market structure differs fundamentally: AIM has no minimum market cap, no minimum free float, lighter regulation, and uses SETSqx (not continuous order-book trading) for 80% of its stocks.
- Sector composition: US extreme returners are disproportionately drawn from technology (where explosive revenue growth drives rerating). UK public equity markets have far less technology exposure. FTSE 100 is dominated by financials, energy, consumer staples, and healthcare. AIM has more resources/mining exposure.
- Interest rate variable: Yartseva uses Federal Funds Rate as a macro control. The Bank of England's transmission mechanism, pace, and amplitude differ. UK monetary policy diverges from the Fed in both timing and magnitude (e.g., 2022-2024: different terminal rates, different speed of cuts).
- Tax regime: UK stamp duty (0.5% on Main Market purchases) has no US equivalent. This affects trading volumes, price discovery, and optimal rebalancing frequency.
- Foye (2018): The Fama-French five-factor model requires respecification for the UK (gross profit instead of operating profit). Even established factor models do not transfer cleanly.
- Hon & Tonks (2003): Momentum was not present in UK data before 1977, suggesting factors may operate differently in the UK over different time periods.

**Probability assessment:** High (60-75%). Not that factors are entirely absent in the UK (value and profitability have UK evidence), but that the specific factor loadings, interaction effects, and coefficient magnitudes from Yartseva will not replicate in a UK context. The strategy is calibrated to a US market that is structurally different.

**Mitigation:** Re-estimate the model using UK-specific data (Gregory, Tharyan & Christidis factor series; LSPD database). But this requires access to expensive datasets, econometric expertise, and sufficient sample size in the UK small-cap universe -- and may reveal that several factors are not statistically significant in the UK.

**Residual risk after mitigation:** Moderate-to-high. Even with UK re-estimation, sample sizes will be smaller, confidence intervals wider, and out-of-sample testing severely limited.

---

### CR-4: Liquidity Makes the Strategy Unimplementable

**Risk description:** The target universe (UK small/mid-cap, especially AIM) suffers from extreme illiquidity. Theoretical factor returns may exist on paper but be completely unachievable after transaction costs and market impact.

**Evidence:**
- AIM bid-ask spreads are 5-10x wider than FTSE 100 constituents. During volatile periods, spreads of 20-40% are documented.
- 80% of AIM stocks trade on SETSqx, which has no continuous order book. Execution requires market-maker interaction, giving the dealer an inherent informational advantage.
- Board, Villa & Wells (1998): The majority of AIM stocks trade infrequently, with trades clustered around a few days. There is no "average" AIM stock -- liquidity is highly heterogeneous and difficult to predict.
- A GBP 10m portfolio spread across 30 AIM positions means average position size of ~GBP 333,000. For stocks with GBP 50-100m market cap and 0.5% daily turnover, this represents multiple days of average volume. Building or liquidating the position would take weeks and involve significant market impact.
- Round-trip costs (entry + exit) in AIM micro-caps could reach 5-10%, consuming multiple years of expected factor premium.

**Probability assessment:** High (70-85%) for AIM-heavy implementation. Moderate (40-50%) if restricted to more liquid Main Market small caps, but this dramatically shrinks the eligible universe and removes many of the smallest stocks where factor premia are theoretically strongest.

**Mitigation:** Impose strict minimum liquidity thresholds (e.g., minimum daily turnover of GBP 50,000, maximum bid-ask spread of 5%). Use patient execution over days/weeks rather than immediate execution. Accept that the implementable universe is a small subset of the theoretical universe.

**Residual risk after mitigation:** Moderate. Liquidity filters will exclude many of the stocks that screen best on the factors, creating an implementation gap between theoretical and realised returns.

---

### CR-5: Overfitting in the Yartseva Model

**Risk description:** Testing 150+ variables on 464 stocks creates extreme risk of overfitting. The resultant model may describe the specific 2009-2024 US sample rather than any generalizable relationship.

**Evidence:**
- Harvey, Liu & Zhu (2016): With 150+ tested variables, the t-statistic threshold for significance should be approximately 3.0, not the conventional 1.96. Many of Yartseva's reported results may not survive this higher bar.
- FCF yield coefficient ranges from 46 to 82 across different specifications. A truly robust predictor should show coefficient stability. This degree of instability (nearly 2x range) suggests sensitivity to model specification.
- GMM estimation with many instruments relative to sample size creates weak-instrument bias, which can generate spuriously significant results.
- Only 2 years of out-of-sample testing (2023-2024). Two years is insufficient to validate a model intended for long-horizon investing. The out-of-sample period covers a specific market regime (post-pandemic normalisation, AI boom) and tells us nothing about performance in other regimes.

**Post-audit update:** The Investment-EBITDA interaction term -- the single most suspicious factor in the original strategy, with no independent replication and reliance solely on Yartseva's 464-stock sample -- has been **removed entirely** from the strategy (weight reduced from 15% to 0%). This partially mitigates the overfitting risk, as the remaining factors (gross profitability, FCF yield, EV/EBITDA value, momentum) all have multiple independent replications across geographies and time periods (Novy-Marx 2013, Fama & French 2018, Bermejo et al. 2021, Asness et al. 2013). The strategy no longer stands or falls with any single unvalidated working paper.

**Probability assessment:** Moderate-to-high (50-65%). Reduced from 65-80% because the most vulnerable factor has been dropped and all retained factors have independent support. However, the specific *combination* and *calibration* of these factors using Yartseva's framework remains a source of specification risk, and the FCF yield coefficient instability is still a concern.

**Mitigation:** Focus only on factors with independent, pre-existing evidence from multiple studies and multiple markets (profitability, value, momentum). This has now been implemented -- every factor with non-zero weight has multiple independent replications. Accept lower expected returns in exchange for greater robustness.

**Residual risk after mitigation:** Moderate. Even well-established factors show post-publication decay (see CR-7). Using only consensus factors reduces overfit risk but also reduces any edge over existing factor products.

---

### CR-6: Factor Decay and Secular Erosion

**Risk description:** Even if the factors were historically valid, changing market structure, increased data availability, and the proliferation of quantitative strategies may have eroded factor premia to insignificance through arbitrage.

**Evidence:**
- Cotter & McGeever (2018): Most UK anomalies show diminished statistical significance over time. Of nine anomalies studied, only profitability and stock turnover remained robust through the full sample.
- Dimson & Marsh (1999): The UK size premium reversed after publication -- from +6% to -6%. This is not a small decay; it is a complete sign reversal.
- UK momentum significance declined markedly in Cotter & McGeever's sample period.
- The asset growth anomaly is debated in Europe -- evidence is mixed between risk-based and mispricing explanations, and may vary by sub-period.
- Increasing availability of factor-based ETFs and smart-beta products means more capital is chasing the same anomalies, reducing their prospective returns.

**Probability assessment:** Moderate-to-high (55-70%). Not all factors decay equally (profitability appears most persistent), but the composite strategy relies on multiple factors, and if even half of them have decayed materially, the overall expected return is substantially impaired.

**Mitigation:** Weight the strategy toward factors with the strongest persistence evidence (gross profitability, cash-based quality). Reduce reliance on size and pure value, which have the weakest recent track records in the UK. Monitor factor returns in real-time and compare to historical benchmarks.

**Residual risk after mitigation:** Moderate. A profitability-dominant strategy is more defensible but is also more crowded (many "quality" funds exist). The edge, if any, is smaller.

---

### CR-7: Post-Publication Factor Decay

**Risk description:** This is the single most important risk for any factor strategy. Even factors that were genuine in-sample become weaker once published, because (a) arbitrage capital flows toward documented anomalies, compressing spreads, and (b) publication creates a statistical selection bias -- only factors that appear significant get published, and regression to the mean guarantees weaker out-of-sample performance.

**Evidence:**
- McLean & Pontiff (2016): This is the definitive study. Across 97 published anomalies, returns were **26% lower out-of-sample** (after discovery but before publication) and **58% lower post-publication**. If applied to the strategy's expected gross factor premiums, the post-publication haircut alone would reduce a 3-5% gross premium to approximately 1.3-2.1%.
- Bermejo et al. (2021): European factor alphas were **approaching zero after 2012**. This is directly relevant -- if European factor premia have already been arbitraged away, a UK factor strategy launched in 2026 is deploying into a post-arbitrage environment.
- The 26% out-of-sample decay reflects statistical overfitting; the additional 32% post-publication decay (58% minus 26%) reflects genuine arbitrage. Both mechanisms apply to this strategy.
- The strategy's core factors were published decades ago (value: Fama & French 1992; profitability: Novy-Marx 2013; momentum: Jegadeesh & Titman 1993). These are not newly discovered anomalies -- they have been subject to arbitrage pressure for years to decades.
- The proliferation of factor-based ETFs, smart-beta products, and quantitative funds targeting the same anomalies means the strategy is competing against institutional capital with lower costs and faster execution.

**Probability assessment:** High (70-80%). Post-publication decay is the best-documented and most robust finding in empirical asset pricing. The question is not whether decay has occurred, but how much remains. The strategy's reliance on factors published 10-30+ years ago, combined with Bermejo et al.'s finding that European alphas approached zero post-2012, makes this the most probable single cause of strategy failure.

**Mitigation:** Limited. One can tilt toward the most persistent factors (profitability has shown the least decay), apply McLean & Pontiff haircuts to expected returns (the strategy improvements document already does this), and focus on less-liquid corners of the market where arbitrage is harder. But the fundamental force -- capital flowing toward documented anomalies -- cannot be reversed by a single small investor.

**Residual risk after mitigation:** High. This risk is largely unmitigable. The honest response is to set performance expectations low (the revised strategy's base case of 0-1% net alpha reflects this) and to accept that the strategy may deliver returns indistinguishable from a simple UK small-cap quality ETF.

---

## Significant Risks (Performance-Degrading)

These risks will not individually break the strategy but will materially reduce returns, Sharpe ratios, or capacity.

---

### SR-1: Transaction Cost Drag

**Risk description:** Rebalancing costs in UK small caps are much higher than in liquid US equities, and will erode a meaningful portion of gross factor returns.

**Evidence:**
- UK stamp duty: 0.5% on Main Market purchases. Unique among major markets.
- AIM stocks are exempt from stamp duty but have wider bid-ask spreads (5-10x FTSE 100).
- Annual rebalancing of a multi-factor strategy creates 40-60% portfolio turnover.
- Momentum strategies require more frequent rebalancing (quarterly or monthly), further increasing costs.
- Assuming 50% annual turnover, 0.5% stamp duty on Main Market purchases, and 2-3% round-trip costs on AIM small caps: estimated annual transaction cost drag of 1.5-3.0%.
- If the gross factor premium is 3-5% annually, transaction costs consume 30-100% of the premium.

**Post-audit update:** The revised strategy now imposes a **2% annual all-in cost budget** as a hard rule (see `strategy_improvements.md` Section 7). If total costs exceed 2% of portfolio value in any calendar year, turnover in the Factor Sleeve must be reduced immediately (extend rebalancing to annual, raise score threshold for replacement). Additionally, the tightened screening gates -- **GBP 50m minimum market cap** (up from GBP 30m), **GBP 50k minimum daily traded value** (up from GBP 25k), and **3% maximum bid-ask spread** (down from 5%) -- are designed to exclude the most expensive-to-trade stocks from the investable universe. These mitigations should reduce the upper bound of the cost range, though they also reduce the universe size and potentially exclude some of the highest-factor-loading stocks.

**Probability assessment:** Near-certainty (>90%). Transaction costs are a known, quantifiable headwind. The cost budget and tighter filters reduce the severity but not the certainty.

**Mitigation:** Focus on AIM (stamp duty exempt). Use annual rather than quarterly rebalancing. Implement patient execution strategies. Accept higher tracking error vs theoretical portfolio. Target slightly larger stocks within the small-cap universe. The 2% cost budget and tightened screening gates provide structural discipline.

---

### SR-2: Momentum Crash Risk

**Risk description:** Momentum is one of the strategy's core factors, and momentum strategies are subject to sharp, devastating drawdowns during bear-market recoveries.

**Evidence:**
- Daniel & Moskowitz (2016): 14 of 15 worst momentum returns occurred when the past two-year market return was negative and the contemporaneous market return was positive. Confirmed in UK data.
- Momentum crashes are not just large negative returns; they can be -40% to -70% in a single quarter. For a concentrated small-cap portfolio, this could mean permanent capital impairment if investors panic-sell at the trough.
- The crash mechanism is well understood (high-beta losers surge in recoveries) but difficult to time perfectly.

**Probability assessment:** Moderate (30-50%) over any 5-year period. Near-certain over a 15-year holding period.

**Mitigation:** Dynamic momentum scaling based on market variance forecasts (Daniel & Moskowitz, 2016). Reduce momentum weight when trailing 24-month market return is negative. Blend momentum with value (negative correlation provides natural hedge, per Asness et al. 2013).

---

### SR-3: UK Market Structural Decline (De-equitisation)

**Risk description:** The UK equity market is shrinking. Fewer listed companies, declining IPO pipeline, persistent fund outflows, and increasing M&A takeouts are reducing the investable universe and depressing valuations.

**Evidence:**
- 20% fewer listed UK companies in 5 years.
- GBP 4 billion in outflows from UK smaller company funds over two years (22% of fund assets).
- AIM at its lowest number of listings since 2001.
- Declining IPO pipeline means the strategy's future opportunity set is shrinking.
- Persistent outflows create a self-reinforcing cycle: lower valuations lead to more M&A (takeout at depressed prices) and more delistings, further shrinking the universe.

**Probability assessment:** High (60-75%) that this trend continues. UK de-equitisation is structural (driven by regulatory burden, pension fund de-risking, private equity activity), not cyclical.

**Mitigation:** Limited. This is a macro trend beyond any single strategy's control. Could expand the universe to include European small caps listed on other exchanges, but this changes the strategy fundamentally.

---

### SR-4: Look-Ahead and Data-Snooping Bias in Backtest

**Risk description:** Any backtest of this strategy will be contaminated by look-ahead bias because the factors were selected based on knowledge of what worked historically. Even using well-established factors, the specific combination, weighting, and interaction terms are chosen with full knowledge of the historical data.

**Evidence:**
- Harvey, Liu & Zhu (2016): The majority of claimed factor discoveries are likely false positives when properly adjusted for multiple testing. The threshold for statistical significance should be a t-statistic of approximately 3.0 for new factor claims.
- Using Harvey et al.'s framework, the probability that the composite multi-factor screen has genuine out-of-sample predictive power is much lower than naive backtest results would suggest.

**Probability assessment:** High (60-70%) that live performance will significantly disappoint relative to backtested results.

**Mitigation:** Apply Bayesian shrinkage to backtest returns. Halve expected alpha as a conservative starting assumption (consistent with McLean & Pontiff's findings). Set live performance expectations well below backtest.

---

### SR-5: Regime Dependence (Bull Market Bias)

**Risk description:** The Yartseva sample period (2009-2024) is almost entirely a bull market: post-GFC recovery, unprecedented quantitative easing, near-zero interest rates for most of the period, and the AI/tech boom. There is no evidence these factors work in secular bear markets, stagflationary environments, or sustained high-rate regimes.

**Evidence:**
- Yartseva's interest rate dummy suggests strong regime dependence. The factor strategy's performance may be substantially a product of the QE era.
- UK interest rates were effectively at or near zero for 2009-2021. The current (2024-2026) environment of 4-5% base rates is fundamentally different.
- The 2009-2024 period saw one of the longest US bull markets in history. Selecting factors that worked during this specific regime tells us little about performance in a 1970s-style stagflation, a 2000-2002-style tech bust, or a prolonged bear market.
- UK small caps have been in a relative bear market vs large caps for several years (persistent fund outflows). If the bull-market tailwind reverses, the strategy's returns could be significantly impaired.

**Probability assessment:** Moderate (40-60%). We cannot know the future macro regime, but we can be confident that the 2009-2024 period was historically unusual.

**Mitigation:** Stress-test the factor model against 1970s, 1990s, and 2000s sub-periods using available UK data (DMS/Gregory datasets). If factors do not hold across multiple regimes, reduce conviction accordingly.

---

### SR-6: Capacity Constraints

**Risk description:** Even if the strategy works in theory, it may not work at meaningful scale. UK small-cap factor strategies face severe capacity limits.

**Evidence:**
- The AIM universe has approximately 679 companies, many with market caps below GBP 20 million.
- After applying liquidity filters, profitability screens, and other factor requirements, the investable universe may be 50-100 stocks.
- A GBP 10 million fund trading in this universe would face significant market impact. A GBP 50 million fund may be entirely unimplementable.
- FTSE SmallCap constituents have declined 30% over 5 years, with available market cap dropping approximately 50%.

**Probability assessment:** High (70-80%) that strategy capacity is limited to GBP 5-20 million. Near-certainty that it cannot scale beyond GBP 50 million without fundamental changes.

**Mitigation:** Accept the capacity constraint. This may be viable as a personal portfolio strategy or a niche fund, but not as an institutional strategy.

---

## Monitoring Risks (Watch List)

These are risks that are not currently critical but could become so. They require ongoing monitoring with defined trigger points.

---

### MR-1: Factor Crowding

**What to watch:** Increasing correlation between the strategy's returns and returns of existing UK small-cap factor ETFs/funds. Rising assets in UK "quality small cap" or "smart beta small cap" strategies.

**Trigger for concern:** If factor spreads (difference between top and bottom quintile returns for profitability, value, momentum) narrow to below 1% annually on a trailing 3-year basis, the factors may be fully priced. If three or more fund launches explicitly targeting similar UK small-cap multi-factor approaches occur within 12 months, crowding risk is elevated.

---

### MR-2: Regulatory Changes Affecting AIM

**What to watch:** Changes to AIM's tax advantages (stamp duty exemption, inheritance tax relief via Business Property Relief, EIS/VCT eligibility of AIM stocks). Changes to NOMAD/regulatory framework. Potential abolition or restructuring of AIM.

**Trigger for concern:** Any UK government consultation or budget proposal affecting AIM tax advantages. Loss of inheritance tax relief would likely trigger a wave of selling and delistings.

---

### MR-3: Data Quality Deterioration

**What to watch:** Availability and timeliness of fundamental data for AIM stocks. Coverage by data vendors (Bloomberg, Refinitiv, FactSet). Accounting standard changes that affect comparability of key metrics (gross profit, FCF, EBITDA).

**Trigger for concern:** If more than 20% of the investable universe has missing or stale data for key factor inputs (gross profitability, FCF yield, book-to-market, asset growth), the strategy cannot be reliably executed.

---

### MR-4: Market Microstructure Changes

**What to watch:** Migration of AIM stocks from SETSqx to SETS (positive) or further deterioration of liquidity. Changes to market-making obligations. Growth or decline of dark pool / off-exchange trading in UK small caps.

**Trigger for concern:** If average bid-ask spreads for the target universe increase by more than 50% from baseline, or if daily volumes decline by more than 30%, re-evaluate the implementability of the strategy.

---

### MR-5: Macro Regime Shift

**What to watch:** UK interest rates, inflation trajectory, gilt yields, sterling strength/weakness. Correlation between UK and US monetary policy cycles.

**Trigger for concern:** If the UK enters a sustained period of stagflation (above-target inflation + negative GDP growth) or if interest rates exceed 6%, the factor model calibrated to the 2009-2024 era may be operating entirely outside its training regime.

---

### MR-6: Concentration of Wealth Creation Accelerates

**What to watch:** Whether the Bessembinder finding (increasing concentration of wealth creation in fewer firms) accelerates further, implying that an ever-smaller fraction of stocks drive market returns.

**Trigger for concern:** If the top 1% of UK stocks explain more than 80% of net UK equity returns over a rolling 5-year period, the probability of any factor screen identifying these stocks is further reduced, and broad factor strategies become indistinguishable from losers.

---

## What Would Invalidate the Strategy

The following conditions, individually or in combination, should trigger a full strategy review and potential abandonment:

### Hard Invalidation Criteria

1. **Three consecutive years of underperformance vs FTSE Small Cap index by >3% per annum.** At this point, the probability that the factor model has genuine predictive power is low enough that continued implementation represents hope rather than evidence.

2. **Gross profitability factor premium turns negative in UK data over a rolling 5-year window.** This is the single most robust factor in the strategy. If it fails, the foundation collapses.

3. **Transaction costs exceed gross factor returns for two consecutive years.** If the strategy cannot generate positive returns net of implementable costs, it is not a viable strategy regardless of theoretical attractiveness.

4. **The investable universe (after liquidity and data quality filters) drops below 40 stocks.** Insufficient diversification to manage the base rate problem and UK small-cap failure rates. The portfolio becomes an uncompensated concentrated bet.

5. **A rigorous, survivorship-free backtest using UK data shows no statistically significant outperformance (t-statistic < 2.0) over the available sample period.** If the strategy does not work even in-sample with clean data, it certainly will not work out-of-sample. The kill switch criteria in `strategy_design_plan.md` Section 8.4 are binding commitments, not aspirational guidelines.

### Soft Invalidation Criteria (Trigger for Reduced Allocation)

6. **Rolling 3-year Sharpe ratio falls below 0.2.** The strategy is generating inadequate risk-adjusted returns.

7. **Factor correlations with existing UK small-cap index funds exceed 0.85.** The strategy is not adding meaningful differentiation; cheaper index exposure is preferable.

8. **More than 50% of positions hit stop-losses or delist within 2 years of purchase.** The screening process is not adequately filtering for survival.

9. **Post-publication evidence accumulates that 3 or more of the core factors (profitability, FCF yield, value, momentum) lose statistical significance in international datasets.** The academic consensus supporting the factor model has eroded.

---

## Summary Risk Matrix

| Risk ID | Risk | Severity | Probability | Time Horizon | Mitigable? |
|---------|------|----------|-------------|--------------|------------|
| CR-1 | Survivorship bias | Strategy-breaking | >90% | Permanent | Partially |
| CR-2 | Base rate neglect | Strategy-breaking | 70-80% | Permanent | Weakly |
| CR-3 | US-to-UK translation | Strategy-breaking | 60-75% | Permanent | Partially |
| CR-4 | Illiquidity | Strategy-breaking | 70-85% | Permanent | Partially |
| CR-5 | Overfitting | Strategy-breaking | 50-65% | Permanent | Partially |
| CR-6 | Factor decay (secular) | Strategy-breaking | 55-70% | Medium-term | Partially |
| CR-7 | Post-publication decay | Strategy-breaking | 70-80% | Permanent | Weakly |
| SR-1 | Transaction costs | Performance-degrading | >90% | Permanent | Partially |
| SR-2 | Momentum crashes | Performance-degrading | 30-50% (5yr) | Episodic | Yes |
| SR-3 | De-equitisation | Performance-degrading | 60-75% | Long-term | No |
| SR-4 | Look-ahead bias | Performance-degrading | 60-70% | Permanent | Partially |
| SR-5 | Regime dependence | Performance-degrading | 40-60% | Unknown | Partially |
| SR-6 | Capacity limits | Performance-degrading | 70-80% | Permanent | No |

**Overall assessment:** The strategy has been revised post-audit to address several critical weaknesses: the unreplicated Investment-EBITDA interaction has been removed (reducing overfitting risk), liquidity filters have been tightened (GBP 50m min market cap, GBP 50k min traded value, 3% max spread), explicit cost discipline has been added (2% annual budget), and binding kill switch criteria have been established. These improvements meaningfully reduce the probability of the most controllable risks (CR-5, SR-1) and demonstrate intellectual honesty about the strategy's limitations. However, the fundamental challenges remain largely unmitigated: post-publication factor decay (CR-7) is the single most probable cause of strategy failure, and the McLean & Pontiff 58% haircut combined with Bermejo et al.'s finding of European alphas approaching zero post-2012 suggests that the strategy may be deploying into an environment where the premia it seeks have already been substantially arbitraged away. UK-specific implementation costs (stamp duty, AIM spreads, SETSqx microstructure) consume a large fraction of whatever gross premium remains. And the base rate problem (CR-2) is mathematical, not addressable by better factor selection. The revised strategy's honest base-case expectation of 0-1% net alpha appropriately reflects these realities. The strategy proponent should be required to demonstrate, with survivorship-free UK data and realistic transaction cost assumptions, that the composite factor model generates statistically significant and economically meaningful net returns before any capital is committed.
