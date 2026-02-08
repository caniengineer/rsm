# Validated Factors for UK Small-Cap Factor Strategy

> Factors below have survived statistical scrutiny (t > 2.5 or equivalent), replicated across
> multiple studies or markets, and carry a plausible economic mechanism. Each entry maps the
> academic finding to a concrete, measurable signal suitable for screening and portfolio
> construction.
>
> **Post-audit note:** Factor weights have been revised to eliminate dependence on single
> unreplicated studies. Every factor with >0% weight now has multiple independent replications
> across geographies. The Investment-EBITDA Growth Interaction factor (formerly Factor 6) has
> been moved to rejected factors -- it rests on a single unreplicated study, the claimed effect
> ("100% of cases") is a red flag for overfitting, and no independent replication exists.
>
> **On post-publication factor decay:** McLean & Pontiff (2016) document that factor returns
> decline by 58% on average after academic publication. All expected alpha estimates in this
> document should be read with this decay in mind. The historical t-statistics cited below were
> measured in-sample; realised go-forward premiums will be materially lower.

---

## Factor Weights

| Factor | Weight | Rationale |
|--------|--------|-----------|
| Gross Profitability (GP/Assets) | **30%** | Deepest evidence base: Novy-Marx 19 countries, Bermejo t=10.88, Foye 2018 UK respecification, Cotter & McGeever 2018 UK persistence |
| FCF Yield | **20%** | Quality signal supported by Fama & French (2018) cash-based profitability; UK-specific calibration unvalidated, so weight reduced from prior 30% |
| Value (EV/EBITDA) | **20%** | Survives Harvey et al. 0.1% threshold; strongest European value metric (Bermejo 2021); multiple independent replications |
| Momentum (12-1 month) | **20%** | Strong European evidence (Bermejo Sharpe 0.80); Asness et al. "value and momentum everywhere"; survives 0.1% multiple-testing threshold |
| Size | **10%** | Universe filter only, not a scored return factor; UK size premium reversed post-publication (Dimson & Marsh 1999) |

---

## 1. Free Cash Flow Yield (FCF/P)

**Title:** Free Cash Flow Yield
**Weight:** 20%
**Source:** Yartseva (2025) -- "Multibagger Stocks: Characteristics and Drivers of Returns"; Fama & French (2018) -- cash-based profitability measures
**Key Insight:** FCF/P is a strong predictor of cross-sectional returns. Regression coefficients range from 46 to 82 across specifications in Yartseva (2025), the largest effect in that study by a wide margin. Companies generating high free cash flow relative to their market price compound value faster than the market, because FCF funds reinvestment, buybacks, and debt reduction without external financing. Fama & French (2018) provide independent support for cash-based profitability measures outperforming accrual-based alternatives in cross-sectional return prediction.
**Measurable Signal:** FCF Yield = Free Cash Flow / Market Capitalisation. Free Cash Flow = Operating Cash Flow minus Capital Expenditures. Use trailing-twelve-month figures. Higher is better; rank universe by decile.
**Evidence Strength:** Moderate-to-Strong. Coefficient magnitudes 46-82 in multivariate regressions (Yartseva 2025); the largest effect in that study. Fama & French (2018) corroborate the superiority of cash-based profitability metrics. However, the specific calibration to UK small caps is unvalidated -- the Yartseva coefficients are derived from US data only, with survivorship bias inherent in the multibagger sample construction. Post-publication factor decay (McLean & Pontiff 2016: 58% average decline) should be assumed to apply.
**Where it Works:** US equities, all cap ranges but especially potent in small-to-mid caps where analyst coverage is thin and mispricing persists longer. Cash-based profitability measures have broader international support (Fama & French 2018).
**Where it Fails:** Capital-intensive turnarounds and early-stage growth companies may show depressed or negative FCF that later normalises; a pure FCF screen will systematically exclude these. Sectors with lumpy capex cycles (mining, semiconductors) can show misleading single-year FCF. The UK-specific magnitude of the FCF yield premium is unknown -- no UK replication exists.
**Implications for Strategy:** Use FCF Yield as a quality filter alongside GP/Assets. Rank the investable universe by FCF/P and favour the top quintile. Combine with profitability and value checks to avoid yield traps (high FCF yield from declining businesses). Weight has been reduced from 30% to 20% to reflect the lack of UK-specific validation.
**Open Questions:** Optimal lookback period (TTM vs. 3-year average). Behaviour in UK markets specifically -- does the signal survive AIM's higher transaction costs? Whether FCF yield adds incremental information once GP/Assets is already in the model, or whether they are largely collinear.

