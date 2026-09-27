# Validation scorecard

Generated for as-of date 2026-07-24.

## What this measures

For each indicator, on each asset, in each currency, this asks one question: every time the indicator crossed into its claimed zone, what happened over the following twelve months, compared with what would have happened at a randomly chosen moment in the same era? An indicator that cannot beat that comparison is rejected and takes no part in the dashboard's scores, however well known it is.

Admission requires at least 5 independent firings, a positive edge, a hit rate at least 10% above the base rate, and a 90% confidence interval on the edge that excludes zero. The interval comes from a block bootstrap that resamples whole firings, because overlapping forward windows are not independent observations and treating them as though they were would overstate confidence.

## Summary

- Combinations tested: 8
- Admitted: 0
- Admitted at half weight: 0
- Rejected: 6
- Not enough data to judge: 2

Roughly 0% of the combinations tested survived. A scorecard where everything passed would be evidence that the engine is not discriminating, not evidence that the indicators are good.

## The multiple-testing problem

6 combinations were tested statistically and 0 survived. Across that many independent tests at a 90% confidence level, roughly 0 would be expected to pass by chance alone even if every indicator were worthless.

**0 survivors against a chance expectation of 0 is not evidence of skill.** The admitted set below is consistent with what testing this many combinations would throw up at random. Individual entries may still be real — the semiconductor results in particular have both a large edge and a plausible mechanism in a genuinely cyclical industry — but the set as a whole should not be read as a group of proven indicators.

The honest conclusion from this run is that the technical family alone does not carry demonstrable information at a twelve-month horizon on most of these assets. That is a useful thing to have established, and it is the reason the dashboard still runs on equal weights while saying so plainly.

## Indicators that failed everywhere

These earned no place on any asset in any currency. They remain configured and computed, and they still appear in the per-asset tables on the dashboard, but they contribute nothing to any score.

- **skew percentile** — rejected on all 8 combinations tested. Worst case for it: on us_large_cap in USD, hit rate 56% against a base rate of 60% is only -4%, short of the 10% required

## Results by indicator

### skew percentile

The CBOE SKEW index: how much more the options market is willing to pay for far-out-of-the-money crash protection than for equivalent upside calls — a direct read on tail-risk pricing, distinct from VIX's at-the-money volatility level. Free via the same Yahoo Finance pull already used for VIX, back to 1990. Scored by percentile of its own history rather than a fixed absolute level, because unlike VIX, SKEW has no well-established "classic" panic/complacency threshold in the literature. Tested first, on the same two assets and the same inverted polarity convention as vix_level_percentile, so the two can be compared directly. Pre-registered with a known reason for skepticism: SKEW has a real reputation among practitioners for spiking without incident and sitting unremarkably before genuine crashes (2020 included) — tested anyway, on the record either way.

Tested on 8 asset and currency combinations; 0 admitted.

| Asset | Currency | Direction | Firings | Hit rate | Base rate | Edge | 90% interval | Out of sample | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| Global equities | INR | bottom | 28 | 39% | 47% | -0.5% | -4.5% to +3.3% | +0.2% (16) | rejected |
| Global equities | INR | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| Global equities | USD | bottom | 28 | 50% | 54% | -0.5% | -5.1% to +3.8% | +1.3% (16) | rejected |
| Global equities | USD | top | 3 | n/a | n/a | n/a | n/a | n/a | not enough data |
| US large cap | INR | bottom | 34 | 44% | 50% | +0.9% | -2.6% to +4.8% | -0.4% (16) | rejected |
| US large cap | INR | top | 5 | 60% | 49% | +12.6% | -0.3% to +27.3% | -1.0% (1) | rejected |
| US large cap | USD | bottom | 36 | 56% | 60% | +1.0% | -2.6% to +4.7% | +0.8% (16) | rejected |
| US large cap | USD | top | 11 | 64% | 41% | +6.8% | -5.4% to +18.5% | -4.2% (1) | rejected |

## Weights in use

Weights are the measured edge, discounted for resting on few firings, then normalised so each gauge's weights sum to one. They are specific to the asset, the currency and the direction: an indicator can be worth a great deal on one asset and nothing on another, which is the entire point of measuring.

No combination earned a weight. Every gauge is unscored until that changes.

## Spliced histories

These assets were studied on a history longer than their ETF, by joining the older index or futures series and scaling it to meet the ETF at the overlap. The join is disclosed here and by the explain command; it is never silent.

- US large cap: history from 1927-12-30

## Caveats

- Forward-return windows overlap, so firings are not independent. The block bootstrap accounts for this; a naive interval would look much narrower and mean much less.
- Assets with short histories produce few independent firings. Bitcoin in particular covers only a handful of cycles, and any verdict on it should be read as provisional rather than settled.
- Rupee results rest on shorter histories than dollar results. A dollar series can be spliced back decades, but a rupee view cannot begin before the exchange rate series does, so the same asset offers fewer firings in rupees. Where the two currencies disagree about an indicator, the dollar verdict is usually the better-evidenced one.
- Thresholds were fixed from the literature before this engine ever ran, and are not tuned in response to these results. A test enforces that a threshold and a validation result cannot change in the same commit.
- Surviving this test means an indicator has historically carried information on this asset. It does not mean it will continue to, and it is not a forecast.
