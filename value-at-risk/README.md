# Value at Risk — Multi Asset Class

Portfolio-level Value at Risk (VaR) analysis across four major asset classes using log-normal return modelling.

---

## Assets Covered

| Asset | Ticker | Class |
|---|---|---|
| EUR/USD | EURUSD=X | FX |
| S&P 500 | ^GSPC | Equity Index |
| Nifty 50 | ^NSEI | Equity Index |
| Hang Seng | (HSI) | Equity Index |

---

## Methodology

```
Data Collection
    └── yfinance API pull for all assets

Return Modelling
    └── Log-normal daily returns: r_t = ln(P_t / P_{t-1})

Portfolio Construction
    ├── Covariance matrix of log returns
    ├── Correlation heatmap across assets
    └── Equal-weighted portfolio aggregation

VaR Estimation
    ├── Parametric VaR — mean/std of portfolio log returns
    ├── Historical VaR — empirical percentile approach
    └── Multiple confidence levels (90% / 95% / 99%)

Visualisation
    ├── Log return time series per asset
    ├── Portfolio value evolution
    ├── Correlation heatmap
    └── VaR distribution plots
```

---

## Key Concepts

- **VaR**: maximum expected loss over a given horizon at a given confidence level
- **Log-normal returns**: more appropriate than arithmetic returns for multi-period compounding
- **Covariance matrix**: captures cross-asset diversification benefit
- **Correlation breakdown**: important during stress periods (correlations spike to 1)

---

## Files

| File | Description |
|---|---|
| `Value at Risk Multi Asset class.ipynb` | Full VaR analysis notebook |

---

## Setup

```bash
pip install pandas numpy matplotlib seaborn yfinance ipykernel
```
