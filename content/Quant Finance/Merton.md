---
title: "Merton Jump Diffusion Model"
draft: False
---
## Derivative Trading Strategies in Sudden Market Movements

>Exploring model calibration and stochastic jump processes in derivative pricing.

See the full project at [quant.wiederhold.dev](https://quant.wiederhold.dev/).

---

The Merton Jump Diffusion model augments the standard GBM by allowing for sudden, random jumps in asset prices. While GBM assumes continuous paths, the Merton model captures rare but significant events (jumps) observed in real markets.

**GBM:** Only continuous, normally distributed returns.
**Merton Jump Diffusion:** Adds a Poisson-driven jump component with lognormally distributed jump sizes.

Mathematically:

$$
dS_t = \mu S_t\,dt + \sigma S_t\,dW_t + S_t (J - 1)\,dN_t
$$

where $N_t$ is a Poisson process (jump times), and $J$ are i.i.d. lognormal jump multipliers.

### Key Parameters
- $\lambda$: Average number of jumps per year (jump intensity)
- $\mu_J$: Mean of log jump size (in log-space)
- $\sigma_J$: Standard deviation of log jump size
- $\mu,\sigma$: Drift and volatility of the continuous part (as in GBM)

Jumps are modeled as $J \sim \exp(\mu_J + \sigma_J Z)$, $Z \sim N(0,1)$.

The Merton Jump Diffusion model enhances the realism of market simulations by accounting for discontinuous price movements.

In my experiments:

For `IBM` (2020-2021), Merton achieved significantly better hedging results than GBM.

Cross-asset analysis showed that the benefit of jump modeling depends on return kurtosis.

While more complex, the Merton framework captures fat tails and tail risk better than GBM, highlighting its practical value for assets prone to sudden market moves.