# Bank Data Analysis — PySpark ETL

End-to-end ETL and analysis of global banking data using Apache Spark, covering market
capitalisation, currency conversion and country-level ranking.

**Stack:** PySpark · Pandas · Seaborn · Matplotlib

---

## Problem

Analyse the world's largest banks by market capitalisation and produce comparable,
currency-normalised figures for cross-country analysis — a workload that demonstrates
distributed processing rather than a single-machine pandas pipeline.

## Data

- Source: archived Wikipedia *List of largest banks* page (Sep 2023 snapshot), scraped programmatically.
- Exchange-rate table for **USD, GBP, EUR and INR** to convert market cap into a common currency.
- Single table, three core columns (rank, bank name, market cap) plus derived fields.

## Pipeline

1. **Extract** — initialise a Spark session, ingest the scraped table into a DataFrame.
2. **Transform** — standardise column names (lowercase/underscores), strip currency symbols
   and commas, cast market cap to numeric USD billions, join exchange rates, drop nulls.
3. **Load / analyse** — Spark aggregations feeding Pandas/Seaborn visualisations.
4. **Explore** — distribution of market cap, top-10 ranking, quartile segmentation and
   cumulative market dominance.

## Outputs

- Cleaned, currency-normalised bank dataset.
- Top-10 banks by market cap, quartile bands and concentration curve.
- Insight into how much of total market cap sits with the largest institutions and where
  outliers distort the distribution.

## Files

| File | Description |
|---|---|
| `Bank_ETL_Analysis.ipynb` | PySpark ETL, transformations and EDA |
| `Bank_ETL_Analysis_Report.pdf` | Data preparation, cleaning, EDA summary and conclusion |
