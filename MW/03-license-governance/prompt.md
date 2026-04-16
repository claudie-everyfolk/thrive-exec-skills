# Claude License Governance & ROI Dashboard

I'm a Director of Platform & SRE at an e-commerce company. We have 200 Claude Enterprise seats costing ~$30K/month, plus GitHub Copilot and free Gemini via Google Workspace. Usage varies wildly across teams — some are power users, others barely log in. I need to build the case for optimizing this spend and present it to leadership.

## Context Frame

We adopted Claude Enterprise 12 weeks ago with a big bang rollout — 200 seats across all engineering teams. Copilot was already in place for code completion. Gemini became free through our Google Workspace plan. Now we have three AI tools with overlapping capabilities and no governance framework. Some teams swear by Claude, others default to Gemini because it's free, and our CFO is asking whether the $360K/year Claude investment is justified.

The three files in this directory are:
- `claude_usage_by_team.csv` — 12 teams x 12 weeks of Claude usage data including sessions, tokens, estimated cost, and primary use case
- `dora_metrics.csv` — Same 12 teams x 12 weeks of DORA metrics (deploy frequency, lead time, change failure rate, MTTR)
- `tool_overlap.md` — Capability comparison of Claude, Gemini, Copilot, and Cortex with cost notes

## The Ask

Analyze all three files together and produce:

1. **Usage-to-Value Analysis** — Which teams are getting real ROI from Claude? Which have idle seats? Segment teams into: power users (high usage + improved metrics), growing (increasing adoption), stalled (low/declining usage), and idle (seats allocated but barely used).

2. **Seat Optimization Plan** — Based on usage data, recommend: seats to reclaim, seats to reallocate to waitlisted teams, and a waitlist priority framework. Target: reduce seats by 20-30% without impacting productive teams.

3. **Tool Rationalization Recommendation** — Given Claude, Gemini, and Copilot overlap, recommend which tool each team should use for which task. Where should we steer people to the free option (Gemini) vs. the paid one (Claude)?

4. **DORA Correlation Analysis** — Do teams that adopted Claude show measurable improvement in DORA metrics? Control for confounding factors (team size, existing maturity). Be honest — if the correlation is weak, say so.

5. **Executive Summary** — A one-page brief for leadership with: current spend, projected optimized spend, ROI evidence, risk of cutting too deep, and recommended next steps. Include a 3/6/12 month cost projection.

## Why This Matters

$360K/year for an AI tool is a real line item. If we can show which teams get value and which don't, we can optimize spend, redistribute to high-impact use cases, and build a governance framework that scales. The alternative is a CFO-mandated across-the-board cut that hurts the teams actually benefiting.

## Iteration Hooks

After reviewing the initial output, try these follow-ups:
- "Build a monthly governance report template I can auto-generate from usage data"
- "Draft the Slack announcement for the seat reallocation — frame it as optimization not punishment"
- "What usage thresholds should trigger automatic seat reclamation? Design the policy"
- "Model three scenarios: keep current spend, cut 25%, cut 50% — impact on each team"

## Stretch Goals

- Design the Claude license governance policy: provisioning criteria, usage thresholds for reclamation, appeal process, exception handling
- Create a quarterly business review template for AI tooling spend
- Draft the AI tool selection guide: "When to use Claude vs. Gemini vs. Copilot" — for distribution to all engineers
