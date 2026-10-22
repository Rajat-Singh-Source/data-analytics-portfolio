# Used Car Price Prediction — Regularised Regression

Regression model that predicts the resale price of used cars from listing features, with
a focus on feature importance and controlling overfitting through regularisation.

**Stack:** Python · Pandas · scikit-learn · Matplotlib · Seaborn

---

## Problem

A used-car reseller wants to price vehicles consistently from their specifications
(mileage, fuel type, transmission, engine size, age, brand) and understand which attributes
actually move price.

## Approach

1. **Data understanding** — schema, missing values, duplicates, target distribution.
2. **Preprocessing** — type fixes, missing-value treatment, categorical encoding, outlier
   handling on price and mileage.
3. **EDA** — price vs mileage, age and fuel type; correlation analysis.
4. **Modelling** — linear baseline, then **Ridge** and **Lasso** with alpha tuning.
5. **Evaluation** — train vs test R², residual and linearity checks, coefficient analysis.

## Results

- Best regularised model reached **test R² ≈ 0.92** (train 0.917 / test 0.922 at low alpha),
  with train–test scores tracking closely — no meaningful overfitting.
- Higher alpha values shrink coefficients toward zero: at alpha ≥ 0.5 the model collapses to
  the mean (R² ≈ 0), which made the regularisation path easy to read and justify.
- Coefficient analysis ranks the price drivers, with vehicle age, engine size/power and
  mileage among the strongest.

## Files

| File | Description |
|---|---|
| `Car_Price_Prediction.ipynb` | EDA, preprocessing, Ridge/Lasso tuning and evaluation |
| `Car_Price_Prediction_Report.pdf` | Report with alpha tables, residual plots and conclusions |
