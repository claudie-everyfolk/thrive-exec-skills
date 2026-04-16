# Demand Exception Reviewer

## Context Frame

I'm the COO at Thrive Market, an e-commerce grocery company selling organic and natural products. We run 3 fulfillment centers (Batesville IN, Reno NV, and one more). Our demand planning team manually reviews SKU-level forecasts each week to catch outliers before they flow into replenishment orders. This takes hours and still misses things. I have this week's forecast data, recent accuracy history, and our business calendar. I want to build an automated exception review process.

## The Ask

Using the attached data files (`sku_forecast.csv`, `forecast_accuracy_history.csv`, and `business_calendar.md`):

1. **Exception report** — Flag every SKU whose current forecast deviates meaningfully from historical patterns. Classify severity as Critical (>40% deviation with no business justification), Warning (20-40% deviation or partial justification), or Watch (notable but explainable). Show the data that triggered each flag.
2. **Root cause classification** — For each exception, assign a root cause: Promo Lift, Seasonal Spike, Data Error, Demand Shift, New Item Bias, or OOS Recovery. Cross-reference the business calendar and accuracy history to support your classification.
3. **Recommended action per exception** — For each flagged SKU, recommend one of: Auto-Adjust (safe to correct algorithmically), Planner Review Required (needs human judgment), Escalate (impacts multiple categories or large dollar value), or Hold (wait for more data).
4. **Forecast health dashboard** — Summary metrics: overall MAPE trend, bias direction by category, number of exceptions by severity, percentage of SKUs within acceptable accuracy bands.
5. **Planner review queue** — A prioritized list of the items that genuinely need human eyes, sorted by business impact (estimated revenue at risk), with all relevant context pre-assembled so the planner can make a decision in under 60 seconds per SKU.

## Why This Matters

Every missed outlier either becomes overstock sitting in our FCs (carrying cost, spoilage risk on perishables) or a stockout that disappoints members. Right now a planner spends 3-4 hours per week eyeballing 200+ SKUs. This should take 10 minutes of review on a pre-built exception list.

## Iteration Hooks

- "Add a column showing estimated revenue impact if we get this forecast wrong by the flagged amount"
- "Break out exceptions by FC — are certain fulfillment centers seeing worse forecast accuracy?"
- "Which categories have the most chronic bias? Show me a trend"
- "Create a simple scoring model I could use to auto-approve forecasts below a risk threshold"

## Stretch Goals

- Build a reusable forecast exception template that could run weekly with fresh data
- Generate a one-paragraph executive summary I could paste into our Monday planning email
- Recommend 3 systemic improvements to our forecasting process based on the patterns you see