---

## 2. Gross Profitability (GP/Assets)

**Title:** Gross Profit-to-Assets (GPA)
**Weight:** 30% (highest-weighted factor)
**Source:** Bermejo et al. (2021) -- European factor study; Novy-Marx (2013) -- original US study replicated across 19 countries; Foye (2018) -- UK respecification confirming profitability factor; Cotter & McGeever (2018) -- UK factor persistence
**Key Insight:** Gross Profit / Total Assets is the most robust profitability metric internationally and carries the deepest evidence base of any factor in this strategy. It captures the economic engine of a business before management can obscure it through accounting choices on SG&A, depreciation, or one-off items. In Europe, GPA delivers a Fama-French 3-factor alpha of 4.23% per annum (t = 10.88), the highest alpha of any single factor tested by Bermejo et al. Novy-Marx (2013) demonstrates the signal across 19 countries. Foye (2018) confirms that profitability factors survive respecification for UK market conditions. Cotter & McGeever (2018) find that factor persistence in UK data supports quality-profitability signals. This convergence of evidence across multiple independent studies, geographies, and time periods makes GP/Assets the most defensible factor in the strategy.
**Measurable Signal:** GPA = (Revenue - Cost of Goods Sold) / Total Assets. Use the most recent annual report. Rank universe by decile; go long the top quintile.
**Evidence Strength:** Strong. t-stat = 10.88 on FF3 alpha in European data (Bermejo et al. 2021). Replicated across 19 countries by Novy-Marx (2013). UK-specific confirmation via Foye (2018) respecification and Cotter & McGeever (2018) persistence analysis. GP/Assets is the most robust profitability measure in international tests; ROE is the weakest. Even after McLean & Pontiff (2016) post-publication decay of 58%, the implied residual alpha remains economically meaningful given the original effect size.
**Where it Works:** US and European equities broadly, including UK. Strongest in small caps where information asymmetry is highest. Works as a stand-alone signal and as the profitability layer in iterative multi-factor strategies.
**Where it Fails:** Asset-light business models (software, platforms) can show extremely high GPA that reflects business model rather than mispricing. Financial companies (banks, insurers) have meaningless COGS lines, so the metric is inapplicable. GPA does not capture capital allocation quality -- a company can have high gross margins and still destroy value through reckless investment. Post-2012 factor alpha decay is noted in European data (Bermejo et al.).
**Implications for Strategy:** Use GPA as the primary profitability filter and the highest-weighted factor in the composite score. In the iterative strategy (value then profitability then momentum), GPA is the profitability layer. When screening, require GPA above the universe median as a minimum quality threshold. Its 30% weight reflects the depth and breadth of independent replication evidence.
**Open Questions:** Whether a trailing-three-year average GPA is more stable than single-year. Whether GPA improvement (delta-GPA) adds incremental information. Exact magnitude of post-publication decay in UK small caps specifically.

---

## 3. Momentum (12-1 Month)

**Title:** Price Momentum (12-minus-1)
**Weight:** 20%
**Source:** Bermejo et al. (2021) -- European momentum; Harvey, Liu & Zhu (2016) -- MOM passes even 0.1% significance threshold; Asness, Moskowitz & Pedersen (2013) -- "Value and Momentum Everywhere"; UK studies (confirmed 1977-96, absent 1955-76)
**Key Insight:** Classical 12-1 momentum (buy past winners, skip the most recent month) is the strongest pure factor in European data (Sharpe 0.80, FF3 alpha 1.54%, t = 2.62) and one of only two factors to survive the harshest multiple-testing thresholds globally (Harvey et al. 2016). Asness, Moskowitz & Pedersen (2013) confirm momentum works across asset classes and geographies, including equities, bonds, currencies, and commodities. The signal is consistent with both behavioural explanations (underreaction to information) and risk-based explanations (time-varying risk premia). Post-publication factor decay (McLean & Pontiff 2016) applies, but the original effect size is large enough that a 58% reduction still leaves an economically meaningful premium.
**Measurable Signal:** 12-1 Momentum = (Price today / Price 12 months ago) - 1, excluding the most recent month. Rank and go long top decile.
**Evidence Strength:** Strong. t = 2.62 in European data (Bermejo et al. 2021). Survives 0.1% multiple-testing significance threshold (Harvey et al. 2016). Confirmed across multiple asset classes and geographies (Asness et al. 2013). However, momentum was absent in UK data from 1955-76 (Hon & Tonks 2003), indicating it is not a universal constant.
**Where it Works:** US and European equities. Strongest in liquid stocks where price discovery is efficient enough to reflect information but slow enough to create exploitable trends.
**Where it Fails:** Momentum crashes are well-documented -- sharp reversals occur in market recoveries after crises (e.g., March 2009). Classical momentum was absent in UK data from 1955-76 (Hon & Tonks 2003), suggesting it is not a universal law. Post-2012 factor alpha decay is noted in European data (Bermejo et al.). Daniel & Moskowitz (2016) document that momentum strategies can lose decades of gains in a few months during crash recoveries; crash protection overlays are advisable.
**Implications for Strategy:** Use standard 12-1 month momentum as the timing layer in the iterative strategy. Rank qualifying stocks (those passing value and profitability gates) by trailing 12-1 month return and favour the top half. Consider crash protection per Daniel & Moskowitz (2016) -- reduce momentum exposure when market volatility exceeds a threshold (e.g., 2x trailing average).
**Open Questions:** Optimal rebalancing frequency for momentum in UK small caps. Whether the post-2012 alpha decay in Europe reflects crowding or structural market change. The interaction between momentum and liquidity in AIM-listed stocks where price discovery may be impaired.

