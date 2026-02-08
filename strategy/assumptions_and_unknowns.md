# Assumptions and Unknowns

**Date:** 2026-02-07 (revised post-audit)
**Purpose:** Exhaustive catalogue of every assumption -- stated or unstated -- embedded in the proposed UK small-cap quality-value-momentum factor strategy, every known unknown, plausible unknown unknowns, and every gap in the evidence base. This document is written from the perspective of a Skeptic/Risk Agent.

---

## Explicit Assumptions

Each assumption below is something the strategy takes as given, either explicitly or implicitly. For each, I evaluate the evidence for and against.

---

### A-1: Factor premia that exist in US equities also exist in UK equities

**Evidence FOR:**
- Asness, Moskowitz & Pedersen (2013): Value and momentum are profitable in UK equities specifically, as part of a multi-country study.
- Rouwenhorst (1998): Momentum confirmed in European markets with magnitudes comparable to US.
- Dimensional Fund Advisors (2015): Profitability premium of 3.6% p.a. in Europe (15 countries, 1982-2014).
- Gregory, Tharyan & Christidis (2013): Constructed UK-equivalent Fama-French and Carhart factors, implying these factors are meaningfully present in UK data.
- Novy-Marx (2013): Gross profitability tested in 19 developed international markets with similar results.

**Evidence AGAINST:**
- Foye (2018): The Fama-French five-factor model requires respecification for the UK. Neither value nor investment premiums were consistently priced across different UK test portfolios.
- Cotter & McGeever (2018): Most UK anomalies show diminished statistical significance over time. Only profitability and stock turnover remain robust.
- Hon & Tonks (2003): Momentum was absent in UK data before 1977, suggesting it is not a permanent feature.
- Dimson & Marsh (1999): UK size premium reversed after publication -- from +6% to -6%. The sign flipped entirely.
- Hanauer & Huber (2016): ROE is *not* robustly priced outside the US, though other profitability measures are.

**Verdict:** PARTIALLY SUPPORTED. Individual factors have some UK evidence, but the specific combination, magnitudes, and interactions from US data cannot be assumed to transfer. The evidence is weaker than proponents suggest, and several key factors (size, investment) have mixed or negative UK evidence.

---

### A-2: Factor premia that existed historically will persist in the future

**Evidence FOR:**
- Risk-based explanations for value, size, and profitability (Fama-French framework) imply structural persistence -- if the premium compensates for bearing risk, it should persist as long as the risk exists.
- Profitability has shown the greatest persistence across time periods and geographies.
- Cash-based profitability measures appear to be less susceptible to arbitrage than price-based anomalies.

**Evidence AGAINST:**
- McLean & Pontiff (2016): Factor returns decline 26% out-of-sample and 58% post-publication. This is the strongest evidence that academic factor discovery leads to factor decay.
- Bermejo et al. (2021): European factor alphas approaching zero post-2012.
- Dimson & Marsh (1999): UK size premium reversed entirely post-publication.
- Cotter & McGeever (2018): Progressive decline in significance of UK anomalies.
- Increased algorithmic trading, factor ETFs, and smart-beta products have dramatically reduced the barriers to factor exploitation since most of these anomalies were discovered.
- If factor premia reflect mispricing (behavioural explanation), they should decay as more capital exploits them. If they reflect risk compensation, they should persist but at lower magnitudes as more investors accept the risk.

**Verdict:** WEAKLY SUPPORTED. Some premium persistence is likely (especially profitability), but the magnitudes observed in historical studies are almost certainly overstated relative to what can be achieved prospectively. A prudent assumption is that realised premia will be 40-60% of historical estimates.

---

### A-3: Small-cap stocks are the right hunting ground for a factor strategy seeking extreme winners

