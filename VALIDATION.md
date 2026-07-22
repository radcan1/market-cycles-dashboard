# Validation scorecard

Generated for as-of date 2026-07-22.

## What this measures

For each indicator, on each asset, in each currency, this asks one question: every time the indicator crossed into its claimed zone, what happened over the following twelve months, compared with what would have happened at a randomly chosen moment in the same era? An indicator that cannot beat that comparison is rejected and takes no part in the dashboard's scores, however well known it is.

Admission requires at least 5 independent firings, a positive edge, a hit rate at least 10% above the base rate, and a 90% confidence interval on the edge that excludes zero. The interval comes from a block bootstrap that resamples whole firings, because overlapping forward windows are not independent observations and treating them as though they were would overstate confidence.

## Summary

- Combinations tested: 1180
- Admitted: 35
- Admitted at half weight: 1
- Rejected: 449
- Not enough data to judge: 695

Roughly 3% of the combinations tested survived. A scorecard where everything passed would be evidence that the engine is not discriminating, not evidence that the indicators are good.

## The multiple-testing problem

485 combinations were tested statistically and 36 survived. Across that many independent tests at a 90% confidence level, roughly 24 would be expected to pass by chance alone even if every indicator were worthless.

36 survivors is 1.5 times the chance expectation of 24, so the admitted set as a whole is unlikely to be an artefact of the number of tests run. Individual entries resting on few firings should still be treated as provisional.

## Indicators that failed everywhere

These earned no place on any asset in any currency. They remain configured and computed, and they still appear in the per-asset tables on the dashboard, but they contribute nothing to any score.

- **aaii spread z** — rejected on all 8 combinations tested. Worst case for it: on us_large_cap in USD, the edge of +1.1% is not distinguishable from zero: the 90% interval runs -6.3% to +8.2% across only 24 firings
- **blowoff reversal** — rejected on all 60 combinations tested. Worst case for it: on biotech in USD, hit rate 33% against a base rate of 45% is only -11%, short of the 10% required
- **bullish divergence deep** — rejected on all 60 combinations tested. Worst case for it: on japan in USD, hit rate 55% against a base rate of 50% is only +5%, short of the 10% required
- **cape percentile** — rejected on all 4 combinations tested. Worst case for it: on us_large_cap in USD, no edge: outcomes after this signal averaged +13.1% against an unconditional +8.8%, so the signal added nothing
- **copper gold ratio** — rejected on all 16 combinations tested. Worst case for it: on equities_global in USD, hit rate 50% against a base rate of 54% is only -4%, short of the 10% required
- **cot commercial percentile** — rejected on all 20 combinations tested. Worst case for it: on gold in USD, no edge: outcomes after this signal averaged +21.2% against an unconditional +12.9%, so the signal added nothing
- **crypto fear greed** — rejected on all 4 combinations tested. Worst case for it: on bitcoin in USD, hit rate 30% against a base rate of 37% is only -7%, short of the 10% required
- **defensive leadership** — rejected on all 2 combinations tested. Worst case for it: on us_large_cap in USD, hit rate 46% against a base rate of 41% is only +5%, short of the 10% required
- **equal weight breadth** — rejected on all 2 combinations tested. Worst case for it: on us_large_cap in USD, no edge: outcomes after this signal averaged +16.4% against an unconditional +12.1%, so the signal added nothing
- **fii flow z** — rejected on all 4 combinations tested. Worst case for it: on india in USD, the edge of +14.1% is not distinguishable from zero: the 90% interval runs -13.7% to +39.9% across only 6 firings
- **financial stress percentile** — never had enough independent firings to judge on any of the 12 combinations tested
- **gold cpi ratio** — never had enough independent firings to judge on any of the 4 combinations tested
- **gold real yield** — rejected on all 4 combinations tested. Worst case for it: on gold in USD, no edge: outcomes after this signal averaged +13.7% against an unconditional +10.5%, so the signal added nothing
- **gold silver ratio** — rejected on all 4 combinations tested. Worst case for it: on silver in USD, hit rate 30% against a base rate of 40% is only -10%, short of the 10% required
- **india gold premium** — rejected on all 4 combinations tested. Worst case for it: on gold in USD, no edge: outcomes after this signal averaged +4.6% against an unconditional +9.6%, so the signal added nothing
- **india vix percentile** — rejected on all 4 combinations tested. Worst case for it: on india in USD, the edge of +11.0% is not distinguishable from zero: the 90% interval runs -9.3% to +30.0% across only 9 firings
- **inr stress z** — rejected on all 2 combinations tested. Worst case for it: on india in USD, hit rate 50% against a base rate of 40% is only +10%, short of the 10% required
- **margin debt yoy** — rejected on all 2 combinations tested. Worst case for it: on us_large_cap in USD, hit rate 50% against a base rate of 44% is only +6%, short of the 10% required
- **mortgage momentum** — never had enough independent firings to judge on any of the 4 combinations tested
- **nifty pe percentile** — rejected on all 4 combinations tested. Worst case for it: on india in USD, the edge of +3.6% is not distinguishable from zero: the 90% interval runs -6.7% to +12.7% across only 9 firings
- **permits yoy** — never had enough independent firings to judge on any of the 4 combinations tested
- **retail washout** — never had enough independent firings to judge on any of the 60 combinations tested
- **sahm rule** — rejected on all 4 combinations tested. Worst case for it: on us_large_cap in USD, hit rate 55% against a base rate of 45% is only +9%, short of the 10% required
- **stocks bonds ratio** — rejected on all 8 combinations tested. Worst case for it: on equities_global in USD, no edge: outcomes after this signal averaged +13.8% against an unconditional +11.0%, so the signal added nothing
- **vix term backwardation** — rejected on all 4 combinations tested. Worst case for it: on us_large_cap in USD, no edge: outcomes after this signal averaged +9.5% against an unconditional +12.1%, so the signal added nothing
- **volume capitulation** — rejected on all 60 combinations tested. Worst case for it: on us_large_cap in USD, hit rate 59% against a base rate of 59% is only +0%, short of the 10% required
- **yield curve uninvert** — rejected on all 4 combinations tested. Worst case for it: on us_large_cap in USD, no edge: outcomes after this signal averaged +12.2% against an unconditional +12.0%, so the signal added nothing

## Results by indicator

### aaii spread z

The AAII weekly survey's bullish minus bearish fraction, as a z-score of its trailing five years. Individual investors surveyed since 1987; the survey's baseline optimism has drifted across decades, which is why the reading is relative to its own recent history rather than an absolute level. Extreme bullishness is the top-side condition.

Tested on 8 asset and currency combinations; 0 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| Global equities | INR | bottom | 11 | 82% | 49% | +4.9% | -3.9% to +13.5% | +7.6% (7) | rejected |
| Global equities | INR | top | 5 | 80% | 50% | +5.3% | -2.4% to +11.4% | +1.5% (2) | rejected |
| Global equities | USD | bottom | 11 | 73% | 53% | +6.2% | -4.3% to +17.2% | +7.6% (7) | rejected |
| Global equities | USD | top | 5 | 80% | 45% | +7.2% | -3.2% to +16.6% | +2.6% (2) | rejected |
| US large cap | INR | bottom | 14 | 71% | 51% | +0.2% | -8.8% to +8.4% | +4.4% (7) | rejected |
| US large cap | INR | top | 5 | 80% | 52% | +2.2% | -4.9% to +9.0% | -0.8% (2) | rejected |
| US large cap | USD | bottom | 24 | 67% | 56% | +1.1% | -6.3% to +8.2% | +4.5% (7) | rejected |
| US large cap | USD | top | 12 | 58% | 44% | +1.6% | -6.6% to +8.9% | +0.4% (2) | rejected |

### blowoff reversal

The first violent crack after a parabolic run — the silver 2011 and bitcoin 2021 species of top, where parabolas break rather than consolidate. Pre-registered: trailing-year return above its 95th percentile of the asset's own history within the past quarter, then a fall of 10% or more inside five sessions. Fires days after the exact peak by design; the claim under test is that what follows such a crack is historically far worse than a normal year.

Tested on 60 asset and currency combinations; 0 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| Biotech | INR | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Biotech | USD | top | 6 | 33% | 45% | +4.2% | -16.6% to +25.1% | +20.4% (3) | rejected |
| Bitcoin | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Bitcoin | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| China equities | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| China equities | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Broad commodities | INR | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Broad commodities | USD | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer discretionary | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer discretionary | USD | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer staples | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer staples | USD | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | USD | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US investment-grade credit | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US investment-grade credit | USD | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Crude oil | INR | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Crude oil | USD | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US dollar regime | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US dollar regime | USD | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Emerging markets | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Emerging markets | USD | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Energy | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Energy | USD | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | USD | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Europe equities | INR | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Europe equities | USD | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Financials | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Financials | USD | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Gold | INR | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Gold | USD | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Healthcare | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Healthcare | USD | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India equities | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India equities | USD | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India midcap | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India midcap | USD | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Industrials | INR | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Industrials | USD | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Japan equities | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Japan equities | USD | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Magnificent 7 | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Magnificent 7 | USD | top | 5 | 40% | 48% | -0.4% | -35.9% to +36.5% | -19.9% (1) | rejected |
| Global real estate (REITs) | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global real estate (REITs) | USD | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Semiconductors | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Semiconductors | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Silver | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Silver | USD | top | 5 | 60% | 57% | -0.5% | -20.8% to +19.7% | n/a | rejected |
| US small cap | INR | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US small cap | USD | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Technology | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Technology | USD | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US Treasuries, long duration | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US Treasuries, long duration | USD | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Utilities | INR | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Utilities | USD | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |

### bullish divergence deep

Weekly bullish divergence counted only deep inside a hole: from at least 25% below the one-year high, price makes a lower low while weekly momentum makes a higher low — the market falling with less force. Pre-registered from the same independent framework (60% precision there, its highest); the ungated monthly cousin in this project was rejected on 73 of 75 combinations, so the hole gate is precisely the difference under test.

Tested on 60 asset and currency combinations; 0 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| Biotech | INR | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Biotech | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Bitcoin | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Bitcoin | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| China equities | INR | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| China equities | USD | bottom | 5 | 40% | 48% | -7.8% | -22.5% to +5.6% | -6.0% (5) | rejected |
| Broad commodities | INR | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Broad commodities | USD | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer discretionary | INR | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer discretionary | USD | bottom | 5 | 80% | 55% | +20.4% | -4.1% to +48.0% | +15.7% (2) | rejected |
| Consumer staples | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer staples | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US investment-grade credit | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US investment-grade credit | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Crude oil | INR | bottom | 7 | 71% | 48% | +5.9% | -11.9% to +22.6% | -5.3% (5) | rejected |
| Crude oil | USD | bottom | 8 | 75% | 46% | +8.3% | -11.3% to +29.3% | -14.0% (4) | rejected |
| US dollar regime | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US dollar regime | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Emerging markets | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Emerging markets | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Energy | INR | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Energy | USD | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Europe equities | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Europe equities | USD | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Financials | INR | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Financials | USD | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Gold | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Gold | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Healthcare | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Healthcare | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India equities | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India equities | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India midcap | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India midcap | USD | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Industrials | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Industrials | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Japan equities | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Japan equities | USD | bottom | 11 | 55% | 50% | +9.7% | -2.2% to +22.3% | +14.8% (1) | rejected |
| Magnificent 7 | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Magnificent 7 | USD | bottom | 7 | 43% | 50% | -5.5% | -25.8% to +14.2% | -0.1% (1) | rejected |
| Global real estate (REITs) | INR | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global real estate (REITs) | USD | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Semiconductors | INR | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Semiconductors | USD | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Silver | INR | bottom | 5 | 40% | 37% | -1.4% | -24.9% to +23.9% | +16.8% (1) | rejected |
| Silver | USD | bottom | 7 | 57% | 41% | +20.2% | -5.4% to +46.4% | +41.2% (3) | rejected |
| US small cap | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US small cap | USD | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Technology | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Technology | USD | bottom | 5 | 20% | 52% | -21.6% | -41.4% to +0.2% | +17.1% (1) | rejected |
| US Treasuries, long duration | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US Treasuries, long duration | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | USD | bottom | 10 | 50% | 54% | -8.8% | -27.0% to +8.2% | n/a | rejected |
| Utilities | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Utilities | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |

### cape percentile

Shiller's cyclically adjusted P/E for the S&P 500 — price against ten years of inflation-adjusted earnings, monthly since 1871. The valuation measure with the longest record in finance, containing 1901, 1929, 1966, 2000 and everything between: the one valuation signal with enough independent episodes to settle whether extremes actually time anything.

Tested on 4 asset and currency combinations; 0 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| US large cap | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | INR | top | 9 | 44% | 50% | +0.0% | -6.8% to +7.2% | -6.1% (5) | rejected |
| US large cap | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | USD | top | 14 | 29% | 47% | -4.4% | -12.3% to +4.0% | -9.8% (5) | rejected |

### capitulation flush

A one-day selling climax counted only deep inside a hole: price at least 25% below its one-year high, and on the day at least two of — drawdown past 35%, daily RSI(14) under 35, volume above 2.5 times its own norm. Definition pre-registered verbatim from an independent framework where it survived an eleven-year test at twice chance; the hypothesis here is that the hole gate is what separates it from this project's own rejected, ungated volume-capitulation signal.

