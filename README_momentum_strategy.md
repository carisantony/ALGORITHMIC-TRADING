# 📁 Momentum-Based Long-Short Strategy (Top 25 Tech Stocks)

This repository contains the full implementation of a factor-based, market-neutral long-short trading strategy that exploits momentum sensitivity (β_umd) among the top 25 technology stocks in the S&P 500.

---

## 📌 Project Overview
- **Objective**: Use Fama-French + Momentum factor models to rank tech stocks by momentum exposure and construct a long-short portfolio.
- **Universe**: Top 25 tech stocks in S&P 500 (2019–2024)
- **Signal**: Momentum beta (β_umd) from 60-day rolling OLS regressions
- **Execution**: Monthly rebalancing; equal-weighted long/short; market-neutral
- **Performance**:
  - Sharpe Ratio: 0.24
  - Cumulative Return: 17.69%

---

## 🧠 Strategy Methodology
- Download daily price data via Alpaca API
- Join with Fama-French 5-Factor + UMD data (Ken French library)
- Compute daily returns and excess returns
- Estimate momentum factor exposure (β_umd) via 60-day rolling regression
- At each month-end:
  - Long top 5 β_umd stocks
  - Short bottom 5 β_umd stocks
- Evaluate performance using Sharpe ratio and cumulative returns

---

## 📁 Repository Structure
```
📂 momentum-longshort-strategy
├── data
│   ├── top25_tech_sp500_close_prices.csv
│   └── FF5.csv
├── notebooks
│   └── strategy_backtest.ipynb
├── outputs
│   └── performance_plot.png
├── main.py
├── README.md
└── requirements.txt
```

---

## 🔍 Key Results
- The strategy shows strong recovery in trending markets (2023–2024)
- Underperformance during COVID and mean-reverting phases (2021–2022)
- Consistent monthly application of signal with robust logic

---

## 📈 Future Enhancements
- Add volatility-based weighting
- Simulate execution costs and slippage
- Expand to cross-sector or global universe
- Include multi-factor signal stacking (e.g., value + momentum)

---

## ⚙️ Requirements
- Python 3.8+
- Libraries: pandas, numpy, statsmodels, matplotlib, pptx

Install via pip:

```bash
pip install -r requirements.txt
```

## 🧾 License
This project is for academic purposes (FIN 7053 - Algorithmic Trading Final Project)

---

## 🙋‍♂️ Author
[CARIS ANTONY MAMPILLY] – Final Project for Algorithmic Trading Course