**Evidence FOR:**
- Yartseva (2025): Extreme winners overwhelmingly start as small caps.
- Mayer (2018): Median starting market cap for 100-baggers was approximately $500 million.
- Stockopedia UK evidence: Top UK winners started at GBP 50-350 million market cap.
- Mathematical necessity: A GBP 5 billion company achieving 10x requires becoming GBP 50 billion, which is top-10 FTSE 100 territory. A GBP 100 million company achieving 10x becomes GBP 1 billion, which is merely FTSE 250.
- Fama-French SMB premium is larger in profitable small caps.

**Evidence AGAINST:**
- Small caps have much higher failure rates. For every small-cap extreme winner, there are dozens of small-cap stocks that delist, go bankrupt, or stagnate.
- The UK size premium reversed post-publication (Dimson & Marsh, 1999).
- UK small caps have experienced persistent fund outflows (GBP 4 billion over two years), structural de-equitisation, and declining liquidity.
- Survivorship bias is most acute in small caps, where attrition rates are highest.
- Small caps are where data quality is worst, transaction costs highest, and capacity most constrained.

**Verdict:** SUPPORTED for the mechanical premise (extreme winners must start small) but NOT SUPPORTED for the investment premise (investing in small caps will lead to extreme returns). The distinction between "extreme winners are found among small caps" and "small caps produce extreme returns" is critical. The former is a tautology; the latter is an unproven claim about forward-looking probabilities.

---

### A-4: Free cash flow yield is a reliable predictor of extreme positive returns

**Evidence FOR:**
- Yartseva (2025): FCF yield is the strongest single predictor in the factor model.
- Fama & French (2018): Cash-based operating profitability dominates accrual-based measures.
- NBIM (2015): Cash flow over assets had a Sharpe ratio of 0.7 globally.

**Evidence AGAINST:**
- Yartseva's FCF yield coefficient ranges from 46 to 82 across specifications. This is not the behaviour of a stable, reliable predictor. It suggests the coefficient is sensitive to model specification, sample period, or both.
- FCF yield is a backward-looking measure. High current FCF does not guarantee future FCF, especially in small caps where business models are evolving.
- FCF can be temporarily inflated by cutting capex, deferring maintenance, or running down working capital -- all of which boost short-term FCF at the expense of long-term value.
- There is no direct UK evidence cited for FCF yield as a predictor of extreme returns. The entire evidence base is US.
- High FCF yield in small caps may proxy for distress (low market cap relative to cash flows because the market perceives the cash flows as unsustainable).

**Verdict:** PARTIALLY SUPPORTED. FCF yield is a reasonable quality/value measure, but its specific power to predict *extreme* positive returns (as opposed to modest above-average returns) is unproven outside the Yartseva sample, and the coefficient instability is concerning.

---

### A-5: The Investment-EBITDA interaction term is a genuine predictive signal

**Evidence FOR:**
- Yartseva (2025): Companies that aggressively expanded assets achieved superior returns in "100% of cases" when expansion was supported by EBITDA growth.
- Titman, Wei & Xie (NBER): Negative investment/return relation is stronger for firms with greater investment discretion.
- Koh (2024): Asset growth/return relationship is most pronounced in firms with both high financing constraints and high profitability (rational q-theory channel).

**Evidence AGAINST:**
- The "100% of cases" claim from Yartseva is a red flag. No factor works in 100% of cases in financial markets. This suggests either (a) an extremely small and unrepresentative subsample, (b) look-ahead bias in defining "supported by EBITDA growth," or (c) overfitting to a specific sample.
- The interaction term is unique to Yartseva. It has not been independently replicated by any other study.
- Defining "EBITDA growth supporting asset growth" requires a judgement call on timing: do you measure EBITDA growth contemporaneously, 1-year lag, 2-year lag? Different choices will give different results.
- Papanastasopoulos (2017): The asset growth anomaly in Europe is more pronounced in loss-making firms and dampened in profitable firms -- the opposite of what a positive Investment-EBITDA interaction would predict.

