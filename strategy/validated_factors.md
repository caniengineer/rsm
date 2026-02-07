# Validated Factors for Multibagger Strategy

> Factors below have survived statistical scrutiny (t > 2.5 or equivalent), replicated across
> multiple studies or markets, and carry a plausible economic mechanism. Each entry maps the
> academic finding to a concrete, measurable signal suitable for screening and portfolio
> construction.

---

## 1. Free Cash Flow Yield (FCF/P)

**Title:** Free Cash Flow Yield
**Source:** Yartseva (2025) -- "Multibagger Stocks: Characteristics and Drivers of Returns"
**Key Insight:** FCF/P is the single strongest statistical predictor of future multibagger returns. Regression coefficients range from 46 to 82 across specifications, dwarfing every other variable tested. Companies generating high free cash flow relative to their market price compound value far faster than the market, because FCF funds reinvestment, buybacks, and debt reduction without external financing.
**Measurable Signal:** FCF Yield = Free Cash Flow / Market Capitalisation. Free Cash Flow = Operating Cash Flow minus Capital Expenditures. Use trailing-twelve-month figures. Higher is better; rank universe by decile.
**Evidence Strength:** Strong. Coefficient magnitudes 46-82 in multivariate regressions; the largest effect in the study by a wide margin.
**Where it Works:** US equities, all cap ranges but especially potent in small-to-mid caps where analyst coverage is thin and mispricing persists longer.
**Where it Fails:** Capital-intensive turnarounds and early-stage growth companies may show depressed or negative FCF that later normalises; a pure FCF screen will systematically exclude these. Sectors with lumpy capex cycles (mining, semiconductors) can show misleading single-year FCF.
**Implications for Strategy:** Use FCF Yield as the primary quantitative filter. Rank the investable universe by FCF/P and concentrate on the top quintile. Combine with profitability and value checks to avoid yield traps (high FCF yield from declining businesses).
**Open Questions:** Optimal lookback period (TTM vs. 3-year average). Whether FCF yield interacts with the investment-EBITDA growth term (i.e., does high FCF yield matter less when capex is rising rapidly?). Behaviour in European and UK markets specifically.

---

## 2. Gross Profitability (GP/Assets)

**Title:** Gross Profit-to-Assets (GPA)
**Source:** Bermejo et al. (2021) -- European factor study; Novy-Marx (2013) original US study; UK/European replication literature
**Key Insight:** Gross Profit / Total Assets is the most robust profitability metric internationally. It captures the economic engine of a business before management can obscure it through accounting choices on SG&A, depreciation, or one-off items. In Europe, GPA delivers a Fama-French 3-factor alpha of 4.23% per annum (t = 10.88), the highest alpha of any single factor tested by Bermejo et al.
**Measurable Signal:** GPA = (Revenue - Cost of Goods Sold) / Total Assets. Use the most recent annual report. Rank universe by decile; go long the top quintile.
**Evidence Strength:** Strong. t-stat = 10.88 on FF3 alpha in European data (Bermejo et al. 2021). Replicated in the US by Novy-Marx (2013). GP/Assets is confirmed as the most robust profitability measure in international tests; ROE is the weakest.
**Where it Works:** US and European equities broadly. Strongest in small caps where information asymmetry is highest. Works as a stand-alone signal and as the profitability layer in iterative multi-factor strategies.
**Where it Fails:** Asset-light business models (software, platforms) can show extremely high GPA that reflects business model rather than mispricing. Financial companies (banks, insurers) have meaningless COGS lines, so the metric is inapplicable. GPA does not capture capital allocation quality -- a company can have high gross margins and still destroy value through reckless investment.
**Implications for Strategy:** Use GPA as the primary profitability filter, replacing ROE or net margin. In the iterative strategy (value then profitability then momentum), GPA is the profitability layer. When screening, require GPA above the universe median as a minimum quality threshold.
**Open Questions:** Whether a trailing-three-year average GPA is more stable than single-year. Whether GPA improvement (delta-GPA) adds incremental information. Interaction with the Yartseva finding that even "modest positive operating profitability" is sufficient for multibaggers -- does GPA need to be high, or merely positive?

---

## 3. Momentum (12-1 Month) with Contrarian Twist

