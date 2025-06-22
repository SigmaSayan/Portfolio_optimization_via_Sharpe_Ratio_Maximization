# 📈 Portfolio Optimization via Sharpe Ratio Maximization

This project implements a portfolio optimization strategy using **Modern Portfolio Theory (MPT)** to determine the optimal allocation of assets that maximizes the **Sharpe Ratio**, thereby improving returns relative to risk.

---

## 🧠 Key Concepts

- **Sharpe Ratio**: A measure of risk-adjusted return.
- **Modern Portfolio Theory (MPT)**: Optimizes portfolio by balancing return and risk through diversification.
- **SLSQP Optimization**: A numerical method used to solve constrained optimization problems.

---

## 📊 Assets Used

- ETFs: `SPY`, `BND`, `GLD`, `QQQ`, `VTI`
- Data Source: [`yfinance`](https://pypi.org/project/yfinance/) (10 years of adjusted close prices)

---

## ⚙️ Methodology

1. **Data Collection**: Historical price data pulled via `yfinance`.
2. **Preprocessing**: Calculated daily **log returns** and annualized **covariance matrix**.
3. **Optimization**:
   - Objective: **Maximize Sharpe Ratio**
   - Constraints:
     - Sum of weights = 1
     - No short selling (`weights >= 0`)
     - Max exposure per asset: `<= 0.45`
   - Solver: `SLSQP` from `scipy.optimize.minimize`
4. **Output**:
   - Optimal Weights
   - Expected Annual Return
   - Expected Volatility
   - Sharpe Ratio
5. **Visualization**: Bar plot of optimal weights using `matplotlib`.

---

## ✅ Results

- **Optimal Sharpe Ratio**: `0.81`
- **Expected Annual Return**: `12.25%`
- **Expected Volatility**: `12.67%`
- **Optimal Allocation**:
  - **GLD**: `45.00%`
  - **QQQ**: `45.00%`
  - **BND**: `9.03%`
  - **SPY**: `0.97%`
  - **VTI**: `0.00%`

---

## 📦 Dependencies

- Python 3.11.5
- `numpy`
- `pandas`
- `yfinance`
- `matplotlib`
- `scipy`

---

## ✍️ Author

**Sayan Das**  
*B.Tech + M.Tech in Mechanical & Financial Engineering*  
*Indian Institute of Technology, Kharagpur (IIT Kharagpur)*

---