**Verdict:** REMOVED FROM STRATEGY. This factor has been dropped entirely from the revised strategy due to: (1) single unreplicated study as the sole source, (2) the "100% of cases" claim being a red flag for overfitting or sample selection, (3) no UK or European replication whatsoever, and (4) contradictory evidence from Papanastasopoulos (2017) showing the opposite pattern in European data. The investment discipline signal is now captured only through a standalone CMA/asset growth screening overlay applied conservatively, without the EBITDA interaction term.

---

### A-6: Rebalancing frequency is appropriate for the factors used

**Evidence FOR:**
- Value and profitability factors are slow-moving and do not require frequent rebalancing.
- Lower turnover reduces stamp duty and spread costs.
- The revised two-sleeve architecture now differentiates rebalancing by purpose: Factor Sleeve rebalances semi-annually, Compounding Sleeve holds indefinitely.

**Evidence AGAINST:**
- Momentum signals have shorter half-lives (3-12 months). Even semi-annual rebalancing may capture only a fraction of the momentum premium.
- Company fundamentals can deteriorate rapidly in small caps. A stock that screens well in January may be in financial distress by July.
- Rebalancing creates calendar effects and potential front-running by other market participants who know when the portfolio will trade.
- The interaction between scheduled rebalancing and illiquid AIM stocks may create forced trades at unfavourable prices at rebalancing dates.

**Verdict:** RESOLVED. The two-sleeve architecture now addresses the previous contradiction. The Factor Sleeve uses semi-annual rebalancing (appropriate for value and profitability signals). The Compounding Sleeve holds indefinitely (no rebalancing conflict). Momentum is monitored quarterly as an overlay within the Factor Sleeve, allowing more timely response to momentum signal decay without requiring full portfolio turnover. This is a material improvement over the original annual rebalancing approach, though the momentum implementation remains a compromise.

---

### A-7: The factors can be reliably measured using available data for UK small caps

**Evidence FOR:**
- Bloomberg, Refinitiv, and FactSet cover most UK-listed companies.
- Compustat Global and Worldscope provide historical fundamental data.

**Evidence AGAINST:**
- AIM stocks often have limited analyst coverage, delayed filings, and lower data quality.
- Gross profitability requires reliable Revenue and COGS data. Many AIM companies report under different accounting standards, may not separately disclose COGS, or may use non-standard line items that are inconsistently coded by data vendors.
- FCF is not a standardised accounting item. Different data providers calculate it differently, especially for small caps with complex capital structures.
- Book-to-market for AIM stocks may be distorted by intangible-heavy businesses where book value is near zero or negative.
- EBITDA can be manipulated through add-backs, non-recurring items, and management-defined "adjusted EBITDA" that differs from standardised calculations.
- Off-market and dark-pool trading makes volume and liquidity data unreliable for many UK stocks.

**Verdict:** WEAKLY SUPPORTED. Data availability is adequate for the largest 100-200 AIM stocks but progressively degrades for smaller companies. The strategy implicitly assumes data quality that may not exist for the very companies it is targeting.

---

### A-8: A 25-35 stock portfolio provides sufficient diversification

**Evidence FOR:**
- Classic portfolio theory suggests 20-30 stocks eliminates most idiosyncratic risk.
- The wider range (25-35, up from the original 20-30) compensates for higher UK small-cap failure rates.
- The two-sleeve architecture partially resolves the concentration vs diversification tension: the Factor Sleeve is diversified (15-20 positions) while the Compounding Sleeve is concentrated (5-10 graduates that have already demonstrated quality through factor persistence).

**Evidence AGAINST:**
- Bessembinder's findings challenge the classic diversification argument for return-seeking portfolios. If only 2-4% of stocks create net wealth, a 30-stock portfolio has roughly a 30-70% probability of containing zero wealth-creators (depending on the assumed hit rate and independence of selection).
- Small-cap stocks are more idiosyncratically volatile than large caps, so more positions are needed to achieve equivalent diversification.
- The strategy's factor screens may inadvertently concentrate the portfolio in correlated sectors (e.g., UK small-cap industrials or consumer services), reducing effective diversification even with 30+ names.
- A single extreme winner in a 35-stock portfolio contributes at most approximately 2.9% initial weight. Even with 10x returns, it becomes approximately 22% of the portfolio (assuming other positions are flat). This is a meaningful contribution but does not transform overall portfolio returns.