---

## 4. Value (EV/EBITDA)

**Title:** Value -- Enterprise Value-to-EBITDA (Primary) and Book-to-Market (Secondary)
**Weight:** 20%
**Source:** Bermejo et al. (2021) -- EV/EBITDA best value metric in Europe, final index 25.21; Harvey, Liu & Zhu (2016) -- HML passes 0.1% multiple-testing threshold; Yartseva (2025) -- B/M > 0.40 significant for cross-sectional returns
**Key Insight:** Value remains one of the two most robustly validated factors in all of finance (alongside momentum), surviving the most extreme multiple-testing corrections (Harvey et al. 2016, 0.1% significance threshold). In European markets, EV/EBITDA is the best-performing value metric, outperforming P/E, P/B, and P/CF, with the highest composite index score in Bermejo et al. (2021). Book-to-Market above 0.40 is a significant cross-sectional predictor of returns in US data (Yartseva 2025), with high-value stocks delivering nearly triple the excess returns of low-value stocks. The weight has been increased to 20% to reflect the depth of multi-study, multi-geography evidence. Post-publication factor decay applies (McLean & Pontiff 2016: 58% average decline), but value's evidence base is uniquely deep and pre-dates modern factor investing, limiting the crowding concern somewhat.
**Measurable Signal:** EV/EBITDA = (Market Cap + Total Debt - Cash) / EBITDA. Lower is cheaper. Rank universe; favour bottom quintile (cheapest). Secondary filter: Book-to-Market = Book Value of Equity / Market Capitalisation. Threshold: B/M > 0.40 (equivalently, P/B < 2.5).
**Evidence Strength:** Strong. HML survives 0.1% significance threshold (Harvey et al. 2016). EV/EBITDA achieves the highest composite score of any value metric in Bermejo et al. (2021). B/M > 0.40 significant in Yartseva (2025). Jensen, Kelly & Pedersen (2023) confirm value as one of 10 significant factor themes out of 13. Value has experienced prolonged drawdowns (2017-2020), but the cross-sectional evidence base extends back decades across multiple independent research teams.
**Where it Works:** Globally, across US and European markets. Effect is strongest in small caps. B/M works well as a binary filter (above/below 0.40). EV/EBITDA is better for continuous ranking within the value bucket.
**Where it Fails:** Value has experienced prolonged drawdowns (2017-2020 in the US). Sectors with intangible-heavy business models (technology, pharma) may appear perpetually expensive on B/M due to accounting treatment of intangibles. EV/EBITDA is unreliable for financial companies. Negative EBITDA renders the ratio meaningless. Value factor returns have decayed post-publication like all factors (McLean & Pontiff 2016).
**Implications for Strategy:** Use EV/EBITDA as the primary value metric for continuous ranking, with B/M > 0.40 as a secondary binary gate. In the iterative strategy, value screening (EV/EBITDA) is the first layer, removing overpriced stocks before profitability and momentum filters are applied. The 20% weight reflects the strong multi-study evidence base and the factor's survival of the most stringent multiple-testing corrections.
**Open Questions:** Whether intangible-adjusted book value (capitalising R&D and SGA) improves B/M's signal. How to handle negative-EBITDA companies. The relative weighting of B/M vs EV/EBITDA in a composite score. Magnitude of value premium in UK small caps specifically.