Tested on 60 asset and currency combinations; 2 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| Biotech | INR | bottom | 9 | 67% | 52% | +30.8% | +6.4% to +55.5% | +27.6% (7) | admitted |
| Biotech | USD | bottom | 10 | 60% | 54% | +25.1% | +2.3% to +48.8% | +27.4% (7) | rejected |
| Bitcoin | INR | bottom | 10 | 10% | 33% | -91.8% | -129.6% to -51.1% | -91.8% (10) | rejected |
| Bitcoin | USD | bottom | 10 | 10% | 33% | -98.8% | -134.6% to -60.7% | -98.8% (10) | rejected |
| China equities | INR | bottom | 5 | 0% | 48% | -12.6% | -21.2% to -5.1% | -11.1% (5) | rejected |
| China equities | USD | bottom | 7 | 43% | 46% | -2.9% | -14.6% to +9.6% | -6.8% (6) | rejected |
| Broad commodities | INR | bottom | 5 | 20% | 40% | -6.7% | -22.6% to +12.4% | +9.5% (2) | rejected |
| Broad commodities | USD | bottom | 5 | 20% | 42% | -7.9% | -25.2% to +12.8% | +8.7% (2) | rejected |
| Consumer discretionary | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer discretionary | USD | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer staples | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer staples | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US investment-grade credit | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US investment-grade credit | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Crude oil | INR | bottom | 14 | 36% | 48% | +3.6% | -19.7% to +28.9% | +3.5% (9) | rejected |
| Crude oil | USD | bottom | 12 | 42% | 46% | -2.4% | -20.8% to +16.9% | -2.3% (6) | rejected |
| US dollar regime | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US dollar regime | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Emerging markets | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Emerging markets | USD | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Energy | INR | bottom | 5 | 60% | 46% | +5.5% | -3.8% to +16.1% | +12.4% (3) | rejected |
| Energy | USD | bottom | 8 | 50% | 50% | +5.0% | -5.5% to +16.5% | +14.0% (3) | rejected |
| Global equities | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Europe equities | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Europe equities | USD | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Financials | INR | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Financials | USD | bottom | 6 | 67% | 53% | +5.0% | -26.8% to +36.6% | +61.3% (1) | rejected |
| Gold | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Gold | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Healthcare | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Healthcare | USD | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India equities | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India equities | USD | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India midcap | INR | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India midcap | USD | bottom | 6 | 50% | 40% | +35.0% | -11.4% to +84.2% | +105.5% (1) | rejected |
| Industrials | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Industrials | USD | bottom | 5 | 60% | 56% | +14.8% | -8.2% to +40.0% | +69.3% (1) | rejected |
| Japan equities | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Japan equities | USD | bottom | 11 | 55% | 50% | +2.6% | -6.5% to +12.1% | +14.1% (1) | rejected |
| Magnificent 7 | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Magnificent 7 | USD | bottom | 8 | 50% | 50% | -16.2% | -35.3% to +4.1% | +20.5% (2) | rejected |
| Global real estate (REITs) | INR | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global real estate (REITs) | USD | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Semiconductors | INR | bottom | 5 | 40% | 50% | +17.7% | -22.1% to +58.2% | +61.0% (2) | rejected |
| Semiconductors | USD | bottom | 9 | 44% | 48% | +4.3% | -23.3% to +37.1% | +50.2% (2) | rejected |
| Silver | INR | bottom | 9 | 44% | 39% | +3.8% | -14.1% to +23.8% | +26.1% (3) | rejected |
| Silver | USD | bottom | 11 | 45% | 42% | -4.5% | -18.3% to +10.2% | +13.0% (3) | rejected |
| US small cap | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US small cap | USD | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Technology | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Technology | USD | bottom | 6 | 33% | 53% | -13.8% | -46.5% to +20.7% | +63.4% (1) | rejected |
| US Treasuries, long duration | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US Treasuries, long duration | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | USD | bottom | 12 | 58% | 54% | -2.7% | -19.3% to +13.3% | +46.9% (1) | rejected |
| Utilities | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Utilities | USD | bottom | 5 | 80% | 56% | +14.2% | +4.3% to +25.1% | +33.0% (1) | admitted |

### copper gold ratio

Murphy's copper-to-gold growth-versus-fear gauge, scored as a mean-reversion extreme: copper over gold, ranked against its own history. Bottom percentiles mark maxed growth fear (bottom-side for cyclical risk assets); top percentiles mark growth euphoria. Applied to cyclical equity slots. Shown in the regime block for context; tested here as a signal.

Tested on 16 asset and currency combinations; 0 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| Global equities | INR | bottom | 8 | 75% | 49% | +3.6% | -3.3% to +10.4% | -0.2% (6) | rejected |
| Global equities | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | USD | bottom | 8 | 50% | 54% | +0.2% | -5.6% to +6.2% | -3.1% (6) | rejected |
| Global equities | USD | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Industrials | INR | bottom | 8 | 50% | 43% | +3.7% | -5.3% to +13.3% | -1.6% (6) | rejected |
| Industrials | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Industrials | USD | bottom | 8 | 50% | 50% | +0.1% | -7.2% to +7.1% | -4.4% (6) | rejected |
| Industrials | USD | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Semiconductors | INR | bottom | 8 | 62% | 46% | +3.7% | -11.5% to +20.0% | +1.0% (6) | rejected |
| Semiconductors | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Semiconductors | USD | bottom | 8 | 50% | 47% | -0.5% | -14.1% to +14.1% | -2.7% (6) | rejected |
| Semiconductors | USD | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | INR | bottom | 8 | 62% | 48% | +3.7% | -4.0% to +12.5% | -1.3% (6) | rejected |
| US large cap | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | USD | bottom | 8 | 38% | 54% | +0.0% | -5.7% to +5.8% | -4.2% (6) | rejected |
| US large cap | USD | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |

### coppock

The Coppock curve: a 10-period weighted moving average of the sum of the 14-month and 11-month rates of change, computed on monthly closes. Designed in 1962 specifically to mark major bottoms, and it is used here only for that — the flag is raised when the curve turns up from below zero.

Tested on 60 asset and currency combinations; 2 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| Biotech | INR | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Biotech | USD | bottom | 5 | 40% | 55% | -5.6% | -20.2% to +12.1% | +4.7% (4) | rejected |
| Bitcoin | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Bitcoin | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| China equities | INR | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| China equities | USD | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Broad commodities | INR | bottom | 5 | 20% | 40% | +1.0% | -11.8% to +16.5% | -0.6% (4) | rejected |
| Broad commodities | USD | bottom | 9 | 33% | 42% | -2.4% | -13.9% to +10.0% | +1.5% (5) | rejected |
| Consumer discretionary | INR | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer discretionary | USD | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer staples | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer staples | USD | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US investment-grade credit | INR | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US investment-grade credit | USD | bottom | 6 | 50% | 49% | +2.6% | -0.1% to +5.6% | +4.3% (3) | rejected |
| Crude oil | INR | bottom | 9 | 56% | 48% | +10.3% | -12.9% to +33.7% | -3.5% (5) | rejected |
| Crude oil | USD | bottom | 10 | 50% | 50% | +9.9% | -11.3% to +30.4% | -3.9% (5) | rejected |
| US dollar regime | INR | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US dollar regime | USD | bottom | 6 | 50% | 48% | -0.5% | -7.3% to +6.4% | +1.5% (3) | rejected |
| Emerging markets | INR | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Emerging markets | USD | bottom | 7 | 57% | 52% | +0.6% | -7.4% to +7.9% | -2.2% (4) | rejected |
| Energy | INR | bottom | 5 | 40% | 46% | -8.4% | -27.5% to +13.9% | -6.1% (4) | rejected |
| Energy | USD | bottom | 7 | 29% | 49% | -4.2% | -17.6% to +11.4% | +2.0% (3) | rejected |
| Global equities | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | USD | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Europe equities | INR | bottom | 5 | 40% | 47% | -12.2% | -26.2% to -1.1% | -1.1% (3) | rejected |
| Europe equities | USD | bottom | 7 | 43% | 51% | +0.3% | -9.0% to +9.7% | -1.1% (5) | rejected |
| Financials | INR | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Financials | USD | bottom | 8 | 62% | 52% | +4.5% | -6.0% to +14.2% | +1.8% (4) | rejected |
| Gold | INR | bottom | 6 | 33% | 38% | -14.8% | -23.7% to -6.7% | -6.1% (3) | rejected |
| Gold | USD | bottom | 6 | 33% | 42% | -6.0% | -13.0% to +0.9% | -4.9% (5) | rejected |
| Healthcare | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Healthcare | USD | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India equities | INR | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India equities | USD | bottom | 6 | 67% | 40% | +5.6% | -8.1% to +18.1% | +7.1% (4) | rejected |
| India midcap | INR | bottom | 5 | 60% | 42% | +20.3% | +1.4% to +39.6% | +23.9% (3) | admitted |
| India midcap | USD | bottom | 7 | 57% | 42% | +13.5% | -7.5% to +34.8% | +27.8% (4) | rejected |
| Industrials | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Industrials | USD | bottom | 6 | 67% | 53% | +3.6% | -7.2% to +13.4% | +6.9% (3) | rejected |
| Japan equities | INR | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Japan equities | USD | bottom | 17 | 59% | 51% | +2.6% | -6.8% to +11.4% | +3.6% (3) | rejected |
| Magnificent 7 | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Magnificent 7 | USD | bottom | 6 | 83% | 50% | +10.7% | -11.3% to +26.6% | +26.9% (1) | rejected |
| Global real estate (REITs) | INR | bottom | 5 | 40% | 49% | -7.2% | -28.3% to +9.0% | +5.4% (3) | rejected |
| Global real estate (REITs) | USD | bottom | 6 | 67% | 45% | +3.3% | -19.3% to +24.7% | +13.0% (4) | rejected |
| Semiconductors | INR | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Semiconductors | USD | bottom | 7 | 71% | 48% | +10.9% | -7.6% to +28.6% | +28.7% (2) | rejected |
| Silver | INR | bottom | 9 | 22% | 39% | -15.2% | -25.1% to -5.9% | -8.9% (5) | rejected |
| Silver | USD | bottom | 8 | 38% | 41% | -13.6% | -25.1% to -2.0% | -11.1% (5) | rejected |
| US small cap | INR | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US small cap | USD | bottom | 7 | 71% | 49% | +15.3% | +4.5% to +26.0% | +7.5% (4) | admitted |
| Technology | INR | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Technology | USD | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US Treasuries, long duration | INR | bottom | 7 | 14% | 42% | -5.2% | -17.5% to +8.6% | -7.0% (5) | rejected |
| US Treasuries, long duration | USD | bottom | 9 | 44% | 49% | -2.3% | -10.9% to +6.4% | -4.4% (6) | rejected |
| US large cap | INR | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | USD | bottom | 27 | 63% | 53% | +3.0% | -5.1% to +10.3% | +14.8% (1) | rejected |
| Utilities | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Utilities | USD | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |

### cot commercial percentile

CFTC commercial net positioning as a percentile of its trailing three years. Commercials are the hedgers with physical business behind their contracts; the classic contrarian reading is that their extremes mark turns — unusually net long near price bottoms, unusually net short near tops. Weekly data from the CFTC's public files back to 1995. Inverted polarity: a high percentile (commercials very long) is the bottom-side condition, so top_zone is the percentile at or below which the top condition holds.

Tested on 20 asset and currency combinations; 0 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| Crude oil | INR | bottom | 6 | 67% | 47% | +9.1% | -10.5% to +26.1% | +1.8% (3) | rejected |
| Crude oil | INR | top | 14 | 57% | 53% | +3.9% | -10.6% to +18.0% | -1.2% (3) | rejected |
| Crude oil | USD | bottom | 9 | 67% | 46% | +5.2% | -9.0% to +19.6% | -1.0% (3) | rejected |
| Crude oil | USD | top | 16 | 56% | 54% | +3.4% | -10.5% to +16.7% | -2.0% (3) | rejected |
| US dollar regime | INR | bottom | 10 | 60% | 45% | +3.5% | -1.9% to +8.6% | +2.9% (6) | rejected |
| US dollar regime | INR | top | 8 | 12% | 50% | -7.4% | -12.7% to -2.0% | -15.6% (2) | rejected |
| US dollar regime | USD | bottom | 10 | 40% | 48% | +1.3% | -2.7% to +5.9% | +0.9% (6) | rejected |
| US dollar regime | USD | top | 8 | 50% | 53% | -2.5% | -7.2% to +1.5% | -10.2% (2) | rejected |
| Gold | INR | bottom | 10 | 40% | 46% | -1.7% | -10.3% to +6.8% | +1.3% (5) | rejected |
| Gold | INR | top | 15 | 33% | 55% | -9.5% | -18.8% to -0.3% | -11.9% (5) | rejected |
| Gold | USD | bottom | 10 | 50% | 46% | -1.5% | -10.1% to +6.8% | +2.3% (5) | rejected |
| Gold | USD | top | 19 | 37% | 54% | -8.4% | -15.8% to -1.5% | -12.3% (5) | rejected |
| Silver | INR | bottom | 15 | 33% | 39% | -7.8% | -16.5% to +1.5% | -6.5% (6) | rejected |
| Silver | INR | top | 14 | 50% | 61% | -4.9% | -24.7% to +12.5% | -14.6% (7) | rejected |
| Silver | USD | bottom | 17 | 29% | 42% | -11.3% | -19.6% to -2.4% | -8.9% (6) | rejected |
| Silver | USD | top | 17 | 47% | 57% | -2.3% | -18.6% to +12.8% | -13.2% (7) | rejected |
| US Treasuries, long duration | INR | bottom | 13 | 31% | 41% | -1.6% | -7.4% to +3.8% | +2.1% (5) | rejected |
| US Treasuries, long duration | INR | top | 16 | 69% | 59% | +0.7% | -7.1% to +7.5% | +5.8% (8) | rejected |
| US Treasuries, long duration | USD | bottom | 15 | 67% | 51% | +2.4% | -1.8% to +6.7% | +3.5% (5) | rejected |
| US Treasuries, long duration | USD | top | 16 | 62% | 49% | +1.7% | -4.3% to +7.4% | +5.8% (8) | rejected |