**Title:** Price Momentum (12-minus-1) and Contrarian Near-Low Signal
**Source:** Bermejo et al. (2021) -- European momentum; Yartseva (2025) -- contrarian momentum for multibaggers; Harvey, Liu & Zhu (2016) -- MOM passes even 0.1% significance threshold; UK studies (confirmed 1977-96, absent 1955-76)
**Key Insight:** Two distinct but related momentum signals emerge from the literature. Classical 12-1 momentum (buy past winners, skip the most recent month) is the strongest pure factor in European data (Sharpe 0.80, FF3 alpha 1.54%, t = 2.62) and one of only two factors to survive the harshest multiple-testing thresholds globally (Harvey et al. 2016). However, for multibagger identification specifically, Yartseva (2025) finds that contrarian momentum works: stocks near their 52-week lows tend to become multibaggers, while stocks near 52-week highs do not. This suggests a two-regime model -- classical momentum works for broad factor portfolios, but multibagger hunters should look for beaten-down stocks that have begun to inflect.
**Measurable Signal:** Classical: 12-1 Momentum = (Price today / Price 12 months ago) - 1, excluding the most recent month. Rank and go long top decile. Contrarian twist for multibaggers: Proximity to 52-Week Low = (Price - 52wk Low) / (52wk High - 52wk Low). Lower values (closer to the low) are preferred. A combined approach: screen for stocks near 52-week lows that have shown positive price change over the last 1-3 months (i.e., inflection from the bottom).
**Evidence Strength:** Strong for classical momentum (t = 2.62 in Europe, survives 0.1% threshold globally). Moderate-to-strong for the contrarian twist (Yartseva multivariate regressions, but single study).
**Where it Works:** US and European equities. Classical momentum strongest in mid-to-large caps with high liquidity. Contrarian twist strongest in small caps and neglected stocks.
**Where it Fails:** Momentum crashes are well-documented -- sharp reversals occur in market recoveries after crises (e.g., March 2009). Classical momentum was absent in UK data from 1955-76 (Hon & Tonks 2003), suggesting it is not a universal law. The contrarian signal can lead to value traps if not paired with fundamental quality checks. Post-2012 factor alpha decay is noted in European data (Bermejo et al.).
**Implications for Strategy:** Deploy a hybrid approach. For the multibagger screen, favour stocks near 52-week lows (contrarian) but require a recent positive inflection (1-3 month positive return) and strong fundamentals (FCF yield, GPA). For portfolio rebalancing and exit timing, use classical 12-1 momentum as a trend-following overlay. Be cautious during post-crash snapback periods.
**Open Questions:** Exact specification of the "inflection" signal -- how many months of positive returns from the trough? Whether the post-2012 alpha decay in Europe reflects crowding or structural market change. Whether momentum and the contrarian signal can coexist in the same model without collinearity problems.

---

## 4. Value (Book-to-Market and EV/EBITDA)

**Title:** Value -- Book-to-Market Ratio and Enterprise Value-to-EBITDA
**Source:** Yartseva (2025) -- B/M > 0.40 significant, high-value multibaggers +34.7% excess vs +12.8% for low-value; Bermejo et al. (2021) -- EV/EBITDA best value metric in Europe, final index 25.21; Harvey, Liu & Zhu (2016) -- HML passes 0.1% threshold
**Key Insight:** Value remains one of the two most robustly validated factors in all of finance (alongside momentum), surviving the most extreme multiple-testing corrections. For multibagger hunting, Book-to-Market above 0.40 is a significant predictor, with high-value multibaggers delivering nearly triple the excess returns of low-value multibaggers. In European markets, EV/EBITDA is the best-performing value metric, outperforming P/E, P/B, and P/CF.
**Measurable Signal:** Book-to-Market = Book Value of Equity / Market Capitalisation. Threshold: B/M > 0.40 (equivalently, P/B < 2.5). EV/EBITDA = (Market Cap + Total Debt - Cash) / EBITDA. Lower is cheaper. Rank universe; favour bottom quintile (cheapest).
**Evidence Strength:** Strong. HML survives 0.1% significance threshold (Harvey et al. 2016). B/M > 0.40 significant in Yartseva (2025). EV/EBITDA achieves the highest composite score of any value metric in Bermejo et al. (2021). Jensen, Kelly & Pedersen (2023) confirm value as one of 10 significant factor themes out of 13.
**Where it Works:** Globally, across US and European markets. Effect is strongest in small caps. B/M works well as a binary filter (above/below 0.40). EV/EBITDA is better for continuous ranking within the value bucket.
**Where it Fails:** Value has experienced prolonged drawdowns (2017-2020 in the US). Sectors with intangible-heavy business models (technology, pharma) may appear perpetually expensive on B/M due to accounting treatment of intangibles. EV/EBITDA is unreliable for financial companies. Negative EBITDA renders the ratio meaningless.
**Implications for Strategy:** Use B/M > 0.40 as a binary gate to ensure the portfolio stays in value territory. Within the qualifying universe, rank by EV/EBITDA for finer discrimination. The Yartseva finding is striking: even among multibaggers, the cheap ones massively outperform the expensive ones. Do not chase expensive growth stories.
**Open Questions:** Whether intangible-adjusted book value (capitalising R&D and SGA) improves B/M's signal. How to handle negative-EBITDA companies that may be future multibaggers in turnaround. The relative weighting of B/M vs EV/EBITDA in a composite score.