---

## 5. Small Cap Size (Universe Filter)

**Title:** Small Capitalisation (Size Effect) -- Universe Filter
**Weight:** 10% (universe filter, not a scored return factor)
**Source:** Yartseva (2025) -- median starting market cap of multibaggers is $348m; Bermejo et al. (2021) -- CMA factor 0.17-0.29% monthly, stronger in small caps; Fama & French (1993) original SMB factor; Dimson & Marsh (1999) -- UK size premium reversal
**Key Insight:** Small capitalisation defines the investable universe but should not be treated as a return-generating factor. The median starting market cap in Yartseva's sample is $348 million, reflecting the mechanical reality that smaller companies have more room to grow. However, the raw size premium has reversed in UK data. Dimson & Marsh (1999) document that the UK small-cap premium turned negative after its initial discovery, a textbook illustration of post-publication factor decay. This is consistent with McLean & Pontiff (2016), who find 58% average decay across all published factors. Small caps offer thinner analyst coverage and wider information asymmetry, creating the mispricing that other factors (GP/Assets, FCF yield, momentum) exploit -- but size itself is not the source of returns.
**Measurable Signal:** Market Capitalisation at screening date. Focus on companies with market cap between GBP 50m and GBP 2bn (micro-to-small cap, adjusted for UK market). Below GBP 50m, AIM liquidity and data quality become severe constraints. Above GBP 2bn, factor signal strength diminishes.
**Evidence Strength:** Weak as a return factor; strong as a universe definition. The $348m median is descriptive (Yartseva 2025), not a causal regression coefficient. The UK size premium reversed post-publication (Dimson & Marsh 1999). 57.4% of all US stocks underperform T-bills (Bessembinder), meaning the small-cap tail is very fat on the left side. Size works as a pre-condition for factor exposure, not as a stand-alone return factor.
**Where it Works:** As a universe filter rather than a return signal. Within the GBP 50m-2bn range, other factors (FCF yield, GPA, momentum, value) do the actual stock selection. Small caps amplify those factor signals because mispricing is larger and more persistent.
**Where it Fails:** The raw size premium is unreliable and negative in UK post-publication data (Dimson & Marsh 1999). AIM-listed UK stocks are stamp-duty-exempt but carry 5-10x wider spreads, which can consume the entire factor premium. Survivorship bias inflates historical small-cap returns. Liquidity constraints limit position sizing.
**Implications for Strategy:** Use market cap as a universe definition (GBP 50m-2bn), not as a scoring factor. The 10% weight reflects size's role as a conditioning variable rather than a return predictor. Ensure any backtest accounts for realistic trading costs -- particularly for AIM stocks where bid-ask spreads are 3-8%. Monitor position sizes to avoid illiquidity risk (no position larger than 5% of average daily volume).
**Open Questions:** Whether the GBP 50m lower bound is sufficient or should be higher given AIM's ongoing shrinkage. Whether a "relative size" measure (percentile within the local exchange) is better than an absolute cutoff.

---

## 6. Iterative Multi-Factor Strategy (Value -> Profitability -> Momentum)