### credit spread percentile

Moody's Baa corporate bond yield minus the 10-year Treasury — the classic academic credit-spread series, daily since 1986. Wide spreads are credit-market panic (a bottom-side condition for risk assets), tight spreads are complacency (top-side). Thresholds fixed from the series' published history before validation: 1.6 points and below is complacency, 4 points and above is capitulation (reached in 2008 and 2020). Stands in for the ICE high-yield spread, which FRED now serves only as a licence-truncated three-year window. Inverted polarity: top_zone is the level at or below which the top condition holds.

Tested on 16 asset and currency combinations; 1 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| US high-yield credit | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | INR | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | USD | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US investment-grade credit | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US investment-grade credit | INR | top | 7 | 71% | 54% | +4.1% | +0.4% to +8.4% | -2.9% (3) | admitted at half weight (unstable out of sample) |
| US investment-grade credit | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US investment-grade credit | USD | top | 7 | 43% | 51% | +0.5% | -1.4% to +2.3% | +0.0% (3) | rejected |
| Global equities | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | INR | top | 7 | 71% | 49% | +5.0% | -3.0% to +12.4% | -3.0% (3) | rejected |
| US large cap | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | USD | top | 19 | 42% | 45% | -1.9% | -6.5% to +2.9% | -0.1% (3) | rejected |

### crypto fear greed

The alternative.me Crypto Fear and Greed index, 0 to 100, blending volatility, momentum, social activity and dominance. Extreme greed is the top-side condition, extreme fear the bottom-side one. History begins only in 2018 — about one and a half cycles — so any verdict on it is provisional by construction.

Tested on 4 asset and currency combinations; 0 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| Bitcoin | INR | bottom | 10 | 40% | 39% | +3.4% | -77.8% to +108.3% | -58.7% (10) | rejected |
| Bitcoin | INR | top | 6 | 83% | 63% | +47.1% | -27.1% to +104.5% | +100.6% (6) | rejected |
| Bitcoin | USD | bottom | 10 | 30% | 37% | +3.8% | -78.8% to +111.2% | -60.6% (10) | rejected |
| Bitcoin | USD | top | 6 | 83% | 63% | +47.5% | -29.9% to +105.1% | +103.5% (6) | rejected |

### defensive leadership

Consumer staples and utilities outperforming the broad index: money staying in equities while hiding in the defensives. Measured as a z-score of the quarterly change in the defensive-basket-to-benchmark price ratio. A rolling-top behaviour, so top-direction only.

Tested on 2 asset and currency combinations; 0 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| US large cap | INR | top | 10 | 50% | 47% | +2.8% | -7.7% to +14.2% | -1.6% (5) | rejected |
| US large cap | USD | top | 13 | 46% | 41% | +3.1% | -7.9% to +14.8% | -2.2% (5) | rejected |

### drawdown percentile

Current drawdown from the running peak, ranked against every drawdown the asset has experienced. A reading in the worst few percent of its own history is one of the few statistically honest bottom markers: it says nothing about timing, only that the price is unusually far below where it has been.

Tested on 60 asset and currency combinations; 5 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| Biotech | INR | bottom | 8 | 75% | 50% | +26.5% | +3.6% to +51.4% | +29.6% (8) | admitted |
| Biotech | USD | bottom | 7 | 71% | 50% | +29.8% | +4.4% to +58.0% | +32.8% (7) | admitted |
| Bitcoin | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Bitcoin | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| China equities | INR | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| China equities | USD | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Broad commodities | INR | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Broad commodities | USD | bottom | 5 | 80% | 37% | +15.9% | +6.2% to +25.7% | +17.7% (5) | admitted |
| Consumer discretionary | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer discretionary | USD | bottom | 5 | 80% | 48% | +22.7% | +3.1% to +44.5% | +23.4% (3) | admitted |
| Consumer staples | INR | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer staples | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | INR | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US investment-grade credit | INR | bottom | 5 | 60% | 56% | +2.8% | -1.7% to +7.3% | +0.4% (5) | rejected |
| US investment-grade credit | USD | bottom | 5 | 60% | 54% | -1.7% | -7.1% to +3.8% | -3.2% (4) | rejected |
| Crude oil | INR | bottom | 6 | 50% | 39% | +14.2% | -22.7% to +55.2% | +27.8% (5) | rejected |
| Crude oil | USD | bottom | 10 | 70% | 47% | +8.9% | -10.9% to +28.8% | +17.3% (5) | rejected |
| US dollar regime | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US dollar regime | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Emerging markets | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Emerging markets | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Energy | INR | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Energy | USD | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Europe equities | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Europe equities | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Financials | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Financials | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Gold | INR | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Gold | USD | bottom | 7 | 43% | 42% | -9.4% | -18.3% to -0.0% | -6.6% (3) | rejected |
| Healthcare | INR | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Healthcare | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India equities | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India equities | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India midcap | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India midcap | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Industrials | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Industrials | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Japan equities | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Japan equities | USD | bottom | 12 | 42% | 54% | -7.2% | -17.7% to +4.4% | n/a | rejected |
| Magnificent 7 | INR | bottom | 5 | 80% | 57% | +6.6% | -9.7% to +22.3% | +12.2% (5) | rejected |
| Magnificent 7 | USD | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global real estate (REITs) | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global real estate (REITs) | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Semiconductors | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Semiconductors | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Silver | INR | bottom | 8 | 25% | 36% | -4.7% | -22.5% to +18.2% | +4.4% (6) | rejected |
| Silver | USD | bottom | 10 | 40% | 39% | -4.1% | -16.9% to +10.5% | -0.7% (6) | rejected |
| US small cap | INR | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US small cap | USD | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Technology | INR | bottom | 5 | 80% | 51% | +20.8% | +6.2% to +32.9% | +24.3% (5) | admitted |
| Technology | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US Treasuries, long duration | INR | bottom | 5 | 60% | 50% | +3.2% | -1.3% to +7.9% | -3.2% (5) | rejected |
| US Treasuries, long duration | USD | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Utilities | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Utilities | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |

### equal weight breadth

The average stock against the index: the half-year change in the equal-weight-to-cap-weight S&P ratio, as a z-score of its trailing five years. When the average stock lags the index badly, a shrinking handful of giants is carrying the market — the narrow-leadership structure of the 2000, 2007 and 2021 tops. The one breadth measure computable from freely available data (both funds trade since 2003), finally testing the deferred breadth family's core claim. Top-direction only; inverted polarity, so the deeply negative tail (narrowing leadership) is the top zone.

Tested on 2 asset and currency combinations; 0 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| US large cap | INR | top | 9 | 44% | 49% | +1.0% | -5.3% to +7.8% | -3.1% (5) | rejected |
| US large cap | USD | top | 9 | 33% | 41% | -4.4% | -11.0% to +3.3% | -5.8% (5) | rejected |

### euphoria rollover

A trend break counted only right after euphoria — the mirror of the capitulation flush's hole gate, applied to the top side. Plain trend breaks fire constantly and were rejected in both this project's source framework and its colleague's; the hypothesis pre-registered here is that a break of the 40-week average arriving within 26 weeks of a 200-week stretch reading of 1.5+ marks the start of the decline the stretch warned about. An exit discipline, not a prediction: it will fire after the exact peak and pay by avoiding the remainder.

Tested on 60 asset and currency combinations; 2 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| Biotech | INR | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Biotech | USD | top | 5 | 40% | 45% | -9.6% | -41.4% to +22.0% | +31.2% (2) | rejected |
| Bitcoin | INR | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Bitcoin | USD | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| China equities | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| China equities | USD | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Broad commodities | INR | top | 5 | 40% | 62% | +5.7% | -5.6% to +18.1% | +8.4% (2) | rejected |
| Broad commodities | USD | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer discretionary | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer discretionary | USD | top | 5 | 60% | 43% | +6.3% | -6.6% to +20.2% | +36.0% (1) | rejected |
| Consumer staples | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer staples | USD | top | 6 | 33% | 47% | -4.5% | -8.9% to +0.1% | -7.3% (1) | rejected |
| US high-yield credit | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | USD | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US investment-grade credit | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US investment-grade credit | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Crude oil | INR | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Crude oil | USD | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US dollar regime | INR | top | 5 | 20% | 54% | -3.8% | -6.4% to -1.1% | -2.3% (3) | rejected |
| US dollar regime | USD | top | 7 | 86% | 50% | +4.2% | +1.8% to +6.8% | +4.3% (5) | admitted |
| Emerging markets | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Emerging markets | USD | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Energy | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Energy | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | INR | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Europe equities | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Europe equities | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Financials | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Financials | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Gold | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Gold | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Healthcare | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Healthcare | USD | top | 5 | 60% | 52% | +1.5% | -5.0% to +8.6% | +4.0% (1) | rejected |
| India equities | INR | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India equities | USD | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India midcap | INR | top | 5 | 100% | 57% | +21.1% | +16.5% to +25.6% | +18.0% (4) | admitted |
| India midcap | USD | top | 5 | 80% | 56% | +12.3% | -8.4% to +27.9% | +11.6% (5) | rejected |
| Industrials | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Industrials | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Japan equities | INR | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Japan equities | USD | top | 6 | 33% | 49% | -3.0% | -11.8% to +7.0% | n/a | rejected |
| Magnificent 7 | INR | top | 5 | 20% | 53% | -2.6% | -16.4% to +14.2% | +15.2% (2) | rejected |
| Magnificent 7 | USD | top | 7 | 43% | 49% | -4.7% | -29.5% to +19.3% | +0.0% (3) | rejected |
| Global real estate (REITs) | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global real estate (REITs) | USD | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Semiconductors | INR | top | 6 | 50% | 56% | +5.3% | -4.9% to +15.3% | +16.9% (2) | rejected |
| Semiconductors | USD | top | 9 | 56% | 51% | -0.6% | -17.5% to +13.2% | +1.9% (5) | rejected |
| Silver | INR | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Silver | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US small cap | INR | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US small cap | USD | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Technology | INR | top | 6 | 33% | 52% | -10.0% | -24.9% to +5.2% | -12.2% (3) | rejected |
| Technology | USD | top | 6 | 50% | 50% | +0.2% | -14.9% to +14.4% | +0.8% (3) | rejected |
| US Treasuries, long duration | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US Treasuries, long duration | USD | top | 5 | 60% | 52% | +3.6% | -2.3% to +9.1% | +0.3% (3) | rejected |
| US large cap | INR | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | USD | top | 11 | 73% | 47% | +8.4% | -0.4% to +17.2% | +23.0% (1) | rejected |
| Utilities | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Utilities | USD | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |

### fii flow z

Foreign portfolio flows into Indian equities at their extremes: the trailing quarter's net FPI investment as a z-score of its own five years. Record foreign selling has historically marked Indian capitulation lows (the bottom-side condition), record enthusiasm has marked crowding (top-side). Monthly NSDL data from 2002. Ships as foreign flows alone because free historical domestic-institution data does not exist — a documented deviation from the sketched FII/DII divergence.

Tested on 4 asset and currency combinations; 0 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| India equities | INR | bottom | 6 | 67% | 40% | +9.9% | -11.9% to +31.9% | +16.2% (4) | rejected |
| India equities | INR | top | 5 | 40% | 59% | -0.8% | -18.0% to +16.4% | -8.8% (3) | rejected |
| India equities | USD | bottom | 6 | 67% | 41% | +14.1% | -13.7% to +39.9% | +21.3% (4) | rejected |
| India equities | USD | top | 5 | 60% | 59% | +0.8% | -18.7% to +20.8% | -9.0% (3) | rejected |

### financial stress percentile

The Chicago Fed's National Financial Conditions Index — a weekly composite of over a hundred credit, funding and volatility measures, running since 1971. The broadest single thermometer of financial-system stress, with the deep history the credit-spread signal lacked: 1974, 1980, 1987, 1990, 1998, 2008, 2011 and 2020 are all in its record. Scored in percentile space against its own history to date. Inverted polarity: extreme tightness is stress, the bottom-side condition for risk assets; the loose extreme is complacency.

Tested on 12 asset and currency combinations; 0 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| US high-yield credit | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | USD | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | USD | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | USD | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |

### gold cpi ratio

Gold's price per unit of the US consumer price level — is the metal expensive against the goods it is supposed to store value in? Monthly, with CPI lagged one month for its publication delay; CPI history since 1947 supports the gold futures splice back to 2000 and the ETF era. High ratio is the top-side condition.

Tested on 4 asset and currency combinations; 0 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| Gold | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Gold | INR | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Gold | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Gold | USD | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |

### gold real yield

