# Week 3 — Metric Calculation & Data Modeling

## What this does
- Calculates Total Spend, CPC, CAC, and ROAS per channel, for each of the
  three attribution models (First-Touch, Last-Touch, Linear).
- Models the results into a star schema:
  - `dim_channel_spend` — dimension table (spend + clicks per channel)
  - `fact_channel_kpis` — fact table (one row per channel per attribution model,
    with cac/roas/revenue computed) — ready for Power BI / Tableau / any BI tool.

## Prerequisites
Needs Weeks 1 & 2 already run so `data/attribution.db` exists with the
`customers`, `touchpoints`, and attribution SQL views loaded.

## Run it
```bash
python 03_kpis_star_schema.py
```

## Assumption
Average order value assumed at $120 (source data has no revenue column) —
see `AVG_ORDER_VALUE` constant at the top of the script.