**Title:** Sequential Factor Layering
**Source:** Bermejo et al. (2021) -- Iterative strategy achieving Sharpe 0.94, alpha 5.65% per annum
**Key Insight:** Applying factors sequentially -- first screening for value, then filtering for profitability within the value bucket, then applying momentum within the profitable-value bucket -- produces dramatically better risk-adjusted returns than any single factor alone or a simple composite. The iterative approach achieves a Sharpe ratio of 0.94 and a Fama-French 3-factor alpha of 5.65% per annum in European data. This works because each layer removes a different type of loser: value removes overpriced stocks, profitability removes value traps, and momentum removes dead-money stocks with no catalyst. Post-publication factor decay (McLean & Pontiff 2016: 58% average) likely applies to the combined strategy as well as to individual factors -- the 5.65% alpha should not be taken at face value as a go-forward expectation.
**Measurable Signal:** Step 1 (Value): Rank by EV/EBITDA, keep the cheapest tercile. Step 2 (Profitability): Within that tercile, rank by GPA, keep the top half. Step 3 (Momentum): Within the remaining set, rank by 12-1 month momentum, keep the top half. The final portfolio is the intersection of cheap, profitable, and trending.
**Evidence Strength:** Strong for the combined strategy (Sharpe 0.94, alpha 5.65% in Bermejo et al. 2021). Note that this is an in-sample result for European markets; out-of-sample and post-2012 decay is flagged. Applying McLean & Pontiff (2016) decay of 58% to the 5.65% gross alpha yields an estimated post-publication alpha of approximately 2.4% before transaction costs -- still meaningful but far from the headline figure.
**Where it Works:** European equities (tested directly). Likely US equities given the individual factor evidence. Small-to-mid caps where factor signals are strongest.
**Where it Fails:** Post-2012 factor alpha decay noted by Bermejo et al. suggests diminishing returns, possibly from factor crowding. The sequential approach reduces the investable universe aggressively -- the final portfolio may be very concentrated (20-40 stocks), increasing idiosyncratic risk. Transaction costs from momentum-driven rebalancing can erode alpha. No UK-specific backtest exists.
**Implications for Strategy:** This is the structural backbone of the screening methodology. Screen sequentially: EV/EBITDA (value) -> GPA (profitability) -> 12-1 month momentum (timing). FCF yield serves as an additional quality overlay applied either before or alongside the profitability step.
**Open Questions:** Optimal rebalancing frequency (monthly vs. quarterly). How many stocks the final portfolio should hold to balance concentration against diversification. Whether the three-step sequential approach outperforms a simple weighted composite score after accounting for the smaller universe size and higher turnover it creates.

---

## Appendix: Factor Evidence Summary Table

| Factor | Primary Source | t-stat or Equivalent | Market | Cap Range | Weight |
|---|---|---|---|---|---|
| GPA (Gross Profitability) | Bermejo et al. (2021) / Novy-Marx (2013) / Foye (2018) / Cotter & McGeever (2018) | t = 10.88 | Europe / 19 countries / UK | All, esp. small | 30% |
| FCF Yield | Yartseva (2025) / Fama & French (2018) | Coeff 46-82 | US / International | All, esp. small | 20% |
| Value (EV/EBITDA) | Bermejo et al. (2021) / Harvey et al. (2016) | Index 25.21 / Survives 0.1% | Europe / Global | All | 20% |
| Momentum (12-1) | Bermejo et al. (2021) / Harvey et al. (2016) / Asness et al. (2013) | t = 2.62 / Survives 0.1% | Europe / Global | All | 20% |
| Value (B/M) | Harvey et al. (2016) / Yartseva (2025) | Survives 0.1% / B/M>0.40 sig | Global / US | All | (secondary to EV/EBITDA) |
| Small Cap (universe filter) | Yartseva (2025) / Dimson & Marsh (1999) | Descriptive ($348m median) / UK premium reversed | US / UK | Micro-small | 10% (filter) |
| Iterative Strategy | Bermejo et al. (2021) | Sharpe 0.94, alpha 5.65% | Europe | All | (methodology, not weighted) |

---

## Notes on Interest Rate Sensitivity

**Evidence quality: Speculative (single-study, Yartseva-only).** Yartseva (2025) finds that rising interest rates reduce multibagger-class returns by 8-12 percentage points. This finding comes from a single unreplicated US working paper and should be treated as speculative rather than actionable. The directional intuition is plausible -- small-cap growth stocks with higher duration are mechanically more rate-sensitive -- but the specific magnitude (8-12pp) is uncorroborated. No UK-specific evidence exists for this effect in the small-cap factor context. If used at all, interest rate sensitivity should serve as a qualitative regime awareness tool, not a systematic portfolio adjustment. Monitor the yield curve slope and Bank of England rate trajectory as background context, but do not make binding allocation changes based solely on this single-paper finding.

---

## Notes on Post-Publication Factor Decay

McLean & Pontiff (2016) document that the average published factor's return declines by 58% after the paper describing it is published. This decay reflects two mechanisms: (1) investor learning and crowding into the signal, and (2) statistical overfitting in the original research. All historical alpha estimates cited in this document -- including Bermejo et al.'s 5.65% iterative strategy alpha and the individual factor premiums -- should be discounted by at least this amount when forming go-forward expectations. The factors with the longest publication history (value, momentum) have had the most time for decay to operate, but they also had the largest original effect sizes, which may leave a residual premium. Newer factors (FCF yield calibration, GP/Assets as measured by Novy-Marx) have had less time for crowding but may face faster decay as information dissemination has accelerated since 2013.
