# Variance Commentary Agent

## Context Frame

I'm the CFO at Thrive Market, an e-commerce grocery company focused on organic and natural products. Every month-end, my team spends 2-3 days manually writing variance commentary for our P&L — comparing actuals against our Annual Operating Plan (AOP) budget and prior year. It's tedious, error-prone, and delays our close process.

I have a GL trial balance export with current month actuals, AOP budget, and prior year comparisons. I also have business context notes from my FP&A team about what happened during the period — promotions we ran, supply chain issues, headcount changes, and new product launches.

## The Ask

Using the attached `gl_trial_balance.csv` and `business_context.md`:

1. **Identify the Top 10 variances by materiality** (actual vs. budget, ranked by absolute dollar impact). For each, write a 2-3 sentence executive narrative explaining what drove the variance, referencing specific business context where available.

2. **Generate a cause-of-change waterfall** showing how we bridge from Budget EBITDA to Actual EBITDA. Group the variances into categories: Revenue Mix, Gross Margin, OpEx Savings, OpEx Overruns, and One-Time Items.

3. **Write an executive summary** (3-5 paragraphs) suitable for our board deck that tells the story of the month — what went well, what didn't, and what we're doing about the misses.

4. **Flag any variances that look like they need investigation** — where the numbers don't align with the business context provided, or where the variance is large but unexplained.

5. **Create a formatted table** of all accounts showing: Account Name, Actual, Budget, Variance $, Variance %, Prior Year, YoY Change %, and a RAG status (Red/Amber/Green based on materiality thresholds you recommend).

## Why This Matters

This exercise replaces what currently takes my FP&A team 2-3 days of manual work. The goal isn't just speed — it's consistency. Every month the commentary should follow the same structure, apply the same materiality logic, and connect variances to real business drivers. If I can get 80% of the way there in minutes instead of days, my team can focus on the 20% that requires human judgment.

## Iteration Hooks

- "Adjust the materiality threshold to only flag variances above $50K"
- "Rewrite the executive summary in a more conservative tone — our board prefers understated"
- "Add a section comparing our fulfillment cost trends to the prior 3 months"
- "Generate the waterfall as a text-based chart I can paste into a slide"

## Stretch Goals

- Ask Claude to generate the variance commentary as a formatted HTML page with conditional coloring
- Request a "management action items" section that suggests specific follow-ups for each red-flagged variance
- Have Claude create a template prompt that your FP&A team can reuse monthly by just swapping in new data