**Verdict:** PARTIALLY RESOLVED. The two-sleeve architecture reduces the tension between diversification and concentration. The Factor Sleeve provides broad factor exposure across 15-20 positions, while the Compounding Sleeve allows concentrated positions in proven winners (5-10 graduates). The 25-35 total range is more defensible than the original 20-40 range for UK small caps, though the fundamental Bessembinder challenge remains.

---

### A-9: The 2009-2024 period is representative of future market conditions

**Evidence FOR:**
- None. No period is ever representative of the future. This is an assumption of convenience.

**Evidence AGAINST:**
- 2009-2024 includes one of the longest US bull markets in history.
- Near-zero interest rates prevailed for most of the period (2009-2021 in the US, 2009-2021 in the UK). This is historically anomalous.
- Unprecedented central bank balance sheet expansion (QE) provided a tailwind to all risk assets, especially small caps and growth stocks.
- The period includes the COVID crash (March 2020) and recovery, which was the fastest in history -- not a normal bear market.
- The AI boom (2023-2024) drove concentrated returns in a narrow set of stocks, which may not repeat.
- Interest rate environments of 4-5% (current) are fundamentally different from 0-0.5% (2009-2021).

**Verdict:** NOT SUPPORTED. Strategies calibrated to the 2009-2024 period are calibrated to an historically anomalous set of conditions. Extrapolating these results to a future that may include sustained high rates, stagflation, or a prolonged bear market is unwarranted.

---

### A-10: The two-sleeve architecture allows both factor rebalancing and patient compounding

**Evidence FOR:**
- The two-sleeve model explicitly separates the rebalancing function (Factor Sleeve, semi-annual) from the compounding function (Compounding Sleeve, hold indefinitely).
- This resolves the internal contradiction in the original strategy, which simultaneously prescribed annual rebalancing and 5-15 year patient holding.
- Compounding Sleeve graduates are selected based on demonstrated factor persistence and fundamental trajectory, not just initial screening.
- Mayer (2018): 100-baggers required at least 10 years of patient holding. The Compounding Sleeve is designed to accommodate this.
- Farago & Hjalmarsson (2023): Positive skewness in individual stock returns increases dramatically with holding period. The Compounding Sleeve captures this.

**Evidence AGAINST:**
- Patient holding in the Compounding Sleeve still requires the investor to tolerate significant intermediate drawdowns. Many extreme winners experienced 50-70% drawdowns along the way.
- Regime changes over 10-15 years can invalidate the original investment thesis. A stock that graduates to the Compounding Sleeve in 2026 may face a fundamentally different competitive, regulatory, or macroeconomic environment by 2036.
- Opportunity cost: capital locked in the Compounding Sleeve in underperformers while waiting for extreme compounding that may never materialise is capital that could have been deployed elsewhere.
- The graduation criteria from Factor Sleeve to Compounding Sleeve require judgement and may introduce behavioural biases (reluctance to demote a former "winner").

**Verdict:** RESOLVED. The internal contradiction has been fixed by the two-sleeve model. The Factor Sleeve rebalances semi-annually with no pretense of patient holding. The Compounding Sleeve holds indefinitely for genuine patient compounding. The two mechanisms no longer contradict each other, though both individually still carry the risks noted above.

---

## Known Unknowns

Things we know we do not know, and that materially affect the strategy's viability.

---

### KU-1: The False Positive Rate of the Factor Screen

We do not know how many stocks passing all factor criteria (small cap, high FCF yield, high gross profitability, moderate value, positive momentum) *fail* to deliver strong returns. Yartseva studied the winners; nobody has studied the losers with identical starting characteristics. Without this denominator, we cannot calculate the precision (positive predictive value) of the screen.

