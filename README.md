# Solar Power Forecasting: Autoregressive Time-Series 

A Machine Learning project that forecasts the AC power output of a solar power plant using weather sensor logs. Designed to simulate a real-world energy trading desk environment. We transition from a static physical baseline to an advanced time-series framework capable of capturing short-term cloud volatility.

---

## Project Architecture & Core Insights

This project focuses on a crucial upgrade: moving from a basic model to a smart time-series approach. In the real world, this shift is essential for an energy trading desk to avoid expensive financial penalties caused by inaccurate power forecasts.

1. **The Physics Baseline (Step 5):** Using a randomized train-test split, we evaluate how perfectly the model maps static physical laws (Weather $\rightarrow$ Power). The Random Forest achieves an exceptional $R^2$ here, proving great data quality.
2. **Trading Simulation (Step 6):** We switch to a strict **Chronological Split (`shuffle=False`)** and introduce **Lag Features** (`AC_POWER_LAG_1` to `_3`). This eliminates data leakage and captures fast-moving cloud fronts, reflecting true forecasting conditions.

---

## Key Results

* **Baseline Performance:** Random Forest outclassed Linear Regression by capturing the highly non-linear time effects.
* **Volatility Optimization:** Transitioning to the Autoregressive setup reduced the Mean Absolute Error (MAE) by **3.65 kW**, making the model significantly more reliable for sudden drops in solar generation.
