# NYC Yellow Taxi — Operations EDA

Exploratory data analysis of 2023 New York City yellow-taxi trips to find where operations
can improve service efficiency, revenue and passenger experience.

**Stack:** Python · Pandas · NumPy · Matplotlib · Seaborn

---

## Problem

Acting as an analyst for a NYC taxi operation: use a year of trip data to identify demand
patterns, pricing behaviour and zone-level imbalances, then translate them into
operational recommendations.

## Data preparation

- Sampled monthly 2023 parquet files down to a combined **~1.89M trips**.
- Standardised column names and merged the duplicated `airport_fee` / `Airport_fee`
  columns (schema drift across monthly files) into one field.
- Imputed missing `passenger_count` with the mode; treated outliers in trip distance,
  fare and duration.
- Parsed pick-up/drop-off timestamps and derived hour, weekday/weekend and distance tiers.

## Analysis

- Trip volume by hour, day of week and month — weekday vs weekend profiles.
- Top pickup/drop-off zones; night-time hotspots and pickup/drop-off imbalance.
- Revenue share of day-time vs night-time trips.
- Average fare per mile by hour, day, passenger count and vendor (distance-tiered).
- Tip percentage behaviour and surcharge frequency by zone and time.

## Key insights

- **Temporal:** peak demand at rush hours, weekends and specific months, with a distinct
  night-time market concentrated in nightlife zones.
- **Financial:** fare tracks distance and duration; tips vary with trip characteristics
  rather than being uniform.
- **Geographical:** demand is concentrated around airports, transit hubs and popular
  destinations, with visible pickup/drop-off imbalances in some zones.
- **Vendor:** fare-per-mile differs between vendors, especially in longer distance tiers.

## Recommendations

- Rebalance vehicle supply toward the top hourly zones and nightlife districts.
- Use distance-tiered pricing/discounting rather than one rate across vendors.
- Target surcharge and airport-fee windows where demand is predictable.

## Files

| File | Description |
|---|---|
| `NYC_Taxi_EDA.ipynb` | Cleaning, bivariate/multivariate EDA and visualisations |
| `NYC_Taxi_Operations_Report.pdf` | Written report with figures, insights and recommendations |