Gold against its strongest fundamental driver. Gold pays nothing, so it competes with the inflation-adjusted yield on safe bonds; a rolling three-year regression of log gold on the 10-year TIPS real yield gives a moving fair-value line, and the raw value is the z-scored residual — how far gold sits above or below what real yields currently justify. TIPS yields exist from 2003. High residual (gold rich versus its driver) is the top-side condition.

Tested on 4 asset and currency combinations; 0 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| Gold | INR | bottom | 6 | 33% | 45% | -4.6% | -14.7% to +6.3% | -18.0% (2) | rejected |
| Gold | INR | top | 10 | 60% | 54% | -5.5% | -16.8% to +4.7% | -3.7% (9) | rejected |
| Gold | USD | bottom | 6 | 17% | 44% | -9.5% | -17.4% to +2.4% | -17.7% (2) | rejected |
| Gold | USD | top | 10 | 60% | 56% | -3.2% | -13.5% to +6.3% | -2.4% (9) | rejected |

### gold silver ratio

Gold priced in silver, the oldest relative-value ratio in metals. A ratio in the highest percentiles of its own history means silver is historically cheap against gold (the 2020 extreme); the lowest percentiles mark silver manias (2011). Scored in percentile space, which sidesteps the ETF-versus- metal unit difference. Attached to the silver slot, where the classic contrarian reading lives. Inverted polarity: a high ratio is the bottom-side (silver-cheap) condition.

Tested on 4 asset and currency combinations; 0 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| Silver | INR | bottom | 10 | 50% | 36% | +1.4% | -8.3% to +11.7% | +3.0% (9) | rejected |
| Silver | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Silver | USD | bottom | 10 | 30% | 40% | +1.2% | -8.6% to +11.8% | +3.0% (9) | rejected |
| Silver | USD | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |

### india gold premium

The premium Indian buyers pay for gold over the world price, measured as the ratio of the domestic gold ETF to the dollar gold price through the rupee lens, z-scored against a trailing two years. Strong physical demand (a high premium) has historically appeared near gold lows; Indian buyers stepping back (a discount) near overheated tops. The windowed z-score re-anchors through import-duty changes, which step the absolute level. Inverted polarity: with the z-score as the raw value, top_zone is the level at or below which the top condition holds (a deep discount).

Tested on 4 asset and currency combinations; 0 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| Gold | INR | bottom | 13 | 31% | 41% | -6.7% | -13.3% to +0.1% | -10.2% (6) | rejected |
| Gold | INR | top | 12 | 42% | 60% | -6.1% | -17.0% to +4.5% | -7.0% (8) | rejected |
| Gold | USD | bottom | 13 | 31% | 42% | -5.0% | -11.9% to +1.9% | -7.2% (6) | rejected |
| Gold | USD | top | 12 | 42% | 58% | -7.0% | -18.0% to +3.3% | -8.0% (8) | rejected |

### india vix percentile

India's own fear gauge, published by NSE since 2008 and spanning both the global financial crisis and the 2020 crash (each above 80). The direct transplant of the project's best validated signal — buying equity panic via the VIX — to Indian equities using India's own volatility index. Thresholds scaled to the Indian series' hotter range: complacency at 11 and below, panic at 30 and above. Inverted polarity: top_zone is the level at or below which the top condition holds.

Tested on 4 asset and currency combinations; 0 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| India equities | INR | bottom | 9 | 67% | 38% | +8.1% | -6.8% to +21.6% | +13.3% (2) | rejected |
| India equities | INR | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India equities | USD | bottom | 9 | 67% | 40% | +11.0% | -9.3% to +30.0% | +12.2% (2) | rejected |
| India equities | USD | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |

### inflation regime

Market-expected inflation — the 10-year breakeven rate — ranked against its own history since 2003. Pre-registered to answer the standing "did you test inflation?" question with evidence rather than opinion. High and rising expected inflation compressed valuations in the 1970s and 2022; the hypothesis is that stocks and bonds fare worse when breakevens sit in their top percentiles. Prior leans strongly toward rejection (this is the anticipatory-macro family that has failed every prior test), tested anyway to close the record honestly.

Tested on 8 asset and currency combinations; 2 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| US high-yield credit | INR | top | 5 | 40% | 51% | +0.2% | -7.2% to +7.5% | +4.2% (4) | rejected |
| US high-yield credit | USD | top | 5 | 40% | 42% | +4.1% | -1.2% to +10.0% | +5.5% (4) | rejected |
| Global equities | INR | top | 5 | 40% | 51% | +3.4% | -8.9% to +16.1% | +9.5% (4) | rejected |
| Global equities | USD | top | 5 | 60% | 45% | +7.4% | -2.7% to +18.7% | +10.6% (4) | rejected |
| US Treasuries, long duration | INR | top | 5 | 80% | 50% | +9.7% | +2.7% to +16.7% | +11.8% (4) | admitted |
| US Treasuries, long duration | USD | top | 5 | 100% | 54% | +12.8% | +7.3% to +18.8% | +12.5% (4) | admitted |
| US large cap | INR | top | 5 | 60% | 51% | +1.3% | -12.0% to +14.5% | +7.7% (4) | rejected |
| US large cap | USD | top | 5 | 60% | 45% | +5.5% | -6.3% to +17.4% | +8.8% (4) | rejected |

### inr stress z

The rupee falling unusually fast — the quarterly change in USDINR as a z-score of its trailing three years. Sharp depreciation episodes (2013, 2018, 2020, 2022) have coincided with foreign selling and Indian equity washouts, making currency stress a candidate capitulation marker for Indian equities. Bottom-direction only: there is no literature claim that a strong rupee marks tops. Inverted polarity: fast depreciation (a high z-score) is the bottom-side condition.

Tested on 2 asset and currency combinations; 0 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| India equities | INR | bottom | 6 | 67% | 39% | +11.4% | -7.1% to +33.2% | +35.0% (2) | rejected |
| India equities | USD | bottom | 6 | 50% | 40% | +11.9% | -11.6% to +38.9% | +40.6% (2) | rejected |

### margin debt yoy

Broker margin debt, year over year — leverage euphoria as a top marker. Rapid margin expansion accompanied 1999, 2007 and 2021; the hypothesis is that peak leverage growth precedes below-normal equity returns. Quarterly FRED series since 1945, lagged one quarter for publication. Pre-registered with a rejection-leaning prior (anticipatory, and leverage tends to peak with price rather than lead it), tested to complete the record.

Tested on 2 asset and currency combinations; 0 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| US large cap | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | USD | top | 8 | 50% | 44% | +3.3% | -3.9% to +10.5% | -13.9% (1) | rejected |

### monthly rsi divergence

Wilder RSI(14) on monthly closes, checked for divergence against price. A bearish divergence is a fresh 12-month price high made with a lower RSI than at the previous 12-month high — the classic signature of a rolling top, where price keeps rising on weakening momentum. The bullish case is the mirror.