---

## 5. Small Cap Size

**Title:** Small Capitalisation (Size Effect)
**Source:** Yartseva (2025) -- median starting market cap of multibaggers is $348m; Bermejo et al. (2021) -- CMA factor 0.17-0.29% monthly, stronger in small caps; Fama & French (1993) original SMB factor
**Key Insight:** Multibagger stocks overwhelmingly begin their runs as small caps. The median starting market cap in Yartseva's sample is $348 million. This is not a pure "small-cap premium" (which has reversed post-publication in the UK per Dimson & Marsh 1999), but rather reflects the mechanical reality that a $350m company can grow 10x to $3.5bn, while a $350bn company growing 10x is nearly impossible. Small caps also offer thinner analyst coverage and wider information asymmetry, creating the mispricing that other factors exploit.
**Measurable Signal:** Market Capitalisation at screening date. Focus on companies with market cap between $100m and $2bn (micro-to-small cap). Below $100m, liquidity and survivorship risks become severe. Above $2bn, multibagger potential diminishes sharply.
**Evidence Strength:** Moderate. The $348m median is descriptive (Yartseva 2025), not a causal regression coefficient. The raw size premium has failed to replicate cleanly post-publication -- the UK size premium reversed (Dimson & Marsh 1999), and 57.4% of all US stocks underperform T-bills (Bessembinder), meaning the small-cap tail is very fat on the left side. Size works as a multibagger pre-condition, not as a stand-alone return factor.
**Where it Works:** As a universe filter rather than a return signal. Within the $100m-$2bn range, other factors (FCF yield, GPA, momentum) do the actual stock selection. Small caps amplify those factor signals because mispricing is larger and more persistent.
**Where it Fails:** The raw size premium is unreliable and may be negative after adjusting for microstructure costs. AIM-listed UK stocks are stamp-duty-exempt but carry 5-10x wider spreads, which can consume the entire size premium. Survivorship bias inflates historical small-cap returns. Liquidity constraints limit position sizing.
**Implications for Strategy:** Use market cap as a universe definition ($100m-$2bn), not as a scoring factor. Ensure any backtest accounts for realistic trading costs -- particularly for AIM stocks where bid-ask spreads are 3-8%. Monitor position sizes to avoid illiquidity risk (no position larger than 5% of average daily volume).
**Open Questions:** Whether the $100m lower bound should be higher for European/UK markets given thinner liquidity. Whether a "relative size" measure (percentile within the local exchange) is better than an absolute dollar cutoff. How to handle currency effects for non-USD markets.

---

## 6. Investment-EBITDA Growth Interaction

**Title:** Capital Investment Conditional on Earnings Growth
**Source:** Yartseva (2025) -- "Multibagger Stocks: Characteristics and Drivers of Returns"
**Key Insight:** Aggressive asset growth is NOT unconditionally positive. The interaction between investment intensity and EBITDA growth is a critical finding: companies that aggressively expand their asset base ONLY generate superior returns when that investment is supported by concurrent EBITDA growth. When asset growth is high but EBITDA growth is low or negative, returns drop by 5 to 23 percentage points. This resolves the long-standing puzzle of why the conservative-minus-aggressive (CMA) investment factor works -- most aggressive investors destroy value, but the rare ones growing into real earnings are future multibaggers.
**Measurable Signal:** Investment Intensity = Year-over-Year Total Asset Growth (%). EBITDA Growth = Year-over-Year EBITDA Growth (%). Interaction term = Asset Growth x EBITDA Growth. Favour companies where BOTH are positive and EBITDA growth exceeds or matches asset growth (i.e., investment is generating returns). Flag and avoid companies with high asset growth (> 20%) and flat or negative EBITDA growth.
**Evidence Strength:** Moderate-to-Strong. The interaction term is statistically significant in Yartseva's multivariate regressions, and the economic magnitude is large (5-23pp return differential). However, this is a single study. The CMA factor (0.17-0.29% monthly in Europe, stronger in small caps, per Bermejo et al.) provides corroborating evidence from the opposite direction -- conservative investment generally outperforms, consistent with the idea that most aggressive investment destroys value.
**Where it Works:** US equities (Yartseva); likely applicable in European markets given CMA evidence. Most relevant for growth-phase small caps where management is making bet-the-company capital allocation decisions.
**Where it Fails:** Lumpy investment (acquisitions, factory builds) can make single-year measurement noisy. EBITDA growth may lag investment by 1-2 years, creating false negatives for companies in the middle of a legitimate expansion. Does not capture investment quality (a company may grow assets and EBITDA through low-ROIC acquisitions).
**Implications for Strategy:** After the initial FCF/Value/GPA screens, apply an investment quality filter. For any company with asset growth above 15%, require that trailing EBITDA growth be at least 50% of asset growth. This separates value-creating growth from empire-building. Consider a 2-year lookback to smooth lumpy investment.
**Open Questions:** Optimal lag structure (contemporaneous vs. 1-year-lagged EBITDA growth). Whether the interaction works symmetrically (i.e., does shrinking assets with stable EBITDA also predict well?). Whether free cash flow growth is a better conditioning variable than EBITDA growth.

