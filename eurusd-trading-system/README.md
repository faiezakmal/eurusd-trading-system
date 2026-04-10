# EUR/USD Volatility-Based Trading System

A hedge-fund quality signal generation, backtesting and risk analysis system for EUR/USD built entirely on realised volatility dynamics.

---

## Overview

The core insight is that **realised volatility is highly autocorrelated and predictable** (ARRV OOS R² = 0.904). This predictability is exploited to build a systematic long/short signal that enters the market when volatility spikes into the top regime and exits when it reverts — filtered by a trend direction filter to avoid noise trades.

---

## Pipeline

```
Data & Features
    └── Log returns, Realised Vol, ATR, EMA filters, Vol percentile rank, HAR-RV components

Stationarity Tests
    └── ADF on price, returns, realised vol, squared/absolute returns

Forecasting Models
    ├── EWMA (λ=0.94)
    ├── HAR-RV   — daily / weekly / monthly components
    ├── ARRV(5)  — AutoReg on Realised Vol  [best: OOS R² = 0.904]
    ├── GARCH(1,1)
    ├── EGARCH
    ├── APARCH
    └── FIGARCH

Regime Detection
    └── K-Means clustering → Low Vol / Med Vol / High Vol regimes

Signal Generation
    ├── Entry: Realised Vol > adaptive 70th percentile (60-day rolling)
    ├── Direction: EMA-50 trend filter (long above / short below)
    ├── Regime gate: no entries in Low Vol regime
    └── Exit: Vol < 30th percentile OR trend reversal

Backtesting
    ├── Inverse-volatility position sizing (target-vol approach)
    ├── Transaction cost: 0.5 pip per trade
    └── Walk-forward: Train 60% / Validation 20% / Test 20%

Risk & Robustness
    ├── Historical VaR & CVaR (90% / 95% / 99%)
    ├── Monte Carlo simulation (1,000 paths, 252 days)
    └── Parameter sensitivity heatmap (entry × exit percentile)
```

---

## Key Results

| Metric | Value |
|---|---|
| Best forecast model | ARRV(5) — OOS R² = 0.904 |
| Sharpe Ratio | See notebook output |
| Sortino Ratio | See notebook output |
| Calmar Ratio | See notebook output |
| Max Drawdown | See notebook output |

---

## Files

| File | Description |
|---|---|
| `EURUSD_Volatility_Trading_System.ipynb` | Main notebook — full pipeline |
| `data/Eurousd.csv` | EUR/USD daily OHLCV data |
| `legacy/Euro USD volatility Calculations.ipynb` | Original volatility modelling work |
| `legacy/Eurousd Trade strat.ipynb` | Original trading strategy work |
| `legacy/Complete_Single_Sheet.ipynb` | Early exploratory analysis |

---

## Setup

```bash
# Clone and create environment
git clone https://github.com/faiezakmal/eurusd-trading-system
cd eurusd-trading-system/eurusd-trading-system

python -m venv venv
venv\Scripts\activate        # Windows
source venv/bin/activate     # Mac/Linux

pip install pandas numpy matplotlib seaborn scipy statsmodels arch scikit-learn ipykernel
```

Open `EURUSD_Volatility_Trading_System.ipynb` in VS Code or Jupyter and select the venv kernel.

---

## Dependencies

```
pandas · numpy · matplotlib · seaborn · scipy
statsmodels · arch · scikit-learn · ipykernel
```