Tested on 120 asset and currency combinations; 2 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| Biotech | INR | bottom | 5 | 80% | 50% | +14.4% | -6.7% to +35.5% | +17.5% (5) | rejected |
| Biotech | INR | top | 11 | 36% | 45% | -1.1% | -15.2% to +12.3% | +4.9% (5) | rejected |
| Biotech | USD | bottom | 5 | 60% | 49% | +6.8% | -15.0% to +26.7% | +9.9% (5) | rejected |
| Biotech | USD | top | 12 | 50% | 45% | +3.0% | -8.1% to +14.4% | +4.8% (7) | rejected |
| Bitcoin | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Bitcoin | INR | top | 8 | 62% | 70% | -78.0% | -256.8% to +85.5% | -66.2% (8) | rejected |
| Bitcoin | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Bitcoin | USD | top | 8 | 75% | 70% | +4.5% | -167.4% to +147.1% | +16.6% (8) | rejected |
| China equities | INR | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| China equities | INR | top | 6 | 33% | 54% | -9.4% | -25.2% to +6.7% | -12.6% (5) | rejected |
| China equities | USD | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| China equities | USD | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Broad commodities | INR | bottom | 6 | 50% | 40% | -1.2% | -17.8% to +12.7% | -1.6% (4) | rejected |
| Broad commodities | INR | top | 10 | 70% | 60% | +0.6% | -8.2% to +8.7% | +2.6% (7) | rejected |
| Broad commodities | USD | bottom | 6 | 33% | 40% | +7.5% | -8.9% to +23.7% | -1.8% (4) | rejected |
| Broad commodities | USD | top | 5 | 20% | 58% | -6.0% | -15.6% to +3.1% | -2.6% (4) | rejected |
| Consumer discretionary | INR | bottom | 5 | 40% | 52% | -3.7% | -28.0% to +21.7% | +17.7% (3) | rejected |
| Consumer discretionary | INR | top | 16 | 44% | 48% | -0.5% | -7.7% to +7.1% | -1.3% (10) | rejected |
| Consumer discretionary | USD | bottom | 5 | 40% | 55% | -4.7% | -21.9% to +12.2% | -3.6% (2) | rejected |
| Consumer discretionary | USD | top | 18 | 50% | 43% | +1.0% | -4.4% to +6.3% | +2.2% (8) | rejected |
| Consumer staples | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer staples | INR | top | 22 | 59% | 52% | +0.9% | -3.0% to +4.7% | +1.3% (14) | rejected |
| Consumer staples | USD | bottom | 6 | 67% | 53% | +1.5% | -5.5% to +8.0% | +7.8% (3) | rejected |
| Consumer staples | USD | top | 22 | 64% | 47% | +3.4% | +0.2% to +7.0% | +3.6% (11) | admitted |
| US high-yield credit | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | INR | top | 16 | 50% | 51% | -0.7% | -3.6% to +2.0% | -0.5% (10) | rejected |
| US high-yield credit | USD | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | USD | top | 13 | 38% | 41% | +0.5% | -2.3% to +3.7% | +1.8% (9) | rejected |
| US investment-grade credit | INR | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US investment-grade credit | INR | top | 15 | 40% | 56% | -1.7% | -5.5% to +1.8% | -1.6% (8) | rejected |
| US investment-grade credit | USD | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US investment-grade credit | USD | top | 19 | 58% | 51% | -0.7% | -2.7% to +1.2% | -1.3% (8) | rejected |
| Crude oil | INR | bottom | 10 | 70% | 47% | +4.5% | -15.9% to +23.2% | -13.4% (5) | rejected |
| Crude oil | INR | top | 9 | 33% | 53% | -12.1% | -29.0% to +4.8% | -4.7% (4) | rejected |
| Crude oil | USD | bottom | 9 | 78% | 48% | +4.7% | -14.3% to +22.0% | -7.7% (5) | rejected |
| Crude oil | USD | top | 9 | 44% | 55% | -10.0% | -24.8% to +5.3% | -6.1% (3) | rejected |
| US dollar regime | INR | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US dollar regime | INR | top | 13 | 62% | 52% | +4.3% | -1.9% to +10.5% | +2.3% (9) | rejected |
| US dollar regime | USD | bottom | 6 | 50% | 49% | +0.8% | -2.9% to +4.4% | +3.7% (4) | rejected |
| US dollar regime | USD | top | 11 | 64% | 53% | +2.4% | -1.9% to +6.5% | +1.2% (7) | rejected |
| Emerging markets | INR | bottom | 5 | 60% | 52% | +4.6% | -5.7% to +14.8% | -0.3% (4) | rejected |
| Emerging markets | INR | top | 14 | 43% | 49% | -2.6% | -9.1% to +3.5% | -2.0% (8) | rejected |
| Emerging markets | USD | bottom | 7 | 43% | 51% | +8.9% | -8.6% to +31.8% | -5.7% (4) | rejected |
| Emerging markets | USD | top | 10 | 30% | 49% | -5.7% | -11.6% to +0.4% | -9.9% (5) | rejected |
| Energy | INR | bottom | 6 | 67% | 46% | +4.0% | -12.7% to +20.6% | +2.5% (4) | rejected |
| Energy | INR | top | 14 | 71% | 54% | +4.1% | -4.5% to +12.7% | +6.0% (6) | rejected |
| Energy | USD | bottom | 7 | 57% | 46% | +4.5% | -13.3% to +23.5% | +8.5% (4) | rejected |
| Energy | USD | top | 17 | 71% | 51% | +5.2% | -4.8% to +14.0% | +6.6% (6) | rejected |
| Global equities | INR | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | INR | top | 12 | 58% | 50% | +1.7% | -3.7% to +7.4% | -0.0% (9) | rejected |
| Global equities | USD | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | USD | top | 11 | 36% | 46% | +1.7% | -5.5% to +9.1% | +3.6% (8) | rejected |
| Europe equities | INR | bottom | 5 | 80% | 46% | +10.0% | +2.3% to +17.2% | +11.3% (2) | admitted |
| Europe equities | INR | top | 16 | 62% | 51% | +5.2% | -2.2% to +12.4% | +4.1% (10) | rejected |
| Europe equities | USD | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Europe equities | USD | top | 11 | 45% | 49% | -1.6% | -9.8% to +6.7% | -4.6% (5) | rejected |
| Financials | INR | bottom | 5 | 20% | 48% | -19.3% | -41.2% to +2.7% | +6.1% (2) | rejected |
| Financials | INR | top | 16 | 50% | 51% | -1.1% | -7.2% to +4.7% | +2.8% (12) | rejected |
| Financials | USD | bottom | 7 | 14% | 52% | -23.7% | -40.8% to -8.8% | -9.5% (3) | rejected |
| Financials | USD | top | 16 | 50% | 49% | +2.0% | -5.0% to +9.0% | +5.2% (8) | rejected |
| Gold | INR | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Gold | INR | top | 14 | 57% | 54% | -4.6% | -14.8% to +3.5% | -6.4% (7) | rejected |
| Gold | USD | bottom | 5 | 20% | 42% | -6.5% | -11.9% to -1.3% | -3.1% (3) | rejected |
| Gold | USD | top | 17 | 47% | 55% | -2.7% | -11.8% to +5.2% | -2.6% (7) | rejected |
| Healthcare | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Healthcare | INR | top | 16 | 69% | 54% | +1.3% | -5.6% to +8.0% | +3.8% (10) | rejected |
| Healthcare | USD | bottom | 5 | 20% | 48% | -12.8% | -24.1% to -2.9% | -3.8% (2) | rejected |
| Healthcare | USD | top | 20 | 60% | 53% | +2.2% | -2.4% to +7.2% | +3.1% (10) | rejected |
| India equities | INR | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India equities | INR | top | 12 | 42% | 59% | -1.4% | -9.2% to +5.7% | -0.5% (9) | rejected |
| India equities | USD | bottom | 5 | 20% | 41% | -5.0% | -8.7% to -1.6% | -2.8% (4) | rejected |
| India equities | USD | top | 9 | 56% | 59% | +7.6% | -2.9% to +17.9% | +9.9% (5) | rejected |
| India midcap | INR | bottom | 6 | 67% | 41% | +18.2% | -7.3% to +52.1% | -0.5% (3) | rejected |
| India midcap | INR | top | 8 | 50% | 57% | +4.9% | -2.8% to +12.9% | -3.0% (6) | rejected |
| India midcap | USD | bottom | 7 | 43% | 40% | +22.6% | -7.8% to +59.0% | -7.1% (4) | rejected |
| India midcap | USD | top | 7 | 29% | 58% | -8.9% | -24.2% to +8.1% | -6.7% (6) | rejected |
| Industrials | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Industrials | INR | top | 19 | 63% | 51% | +2.1% | -4.8% to +8.9% | +1.8% (10) | rejected |
| Industrials | USD | bottom | 6 | 67% | 54% | -0.4% | -17.5% to +13.8% | -1.2% (3) | rejected |
| Industrials | USD | top | 17 | 35% | 45% | -0.8% | -6.6% to +5.0% | +3.4% (7) | rejected |
| Japan equities | INR | bottom | 5 | 40% | 53% | -4.4% | -11.8% to +3.2% | -0.5% (2) | rejected |
| Japan equities | INR | top | 15 | 53% | 52% | +0.7% | -6.5% to +7.4% | -0.2% (11) | rejected |
| Japan equities | USD | bottom | 21 | 48% | 51% | -8.7% | -16.0% to -1.4% | -3.3% (3) | rejected |
| Japan equities | USD | top | 39 | 46% | 49% | -4.4% | -10.1% to +0.7% | -4.2% (7) | rejected |
| Magnificent 7 | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Magnificent 7 | INR | top | 20 | 55% | 49% | -2.6% | -9.6% to +4.4% | -4.2% (10) | rejected |
| Magnificent 7 | USD | bottom | 6 | 67% | 50% | +6.6% | -17.0% to +26.8% | +23.1% (2) | rejected |
| Magnificent 7 | USD | top | 32 | 44% | 50% | -5.4% | -13.7% to +2.6% | -0.6% (10) | rejected |
| Global real estate (REITs) | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global real estate (REITs) | INR | top | 14 | 50% | 48% | +4.6% | -4.3% to +14.2% | -0.8% (6) | rejected |
| Global real estate (REITs) | USD | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global real estate (REITs) | USD | top | 15 | 53% | 50% | +0.3% | -5.0% to +5.3% | +1.6% (8) | rejected |
| Semiconductors | INR | bottom | 6 | 33% | 49% | +13.2% | -24.6% to +61.5% | +45.1% (3) | rejected |
| Semiconductors | INR | top | 12 | 50% | 55% | +1.4% | -10.6% to +15.3% | +2.7% (8) | rejected |
| Semiconductors | USD | bottom | 10 | 40% | 49% | +6.5% | -6.6% to +20.2% | +7.1% (4) | rejected |
| Semiconductors | USD | top | 12 | 50% | 50% | +1.3% | -14.0% to +15.6% | +6.1% (7) | rejected |
| Silver | INR | bottom | 5 | 20% | 39% | -14.1% | -27.6% to +4.2% | -8.8% (3) | rejected |
| Silver | INR | top | 13 | 54% | 61% | -10.2% | -32.5% to +6.9% | -17.3% (7) | rejected |
| Silver | USD | bottom | 7 | 29% | 41% | -2.4% | -19.9% to +16.4% | +5.0% (4) | rejected |
| Silver | USD | top | 12 | 42% | 58% | -24.8% | -51.2% to -1.0% | -21.8% (6) | rejected |
| US small cap | INR | bottom | 5 | 60% | 44% | +12.2% | -1.0% to +26.7% | +19.1% (4) | rejected |
| US small cap | INR | top | 14 | 64% | 52% | +3.6% | -4.2% to +10.3% | +3.3% (7) | rejected |
| US small cap | USD | bottom | 7 | 57% | 50% | +2.3% | -14.0% to +17.0% | +9.1% (5) | rejected |
| US small cap | USD | top | 15 | 60% | 51% | +0.9% | -4.2% to +5.7% | +4.1% (5) | rejected |
| Technology | INR | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Technology | INR | top | 19 | 47% | 47% | +0.1% | -7.4% to +7.4% | +0.3% (12) | rejected |
| Technology | USD | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Technology | USD | top | 22 | 55% | 51% | -1.0% | -6.7% to +4.1% | +2.6% (13) | rejected |
| US Treasuries, long duration | INR | bottom | 6 | 33% | 42% | -2.6% | -8.3% to +3.5% | +2.0% (5) | rejected |
| US Treasuries, long duration | INR | top | 12 | 75% | 59% | +0.3% | -9.3% to +8.5% | -0.2% (5) | rejected |
| US Treasuries, long duration | USD | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US Treasuries, long duration | USD | top | 12 | 50% | 51% | -0.0% | -4.7% to +4.3% | +1.1% (5) | rejected |
| US large cap | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | INR | top | 19 | 47% | 47% | -4.6% | -9.7% to +0.4% | -2.4% (12) | rejected |
| US large cap | USD | bottom | 22 | 32% | 53% | -10.9% | -19.1% to -2.9% | -11.3% (2) | rejected |
| US large cap | USD | top | 72 | 46% | 47% | -2.1% | -4.9% to +0.8% | -0.9% (9) | rejected |
| Utilities | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Utilities | INR | top | 19 | 47% | 50% | +2.4% | -2.8% to +7.7% | +1.2% (10) | rejected |
| Utilities | USD | bottom | 5 | 40% | 59% | -10.4% | -30.0% to +9.9% | +9.3% (1) | rejected |
| Utilities | USD | top | 18 | 39% | 43% | +1.6% | -3.8% to +7.0% | +2.8% (9) | rejected |

### mortgage momentum

How fast US mortgage rates have moved over the trailing year, weekly since 1971. A four-point rise in twelve months (2022) crushes affordability and REIT valuations — a fast rise is the top-side condition for property, so the polarity is inverted; a fast fall is the tailwind of 2009 and 2020, the bottom-side condition.

Tested on 4 asset and currency combinations; 0 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| Global real estate (REITs) | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global real estate (REITs) | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global real estate (REITs) | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global real estate (REITs) | USD | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |

### nifty pe percentile

The Nifty 50's trailing price-to-earnings ratio, from NSE's official series running since 1999 — a history that includes the 2000 and 2008 valuation extremes at both ends. The score ranks today's P/E within that whole record. The file arrives by hand: niftyindices.com publishes it freely to browsers and blocks scripts, so the CSV in data/manual/ is refreshed manually and the reading goes visibly stale when it is not.

Tested on 4 asset and currency combinations; 0 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| India equities | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India equities | INR | top | 9 | 89% | 59% | +5.0% | -4.2% to +12.9% | +2.3% (8) | rejected |
| India equities | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India equities | USD | top | 9 | 78% | 59% | +3.6% | -6.7% to +12.7% | +2.5% (8) | rejected |

### permits yoy

US housing permits, year over year — the housing cycle's own throttle, monthly since 1960 and lagged one month for publication. Permits collapsed by half into 2009 and boomed in every recovery; this gives the REIT slot an indicator from its own industry rather than generic price technicals. A boom is the top-side condition, a collapse the bottom-side one.

Tested on 4 asset and currency combinations; 0 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| Global real estate (REITs) | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global real estate (REITs) | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global real estate (REITs) | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global real estate (REITs) | USD | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |

### price vs 200dma z

Z-score of the percentage distance between price and its 200-day moving average, measured against the asset's own history of that distance. Stretch above trend is a top-side condition; capitulation below it is a bottom-side condition. Scored per asset because a 10% gap means something different for Bitcoin than for Treasuries.