**Why it matters:** If the screen selects 200 stocks annually but only 5 deliver strong returns, the false positive rate is 97.5%. The portfolio would be dominated by underperformers, and net returns would depend entirely on how those 195 "false positives" perform -- a question the strategy does not address.

---

### KU-2: The UK-Specific Factor Premiums After Transaction Costs

We do not have a reliable, survivorship-free estimate of net-of-cost factor premiums for UK small caps. Published factor premiums are almost always gross of transaction costs, and for illiquid UK small caps, the gap between gross and net returns could be 2-5% annually.

**Why it matters:** If the gross multi-factor premium is 4% and transaction costs are 3%, the net premium is 1% -- barely distinguishable from noise and almost certainly not statistically significant.

---

### KU-3: The Current State of Factor Decay in UK Markets

We do not know where UK factor premiums stand today relative to their historical averages. Bermejo et al. found European alphas approaching zero post-2012, but their sample period ends before 2020. Cotter & McGeever's UK data extends to 2013. We are extrapolating from data that is 10+ years old.

**Why it matters:** If factor premiums have continued to decay (as theory and evidence suggest they should), the strategy may be launching into a market where the factors it relies upon have already been arbitraged away.

---

### KU-4: How the Strategy Performs in a Sustained Bear Market

We have no evidence on how a UK multi-factor small-cap strategy performs during a prolonged downturn. The Yartseva sample begins at the GFC trough (2009) and does not include any secular bear market period. UK bear markets (1973-1975, 2000-2003) may see value traps, momentum crashes, and small-cap underperformance simultaneously.

**Why it matters:** If the strategy is deployed and a bear market occurs within the first 3-5 years, the investor faces significant drawdowns with no historical basis for expecting recovery.

---

### KU-5: The Interaction Between AIM Structural Decline and Factor Efficacy

We do not know how AIM's shrinking universe affects the statistical power and economic magnitude of factor premiums. A universe of 679 companies (and shrinking) may not be large enough to support robust cross-sectional factor strategies.

**Why it matters:** Factor investing relies on ranking a large universe and holding the top quantile. If the investable universe after filters is 50 stocks, the strategy degenerates into stock picking with a quantitative veneer.

---

### KU-6: The Actual Bid-Ask Spread Distribution for the Target Universe

Published bid-ask spread data for AIM stocks is limited and often stale. We do not know the real-time spread distribution for the specific stocks the strategy would target.

**Why it matters:** Position-level profitability is directly determined by execution costs. Without real-time spread data, any return estimate is speculative.

---

### KU-7: Whether the Factor Tilt Adds Value Over a Passive UK Small-Cap Quality ETF

The strategy has been reframed: it no longer targets extreme winners ("multibaggers") explicitly. It is now a factor-tilt strategy with incidental exposure to the population from which extreme winners emerge. The relevant question is therefore no longer "does targeting multibaggers add value?" but rather "does this specific factor tilt add value over a passive UK small-cap quality ETF after costs?"

**Why it matters:** If the strategy does not outperform a simple UK quality small-cap ETF (such as an iShares MSCI UK Small Cap Quality Factor ETF or equivalent) after accounting for transaction costs, management effort, illiquidity, and tax drag from rebalancing, then the additional complexity is uncompensated. The reframing makes this comparison more honest but does not change the fundamental question.

---

### KU-8: The Optimal Factor Weighting for UK Markets

The revised strategy uses the following factor weights: Gross Profitability 30%, FCF Yield 20%, EV/EBITDA (value) 20%, Momentum 20%, Size 10%. The Investment-EBITDA interaction has been removed entirely. These weights are informed by the relative strength of UK evidence for each factor (profitability strongest, size weakest) but remain estimates without direct UK optimisation.

**Why it matters:** Factor weighting is a first-order determinant of strategy returns. Getting it wrong can reverse the sign of the strategy's alpha. The current weights are more defensible than equal weighting (they reflect the evidence hierarchy) but have not been validated against UK small-cap data.

