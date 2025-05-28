# 📈 Sharpe Ratio Optimizer via Markowitz Sweep

This project implements a **Sharpe ratio-maximizing portfolio optimizer** using the **Markowitz efficient frontier** method in Python with NumPy and CVXPY.

It visualizes the **tangency portfolio** where the **Capital Market Line (CML)** is tangent to the efficient frontier—highlighting the optimal risk-return tradeoff.

---

## 🧠 What It Does

Given:
- A covariance matrix of asset returns $\Sigma$
- A vector of expected returns $\mu$
- A specified risk-free rate $R_f$

The optimizer solves:

$$
\max_w \quad \frac{\mu^T w - R_f}{\sqrt{w^T \Sigma w}} \quad \text{subject to} \quad \sum w_i = 1, \quad w_i \geq 0
$$

Rather than solving this non-convex problem directly, it:
1. Sweeps through a range of target returns
2. Solves a minimum-variance problem for each
3. Computes Sharpe ratios
4. Selects the portfolio with the highest Sharpe ratio

---

## 🔍 Features

- ✅ Finds the **maximum Sharpe ratio portfolio** using convex optimization
- ✅ Visualizes the **efficient frontier** and **Capital Market Line (CML)**
- ✅ Supports **long-only** portfolios (no short-selling)
- ✅ Handles arbitrary asset count
- ✅ Extensible to unconstrained or cardinality-constrained models
- ✅ Cleanly structured with theory-explaining comments and plots

---

## 📊 Visualization

- Efficient frontier: risk vs expected return
- Max Sharpe point: highlighted
- Capital Market Line: from risk-free rate tangent to the frontier

---

## 📦 Requirements

- Python 3.x
- NumPy
- CVXPY
- Matplotlib

Install dependencies:

```bash
pip install numpy cvxpy matplotlib
