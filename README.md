# Convex Lake Research

Research notebooks built on Convex Lake's own historical market data.

## Notebooks

- **`brier_score_by_category.ipynb`** — Prediction market calibration by category, computed
  directly from Polymarket candles data across 12 categories, checked at five points through
  each market's observed lifetime (10%/25%/50%/75%/90%). Finds that calibration is not just
  domain-specific in level (entertainment/tech/people well-calibrated, sports/esports
  poorly-calibrated) but in dynamics — some categories sharpen sharply as resolution
  approaches, others (notably sports) barely improve at all.

- **`kalshi_btc_liquidity.ipynb`** — Full census (all 932,485 locally downloaded files, no
  sampling) of Kalshi's BTC hourly strike-ladder markets. Finds 12.2% of listed markets ever
  trade, a -0.318 correlation between volume and spread, and a moneyness-vs-spread proxy that
  initially ran backwards because of dead default quotes — corrected at the row level, which
  then exposes a second, unexplained quoting artifact confirmed across 665,000+ rows.

- **`polymarket_weather_calibration_by_city.ipynb`** — Full census of Polymarket's weather
  markets, by city. Finds Atlanta calibrates best and Seoul worst, with London and New York
  (the two highest-volume cities by far) sitting in the middle of the pack — sample size
  doesn't predict calibration (r = 0.28, not significant). A multi-checkpoint breakdown shows
  every city sharpens toward resolution and converges to a tight band by 90% of a market's
  lifetime, regardless of its mid-life ranking.

- **`copytrading_slippage_simulation.ipynb`** — Can you copytrade a profitable
  prediction-market account? Real accounts, real trades, real millisecond-resolution order
  books on Predict.fun and Limitless, with a round-trip latency model grounded in each
  venue's actual settlement architecture (off-chain matching vs. on-chain Base
  confirmation). Reconstructs real equity curves: a directional strategy survives
  copytrading with a ~5% haircut; a thin-margin arbitrage strategy goes from a real
  +$45,492 profit to a loss on the identical trades, because its edge is smaller than the
  tail risk a realistic delay exposes it to.

Data used by these notebooks comes from Convex Lake's own API — see
[the API docs](https://convexlake.com/docs) for current coverage.