---

## Unknown Unknowns

Categories of risk we may not have considered, by their nature speculative but historically significant.

---

### UU-1: Black Swan Events Specific to UK Small Caps

Examples that have occurred historically but were not anticipated:
- COVID-19 lockdowns (2020) disproportionately affected UK small-cap consumer/hospitality companies.
- Brexit referendum (2016) caused sterling to drop 10% overnight, destroying international purchasing power.
- Woodford fund collapse (2019) triggered forced selling across UK small-cap funds, creating liquidity cascades.
- Russian invasion of Ukraine (2022) caused energy price shocks that hit UK small caps asymmetrically.

Future examples could include: a UK banking crisis, a sudden loss of AIM tax advantages, a major accounting fraud in AIM stocks triggering regulatory crackdown, a cyberattack on London Stock Exchange infrastructure, or a pension fund liquidity crisis forcing UK small-cap fire sales.

---

### UU-2: Technological Disruption of Market Structure

- Shift to blockchain-based settlement could fundamentally alter UK equity trading.
- AI-driven trading strategies exploiting the same factors at microsecond timescales.
- Democratisation of factor investing through retail platforms (e.g., Freetrade, Hargreaves Lansdown offering factor-tilted portfolios) crowding out premium.
- Potential changes to T+1 or T+0 settlement affecting AIM market-making.

---

### UU-3: Political/Geopolitical Risks

- UK government policy changes: windfall taxes on specific sectors, changes to capital gains tax regime (affecting holding period incentives), changes to ISA/pension rules affecting small-cap investment.
- Geopolitical realignment: UK trade policy shifts affecting small-cap exporters.
- Scottish independence or other constitutional changes creating market uncertainty.
- Changes to FCA regulatory posture toward AIM (tightening that reduces listings, or loosening that reduces quality).

---

### UU-4: Correlated Factor Failure

Multiple factors may fail simultaneously due to a common cause. For example:
- A liquidity crisis could cause small caps (size factor), high-momentum stocks (momentum factor), and value stocks (value factor) to all underperform simultaneously.
- This occurred during the 2007-2009 crisis when Quant hedge funds suffered correlated losses across supposedly independent factor strategies.
- If the factors are driven by common underlying risk exposures (e.g., liquidity risk), a liquidity shock would impair all factors at once.

---

### UU-5: Data Provider Failure or Methodology Change

- Bloomberg or Refinitiv could change their data calculation methodology for key inputs (EBITDA, free cash flow, gross profit), retroactively altering factor signals.
- A data vendor going offline or reducing AIM coverage.
- Accounting standard changes (IFRS updates) affecting comparability of fundamental data across time.

---

## Evidence Gaps

Where the academic and practitioner literature is silent, insufficient, or conflicting on questions material to the strategy.

---

### EG-1: No Survivorship-Free UK Extreme Winner Study Exists

The Yartseva study is US-only and examines winners retrospectively. The Stockopedia UK evidence is anecdotal (top 10 winners over 10 years), not a systematic study. No academic paper has systematically identified UK extreme winners, controlled for survivorship, and estimated the conditional probability of achieving 5-10x returns given specific factor characteristics.

**What is needed:** A study using LSPD (London Share Price Database) or equivalent survivorship-free UK dataset that identifies ALL stocks matching the factor criteria at each point in time, tracks their forward returns including delistings, and estimates the precision (positive predictive value) and recall of the factor screen for extreme return outcomes.

---

### EG-2: No Net-of-Cost UK Small-Cap Factor Return Estimates

Published UK factor premiums are invariably gross of transaction costs. No study has estimated the after-cost return to a composite multi-factor strategy in UK small caps with realistic assumptions for stamp duty, bid-ask spreads, market impact, and AIM-specific execution challenges.

**What is needed:** Implementation-aware factor return estimates using actual AIM transaction cost data (from broker execution reports or proprietary datasets), not theoretical estimates based on quoted spreads.

---

