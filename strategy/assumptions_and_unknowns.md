# Assumptions and Unknowns

**Date:** 2026-02-07
**Purpose:** Exhaustive catalogue of every assumption -- stated or unstated -- embedded in the proposed UK multi-factor multibagger strategy, every known unknown, plausible unknown unknowns, and every gap in the evidence base. This document is written from the perspective of a Skeptic/Risk Agent.

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

### A-3: Small-cap stocks are the right hunting ground for multibaggers

**Evidence FOR:**
- Yartseva (2025): Multibaggers overwhelmingly start as small caps.
- Mayer (2018): Median starting market cap for 100-baggers was approximately $500 million.
- Stockopedia UK evidence: Top UK winners started at GBP 50-350 million market cap.
- Mathematical necessity: A GBP 5 billion company achieving 10x requires becoming GBP 50 billion, which is top-10 FTSE 100 territory. A GBP 100 million company achieving 10x becomes GBP 1 billion, which is merely FTSE 250.
- Fama-French SMB premium is larger in profitable small caps.

**Evidence AGAINST:**
- Small caps have much higher failure rates. For every small-cap multibagger, there are dozens of small-cap stocks that delist, go bankrupt, or stagnate.
- The UK size premium reversed post-publication (Dimson & Marsh, 1999).
- UK small caps have experienced persistent fund outflows (GBP 4 billion over two years), structural de-equitisation, and declining liquidity.
- Survivorship bias is most acute in small caps, where attrition rates are highest.
- Small caps are where data quality is worst, transaction costs highest, and capacity most constrained.

**Verdict:** SUPPORTED for the mechanical premise (multibaggers must start small) but NOT SUPPORTED for the investment premise (investing in small caps will lead to multibagger returns). The distinction between "multibaggers are found among small caps" and "small caps produce multibagger returns" is critical. The former is a tautology; the latter is an unproven claim about forward-looking probabilities.

---

### A-4: Free cash flow yield is a reliable predictor of extreme positive returns

**Evidence FOR:**
- Yartseva (2025): FCF yield is the strongest single predictor in the multibagger model.
- Fama & French (2018): Cash-based operating profitability dominates accrual-based measures.
- NBIM (2015): Cash flow over assets had a Sharpe ratio of 0.7 globally.

**Evidence AGAINST:**
- Yartseva's FCF yield coefficient ranges from 46 to 82 across specifications. This is not the behaviour of a stable, reliable predictor. It suggests the coefficient is sensitive to model specification, sample period, or both.
- FCF yield is a backward-looking measure. High current FCF does not guarantee future FCF, especially in small caps where business models are evolving.
- FCF can be temporarily inflated by cutting capex, deferring maintenance, or running down working capital -- all of which boost short-term FCF at the expense of long-term value.
- There is no direct UK evidence cited for FCF yield as a multibagger predictor. The entire evidence base is US.
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

**Verdict:** WEAKLY SUPPORTED / LIKELY OVERFIT. This is the most suspicious component of the strategy. An interaction term found in a single retrospective study of winners, with no independent replication, should be treated with extreme skepticism. At best, it is a heuristic ("invest in companies that grow assets while also growing earnings"). At worst, it is noise.

---

### A-6: Annual rebalancing is sufficient

**Evidence FOR:**
- Annual rebalancing reduces transaction costs relative to monthly or quarterly rebalancing.
- Value and profitability factors are slow-moving and do not require frequent rebalancing.
- Lower turnover reduces stamp duty and spread costs.

**Evidence AGAINST:**
- Momentum signals have shorter half-lives (3-12 months). Annual rebalancing may capture only a fraction of the momentum premium or may enter/exit too late.
- Company fundamentals can deteriorate rapidly in small caps. A stock that screens well in January may be in financial distress by July.
- Annual rebalancing creates calendar effects and potential front-running by other market participants who know when the portfolio will trade.
- The interaction between annual rebalancing and illiquid AIM stocks may create forced trades at unfavourable prices at rebalancing dates.

**Verdict:** PARTIALLY SUPPORTED for value/profitability, NOT SUPPORTED for momentum. The strategy cannot credibly include momentum as a factor while rebalancing annually. Either momentum must be rebalanced more frequently (increasing costs) or excluded (reducing theoretical returns).

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

### A-8: A 20-40 stock portfolio provides sufficient diversification

**Evidence FOR:**
- Classic portfolio theory suggests 20-30 stocks eliminates most idiosyncratic risk.
- Concentration is needed to achieve multibagger returns (a 100-stock portfolio with one 10-bagger only delivers 10% at the portfolio level from that winner).

