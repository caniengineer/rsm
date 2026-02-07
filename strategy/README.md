# UK Multi-Bagger Factor Investing Strategy

**An Evidence-Based Approach to Identifying Exceptional UK Equities**

---

## Executive Summary

This is a **UK small-cap quality-value-momentum factor strategy** with a conviction hold carve-out. It is not a multibagger identification system -- no factor screen can reliably predict which specific stocks will deliver extreme returns. Instead, the strategy systematically buys cheap, profitable, trending UK small caps, generating factor-driven alpha while incidentally increasing exposure to the population from which multibaggers emerge.

### The Core Problem

Most stocks destroy value. Bessembinder (2018, 2023) demonstrates that 57.4% of all US stocks underperform Treasury bills over their lifetimes, and only 2-4% of listed companies account for virtually all net stock market wealth creation. Internationally, the picture is worse — only 42.4% of stocks outperform bills across 57 countries. The base rate for identifying a multi-bagger is vanishingly small, and no combination of factor screens has been demonstrated to raise this probability to reliably actionable levels.

### What the Evidence Supports

After analysis of Novy-Marx (2013), Harvey, Liu & Zhu (2016), Bermejo et al. (2021), Yartseva (2025), and extensive UK/European factor studies:

**Factors with strong multi-source validation (used as core factors):**
1. **Gross Profitability (GP/Assets)** — Most robust quality metric internationally (Novy-Marx 2013, Bermejo 2021 FF3 alpha 4.23% t=10.88, Cotter & McGeever 2018 UK persistence). Weight: 30%.
2. **Valuation (EV/EBITDA)** — Strongest European value metric (Bermejo 2021). Value survives harshest multiple-testing corrections (Harvey et al. 2016). Weight: 25%.
3. **Momentum (12-1 month)** — Strongest pure European factor (Sharpe 0.80, Bermejo). Confirmed in UK post-1977 (Liu et al. 1999). Weight: 20%.

**Factors with partial support (used as secondary checks):**
4. **Free Cash Flow Yield** — Cash-based quality check (Fama & French 2018). Yartseva (2025) reports it as the strongest multibagger predictor, but this is a single unreplicated US study. Weight: 15%.
5. **Small Cap Size** — Universe filter, not a return predictor (UK size premium reversed post-publication). Weight: 10%.

**Factors excluded (insufficient independent evidence):**
- Investment-EBITDA interaction (Yartseva only, no replication)
- Contrarian momentum / near 52-week lows (Yartseva only, contradicts standard momentum)
- Interest rate regime overlay (Yartseva only, US-specific)

**Factors correctly rejected (statistically insignificant):**
- Earnings growth, dividend policy, debt levels, share buybacks, analyst coverage, R&D intensity, Altman Z-scores (all: Yartseva 2025)

### The Strategy

Two-tier portfolio targeting UK-listed equities (Main Market + AIM) with market caps of GBP 30m-1,000m:

**Tier 1 — Core Factor Portfolio (80% of capital, 16-24 positions):**
1. **Universe**: ~250-400 eligible UK stocks after liquidity and sector filters
2. **Profitability Gate**: GP/Assets above 40th percentile
3. **Cash Flow Gate**: Positive FCF, FCF yield above median
4. **Valuation Filter**: EV/EBITDA below 60th percentile
5. **Scoring & Selection**: Composite score (GP/Assets 30%, EV/EBITDA 25%, Momentum 20%, FCF Yield 15%, Size 10%)
6. Semi-annual rebalancing. Average holding period ~3 years.

**Tier 2 — Conviction Holds (20% of capital, 4-6 positions):**
- Drawn from Tier 1 based on strongest fundamentals + qualitative business quality
- Exempt from factor-based rebalancing
- Held until business thesis breaks (5-10+ years)
- This is where multibagger compounding can occur — if it occurs at all

**Target return profile**: 1-3% net annual alpha over FTSE Small Cap Index from Tier 1 factor exposure. Tier 2 returns are unpredictable by design. No specific multibagger return promise is made.

### Critical Risks and Honest Limitations

This strategy has significant risks that are documented in detail:

1. **Survivorship bias** — Yartseva studied only successful 10x stocks; the false-positive rate is unknown
2. **Base rate problem** — Even with perfect screens, only 2-4% of stocks create meaningful wealth
3. **US-to-UK translation** — All Yartseva findings are US-only; UK market structure differs materially
4. **Factor decay** — Alphas approaching zero post-2012 (Bermejo); 58% lower post-publication (McLean & Pontiff)
5. **Liquidity constraints** — AIM spreads of 5-10x FTSE 100; stamp duty 0.5% on Main Market
6. **UK de-equitisation** — 20% fewer listed companies in 5 years; persistent fund outflows

### The Final Check

*"If this strategy fails, can I clearly explain why using the papers?"*

