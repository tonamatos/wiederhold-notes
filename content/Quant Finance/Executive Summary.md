---
draft: True
---
# Executive Summary

My project explores **delta-hedging performance under the Merton Jump Diffusion model** compared to the classical **Geometric Brownian Motion (GBM)** framework.

The motivation stems from a core limitation of the GBM assumption: it models returns as normally distributed, thereby underestimating real-world jump risk and fat-tailed behavior observed in equity markets.

I develop a full simulation and calibration pipeline to assess how jump modeling impacts option pricing and hedging accuracy.

The analysis proceeds in eight stages:

1. **Model Setup and Simulation.**
2. **Merton Jump Diffusion Simulation:** Implemented both GBM and Merton stochastic processes and visualized their path dynamics.
3. **Monte Carlo Option Pricer:** Priced European call options under each model using uncalibrated parameters to illustrate baseline differences.
4. **Model Calibration with Historical Data:** Estimate parameters for `IBM` stock in 2020.
5. **Delta Estimation for Merton:** Used finite difference approach.
6. **Delta Hedging Comparison:** Simulation from the perspective of a market maker.
7. **Cross-Asset Comparison:** Repeated the backtest across multiple stocks, relating performance to each asset's return kurtosis.
8. **Conclusion.**

Results indicate that **Merton's inclusion of jump risk leads to more realistic P&L behavior** for assets exhibiting moderate excess kurtosis (typically between 2–5).

For example, when calibrating on **IBM (2020)** and backtesting on **2021**, the Merton model achieved a hedging P&L of **\$11.56** versus **\$8.53** under GBM, a substantial improvement in replicating real price dynamics.

However, for highly irregular assets or noisy calibration periods, Merton's additional parameters may reduce robustness.

Overall, this study demonstrates that **jump-diffusion modeling provides tangible benefits** in environments where asset returns deviate meaningfully from Gaussian assumptions.

The framework developed here can be extended to other derivative types, alternative jump distributions, or high-frequency calibration approaches to further assess model realism and hedging efficiency.