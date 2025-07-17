# Strategic Asset Allocation and Risk Optimization for Multi-Asset Portfolio

**Author:** MD Amir Khan | **Date:** August 2024  
**Tools:** Python, Riskfolio-Lib, SciPy (SLSQP), Matplotlib, yFinance, NumPy, Pandas

---

## 📌 Project Overview

This project focuses on building and evaluating optimized portfolio strategies across 25 publicly traded equities from 2020–2024. It leverages modern portfolio theory, Monte Carlo simulations, risk-based optimization, and financial engineering tools to construct robust, risk-aware portfolios that maximize the Sharpe ratio under different risk measures, including CVaR.

---

## 💼 Key Objectives

- Develop a quantitative framework for multi-asset strategic asset allocation.
- Optimize portfolios under multiple risk constraints using `Riskfolio-Lib` and `SciPy SLSQP`.
- Compare risk-adjusted return trade-offs across 13+ risk measures.
- Visualize efficient frontiers, asset allocations, and portfolio risk profiles.
- Implement both classical and machine-driven optimization techniques to validate model robustness.

---

## ⚙️ Tools and Libraries

| Tool / Library     | Purpose                                                       |
|--------------------|---------------------------------------------------------------|
| **Riskfolio-Lib**  | Portfolio optimization using various risk measures and models |
| **SciPy (SLSQP)**  | Constrained optimization for Sharpe-maximizing portfolios      |
| **Matplotlib**     | Visualization of portfolio weights and efficient frontiers    |
| **yFinance**       | Historical financial data retrieval for equities              |
| **Pyfolio**        | Performance and risk attribution (optional integration)       |
| **NumPy & Pandas** | Data manipulation, return calculations, and matrix operations |

---

## 🧠 Methodology

1. **Data Collection:**  
   - Retrieved adjusted close price data for 25 tech, growth, and cyclical stocks using `yfinance`.
   - Computed daily returns and log returns.

2. **Portfolio Construction & Optimization:**  
   - Created a `Portfolio` object via `Riskfolio-Lib` and configured historical mean/covariance.
   - Optimized for maximum Sharpe ratio under:
     - **Mean-Variance (MV)**
     - **Conditional Value at Risk (CVaR)**
     - 13+ other risk measures (MDD, CDaR, SLPM, etc.)

3. **Monte Carlo Simulation:**  
   - Ran 10,000 random portfolios to estimate the empirical efficient frontier.
   - Identified portfolio with the highest Sharpe ratio via brute force.

4. **SLSQP Optimization:**  
   - Applied `scipy.optimize.minimize` with bounds and constraints to solve for weights that maximize Sharpe ratio analytically.

5. **Visualization:**  
   - Plotted efficient frontiers and frontier composition.
   - Compared asset allocations across all risk measures using grouped bar charts.

---

## 📊 Results

- **Maximum Sharpe Ratio (Monte Carlo):** 0.81  
- **Maximum Sharpe Ratio (SLSQP):** 1.24  
- **Expected Annual Return (Optimized):** 48.48%  
- **Expected Volatility (Optimized):** 39.24%  

Efficient frontiers were plotted for both Mean-Variance and Mean-CVaR models, showing improved stability under CVaR with reasonable downside risk protection.

---

## 📁 Project Structure

├── data/ # Raw & processed market data
├── notebooks/ # Jupyter notebooks for simulation & optimization
├── plots/ # Efficient frontiers, pie charts, bar charts
├── requirements.txt # List of libraries to install
└── README.md # This file


🚀 Future Extensions
Integrate Black-Litterman model for subjective views and market equilibrium.

Add automated rebalancing and backtesting using Zipline.

Incorporate regime switching models to adapt to changing market volatility.