### EG-3: The Investment-EBITDA Interaction Has Not Been Tested in UK/European Data

*Note: This evidence gap is now moot for the revised strategy, as the Investment-EBITDA interaction has been removed entirely from the factor model. Retained here for completeness and as a record of why the factor was dropped.*

This was a novel finding from Yartseva (2025) tested exclusively in US data. No independent replication existed in any market. The European asset growth literature (Papanastasopoulos 2017; European Journal of Finance 2022) did not test this specific interaction, and Papanastasopoulos's findings on the asset growth anomaly in European loss-making firms contradicted the interaction's predicted direction.

**Resolution:** Factor removed from strategy. The investment discipline signal is now captured only through a standalone CMA/asset growth screening overlay, which has broader academic support.

---

### EG-4: No Evidence on Factor Efficacy in a Shrinking Equity Universe

All factor studies assume a reasonably stable or growing investable universe. The UK is experiencing de-equitisation (20% fewer listed companies in 5 years). No study has examined whether factor premiums behave differently in a shrinking universe where the cross-section becomes progressively smaller and less heterogeneous.

**What is needed:** Empirical analysis of factor returns as a function of universe size, or at minimum, sub-period analysis of UK factor returns during periods of delisting acceleration.

---

### EG-5: Conflicting Evidence on the Asset Growth Anomaly's Origin

Papanastasopoulos (2017) finds the European asset growth anomaly is consistent with mispricing (stronger in loss-making firms). The European Journal of Finance (2022) finds evidence more consistent with risk-based explanation. Koh (2024) supports the q-theory channel. These explanations have different implications for persistence and tradability. If the anomaly reflects mispricing, it should decay as more investors exploit it. If it reflects risk, it should persist but the risk must be borne.

**What is needed:** Resolution of the mispricing vs risk debate for the European/UK asset growth anomaly, ideally through out-of-sample testing and economic mechanism identification.

---

### EG-6: No Evidence on Factor Performance During UK-Specific Crises

The UK factor literature tests factors over full sample periods or sub-periods defined by calendar years. No study has specifically examined factor performance during UK-specific crisis periods: the ERM exit (1992), dotcom bust (2000-2003), GFC (2007-2009), Brexit referendum (2016), COVID (2020), or the 2022 gilt crisis. These events are where the strategy is most vulnerable, and where factor behaviour may deviate most from long-run averages.

**What is needed:** Event-study analysis of UK factor returns during crisis periods, with particular attention to factor correlations and drawdowns.

---

### EG-7: Momentum Half-Life in UK Small Caps Is Unknown

The momentum literature establishes that 12-1 month momentum is profitable in UK equities (Liu et al. 1999, Hon & Tonks 2003), but the half-life of the momentum signal -- how quickly it decays after formation -- has not been established for UK small caps specifically. Given the strategy's semi-annual rebalancing frequency (with quarterly momentum monitoring as an overlay), the momentum signal may still partially decay between action points.

**What is needed:** Signal decay analysis for momentum in UK small caps, comparing formation periods and holding periods to determine optimal implementation frequency.

---

### EG-8: No Literature on How Factor Strategies Interact With AIM Tax Advantages

AIM stocks benefit from inheritance tax relief (Business Property Relief after 2 years), stamp duty exemption, and eligibility for ISAs and SIPPs. These tax advantages create non-fundamental demand for AIM stocks that may distort factor signals. For example, inheritance tax planning may inflate the prices of otherwise unattractive AIM stocks, or stamp duty exemption may encourage excessive trading that alters momentum patterns. No academic study has examined how these tax-driven flows interact with factor premia.

**What is needed:** Analysis of whether AIM tax advantages create systematic biases in factor returns, and whether factor strategies should adjust for tax-driven demand.

---

### EG-9: The Literature Is Silent on Optimal Position Sizing for Skewed-Return Factor Strategies

