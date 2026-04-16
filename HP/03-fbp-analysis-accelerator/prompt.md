# FBP Analysis Accelerator

## Context Frame

I'm the CFO at Thrive Market. Our Finance Business Partners (FBPs) are bottlenecked on the Data team for any analysis that goes beyond what Excel can handle. We have member cohort data with 5,000+ rows that crashes Excel or takes forever to pivot. Every time an FBP needs a cohort retention curve, an LTV analysis by channel, or a category penetration breakdown, they file a ticket with Data and wait 3-5 days.

Claude Code can write and run Python directly — which means my FBPs can go from question to answer in minutes, not days. I want to prove this works with our member cohort data so I can roll it out to the broader finance team.

## The Ask

Using the attached `member_cohort_data.csv` and `analysis_frameworks.md`:

1. **Cohort retention analysis:** Build retention curves for the last 12 monthly cohorts. Show month-over-month retention rates (Month 0 through Month 11) in a cohort triangle/heatmap. Identify which cohorts are outperforming and underperforming. Generate a visualization.

2. **LTV by acquisition channel:** Calculate the 6-month and projected 12-month LTV for each acquisition channel (Organic, Paid Social, Referral, Influencer, SEM, Email). Show which channels have the best and worst unit economics. Include a bar chart comparing LTV/CAC ratios.

3. **Category penetration deep dive:** Analyze how category purchasing patterns (Pantry, Snacks, Vitamins, Beauty, Fresh, Beverages, Household) change across cohort vintages. Are newer cohorts buying differently than older ones? Visualize as a stacked bar chart or heatmap.

4. **Reusable prompt template:** Create a markdown prompt template that any FBP on my team can use to run similar analyses. It should have clearly marked placeholders for the data file, the analysis type, and any parameters they want to adjust (date range, filters, grouping columns).

## Why This Matters

This isn't just about one analysis — it's about changing how finance operates. If I can show my FBP team that they can get Python-quality analysis through plain English prompts, we eliminate the Data team bottleneck and cut our analysis turnaround from days to minutes. The reusable template is the key deliverable — it turns this from a one-off demo into a repeatable capability.

## Iteration Hooks

- "Filter the retention analysis to only show members who signed up through Paid Social — I want to see if that channel's retention is improving"
- "Add a seasonal decomposition — are there months where all cohorts drop off?"
- "Break the LTV analysis by membership type (Annual vs. Monthly) in addition to channel"
- "Run the category analysis for just the Fresh category to see adoption curves in new metros"

## Stretch Goals

- Ask Claude to build an interactive HTML dashboard with dropdown filters for cohort, channel, and region
- Request a "data quality report" that flags any anomalies in the raw data before running the analysis
- Have Claude generate a slide-ready executive summary with embedded charts
- Ask Claude to predict which current members are at highest churn risk based on the cohort patterns