Tested on 120 asset and currency combinations; 5 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| Biotech | INR | bottom | 9 | 67% | 49% | +26.1% | +3.7% to +50.6% | +36.1% (6) | admitted |
| Biotech | INR | top | 9 | 56% | 51% | +10.7% | -2.4% to +24.9% | +40.0% (2) | rejected |
| Biotech | USD | bottom | 10 | 50% | 53% | +16.5% | -2.8% to +37.6% | +30.4% (6) | rejected |
| Biotech | USD | top | 8 | 62% | 47% | +14.7% | +1.7% to +28.4% | +39.3% (2) | admitted |
| Bitcoin | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Bitcoin | INR | top | 6 | 67% | 67% | -131.2% | -462.0% to +83.5% | -133.6% (6) | rejected |
| Bitcoin | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Bitcoin | USD | top | 6 | 67% | 68% | -147.0% | -509.4% to +88.3% | -150.2% (6) | rejected |
| China equities | INR | bottom | 8 | 38% | 45% | -4.1% | -12.0% to +2.8% | -8.2% (6) | rejected |
| China equities | INR | top | 7 | 86% | 55% | +8.7% | -5.0% to +21.6% | +10.4% (5) | rejected |
| China equities | USD | bottom | 7 | 29% | 46% | -7.4% | -15.3% to +0.6% | -10.3% (6) | rejected |
| China equities | USD | top | 6 | 83% | 55% | +9.9% | -3.6% to +21.8% | +9.4% (5) | rejected |
| Broad commodities | INR | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Broad commodities | INR | top | 5 | 40% | 57% | -4.5% | -26.3% to +17.3% | -18.5% (3) | rejected |
| Broad commodities | USD | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Broad commodities | USD | top | 5 | 60% | 56% | +1.4% | -23.4% to +26.3% | -16.4% (3) | rejected |
| Consumer discretionary | INR | bottom | 8 | 50% | 52% | -6.9% | -21.5% to +7.1% | +6.2% (5) | rejected |
| Consumer discretionary | INR | top | 6 | 33% | 48% | +2.4% | -4.5% to +11.2% | +0.5% (2) | rejected |
| Consumer discretionary | USD | bottom | 11 | 55% | 56% | -1.4% | -14.1% to +9.9% | +5.1% (5) | rejected |
| Consumer discretionary | USD | top | 7 | 43% | 44% | +3.4% | -7.2% to +16.0% | +13.5% (3) | rejected |
| Consumer staples | INR | bottom | 7 | 71% | 49% | +4.8% | -0.2% to +10.4% | +10.2% (5) | rejected |
| Consumer staples | INR | top | 9 | 56% | 52% | +0.1% | -5.6% to +6.2% | n/a | rejected |
| Consumer staples | USD | bottom | 6 | 83% | 53% | +3.0% | -3.1% to +8.5% | +8.2% (4) | rejected |
| Consumer staples | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | USD | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | USD | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US investment-grade credit | INR | bottom | 6 | 33% | 44% | +1.3% | -8.1% to +13.3% | -0.9% (4) | rejected |
| US investment-grade credit | INR | top | 8 | 50% | 54% | -0.4% | -6.9% to +6.3% | -0.3% (2) | rejected |
| US investment-grade credit | USD | bottom | 7 | 57% | 49% | -1.4% | -6.1% to +3.2% | -4.0% (4) | rejected |
| US investment-grade credit | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Crude oil | INR | bottom | 7 | 43% | 48% | +0.7% | -21.7% to +25.3% | +19.5% (3) | rejected |
| Crude oil | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Crude oil | USD | bottom | 5 | 40% | 47% | -4.4% | -36.3% to +27.6% | -0.2% (2) | rejected |
| Crude oil | USD | top | 5 | 60% | 52% | +1.3% | -34.3% to +38.0% | -24.7% (2) | rejected |
| US dollar regime | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US dollar regime | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US dollar regime | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US dollar regime | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Emerging markets | INR | bottom | 6 | 50% | 52% | +4.1% | -20.4% to +30.5% | +12.5% (3) | rejected |
| Emerging markets | INR | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Emerging markets | USD | bottom | 5 | 60% | 50% | +11.2% | -24.0% to +47.0% | +14.2% (3) | rejected |
| Emerging markets | USD | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Energy | INR | bottom | 10 | 50% | 46% | -2.1% | -11.2% to +7.1% | +9.4% (4) | rejected |
| Energy | INR | top | 6 | 67% | 54% | -0.7% | -21.8% to +21.9% | -37.8% (2) | rejected |
| Energy | USD | bottom | 10 | 60% | 49% | -1.7% | -12.4% to +9.5% | +13.4% (4) | rejected |
| Energy | USD | top | 6 | 33% | 50% | -12.9% | -24.1% to -1.5% | -32.0% (2) | rejected |
| Global equities | INR | bottom | 8 | 75% | 49% | +10.1% | +2.6% to +17.7% | +10.1% (6) | admitted |
| Global equities | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | USD | bottom | 7 | 86% | 54% | +9.3% | +0.6% to +18.8% | +10.2% (6) | admitted |
| Global equities | USD | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Europe equities | INR | bottom | 7 | 43% | 49% | -8.1% | -23.6% to +6.5% | +15.1% (3) | rejected |
| Europe equities | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Europe equities | USD | bottom | 6 | 67% | 52% | +3.4% | -13.4% to +19.4% | +13.9% (3) | rejected |
| Europe equities | USD | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Financials | INR | bottom | 6 | 33% | 48% | -12.4% | -41.6% to +16.0% | +10.3% (2) | rejected |
| Financials | INR | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Financials | USD | bottom | 7 | 43% | 52% | -4.0% | -31.4% to +22.0% | +11.4% (2) | rejected |
| Financials | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Gold | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Gold | INR | top | 10 | 40% | 54% | -8.8% | -20.7% to +2.8% | -12.8% (6) | rejected |
| Gold | USD | bottom | 6 | 33% | 45% | -7.0% | -16.8% to +3.6% | n/a | rejected |
| Gold | USD | top | 11 | 45% | 56% | -3.7% | -14.0% to +6.0% | -17.5% (4) | rejected |
| Healthcare | INR | bottom | 8 | 50% | 46% | +2.4% | -5.8% to +10.3% | +14.8% (5) | rejected |
| Healthcare | INR | top | 9 | 44% | 56% | +1.3% | -7.5% to +10.1% | +18.2% (1) | rejected |
| Healthcare | USD | bottom | 11 | 55% | 47% | +1.3% | -8.1% to +10.3% | +8.3% (5) | rejected |
| Healthcare | USD | top | 5 | 80% | 53% | +4.7% | -4.0% to +13.0% | n/a | rejected |
| India equities | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India equities | INR | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India equities | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India equities | USD | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India midcap | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India midcap | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India midcap | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India midcap | USD | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Industrials | INR | bottom | 8 | 75% | 47% | +3.9% | -13.6% to +21.0% | +19.9% (4) | rejected |
| Industrials | INR | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Industrials | USD | bottom | 8 | 38% | 55% | +3.2% | -9.8% to +16.4% | +20.1% (4) | rejected |
| Industrials | USD | top | 5 | 20% | 46% | -2.5% | -10.4% to +8.9% | +6.0% (2) | rejected |
| Japan equities | INR | bottom | 7 | 57% | 51% | +12.6% | -1.2% to +26.6% | +21.3% (5) | rejected |
| Japan equities | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Japan equities | USD | bottom | 16 | 38% | 51% | -0.5% | -6.6% to +5.9% | +12.0% (4) | rejected |
| Japan equities | USD | top | 13 | 31% | 49% | -6.7% | -14.4% to +0.6% | -1.8% (1) | rejected |
| Magnificent 7 | INR | bottom | 8 | 50% | 52% | +1.8% | -14.4% to +17.6% | +9.0% (5) | rejected |
| Magnificent 7 | INR | top | 8 | 38% | 49% | -2.9% | -12.6% to +6.2% | -11.2% (4) | rejected |
| Magnificent 7 | USD | bottom | 11 | 64% | 50% | -0.5% | -20.9% to +19.0% | +9.1% (5) | rejected |
| Magnificent 7 | USD | top | 12 | 33% | 50% | -16.1% | -30.6% to -3.2% | -10.6% (5) | rejected |
| Global real estate (REITs) | INR | bottom | 7 | 14% | 51% | -8.6% | -19.7% to +3.4% | +2.6% (4) | rejected |
| Global real estate (REITs) | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global real estate (REITs) | USD | bottom | 5 | 20% | 49% | -21.5% | -37.8% to -9.4% | -6.8% (2) | rejected |
| Global real estate (REITs) | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Semiconductors | INR | bottom | 7 | 57% | 47% | +15.0% | -14.5% to +43.2% | +27.3% (5) | rejected |
| Semiconductors | INR | top | 9 | 44% | 49% | -3.4% | -16.8% to +10.5% | -7.1% (5) | rejected |
| Semiconductors | USD | bottom | 7 | 86% | 49% | +37.4% | +15.5% to +61.6% | +33.3% (5) | admitted |
| Semiconductors | USD | top | 7 | 43% | 52% | -15.0% | -29.4% to -0.2% | -5.5% (5) | rejected |
| Silver | INR | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Silver | INR | top | 6 | 50% | 61% | -6.2% | -21.5% to +10.3% | +2.1% (3) | rejected |
| Silver | USD | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Silver | USD | top | 6 | 50% | 57% | +1.8% | -15.2% to +19.9% | +12.0% (2) | rejected |
| US small cap | INR | bottom | 8 | 50% | 49% | +9.1% | -8.7% to +27.5% | +25.8% (4) | rejected |
| US small cap | INR | top | 5 | 20% | 53% | -1.2% | -11.6% to +9.9% | -21.5% (1) | rejected |
| US small cap | USD | bottom | 8 | 62% | 49% | +9.9% | -7.6% to +27.0% | +24.2% (4) | rejected |
| US small cap | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Technology | INR | bottom | 8 | 62% | 53% | +5.1% | -10.7% to +19.9% | +12.0% (5) | rejected |
| Technology | INR | top | 7 | 57% | 49% | -1.6% | -8.9% to +6.3% | -9.8% (3) | rejected |
| Technology | USD | bottom | 8 | 62% | 53% | +6.9% | -16.3% to +28.0% | +13.9% (5) | rejected |
| Technology | USD | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US Treasuries, long duration | INR | bottom | 7 | 29% | 41% | -4.7% | -9.8% to +1.1% | -2.2% (4) | rejected |
| US Treasuries, long duration | INR | top | 6 | 50% | 57% | -0.9% | -18.4% to +16.4% | +2.8% (2) | rejected |
| US Treasuries, long duration | USD | bottom | 8 | 75% | 50% | +5.3% | -2.4% to +13.6% | +2.9% (4) | rejected |
| US Treasuries, long duration | USD | top | 8 | 50% | 50% | -1.0% | -8.0% to +6.3% | +0.9% (3) | rejected |
| US large cap | INR | bottom | 8 | 50% | 52% | -3.0% | -15.9% to +9.0% | +9.2% (5) | rejected |
| US large cap | INR | top | 5 | 60% | 48% | +1.6% | -2.6% to +5.7% | +10.3% (1) | rejected |
| US large cap | USD | bottom | 25 | 52% | 54% | -1.3% | -8.8% to +6.1% | +9.6% (5) | rejected |
| US large cap | USD | top | 18 | 44% | 47% | -1.5% | -6.1% to +3.4% | -5.3% (2) | rejected |
| Utilities | INR | bottom | 10 | 50% | 51% | -0.4% | -7.0% to +6.5% | +4.2% (4) | rejected |
| Utilities | INR | top | 7 | 57% | 50% | +2.3% | -1.9% to +6.6% | -3.2% (2) | rejected |
| Utilities | USD | bottom | 5 | 40% | 56% | -4.4% | -14.7% to +7.5% | +2.3% (3) | rejected |
| Utilities | USD | top | 6 | 50% | 40% | +5.9% | -0.4% to +12.3% | +7.6% (4) | rejected |

### price vs 200wma z

The weekly-scale twin of price_vs_200dma_z: z-score of the distance between the weekly close and its 200-week moving average. Slower and less noisy; the 200-week average is the level major bear markets have historically found.

Tested on 120 asset and currency combinations; 5 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| Biotech | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Biotech | INR | top | 7 | 29% | 46% | -6.0% | -19.7% to +11.6% | +39.5% (1) | rejected |
| Biotech | USD | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Biotech | USD | top | 7 | 43% | 45% | +3.9% | -8.7% to +18.3% | +28.0% (2) | rejected |
| Bitcoin | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Bitcoin | INR | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Bitcoin | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Bitcoin | USD | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| China equities | INR | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| China equities | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| China equities | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| China equities | USD | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Broad commodities | INR | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Broad commodities | INR | top | 5 | 60% | 60% | +1.3% | -10.7% to +13.4% | +0.6% (2) | rejected |
| Broad commodities | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Broad commodities | USD | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer discretionary | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer discretionary | INR | top | 6 | 33% | 49% | -4.8% | -10.0% to +0.5% | n/a | rejected |
| Consumer discretionary | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer discretionary | USD | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer staples | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer staples | INR | top | 5 | 40% | 52% | -2.6% | -11.7% to +7.3% | n/a | rejected |
| Consumer staples | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer staples | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | USD | bottom | 7 | 57% | 58% | +4.8% | -1.4% to +11.3% | +6.3% (5) | rejected |
| US high-yield credit | USD | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US investment-grade credit | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US investment-grade credit | INR | top | 5 | 40% | 56% | -1.7% | -6.6% to +3.4% | n/a | rejected |
| US investment-grade credit | USD | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US investment-grade credit | USD | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Crude oil | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Crude oil | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Crude oil | USD | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Crude oil | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US dollar regime | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US dollar regime | INR | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US dollar regime | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US dollar regime | USD | top | 7 | 86% | 50% | +3.7% | -0.2% to +6.9% | +4.7% (4) | rejected |
| Emerging markets | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Emerging markets | INR | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Emerging markets | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Emerging markets | USD | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Energy | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Energy | INR | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Energy | USD | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Energy | USD | top | 7 | 14% | 51% | -15.2% | -25.1% to -6.4% | -4.9% (3) | rejected |
| Global equities | INR | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | USD | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Europe equities | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Europe equities | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Europe equities | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Europe equities | USD | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Financials | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Financials | INR | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Financials | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Financials | USD | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Gold | INR | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Gold | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Gold | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Gold | USD | top | 5 | 60% | 55% | +2.4% | -14.2% to +16.8% | -32.7% (1) | rejected |
| Healthcare | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Healthcare | INR | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Healthcare | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Healthcare | USD | top | 7 | 57% | 53% | -1.6% | -12.8% to +9.3% | +15.0% (1) | rejected |
| India equities | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India equities | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India equities | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India equities | USD | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India midcap | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India midcap | INR | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India midcap | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India midcap | USD | top | 6 | 100% | 59% | +17.0% | +10.0% to +24.8% | +20.2% (5) | admitted |
| Industrials | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Industrials | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Industrials | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Industrials | USD | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Japan equities | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Japan equities | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Japan equities | USD | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Japan equities | USD | top | 8 | 38% | 49% | -8.8% | -22.0% to +2.7% | n/a | rejected |
| Magnificent 7 | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Magnificent 7 | INR | top | 6 | 83% | 53% | +6.5% | +3.6% to +8.9% | +3.1% (2) | admitted |
| Magnificent 7 | USD | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Magnificent 7 | USD | top | 11 | 55% | 49% | +0.1% | -17.4% to +18.7% | +17.8% (4) | rejected |
| Global real estate (REITs) | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global real estate (REITs) | INR | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global real estate (REITs) | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global real estate (REITs) | USD | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Semiconductors | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Semiconductors | INR | top | 6 | 83% | 55% | +22.6% | +8.5% to +35.9% | +29.5% (3) | admitted |
| Semiconductors | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Semiconductors | USD | top | 11 | 82% | 50% | +20.0% | +8.8% to +30.5% | +31.5% (7) | admitted |
| Silver | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Silver | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Silver | USD | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Silver | USD | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US small cap | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US small cap | INR | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US small cap | USD | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US small cap | USD | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Technology | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Technology | INR | top | 7 | 86% | 52% | +11.4% | +3.0% to +21.7% | +15.6% (3) | admitted |
| Technology | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Technology | USD | top | 6 | 50% | 50% | +3.7% | -9.1% to +16.9% | +5.4% (4) | rejected |
| US Treasuries, long duration | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US Treasuries, long duration | INR | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US Treasuries, long duration | USD | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US Treasuries, long duration | USD | top | 5 | 40% | 52% | +1.4% | -6.4% to +9.7% | +15.8% (1) | rejected |
| US large cap | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | INR | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | USD | bottom | 7 | 57% | 54% | +1.9% | -9.0% to +13.0% | n/a | rejected |
| US large cap | USD | top | 16 | 38% | 47% | -2.0% | -9.5% to +5.6% | n/a | rejected |
| Utilities | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Utilities | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Utilities | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Utilities | USD | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |

### price vs m2

The asset's price divided by the previous month's US M2 money stock — price per unit of liquidity rather than price per dollar. Money growth lifts the fair value of everything; an asset in the highest percentiles of its own price-to-M2 history has outrun the liquidity that carries it, and one in the lowest has been left behind by it. Monthly, in dollars for every asset, M2 since 1959 from FRED. Caveats the scorecard carries: M2 is seasonally adjusted and lightly revised, and this family's academic record is better at saying "stretched" than at saying "when".

