# Monte Carlo Stock Price Simulator

Estimates a stock's drift and volatility from 5 years of historical market data, then simulates 10,000 one-year price paths using Geometric Brownian Motion to quantify downside risk.

## What it does
1. Pulls 5 years of daily prices for any ticker (via `yfinance`)
2. Estimates annualized drift and volatility from daily log returns
3. Checks the normality assumption (histogram vs. fitted normal, excess kurtosis)
4. Simulates 10,000 GBM price paths over 252 trading days, fully vectorized in NumPy
5. Reports risk metrics: 95% Value-at-Risk, expected shortfall (CVaR), probability of loss, and a 90% price interval

## Tools
Python · NumPy · Pandas · Matplotlib · yfinance · Jupyter Notebooks/Google Colab

## Key takeaway
GBM is the classic baseline (it underlies Black-Scholes), but the notebook also shows where it fails: observed returns have significant excess kurtosis, so the model understates tail risk. Limitations discussed in the final section.
