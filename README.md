# German Electricity Demand Forecasting

**Student:** Lokesh Rottela  
**Student ID:** 24083481

## Overview

This repository contains the completed time-series forecasting case study for German electricity demand. The executed notebook compares benchmark, statistical, machine-learning and neural-network approaches using hourly demand from January 2015 to September 2020.

## Main notebook

`24083481_German_Electricity_Demand_Forecasting.ipynb`

## Methods included

- Data preparation and daily/weekly aggregation
- Exploratory analysis and STL decomposition
- ADF, KPSS, ACF, PACF and differencing
- Mean, naive, seasonal-naive and drift benchmarks
- Two-stage AIC-based SARIMA selection
- SARIMA residual diagnostics and prediction intervals
- Conditional SARIMAX using Berlin temperature and German holidays
- Random Forest and Gradient Boosting with time-series cross-validation
- Hourly LSTM tuning and recursive forecasting
- Diebold-Mariano comparison and structural-change analysis

## Forecast design

- The final 104 complete weeks form an untouched chronological test set.
- Fixed-origin and conditional forecasts are labelled separately.
- Observed test-period temperature is used only for models explicitly labelled conditional.
- Demand lag and rolling features are generated without using future target values.
- Feature models forecast recursively across the test period.
- Scaling and hyperparameter selection use training data only.

## Key result

Gradient Boosting achieved the lowest numerical weekly RMSE, but its improvement over seasonal naive was not statistically significant. Seasonal naive was therefore selected as the operational recommendation because it provides competitive accuracy, transparency and low maintenance.

## Repository structure

```text
german_electricity_forecasting_submission/
├── 24083481_German_Electricity_Demand_Forecasting.ipynb
├── README.md
├── requirements.txt
├── .gitignore
├── data/
│   └── processed/
├── figures/
└── results/
    ├── models/
    ├── all_weekly_metrics.csv
    ├── metrics_by_period.csv
    ├── experiment_summary.json
    ├── operational_recommendation.json
    └── submission_validation.txt
```

## Running the notebook

1. Upload the notebook to Google Colab.
2. Select Python 3 and a T4 GPU. The GPU mainly accelerates the LSTM; SARIMA remains CPU-bound.
3. Install dependencies using `pip install -r requirements.txt` when running locally.
4. Restart the runtime and run all cells in order.
5. The notebook regenerates its processed data, figures and complete results folders.

The notebook already contains the outputs from the completed execution.
