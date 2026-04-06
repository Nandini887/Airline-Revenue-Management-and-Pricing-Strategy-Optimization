# Airline-Revenue-Management-and-Pricing-Strategy-Optimization
Applied dynamic programming and demand forecasting to optimize airline ticket pricing strategy across a 365-day horizon, modeling customer demand distributions for 5 price points, conducting sensitivity analysis on sales probabilities, and identifying the overbooking policy that maximized expected discounted profit through Monte Carlo simulation.

## Project Overview

This project formulates airline pricing as a finite-horizon dynamic programming problem. The airline must decide daily prices for coach and first-class tickets while balancing revenue generation against overbooking penalties at departure.

The model incorporates:
- Price-dependent demand probabilities
- Discounted future revenue
- Binomial passenger show-up uncertainty
- Overbooking penalties for bumping and denied boarding
- Sensitivity analysis on demand forecasting errors
- Forward Monte Carlo simulation (10,000 trials)

## Business Objective

Maximize expected discounted profit across 365 selling days for:
- 100 coach seats
- 20 first-class seats

Penalty structure:
- $50 for bumping coach to first class
- $425 for denied boarding

## Methodology

### Dynamic Programming

- State space: (t, c, f)
  - t = days remaining
  - c = coach tickets sold
  - f = first-class tickets sold
- Bellman equation used for backward induction
- Daily discount factor derived from 17% annual interest rate

### Overbooking Optimization

- Tested overbooking levels from 5 to 20 extra seats
- Identified optimal buffer: 9 seats
- Maximum expected discounted profit: $42,171

### Flexible No-Sale Policy

- Introduced dynamic demand control
- Allowed policy to stop selling when risk exceeded marginal benefit
- Improved robustness without requiring fixed caps

### Sensitivity Analysis

- Perturbed demand probabilities ±10 percentage points
- Found first-class premium pricing most sensitive to forecast errors
- Identified key revenue-risk drivers

### Seasonality Modeling

- Introduced time-dependent demand multiplier
- Re-optimized policy under varying demand conditions
- Confirmed stability of optimal overbooking level

### Forward Simulation

- Simulated 10,000 booking horizons
- Compared fixed-cap and flexible policies
- Found approximately 98% of overbooked flights generate positive net gain
- Confirmed overbooking as a profit driver

## Key Insights

- Moderate overbooking increases profit; excessive overbooking increases risk.
- Premium demand forecasting accuracy has the largest financial impact.
- Dynamic pricing with state-awareness outperforms static caps.
- Overbooking is financially justified under realistic demand uncertainty.
- Dynamic programming effectively captures long-horizon revenue-risk tradeoffs.

## Tools Used

- Python
- Dynamic Programming (Backward Induction)
- Binomial Probability Modeling
- Sensitivity Analysis
- Monte Carlo Simulation
- Profit Distribution Analysis
