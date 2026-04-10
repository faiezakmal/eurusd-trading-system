# Quantitative Finance Portfolio

A collection of quantitative finance projects covering volatility modelling, trading signal systems, risk management and credit risk prediction.

---

## Projects

### 1. [EUR/USD Volatility Trading System](./eurusd-trading-system/)
> Hedge-fund quality signal generation and backtesting system for EUR/USD

- Volatility forecasting: EWMA, HAR-RV, ARRV, GARCH/EGARCH/APARCH/FIGARCH
- K-Means regime detection (Low / Med / High vol)
- Adaptive entry/exit signals with EMA trend filter
- Inverse-volatility position sizing
- Full risk suite: VaR, CVaR, Monte Carlo, walk-forward test
- Performance dashboard: Sharpe, Sortino, Calmar, monthly heatmap

### 2. [Value at Risk — Multi Asset Class](./value-at-risk/)
> Portfolio-level VaR analysis across equities, FX and indices

- Assets: EUR/USD, S&P 500, Nifty 50, Hang Seng
- Log-normal return modelling, covariance matrix, correlation heatmap
- Historical and parametric VaR with multiple confidence levels
- Equal-weighted portfolio aggregation

### 3. [Credit Risk Model Pipeline](./credit-risk/)
> End-to-end ML pipeline for predicting credit default probability

- Dataset: German Credit (Hofmann, 1000 entries, 20 features)
- Exploratory analysis, feature engineering, encoding
- Classification models with performance evaluation
- Business-ready risk scoring output

---

## Stack

![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-grey?logo=pandas)
![NumPy](https://img.shields.io/badge/NumPy-grey?logo=numpy)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-grey?logo=scikitlearn)
![Statsmodels](https://img.shields.io/badge/Statsmodels-grey)
![ARCH](https://img.shields.io/badge/ARCH-GARCH-grey)
![Matplotlib](https://img.shields.io/badge/Matplotlib-grey?logo=plotly)
![Seaborn](https://img.shields.io/badge/Seaborn-grey)
![Jupyter](https://img.shields.io/badge/Jupyter-grey?logo=jupyter)
