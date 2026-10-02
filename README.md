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

Data used by these notebooks comes from Convex Lake's own API — see
[the API docs](https://convexlake.com/docs) for current coverage.
