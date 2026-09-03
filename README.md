# Capital-Efficient ETF Suite and Wealth Planner

An empirical quantitative backtesting engine and forward Monte Carlo wealth projection visualizer designed to evaluate capital-efficient multi-asset allocations featuring trend following, multi-asset carry, and Treasury stacking overlays.

The web application pairs a monthly historical backtest engine (January 2000 through February 2026) with an institutional-grade forward wealth planning engine that simulates multi-decade accumulation and decumulation horizons (2026+).

---

## Features

* **Empirical Historical Backtest (2000–2026):** Evaluates multi-asset portfolios utilizing systematic factor overlays against conventional benchmarks (60/40 balanced and 69/31 global equity) with metrics including CAGR, Max Drawdown, Annualized Volatility, Sharpe Ratio, Sortino Ratio, and Ulcer Index.
* **Future Wealth Planner (2026+):** Simulates forward capital accumulation and decumulation up to a 150-year horizon. Accommodates customizable starting balances, recurring contributions with annual inflation escalation, and configurable withdrawal strategies (fixed nominal/inflation-adjusted dollar amounts vs. dynamic annual Safe Withdrawal Rates).
* **Synchronized Macroeconomic Cycles:** Forward simulations utilize a block-bootstrap engine driven by shared historical cyclical shocks paired with mean-reverting economic regimes. This ensures realistic drawdowns occur simultaneously across scenarios while modeling asymmetric recovery speeds across the 95th, 75th, 50th, 25th, and 5th percentiles.
* **Dynamic CMA Drift Calibration:** Anchors forward projections to institutional Capital Market Assumptions (Moderate ~8.5% central, Conservative ~7.2% central, or Unadjusted Historical Resampling). Sampled simulation paths are dynamically calibrated so median performance strictly reflects target long-term drift without stochastic drift distortion.
* **Time-Weighted Return Separation:** Year-by-year calendar return tables isolate true investment performance by compounding underlying monthly asset returns, preventing external contributions and withdrawals from distorting reported market returns.

---

## Trademark Notice and Nominative Fair Use

"Return Stacked" is a registered trademark of ReSolve Asset Management and Newfound Research.

Ticker symbols referenced throughout this repository and its associated web interface (including RSST, RSIT, RSBT, RSSB, RSBY, and RSSY) refer to publicly registered exchange-traded funds and are utilized strictly under **nominative fair use** for identification, educational comparison, and quantitative research purposes.

This repository is an independent, non-commercial open-source research initiative. It is **not** affiliated with, sponsored by, endorsed by, or associated with ReSolve Asset Management, Newfound Research, Simplify Asset Management, or their respective affiliates.

---

## Data Sources and Methodology

Historical proxies and factor series utilized in this engine are derived from the following public and institutional datasets:

1. **Trend Overlay Suite (RSST / RSIT / RSBT):**
   * Sourced from the **Societe Generale Trend Index** via Societe Generale Prime Services ([Societe Generale Index Feeds](https://wholesale.banking.societegenerale.com/fileadmin/indices_feeds/ti_screen/index.html)).
   * The SG Trend Index tracks the equal-weighted net performance of the ten largest institutional trend-following CTAs.
2. **Carry Overlay Suite (RSSY / RSBY):**
   * Sourced from the **AQR Capital Management "Century of Factor Premia"** dataset ([AQR Factor Premia Monthly](https://www.aqr.com/Insights/Datasets/Century-of-Factor-Premia-Monthly)).
   * Utilizes the `All Macro Carry` factor series, scaled to match the targeted 10.0% annualized volatility overlay budget typical of systematic futures carry overlays.
3. **Core Collateral and Benchmark Pricing:**
   * Adjusted close monthly returns for core collateral (SPY, VEA, IEF) and cash yield (^IRX 3-Month Treasury Bills) are sourced via Yahoo Finance.
4. **Expense Ratios and Fee Modeling:**
   * Net annual management fees are deducted monthly from each sleeve: 0.95% for single-stack strategies (RSST, RSIT, RSBT, RSSY, RSBY), 0.54% for RSSB, 0.03% for SPY, 0.06% for VEA, and 0.15% for IEF.

---

## Disclaimers

### Not Financial Advice

This repository and its web application are provided strictly for academic, educational, and quantitative research purposes. Nothing contained herein constitutes financial, investment, legal, or tax advice. No recommendation or solicitation is made regarding the advisability of purchasing or holding any security, ETF, or asset allocation. Consult a licensed financial advisor before making capital allocation decisions.

### Hypothetical and Backtested Limitations

All simulated returns, statistical metrics, drawdowns, and portfolio projections are hypothetical and retrospective. Backtested results do not represent actual live trading performance and cannot account for real-time market impact, execution slippage, bid-ask spreads, margin calls, tracking error, or evolving regulatory constraints. Splicing historical index data prior to actual ETF inception dates introduces inherent survivorship and proxy biases. Past performance does not guarantee or indicate future results.

---

## License

This project is licensed under the terms of the **MIT License**.
