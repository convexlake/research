# Convex Lake Research

Research notebooks built on Convex Lake's own historical market data.

## Notebooks

- **`brier_score_by_category.ipynb`** — Prediction market calibration by category, computed
  directly from Polymarket candles data across 12 categories, checked at five points through
  each market's observed lifetime (10%/25%/50%/75%/90%). Finds that calibration is not just
  domain-specific in level (entertainment/tech/people well-calibrated, sports/esports
  poorly-calibrated) but in dynamics — some categories sharpen sharply as resolution
  approaches, others (notably sports) barely improve at all.

Data used by these notebooks comes from Convex Lake's own API — see
[the API docs](https://convexlake.com/docs) for current coverage.
