# Two-Asset Portfolio Risk Analysis and Mean-Variance Optimisation

This  project applies Markowitz mean-variance portfolio theory to a two-asset portfolio of Amazon (AMZN) and Tesla (TSLA), constructing the efficient frontier, identifying the market portfolio, and performing Value at Risk estimation. All analysis was conducted in Excel.

## Objective

Evaluate the risk–return profile of a two-asset equity portfolio using historical weekly return data: estimate individual asset risk, construct the efficient frontier, identify the optimal risky portfolio under different risk-free rate assumptions, and quantify downside risk via Value at Risk.

## Data

- **Assets**: Amazon (AMZN) and Tesla (TSLA) — weekly closing prices
- **Sample**: 150 weeks of weekly returns, retrieved using Excel's STOCKHISTORY function
- **Risk-free rate**: Weekly interest rate of 0.1% (with sensitivity analysis at 0.05%)

## Methodology

- **Return distributions**: Computed weekly log returns for each stock and plotted histograms to visualise the return distribution shape, skewness, and tail behaviour
- **Descriptive statistics**: Estimated mean weekly return (μ) and standard deviation (σ) for each asset, and pairwise correlation (ρ)
- **Value at Risk**: Calculated 95% VaR for each stock by treating the histogram as a probability mass function — identifying the loss threshold below which 5% of returns fall
- **Efficient frontier**: Swept portfolio weight ω₁ from −0.95 to 1.45 (allowing short-selling), computing expected return, portfolio standard deviation, and Sharpe ratio at each allocation. Plotted the frontier in the μ–σ plane, including the global minimum-variance portfolio
- **Market portfolio**: Introduced a risk-free asset (weekly rate 0.1%) and identified the tangency portfolio — the allocation maximising the Sharpe ratio, defining the Capital Market Line
- **Sensitivity analysis**: Re-computed the market portfolio and Sharpe ratio under a lower risk-free rate (0.05%) to assess how the optimal allocation and risk-adjusted performance shift with the interest rate environment

## Key Results

| Metric | AMZN | TSLA |
|--------|------|------|
| Mean weekly return | −0.22% | −0.15% |
| Weekly std. deviation | 9.26% | 11.03% |

- **Correlation**: ρ = 0.767 — high positive co-movement, limiting diversification benefit
- **Market portfolio** (at r_f = 0.1% weekly): ~90% AMZN / 10% TSLA, with portfolio σ = 9.21%
- **Sensitivity**: Reducing the risk-free rate to 0.05% shifts the tangency point and alters the Sharpe ratio, demonstrating the market portfolio's dependence on the risk-free rate assumption


## Concepts Applied

- Markowitz mean-variance framework
- Efficient frontier and global minimum-variance portfolio
- Sharpe ratio and tangency (market) portfolio
- Capital Market Line (CML)
- Value at Risk (histogram-based, 95% confidence)
- Portfolio variance with correlated assets: σ²_p = ω₁²σ₁² + ω₂²σ₂² + 2ω₁ω₂ρσ₁σ₂