---

## 7. Iterative Multi-Factor Strategy (Value -> Profitability -> Momentum)

**Title:** Sequential Factor Layering
**Source:** Bermejo et al. (2021) -- Iterative strategy achieving Sharpe 0.94, alpha 5.65% per annum
**Key Insight:** Applying factors sequentially -- first screening for value, then filtering for profitability within the value bucket, then applying momentum within the profitable-value bucket -- produces dramatically better risk-adjusted returns than any single factor alone or a simple composite. The iterative approach achieves a Sharpe ratio of 0.94 and a Fama-French 3-factor alpha of 5.65% per annum in European data. This works because each layer removes a different type of loser: value removes overpriced stocks, profitability removes value traps, and momentum removes dead-money stocks with no catalyst.
**Measurable Signal:** Step 1 (Value): Rank by EV/EBITDA, keep the cheapest tercile. Step 2 (Profitability): Within that tercile, rank by GPA, keep the top half. Step 3 (Momentum): Within the remaining set, rank by 12-1 month momentum, keep the top half. The final portfolio is the intersection of cheap, profitable, and trending.
**Evidence Strength:** Strong for the combined strategy (Sharpe 0.94, alpha 5.65% in Bermejo et al. 2021). Note that this is an in-sample result for European markets; out-of-sample and post-2012 decay is flagged.
**Where it Works:** European equities (tested directly). Likely US equities given the individual factor evidence. Small-to-mid caps where factor signals are strongest.
**Where it Fails:** Post-2012 factor alpha decay noted by Bermejo et al. suggests diminishing returns, possibly from factor crowding. The sequential approach reduces the investable universe aggressively -- the final portfolio may be very concentrated (20-40 stocks), increasing idiosyncratic risk. Transaction costs from momentum-driven rebalancing can erode alpha.
**Implications for Strategy:** This is the structural backbone of the screening methodology. Screen sequentially: FCF Yield / EV/EBITDA (value) -> GPA (profitability) -> Momentum or contrarian inflection (timing). Layer the Yartseva-specific signals (B/M > 0.40, investment-EBITDA interaction, near 52-week low) as additional filters or tiebreakers.
**Open Questions:** Optimal rebalancing frequency (monthly vs. quarterly). Whether the Yartseva contrarian signal should replace classical momentum at step 3 for multibagger-specific hunting. How many stocks the final portfolio should hold to balance concentration (for multibagger upside) against diversification (for drawdown control).

---

## Appendix: Factor Evidence Summary Table

| Factor | Primary Source | t-stat or Equivalent | Market | Cap Range |
|---|---|---|---|---|
| FCF Yield | Yartseva (2025) | Coeff 46-82 | US | All, esp. small |
| GPA | Bermejo et al. (2021) | t = 10.88 | Europe | All, esp. small |
| Momentum (12-1) | Bermejo et al. (2021) / Harvey et al. (2016) | t = 2.62 / survives 0.1% | Europe / Global | All |
| Contrarian (near 52wk low) | Yartseva (2025) | Significant in regression | US | Small |
| Value (B/M) | Harvey et al. (2016) / Yartseva (2025) | Survives 0.1% / B/M>0.40 sig | Global / US | All |
| Value (EV/EBITDA) | Bermejo et al. (2021) | Index 25.21 (top rank) | Europe | All |
| Small Cap (universe filter) | Yartseva (2025) | Descriptive ($348m median) | US | Micro-small |
| Inv x EBITDA Growth | Yartseva (2025) | Significant interaction | US | Small-mid |
| Iterative Strategy | Bermejo et al. (2021) | Sharpe 0.94, alpha 5.65% | Europe | All |

---

## Notes on Interest Rate Sensitivity

Yartseva (2025) finds that rising interest rates reduce multibagger returns by 8-12 percentage points. This is not a stock-selection factor but a regime variable. Implications: weight the portfolio more aggressively during rate-cutting or stable-rate environments; reduce exposure or tighten screens during tightening cycles. Consider monitoring the yield curve slope or central bank forward guidance as a top-down overlay.