The strategy literature discusses factor selection and portfolio construction (equal-weight vs value-weight), but no paper addresses optimal position sizing when the objective is to capture extreme positive skewness through a factor tilt. Standard mean-variance optimisation is inappropriate when the return distribution is heavily right-skewed. Kelly criterion-based approaches have been proposed for concentrated bets but not for multi-factor small-cap strategies.

**What is needed:** Position sizing framework that accounts for the extreme skewness of individual stock returns, the base rate of extreme return outcomes, and the liquidity constraints of UK small caps.

---

### EG-10: No Comparative Study of UK Multi-Factor vs Single-Factor Small-Cap Strategies

It is unknown whether combining multiple factors outperforms the best single factor (gross profitability) in UK small caps after transaction costs. Multi-factor strategies incur higher turnover (because factor signals can conflict, forcing trades), while single-factor strategies are simpler and cheaper to implement. The added complexity of the multi-factor approach may not be compensated.

**What is needed:** Comparative backtest of composite multi-factor vs single-factor (profitability only) UK small-cap strategies, net of realistic transaction costs, using survivorship-free data.

---

## Summary: The Burden of Proof

The revised strategy relies on a shorter and more honest chain of assumptions than the original. The removal of the Investment-EBITDA interaction and the resolution of the rebalancing/holding contradiction through the two-sleeve architecture have addressed two of the weakest links. The remaining chain:

1. US factor premia exist in the UK (partially supported -- ~70%)
2. Historical factor premia will persist (weakly supported -- ~50%)
3. Small caps are the right universe (tautologically true for extreme winners, practically unproven -- ~70%)
4. FCF yield predicts strong returns (single-study US evidence with unstable coefficients -- ~50%)
5. ~~Investment-EBITDA interaction is genuine~~ **REMOVED** -- no longer part of the assumption chain
6. ~~Annual rebalancing is sufficient / contradicts holding period~~ **RESOLVED** -- two-sleeve architecture addresses both rebalancing and holding
7. Data quality is adequate (deteriorates for smallest stocks -- ~50%)
8. 25-35 positions provide sufficient diversification (partially resolved by two-sleeve architecture -- ~55%)
9. 2009-2024 is representative (it is not -- ~30%)
10. ~~Patient holding contradicts rebalancing~~ **RESOLVED** -- Factor Sleeve rebalances, Compounding Sleeve holds

**Revised compound probability:** With Investment-EBITDA removed and two internal contradictions resolved, the assumption chain shortens to seven independent assumptions. Assigning the probabilities above: 0.70 x 0.50 x 0.70 x 0.50 x 0.50 x 0.55 x 0.30 = approximately **1.0%**.

This is a material improvement over the original estimate of approximately 0.09%, driven by removing the weakest assumption (Investment-EBITDA at ~30%) and resolving two contradictions (rebalancing at ~40% and holding period at ~30%). The revised strategy eliminates three of the lowest-probability links.

However, a 1% joint probability still means the strategy faces long odds of working exactly as described. The fundamental challenges remain:

- **Factor decay is real and ongoing.** The post-publication attenuation documented by McLean & Pontiff (2016) applies to every factor in the strategy.
- **UK small-cap structural headwinds persist.** De-equitisation, illiquidity, and declining AIM quality are not addressed by better portfolio construction.
- **No UK-specific validation exists.** The strategy is still built primarily on US evidence extrapolated to the UK.
- **The 2009-2024 calibration period remains unrepresentative.** No portfolio design change fixes this.

The revised strategy is more honest and internally consistent than the original. It no longer claims to target extreme winners through a factor model while simultaneously rebalancing away from winners. It no longer relies on an unreplicated interaction term. It acknowledges the factor-tilt nature of the approach rather than wrapping it in aspirational language about extreme compounding.

But intellectual honesty does not equal investment merit. The proponents still bear the burden of demonstrating, with UK data and realistic assumptions, that this specific factor tilt generates positive net-of-cost alpha over a passive UK small-cap quality ETF. Until that evidence is produced, the strategy should be considered speculative -- albeit more carefully constructed speculation than the original version.