Tested on 120 asset and currency combinations; 5 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| Biotech | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Biotech | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Biotech | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Biotech | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Bitcoin | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Bitcoin | INR | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Bitcoin | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Bitcoin | USD | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| China equities | INR | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| China equities | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| China equities | USD | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| China equities | USD | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Broad commodities | INR | bottom | 6 | 33% | 36% | -6.3% | -14.9% to +3.3% | -4.4% (6) | rejected |
| Broad commodities | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Broad commodities | USD | bottom | 6 | 33% | 38% | -4.6% | -14.2% to +4.8% | -2.7% (6) | rejected |
| Broad commodities | USD | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer discretionary | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer discretionary | INR | top | 7 | 57% | 52% | +4.6% | -2.1% to +11.6% | +5.6% (6) | rejected |
| Consumer discretionary | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer discretionary | USD | top | 7 | 43% | 48% | +1.8% | -5.3% to +10.3% | +2.9% (6) | rejected |
| Consumer staples | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer staples | INR | top | 8 | 38% | 47% | +0.9% | -2.8% to +5.1% | +1.7% (7) | rejected |
| Consumer staples | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer staples | USD | top | 8 | 50% | 53% | +1.8% | -1.3% to +4.8% | +2.3% (7) | rejected |
| US high-yield credit | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | USD | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US investment-grade credit | INR | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US investment-grade credit | INR | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US investment-grade credit | USD | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US investment-grade credit | USD | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Crude oil | INR | bottom | 9 | 44% | 46% | -17.1% | -37.2% to +2.6% | -33.3% (4) | rejected |
| Crude oil | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Crude oil | USD | bottom | 9 | 44% | 47% | -16.9% | -35.8% to +1.4% | -31.2% (4) | rejected |
| Crude oil | USD | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US dollar regime | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US dollar regime | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US dollar regime | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US dollar regime | USD | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Emerging markets | INR | bottom | 5 | 60% | 53% | +10.4% | -2.8% to +25.3% | +11.6% (5) | rejected |
| Emerging markets | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Emerging markets | USD | bottom | 5 | 60% | 53% | +12.6% | -4.2% to +29.9% | +13.9% (5) | rejected |
| Emerging markets | USD | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Energy | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Energy | INR | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Energy | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Energy | USD | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | INR | top | 6 | 67% | 47% | +12.1% | +3.4% to +19.4% | +10.3% (6) | admitted |
| Global equities | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | USD | top | 6 | 67% | 43% | +13.3% | +3.8% to +21.1% | +11.9% (6) | admitted |
| Europe equities | INR | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Europe equities | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Europe equities | USD | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Europe equities | USD | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Financials | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Financials | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Financials | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Financials | USD | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Gold | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Gold | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Gold | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Gold | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Healthcare | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Healthcare | INR | top | 10 | 50% | 53% | +2.9% | -1.6% to +7.7% | +3.3% (9) | rejected |
| Healthcare | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Healthcare | USD | top | 10 | 60% | 51% | +1.1% | -3.9% to +6.4% | +2.0% (9) | rejected |
| India equities | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India equities | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India equities | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India equities | USD | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India midcap | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India midcap | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India midcap | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India midcap | USD | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Industrials | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Industrials | INR | top | 6 | 83% | 55% | +9.3% | +3.2% to +15.0% | +9.1% (5) | admitted |
| Industrials | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Industrials | USD | top | 6 | 50% | 47% | +8.3% | -0.9% to +16.8% | +7.2% (5) | rejected |
| Japan equities | INR | bottom | 11 | 64% | 48% | +0.8% | -5.1% to +6.1% | +2.8% (5) | rejected |
| Japan equities | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Japan equities | USD | bottom | 13 | 69% | 51% | +5.1% | -4.9% to +15.2% | +5.9% (5) | rejected |
| Japan equities | USD | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Magnificent 7 | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Magnificent 7 | INR | top | 7 | 57% | 47% | +4.1% | -7.9% to +15.7% | +1.0% (7) | rejected |
| Magnificent 7 | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Magnificent 7 | USD | top | 9 | 44% | 48% | -9.6% | -24.1% to +4.6% | +1.9% (7) | rejected |
| Global real estate (REITs) | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global real estate (REITs) | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global real estate (REITs) | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global real estate (REITs) | USD | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Semiconductors | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Semiconductors | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Semiconductors | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Semiconductors | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Silver | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Silver | INR | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Silver | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Silver | USD | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US small cap | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US small cap | INR | top | 10 | 80% | 58% | +7.6% | +1.9% to +12.8% | +7.8% (7) | admitted |
| US small cap | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US small cap | USD | top | 10 | 70% | 56% | +7.0% | +0.8% to +12.9% | +7.1% (7) | admitted |
| Technology | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Technology | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Technology | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Technology | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US Treasuries, long duration | INR | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US Treasuries, long duration | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US Treasuries, long duration | USD | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US Treasuries, long duration | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | INR | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | USD | bottom | 9 | 44% | 55% | -4.2% | -12.8% to +4.0% | n/a | rejected |
| US large cap | USD | top | 5 | 0% | 42% | -13.3% | -18.3% to -8.7% | -7.5% (4) | rejected |
| Utilities | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Utilities | INR | top | 5 | 60% | 50% | +5.7% | -1.3% to +12.3% | +5.7% (5) | rejected |
| Utilities | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Utilities | USD | top | 5 | 60% | 43% | +2.5% | -4.5% to +9.6% | +2.5% (5) | rejected |

### retail washout

Retail abandonment deep in a drawdown: the off-exchange share of volume (a free FINRA proxy for retail participation, sampled monthly since 2009) collapses at least 1.5 standard deviations below its own one-year norm while price sits 25%+ below its one-year high. Pre-registered from an independent framework where it was the highest-lift bottom signal measured (2.48x) — on 19 episodes and the shortest history in that project, which is exactly why it is re-tested here on seventeen years. US-listed assets only; the rupee-native slot simply reads unavailable.

Tested on 60 asset and currency combinations; 0 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| Biotech | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Biotech | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Bitcoin | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Bitcoin | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| China equities | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| China equities | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Broad commodities | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Broad commodities | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer discretionary | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer discretionary | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer staples | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer staples | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US investment-grade credit | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US investment-grade credit | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Crude oil | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Crude oil | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US dollar regime | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US dollar regime | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Emerging markets | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Emerging markets | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Energy | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Energy | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Europe equities | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Europe equities | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Financials | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Financials | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Gold | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Gold | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Healthcare | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Healthcare | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India equities | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India equities | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India midcap | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India midcap | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Industrials | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Industrials | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Japan equities | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Japan equities | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Magnificent 7 | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Magnificent 7 | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global real estate (REITs) | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global real estate (REITs) | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Semiconductors | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Semiconductors | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Silver | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Silver | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US small cap | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US small cap | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Technology | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Technology | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US Treasuries, long duration | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US Treasuries, long duration | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Utilities | INR | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Utilities | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |

### runup percentile

Trailing 12-month return ranked against the asset's own history. The top-side counterpart to drawdown_percentile: a return in the highest few percent of everything this asset has ever done is a top-side condition, not a forecast.

Tested on 60 asset and currency combinations; 1 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| Biotech | INR | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Biotech | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Bitcoin | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Bitcoin | USD | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| China equities | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| China equities | USD | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Broad commodities | INR | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Broad commodities | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer discretionary | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer discretionary | USD | top | 7 | 71% | 48% | +7.2% | -2.2% to +18.3% | +10.4% (4) | rejected |
| Consumer staples | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Consumer staples | USD | top | 9 | 44% | 49% | +1.5% | -1.8% to +5.0% | +2.4% (4) | rejected |
| US high-yield credit | INR | top | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | USD | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US investment-grade credit | INR | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US investment-grade credit | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Crude oil | INR | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Crude oil | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US dollar regime | INR | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US dollar regime | USD | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Emerging markets | INR | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Emerging markets | USD | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Energy | INR | top | 5 | 60% | 59% | -8.8% | -33.4% to +13.8% | -11.9% (5) | rejected |
| Energy | USD | top | 7 | 43% | 55% | -15.6% | -32.3% to +1.8% | -19.8% (5) | rejected |
| Global equities | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Europe equities | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Europe equities | USD | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Financials | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Financials | USD | top | 10 | 70% | 51% | +3.0% | -3.5% to +9.0% | +7.1% (6) | rejected |
| Gold | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Gold | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Healthcare | INR | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Healthcare | USD | top | 9 | 56% | 51% | +0.8% | -8.0% to +9.1% | +7.8% (4) | rejected |
| India equities | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India equities | USD | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India midcap | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India midcap | USD | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Industrials | INR | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Industrials | USD | top | 9 | 56% | 48% | -0.2% | -7.4% to +6.9% | +3.9% (5) | rejected |
| Japan equities | INR | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Japan equities | USD | top | 10 | 50% | 49% | -0.6% | -8.5% to +7.8% | +21.6% (1) | rejected |
| Magnificent 7 | INR | top | 7 | 57% | 45% | -0.0% | -12.5% to +12.1% | -4.9% (7) | rejected |
| Magnificent 7 | USD | top | 10 | 20% | 47% | -16.4% | -34.6% to +1.4% | +2.2% (3) | rejected |
| Global real estate (REITs) | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global real estate (REITs) | USD | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Semiconductors | INR | top | 9 | 56% | 50% | +3.9% | -10.5% to +18.6% | +2.2% (9) | rejected |
| Semiconductors | USD | top | 8 | 50% | 47% | +4.7% | -13.5% to +22.3% | +3.6% (8) | rejected |
| Silver | INR | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Silver | USD | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US small cap | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US small cap | USD | top | 5 | 80% | 56% | +11.9% | +3.3% to +20.8% | +14.6% (4) | admitted |
| Technology | INR | top | 7 | 43% | 46% | +3.6% | -6.7% to +15.2% | +0.9% (7) | rejected |
| Technology | USD | top | 5 | 40% | 49% | -7.8% | -17.6% to +2.8% | -9.6% (4) | rejected |
| US Treasuries, long duration | INR | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US Treasuries, long duration | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | INR | top | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | USD | top | 13 | 38% | 45% | +0.8% | -4.7% to +6.9% | +7.5% (4) | rejected |
| Utilities | INR | top | 6 | 50% | 49% | +3.8% | -4.3% to +11.6% | +1.4% (5) | rejected |
| Utilities | USD | top | 5 | 60% | 45% | +5.6% | -2.0% to +14.0% | +3.6% (3) | rejected |

### sahm rule

The Sahm rule — the three-month average unemployment rate rising half a point above its own twelve-month low, the most reliable simple marker that a recession has already begun. Uses the real-time series (unemployment data as first published), so the backtest sees only what was knowable at the time. The open question the engine answers: by the time this fires, is there still anything left to avoid in equities, or has the market long since moved?

Tested on 4 asset and currency combinations; 0 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| Global equities | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | USD | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | USD | top | 11 | 55% | 45% | +2.2% | -11.6% to +15.8% | -25.2% (2) | rejected |

### stocks bonds ratio

Murphy's stocks-to-bonds risk-appetite gauge, scored as a mean-reversion extreme: US large-cap price over long-Treasury price, ranked against its own history. Top percentiles mark stretched risk appetite (top-side for equities); bottom percentiles mark a flight to safety (bottom-side). Shown in the regime block for context; tested here as a signal because the ratio-at-an-extreme framing matches the drawdown and stretch family that passed, unlike Murphy's lead-lag rotation which this project has rejected.

Tested on 8 asset and currency combinations; 0 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| Global equities | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | INR | top | 7 | 43% | 51% | -1.4% | -8.3% to +6.1% | -3.1% (5) | rejected |
| Global equities | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | USD | top | 7 | 43% | 47% | -2.8% | -10.7% to +5.5% | -4.9% (5) | rejected |
| US large cap | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | INR | top | 7 | 43% | 51% | -2.5% | -8.5% to +3.8% | -3.4% (5) | rejected |
| US large cap | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | USD | top | 7 | 29% | 46% | -3.9% | -10.4% to +3.1% | -5.2% (5) | rejected |

### vix level percentile

The VIX level. High readings mean the market is paying up for protection — fear, historically a bottom-side condition — and sustained low readings mean complacency. Thresholds are the classic absolute levels from the literature: panic at 35 and above, complacency at 12 and below. Because the polarity is inverted, top_zone is the level at or below which the top condition holds.

Tested on 8 asset and currency combinations; 4 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| Global equities | INR | bottom | 12 | 67% | 49% | +10.6% | +4.1% to +17.4% | +11.4% (8) | admitted |
| Global equities | INR | top | 10 | 50% | 51% | +0.0% | -4.1% to +4.3% | +2.1% (7) | rejected |
| Global equities | USD | bottom | 12 | 75% | 54% | +9.9% | +2.4% to +17.8% | +9.2% (8) | admitted |
| Global equities | USD | top | 10 | 50% | 46% | +0.9% | -4.1% to +5.7% | +0.5% (7) | rejected |
| US large cap | INR | bottom | 12 | 67% | 49% | +8.5% | +0.6% to +16.8% | +10.4% (8) | admitted |
| US large cap | INR | top | 15 | 60% | 49% | +1.6% | -3.0% to +6.2% | +2.2% (7) | rejected |
| US large cap | USD | bottom | 17 | 71% | 56% | +8.4% | +1.9% to +15.1% | +8.4% (8) | admitted |
| US large cap | USD | top | 22 | 41% | 43% | -1.4% | -4.9% to +2.0% | +0.6% (7) | rejected |