**Evidence AGAINST:**
- Bessembinder's findings demolish the classic diversification argument for return-seeking portfolios. If only 2-4% of stocks create net wealth, a 30-stock portfolio has roughly a 30-70% probability of containing zero wealth-creators (depending on the assumed hit rate and independence of selection).
- Small-cap stocks are more idiosyncratically volatile than large caps, so more positions are needed to achieve equivalent diversification.
- The strategy's factor screens may inadvertently concentrate the portfolio in correlated sectors (e.g., UK small-cap industrials or consumer services), reducing effective diversification even with 30+ names.
- A single multibagger in a 40-stock portfolio contributes at most 2.5% initial weight. Even with 10x returns, it becomes approximately 20% of the portfolio (assuming other positions are flat). This is a meaningful contribution but far from the "multibagger portfolio" narrative.

**Verdict:** PROBLEMATIC. There is an inherent contradiction between diversification (needed to manage the base rate problem) and concentration (needed to benefit meaningfully from multibaggers). The strategy cannot resolve this tension. It is attempting to be both a factor tilt and a multibagger hunter, and it cannot optimally be both.

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

### A-10: Patient holding (5-15 years) will allow multibagger returns to compound

**Evidence FOR:**
- Mayer (2018): 100-baggers required at least 10 years of patient holding.
- Farago & Hjalmarsson (2023): Positive skewness in individual stock returns increases dramatically with holding period.
- Compounding is a mathematical identity. If a stock grows at 15% annually, it doubles in approximately 5 years and reaches 4x in 10 years.

**Evidence AGAINST:**
- Patient holding requires the investor to tolerate significant intermediate drawdowns. Many 10x stocks experienced 50-70% drawdowns along the way. Few investors can sustain this psychologically.
- The strategy says "hold for 5-15 years" but also includes annual rebalancing. These are contradictory. Rebalancing means selling winners and buying new positions, which mechanically prevents multibagger compounding.
- Regime changes over 10-15 years can invalidate the original investment thesis. A stock that screens well in 2026 may face a fundamentally different competitive, regulatory, or macroeconomic environment by 2036.
- Opportunity cost: capital locked in underperformers for 10 years while waiting for a "multibagger" scenario that may never materialise is capital that could have been deployed elsewhere.

**Verdict:** INTERNALLY CONTRADICTORY. The strategy cannot simultaneously rebalance annually based on factor signals and hold positions for 10-15 years to allow compounding. These are incompatible portfolio management approaches.

---

## Known Unknowns

Things we know we do not know, and that materially affect the strategy's viability.

---

### KU-1: The False Positive Rate of the Factor Screen

We do not know how many stocks passing all factor criteria (small cap, high FCF yield, high gross profitability, moderate value, positive momentum, EBITDA-supported asset growth) *fail* to deliver multibagger returns. Yartseva studied the winners; nobody has studied the losers with identical starting characteristics. Without this denominator, we cannot calculate the precision (positive predictive value) of the screen.

**Why it matters:** If the screen selects 200 stocks annually but only 5 become multibaggers, the false positive rate is 97.5%. The portfolio would be dominated by non-multibaggers, and net returns would depend entirely on how those 195 "false positives" perform -- a question the strategy does not address.

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

We have no evidence on how a UK multi-factor multibagger strategy performs during a prolonged downturn. The Yartseva sample begins at the GFC trough (2009) and does not include any secular bear market period. UK bear markets (1973-1975, 2000-2003) may see value traps, momentum crashes, and small-cap underperformance simultaneously.

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

### KU-7: Whether "Multibagger" Targeting Adds Value Over Standard Factor Investing

We do not know whether a multi-factor strategy explicitly targeting extreme positive returns (multibaggers) outperforms a standard multi-factor strategy that simply buys stocks ranking highly on the same factors without any multibagger narrative. The "multibagger" framing may just be marketing layered on top of a conventional quality-value-momentum small-cap tilt.

**Why it matters:** If the strategy does not outperform a simple UK quality small-cap ETF after costs, the additional complexity and illiquidity are uncompensated.

---

### KU-8: The Optimal Factor Weighting for UK Markets

We do not know what weights to assign each factor (FCF yield, gross profitability, value, momentum, size, investment-EBITDA) for UK small caps. Yartseva's coefficients are US-specific. Equal weighting is a default but may not be optimal. Data-driven optimisation risks overfitting.

**Why it matters:** Factor weighting is a first-order determinant of strategy returns. Getting it wrong can reverse the sign of the strategy's alpha.

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

### EG-1: No Survivorship-Free UK Multibagger Study Exists

The Yartseva study is US-only and examines winners retrospectively. The Stockopedia UK evidence is anecdotal (top 10 winners over 10 years), not a systematic study. No academic paper has systematically identified UK multibaggers, controlled for survivorship, and estimated the conditional probability of achieving 5-10x returns given specific factor characteristics.

**What is needed:** A study using LSPD (London Share Price Database) or equivalent survivorship-free UK dataset that identifies ALL stocks matching the factor criteria at each point in time, tracks their forward returns including delistings, and estimates the precision (positive predictive value) and recall of the factor screen for multibagger outcomes.

---

