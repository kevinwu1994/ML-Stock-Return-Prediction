# ML-Based Cross-Sectional Equity Return Prediction

## Project Overview

This project develops a machine learning framework for cross-sectional stock return prediction and portfolio construction.

Using monthly stock prices, macroeconomic variables, and firm-level fundamental factors, the project evaluates whether machine learning models can generate profitable trading signals after transaction costs.

The framework combines:

* Rolling-window out-of-sample prediction
* Semiannual hyperparameter tuning
* Lagged fundamental variables
* Long-short portfolio construction
* Transaction cost modeling
* Signal smoothing and turnover control
* Robustness testing

The project is designed as a realistic quantitative research workflow rather than a purely predictive machine learning exercise.

---

## Models

The following models are evaluated:

* Ridge Regression
* Random Forest
* Gradient Boosting

---

## Features

### Technical Features

* 1-month momentum
* 3-month momentum
* 6-month momentum
* 3-month rolling volatility

### Macroeconomic Features

* Short-term interest rate (TB3MS)
* Term spread
* Inflation

### Fundamental Features

* PE ratio
* PB ratio
* ROE
* Profit Margin
* Debt-to-Equity
* Market Capitalization

Composite and rank-based features are also constructed to improve cross-sectional comparability.

---

## Methodology

### Rolling Prediction Framework

* Training window: 72 months
* Prediction frequency: Monthly
* Hyperparameter tuning: Every 6 months
* Fundamental lag: 1 month
* Out-of-sample period: March 2023 to February 2026

All predictions are generated strictly out-of-sample to reduce look-ahead bias.

---

## Portfolio Construction

The predicted returns are translated into a long-short equity strategy with:

* Entry threshold: Top/Bottom 15%
* Exit threshold: 35%
* Rebalancing frequency: Every 2 months
* Signal smoothing window: 3 months

Transaction costs are incorporated into the backtest.

---

## Main Results

### Best Model: Random Forest

| Metric                | Value  |
| --------------------- | ------ |
| Annualized Net Return | 23.1%  |
| Net Sharpe Ratio      | 1.01   |
| Final Portfolio Value | 1.78   |
| Max Drawdown          | -16.9% |
| Hit Ratio             | 61.8%  |

The results suggest that nonlinear machine learning models can capture cross-sectional return patterns not fully explained by traditional linear models.

---

## Repository Structure

```text
notebooks/     -> Main project notebooks
report/        -> Final report and presentation
outputs/       -> Strategy outputs and evaluation tables
figures/       -> Performance plots
data_sample/   -> Small sample datasets
```

---

## Limitations

Several limitations remain:

* Fundamental data is not fully point-in-time
* The stock universe is relatively limited
* Transaction costs are simplified
* The out-of-sample period is relatively short

The framework is intended for research and educational purposes.

---

## Future Improvements

Potential future improvements include:

* Larger stock universe
* Sector-neutral portfolio construction
* More realistic execution cost modeling
* Point-in-time institutional datasets
* Live trading integration

---
## Quick Start

```bash
pip install -r requirements.txt
```

Open:

```text
notebooks/ML_FinalProject.ipynb
```

Run all cells to reproduce the results.

## Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* Matplotlib
* Yfinance
* Jupyter Notebook

---

## Author
Fenglei Wu 
|MS Candidate | Machine Learning & Quantitative Finance
