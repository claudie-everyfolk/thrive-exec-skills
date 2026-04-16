# Engineering AI Investment Analyzer

## Context Frame

I'm the CTO at Thrive Market, a membership-based online grocery company. My engineering org is about 70 people across 8 teams. I'm spending over $600K/year on AI and observability tooling — $50K/year on Claude Enterprise (200 seats plus token costs), $550K/year on New Relic, plus GitHub Copilot, CodeRabbit (in trial), and several functional team AI tools. My board wants ROI numbers. My CFO wants to know if we're getting value from 200 Claude seats when maybe 60 people are active.

I'm giving you three files:
- `ai_tool_usage.csv` — Claude Enterprise usage by team over 12 weeks
- `engineering_metrics.csv` — DORA metrics and productivity signals by team for the same 12 weeks
- `tool_inventory.md` — complete inventory of AI/ML tools with costs, owners, and status

## The Ask

1. **AI tool ROI analysis.** For each major tool (Claude Enterprise, GitHub Copilot, New Relic), analyze usage vs cost. Identify underutilized seats, power users driving outsized value, and tools where spend doesn't match adoption. Give me the dollar-per-active-user breakdown.

2. **Team-level adoption scorecard.** For each engineering team, score their AI tool adoption maturity. Which teams are thriving and should be showcased? Which teams have seats but aren't using them? Which teams might need different tools rather than more training?

3. **Seat optimization plan.** We're paying for 200 Claude Enterprise seats. Show me exactly how many are active, how many are zero-activity, and what reallocation looks like. Factor in the waitlist from non-engineering teams who want access. Calculate the savings or reallocation potential.

4. **DORA correlation analysis.** Do teams with higher Claude usage actually ship better? Correlate Claude adoption metrics with DORA improvements (deployment frequency, lead time, change failure rate, MTTR). Be honest — if the correlation is weak or mixed, say so. I need the real picture, not a sales pitch.

5. **Investment recommendation for next quarter.** For each tool in the inventory: keep as-is, expand, reduce, or cut. Justify each recommendation with data from the usage and metrics files. Include a net savings/investment number.

## Why This Matters

$600K+ in AI tooling is a board-level line item. I need to walk into the next budget review with a clear story: here's what's working, here's what's not, here's what I'd change. Not vibes — data. The teams that are getting real value from these tools should get more. The tools that aren't earning their keep should be cut or replaced.

## Iteration Hooks

- "Build me a one-page executive summary I can present to the board with the key numbers"
- "Which teams should be our internal AI champions? Design a peer training program using our top adopters"
- "Model the cost impact if we cut Claude seats from 200 to 120 and redistributed savings to expand Copilot"
- "Compare New Relic's $550K cost against what we could build with Claude-powered observability"

## Stretch Goals

- Build a "build vs buy" analysis for New Relic AI capabilities vs Claude-powered observability (custom dashboards, alert analysis, incident summarization built on Claude Enterprise)
- Design a quarterly AI tool review cadence: what metrics to track, who reviews, what triggers a tool being put on probation
- Project the 12-month trajectory: if current adoption trends continue, what does the AI tool budget look like in Q1 2027? Where should we be investing now to capture the most value?