### EG-2: No Net-of-Cost UK Small-Cap Factor Return Estimates

Published UK factor premiums are invariably gross of transaction costs. No study has estimated the after-cost return to a composite multi-factor strategy in UK small caps with realistic assumptions for stamp duty, bid-ask spreads, market impact, and AIM-specific execution challenges.

**What is needed:** Implementation-aware factor return estimates using actual AIM transaction cost data (from broker execution reports or proprietary datasets), not theoretical estimates based on quoted spreads.

---

### EG-3: The Investment-EBITDA Interaction Has Not Been Tested in UK/European Data

This is a novel finding from Yartseva (2025) tested exclusively in US data. No independent replication exists in any market. The European asset growth literature (Papanastasopoulos 2017; European Journal of Finance 2022) does not test this specific interaction.

**What is needed:** Independent testing of the Investment-EBITDA interaction in UK/European small caps using a survivorship-free dataset, before incorporating it as a strategy component.

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

The momentum literature establishes that 12-1 month momentum is profitable in UK equities (Liu et al. 1999, Hon & Tonks 2003), but the half-life of the momentum signal -- how quickly it decays after formation -- has not been established for UK small caps specifically. Given the strategy's annual rebalancing frequency, the momentum signal may be largely decayed by the time it is acted upon.

**What is needed:** Signal decay analysis for momentum in UK small caps, comparing formation periods and holding periods to determine optimal implementation frequency.

---

### EG-8: No Literature on How Factor Strategies Interact With AIM Tax Advantages

AIM stocks benefit from inheritance tax relief (Business Property Relief after 2 years), stamp duty exemption, and eligibility for ISAs and SIPPs. These tax advantages create non-fundamental demand for AIM stocks that may distort factor signals. For example, inheritance tax planning may inflate the prices of otherwise unattractive AIM stocks, or stamp duty exemption may encourage excessive trading that alters momentum patterns. No academic study has examined how these tax-driven flows interact with factor premia.

**What is needed:** Analysis of whether AIM tax advantages create systematic biases in factor returns, and whether factor strategies should adjust for tax-driven demand.

---

### EG-9: The Literature Is Silent on Optimal Position Sizing for Multibagger Strategies

The strategy literature discusses factor selection and portfolio construction (equal-weight vs value-weight), but no paper addresses optimal position sizing when the objective is to capture extreme positive skewness. Standard mean-variance optimisation is inappropriate when the return distribution is heavily right-skewed. Kelly criterion-based approaches have been proposed for concentrated bets but not for multi-factor small-cap strategies.

**What is needed:** Position sizing framework that accounts for the extreme skewness of individual stock returns, the base rate of multibagger outcomes, and the liquidity constraints of UK small caps.

---

### EG-10: No Comparative Study of UK Multi-Factor vs Single-Factor Small-Cap Strategies

It is unknown whether combining multiple factors outperforms the best single factor (gross profitability) in UK small caps after transaction costs. Multi-factor strategies incur higher turnover (because factor signals can conflict, forcing trades), while single-factor strategies are simpler and cheaper to implement. The added complexity of the multi-factor approach may not be compensated.

**What is needed:** Comparative backtest of composite multi-factor vs single-factor (profitability only) UK small-cap strategies, net of realistic transaction costs, using survivorship-free data.

---

## Summary: The Burden of Proof

The strategy as proposed relies on a chain of assumptions, each of which must hold for the strategy to succeed:

1. US factor premia exist in the UK (partially supported)
2. Historical factor premia will persist (weakly supported)
3. Small caps are the right universe (tautologically true, practically unproven)
4. FCF yield predicts extreme returns (single-study US evidence with unstable coefficients)
5. Investment-EBITDA interaction is genuine (no replication, likely overfit)
6. Annual rebalancing is sufficient (contradicts momentum inclusion and multibagger holding period)
7. Data quality is adequate (deteriorates for smallest stocks)
8. Diversification is sufficient (in tension with multibagger concentration)
9. 2009-2024 is representative (it is not)
10. Patient holding allows compounding (contradicts rebalancing approach)

If we assign generous probabilities to each assumption holding (say, 70% for the strongest, 30% for the weakest), the joint probability of all ten holding simultaneously is approximately 0.7 x 0.5 x 0.7 x 0.5 x 0.3 x 0.4 x 0.5 x 0.4 x 0.3 x 0.3 = approximately **0.09%**. Even being very generous with individual probabilities, the compound probability that the strategy works as described is extremely low.

This does not mean factor investing in UK small caps is worthless. It means that the specific strategy as articulated -- targeting multibaggers using a US-derived multi-factor model in an illiquid, shrinking UK small-cap universe with annual rebalancing -- faces a preponderance of unresolved challenges. The proponents bear the burden of demonstrating, with UK data and realistic assumptions, that the strategy generates positive net-of-cost alpha. Until that evidence is produced, the strategy should be considered speculative.
