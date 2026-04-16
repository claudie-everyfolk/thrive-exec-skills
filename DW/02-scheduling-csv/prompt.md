# Scheduling CSV Generator

## Context Frame

I'm VP of Member Services at Thrive Market. I manage ~80 agents across three sites: HQ (11 agents), BPO Manila (~40 agents), and BPO Bogota (~30 agents). We use Zendesk WFM for workforce management, and scheduling is one of our biggest time sinks — 15 min/day for HQ, and up to 1 hour per site per day for BPO. That's potentially 2+ hours daily just building schedules.

Zendesk WFM accepts a CSV upload to bulk-load schedules. If I can generate a valid CSV that respects all our business rules, coverage requirements, and agent constraints, I can compress hours of scheduling into minutes.

I'm attaching four files:
- **agent_roster.csv** — 30 agents with their site, role, shift preferences, skills, and constraints
- **coverage_requirements.csv** — hourly coverage needs by day of week and channel
- **zendesk_wfm_schema.md** — the exact CSV format Zendesk WFM expects for upload
- **scheduling_rules.md** — business rules that must be followed

## The Ask

Generate a complete, valid Zendesk WFM schedule for the week of April 20–26, 2026 (Monday through Sunday). Specifically:

1. **Valid Zendesk WFM CSV** — Output a CSV file matching the exact schema in `zendesk_wfm_schema.md`. Every row must pass validation: correct date format, 24-hour time format, breaks for shifts >6 hours, valid agent IDs from the roster.
2. **Coverage analysis** — For each hour of each day, show whether minimum coverage requirements are met for chat, voice, and email. Flag any hours where we're under minimum.
3. **Rule violation check** — Verify that no business rules from `scheduling_rules.md` are violated. If any rule can't be satisfied (e.g., not enough bilingual agents for peak voice), flag it explicitly.
4. **Utilization summary by agent** — Show each agent's total scheduled hours for the week, compared to their max_hours_week. Flag anyone over 90% utilization or under 60%.
5. **Gap report** — Identify the shifts/hours where coverage is thinnest (fewest agents above minimum) and recommend where to add flex coverage.

## Why This Matters

Every hour my leads spend on scheduling is an hour they're not coaching agents or handling escalations. For BPO sites with 40-70 agents and complex shift patterns across time zones, this is a massive operational tax. If Claude can generate a valid, rule-compliant schedule in minutes, that's 10+ hours per week back to the team.

## Iteration Hooks

- "Three agents just called in sick on Wednesday: AGT-007, AGT-018, AGT-025. Regenerate Wednesday's schedule and show me the coverage impact."
- "We just got approval to hire 2 more L1 agents for Manila. Add them to the roster and show me how coverage gaps change."
- "Generate a night-shift-only schedule for Manila to cover 11PM-8AM ET — what's the minimum headcount?"
- "Show me the cost difference between this schedule and one that maxes out every agent's hours."

## Stretch Goals

- Create a schedule optimization score (0-100) that weighs coverage compliance, utilization efficiency, rule adherence, and preference satisfaction
- Generate a "what if" analysis: what happens to coverage if we lose 10% of agents on any given day
- Build a reusable scheduling template that I can update weekly with just PTO changes