**Yes.** The strategy would fail if:
- Survivorship bias in Yartseva overstates the predictive power of the identified factors (base-rate probability remains too low even with correct factor tilts)
- Factor premiums continue their post-2012 decay toward zero (Bermejo's documented trend)
- UK-specific implementation costs (stamp duty, AIM spreads, illiquidity) consume the gross factor premiums
- The 2009-2024 bull market period that generated Yartseva's sample is not representative of future market regimes
- Concentrated UK small-cap exposure coincides with continued de-equitisation and fund outflows

Each of these failure modes is documented, probability-assessed, and has specific monitoring triggers in the risk documentation.

---

## Document Index

| File | Purpose |
|------|---------|
| [literature_review.md](literature_review.md) | Paper-by-paper synthesis with evidence mapping |
| [uk_european_factor_literature_review.md](uk_european_factor_literature_review.md) | Deep-dive UK/European empirical factor evidence |
| [validated_factors.md](validated_factors.md) | Factors accepted into the strategy with measurement formulas |
| [rejected_or_weak_factors.md](rejected_or_weak_factors.md) | Factors rejected or classified as weak with reasoning |
| [strategy_design_plan.md](strategy_design_plan.md) | Complete strategy design with implementation details |
| [risks_and_failure_modes.md](risks_and_failure_modes.md) | Adversarial risk analysis and failure mode catalogue |
| [assumptions_and_unknowns.md](assumptions_and_unknowns.md) | Explicit assumptions, evidence gaps, and unknowns |

---

## Evidence Classification System

Throughout all documents, evidence is classified as:

| Label | Meaning |
|-------|---------|
| **[CORE EVIDENCE]** | From the four mandatory source papers |
| **[DIRECT EVIDENCE]** | From specific academic papers with citations |
| **[SUPPORTING EVIDENCE]** | From closely related research |
| **[RELATED EVIDENCE]** | From adjacent academic work |
| **[INFERENCE]** | Reasonable logical extension of evidence |
| **[SPECULATIVE]** | Beyond what evidence directly supports |
| **[DATA SUPPORTS]** | Directly supported by empirical data |
| **[REASONABLE ASSUMPTION]** | Logical extension of validated findings |

---

## Mandatory Source Papers Analysed

1. **Yartseva (2025)** — "The Alchemy of Multibagger Stocks: An Empirical Investigation of Factors That Drive Outperformance." CAFE Working Paper No. 33, Birmingham City University. *464 multibagger stocks, 150+ variables, GMM estimation.*

2. **Harvey, Liu & Zhu (2016)** — "...and the Cross-Section of Expected Returns." Review of Financial Studies, 29(1): 5-68. *316 factors, multiple testing framework, t > 3.0 threshold.*

3. **Bermejo et al. (2021)** — "Factor investing: A stock selection methodology for the European equity market." Heliyon, 7(10): e08168. *600 European large-caps, iterative multi-factor strategies, Sharpe 0.94.*

4. **UK/European Empirical Factor Studies** — Including Dimson, Marsh & Staunton (DMS database), Gregory, Tharyan & Christidis (2013), Novy-Marx (2013), Asness, Moskowitz & Pedersen (2013), Daniel & Moskowitz (2016), Bessembinder (2018, 2023), and 20+ additional papers.

---

## Key Insight Summary

| # | Insight | Source | Confidence | Strategy Implication |
|---|---------|--------|------------|---------------------|
| 1 | Gross Profitability (GP/Assets) is the most robust quality metric internationally | Novy-Marx 2013, Bermejo 2021, Cotter & McGeever 2018 | High | Core factor (30% weight) |
| 2 | Only 9 of 313 factors survive rigorous multiple-testing adjustment (t > 3.0) | Harvey et al. 2016 | High | Use only multi-validated factors |
| 3 | Iterative multi-factor combinations (value→quality→momentum) achieve Sharpe 0.94 | Bermejo et al. 2021 | High (European large-cap) | Structural approach adopted |
| 4 | 57.4% of stocks underperform Treasury bills over their lifetimes | Bessembinder 2018 | High | Diversification is essential |
| 5 | Earnings growth does NOT predict multi-bagger outcomes | Yartseva 2025 | High (counterintuitive) | Excluded from model |
| 6 | UK size premium reversed post-publication (+6% → -6%) | Dimson & Marsh 1999 | High | Size as universe filter only |
| 7 | Factor alphas are decaying toward zero post-2012 | Bermejo 2021 | Moderate | Alpha expectations reduced to 1-3% net |
| 8 | UK AIM market has structural liquidity constraints (5-10x wider spreads) | Multiple sources | High | Strict liquidity filters applied |
| 9 | Factor returns decline 58% post-publication | McLean & Pontiff 2016 | High | All gross premiums discounted |
| 10 | Investment-EBITDA interaction is unreplicated | Yartseva 2025 only | Low | Excluded from scoring model |