### vix term backwardation

The VIX term structure: the front index against its three-month counterpart. In calm markets the curve slopes upward; it inverts (backwardation) only when near-term panic outbids the future, which historically marks capitulation windows far more selectively than the VIX level alone.

Tested on 4 asset and currency combinations; 0 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| Global equities | INR | bottom | 21 | 43% | 49% | -2.8% | -7.6% to +1.7% | -1.2% (12) | rejected |
| Global equities | USD | bottom | 21 | 48% | 54% | -3.8% | -9.1% to +1.3% | -1.3% (12) | rejected |
| US large cap | INR | bottom | 24 | 46% | 53% | -2.4% | -7.9% to +3.0% | -2.5% (12) | rejected |
| US large cap | USD | bottom | 24 | 54% | 61% | -2.6% | -8.6% to +2.6% | -2.5% (12) | rejected |

### volume capitulation

A volume spike on a sharp down day: volume at least three standard deviations above its own recent history while the day's return is worse than minus three percent. Capitulation is a crowd event, and this is the cheapest observable trace of one.

Tested on 60 asset and currency combinations; 0 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| Biotech | INR | bottom | 15 | 53% | 51% | -1.7% | -15.8% to +12.3% | -3.3% (10) | rejected |
| Biotech | USD | bottom | 16 | 56% | 52% | +0.9% | -11.0% to +13.1% | -1.7% (10) | rejected |
| Bitcoin | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Bitcoin | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| China equities | INR | bottom | 9 | 56% | 48% | +0.9% | -11.9% to +13.6% | -1.6% (7) | rejected |
| China equities | USD | bottom | 8 | 50% | 46% | -1.9% | -16.7% to +12.4% | -3.4% (7) | rejected |
| Broad commodities | INR | bottom | 7 | 71% | 42% | +13.6% | -3.8% to +31.1% | +23.6% (4) | rejected |
| Broad commodities | USD | bottom | 6 | 50% | 43% | +8.6% | -14.8% to +31.4% | +21.3% (4) | rejected |
| Consumer discretionary | INR | bottom | 9 | 56% | 52% | +6.4% | -6.3% to +19.7% | +6.4% (5) | rejected |
| Consumer discretionary | USD | bottom | 8 | 62% | 48% | +10.1% | -1.0% to +23.8% | +5.2% (5) | rejected |
| Consumer staples | INR | bottom | 8 | 62% | 48% | +4.6% | -3.1% to +15.0% | +2.7% (4) | rejected |
| Consumer staples | USD | bottom | 9 | 67% | 54% | +3.7% | -1.0% to +8.6% | +1.7% (5) | rejected |
| US high-yield credit | INR | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US high-yield credit | USD | bottom | 4 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US investment-grade credit | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US investment-grade credit | USD | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Crude oil | INR | bottom | 14 | 57% | 48% | +4.5% | -15.2% to +25.6% | +12.1% (8) | rejected |
| Crude oil | USD | bottom | 14 | 64% | 48% | +2.3% | -17.0% to +22.0% | +10.2% (8) | rejected |
| US dollar regime | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US dollar regime | USD | bottom | 0 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Emerging markets | INR | bottom | 14 | 79% | 53% | +7.7% | -1.7% to +15.3% | +15.5% (5) | rejected |
| Emerging markets | USD | bottom | 13 | 69% | 50% | +7.7% | -4.7% to +18.3% | +14.0% (4) | rejected |
| Energy | INR | bottom | 14 | 57% | 47% | +3.8% | -6.7% to +13.7% | -1.1% (6) | rejected |
| Energy | USD | bottom | 15 | 53% | 50% | -3.3% | -13.2% to +6.9% | -5.9% (6) | rejected |
| Global equities | INR | bottom | 6 | 50% | 49% | +7.4% | -2.5% to +17.6% | +10.9% (4) | rejected |
| Global equities | USD | bottom | 7 | 43% | 54% | -0.3% | -9.7% to +10.5% | +5.5% (5) | rejected |
| Europe equities | INR | bottom | 9 | 56% | 48% | +6.1% | -1.1% to +13.6% | +9.8% (5) | rejected |
| Europe equities | USD | bottom | 10 | 60% | 51% | +3.5% | -4.1% to +11.0% | +7.4% (5) | rejected |
| Financials | INR | bottom | 12 | 42% | 51% | -3.3% | -13.6% to +6.1% | +0.3% (8) | rejected |
| Financials | USD | bottom | 12 | 33% | 53% | -6.1% | -14.8% to +2.1% | -1.4% (7) | rejected |
| Gold | INR | bottom | 8 | 50% | 46% | -1.7% | -8.2% to +4.9% | -13.8% (2) | rejected |
| Gold | USD | bottom | 8 | 38% | 45% | -6.5% | -14.1% to +0.9% | -7.9% (2) | rejected |
| Healthcare | INR | bottom | 7 | 57% | 45% | +5.8% | -4.3% to +17.1% | +9.4% (4) | rejected |
| Healthcare | USD | bottom | 8 | 50% | 50% | +1.4% | -8.4% to +10.4% | +7.0% (4) | rejected |
| India equities | INR | bottom | 6 | 50% | 39% | +8.7% | -2.9% to +20.3% | +6.6% (5) | rejected |
| India equities | USD | bottom | 7 | 57% | 41% | +4.4% | -5.4% to +14.2% | +2.3% (6) | rejected |
| India midcap | INR | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| India midcap | USD | bottom | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Industrials | INR | bottom | 7 | 71% | 44% | +1.5% | -11.0% to +13.5% | +9.4% (4) | rejected |
| Industrials | USD | bottom | 12 | 58% | 55% | +3.5% | -5.1% to +11.1% | +4.6% (6) | rejected |
| Japan equities | INR | bottom | 8 | 50% | 51% | +6.3% | -2.8% to +17.9% | +14.2% (4) | rejected |
| Japan equities | USD | bottom | 12 | 58% | 51% | +7.6% | +0.1% to +15.2% | +10.0% (4) | rejected |
| Magnificent 7 | INR | bottom | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Magnificent 7 | USD | bottom | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global real estate (REITs) | INR | bottom | 10 | 80% | 53% | +12.1% | -2.1% to +25.7% | +7.7% (4) | rejected |
| Global real estate (REITs) | USD | bottom | 10 | 80% | 48% | +11.9% | -3.4% to +28.1% | +8.1% (4) | rejected |
| Semiconductors | INR | bottom | 14 | 36% | 49% | -4.7% | -15.7% to +6.9% | -10.5% (9) | rejected |
| Semiconductors | USD | bottom | 16 | 44% | 48% | -4.5% | -17.0% to +8.7% | -11.6% (9) | rejected |
| Silver | INR | bottom | 16 | 50% | 39% | +9.7% | -7.5% to +30.4% | +16.9% (8) | rejected |
| Silver | USD | bottom | 16 | 50% | 43% | +7.4% | -9.3% to +27.0% | +15.5% (8) | rejected |
| US small cap | INR | bottom | 12 | 75% | 48% | +7.3% | -2.8% to +16.9% | +11.6% (7) | rejected |
| US small cap | USD | bottom | 12 | 75% | 48% | +4.4% | -4.0% to +12.5% | +10.0% (6) | rejected |
| Technology | INR | bottom | 10 | 40% | 50% | +3.0% | -10.1% to +16.0% | +8.3% (6) | rejected |
| Technology | USD | bottom | 13 | 54% | 54% | -8.0% | -23.1% to +6.3% | +5.4% (6) | rejected |
| US Treasuries, long duration | INR | bottom | 6 | 50% | 44% | +3.1% | -8.8% to +18.6% | -7.8% (3) | rejected |
| US Treasuries, long duration | USD | bottom | 5 | 60% | 47% | +1.4% | -6.8% to +10.2% | -3.0% (3) | rejected |
| US large cap | INR | bottom | 8 | 75% | 53% | +2.1% | -7.6% to +12.1% | +4.0% (5) | rejected |
| US large cap | USD | bottom | 17 | 59% | 59% | +3.0% | -3.2% to +9.3% | +1.0% (6) | rejected |
| Utilities | INR | bottom | 10 | 60% | 50% | +9.4% | -0.2% to +19.9% | +8.3% (6) | rejected |
| Utilities | USD | bottom | 10 | 60% | 56% | +6.6% | -2.5% to +15.4% | +8.6% (6) | rejected |

### yield curve uninvert

The 10-year minus 2-year Treasury spread steepening back through zero after a sustained inversion. The inversion is the famous warning, but the historical damage to equities has clustered after the curve un-inverts — when the cutting cycle and the recession are actually arriving — so the top flag fires on the way out, not the way in. Daily since 1976, which covers the 1980, 1990, 2000, 2007 and 2019 episodes.

Tested on 4 asset and currency combinations; 0 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| Global equities | INR | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | USD | top | 1 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | INR | top | 2 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | USD | top | 6 | 17% | 44% | -0.3% | -7.0% to +8.4% | -2.8% (1) | rejected |

## Weights in use

Weights are the measured edge, discounted for resting on few firings, then normalised so each gauge's weights sum to one. They are specific to the asset, the currency and the direction: an indicator can be worth a great deal on one asset and nothing on another, which is the entire point of measuring.

| Asset | Currency | Gauge | Indicator | Weight |
|---|---|---|---|---|
| Biotech | INR | bottom opportunity | capitulation flush | 0.38 |
| Biotech | INR | bottom opportunity | price vs 200dma z | 0.32 |
| Biotech | INR | bottom opportunity | drawdown percentile | 0.31 |
| Biotech | USD | bottom opportunity | drawdown percentile | 1.00 |
| Biotech | USD | top risk | price vs 200dma z | 1.00 |
| Broad commodities | USD | bottom opportunity | drawdown percentile | 1.00 |
| Consumer discretionary | USD | bottom opportunity | drawdown percentile | 1.00 |
| Consumer staples | USD | top risk | monthly rsi divergence | 1.00 |
| US investment-grade credit | INR | top risk | credit spread percentile | 1.00 |
| US dollar regime | USD | top risk | euphoria rollover | 1.00 |
| Global equities | INR | bottom opportunity | vix level percentile | 0.56 |
| Global equities | INR | bottom opportunity | price vs 200dma z | 0.44 |
| Global equities | INR | top risk | price vs m2 | 1.00 |
| Global equities | USD | bottom opportunity | vix level percentile | 0.58 |
| Global equities | USD | bottom opportunity | price vs 200dma z | 0.42 |
| Global equities | USD | top risk | price vs m2 | 1.00 |
| Europe equities | INR | bottom opportunity | monthly rsi divergence | 1.00 |
| India midcap | INR | bottom opportunity | coppock | 1.00 |
| India midcap | INR | top risk | euphoria rollover | 1.00 |
| India midcap | USD | top risk | price vs 200wma z | 1.00 |
| Industrials | INR | top risk | price vs m2 | 1.00 |
| Magnificent 7 | INR | top risk | price vs 200wma z | 1.00 |
| Semiconductors | INR | top risk | price vs 200wma z | 1.00 |
| Semiconductors | USD | bottom opportunity | price vs 200dma z | 1.00 |
| Semiconductors | USD | top risk | price vs 200wma z | 1.00 |
| US small cap | INR | top risk | price vs m2 | 1.00 |
| US small cap | USD | bottom opportunity | coppock | 1.00 |
| US small cap | USD | top risk | runup percentile | 0.55 |
| US small cap | USD | top risk | price vs m2 | 0.45 |
| Technology | INR | bottom opportunity | drawdown percentile | 1.00 |
| Technology | INR | top risk | price vs 200wma z | 1.00 |
| US Treasuries, long duration | INR | top risk | inflation regime | 1.00 |
| US Treasuries, long duration | USD | top risk | inflation regime | 1.00 |
| US large cap | INR | bottom opportunity | vix level percentile | 1.00 |
| US large cap | USD | bottom opportunity | vix level percentile | 1.00 |
| Utilities | USD | bottom opportunity | capitulation flush | 1.00 |

## Spliced histories

These assets were studied on a history longer than their ETF, by joining the older index or futures series and scaling it to meet the ETF at the overlap. The join is disclosed here and by the explain command; it is never silent.

- Bitcoin: history from 2014-09-17
- Crude oil: history from 2000-08-23
- Gold: history from 2000-08-30
- India equities: history from 2007-09-17
- India midcap: history from 2007-09-24
- Japan equities: history from 1965-01-05
- Magnificent 7: history from 1985-10-01
- Silver: history from 2000-08-30
- US large cap: history from 1927-12-30

## Caveats

- Forward-return windows overlap, so firings are not independent. The block bootstrap accounts for this; a naive interval would look much narrower and mean much less.
- Assets with short histories produce few independent firings. Bitcoin in particular covers only a handful of cycles, and any verdict on it should be read as provisional rather than settled.
- Rupee results rest on shorter histories than dollar results. A dollar series can be spliced back decades, but a rupee view cannot begin before the exchange rate series does, so the same asset offers fewer firings in rupees. Where the two currencies disagree about an indicator, the dollar verdict is usually the better-evidenced one.
- Thresholds were fixed from the literature before this engine ever ran, and are not tuned in response to these results. A test enforces that a threshold and a validation result cannot change in the same commit.
- Surviving this test means an indicator has historically carried information on this asset. It does not mean it will continue to, and it is not a forecast.
