# Sprint Health Analyzer & Standup Generator

## Context Frame

I'm a PM at Thrive Market running a 2-week sprint for the Discovery & Personalization squad. We're on day 8 of 10 (the sprint ends Friday). I have:

- `@jira_sprint_data.csv` — all 35 tickets in this sprint with statuses, assignees, story points, and timestamps
- `@sprint_goals.md` — the 3 sprint goals we committed to, with success criteria
- `@team_context.md` — team composition, capacity notes, and mid-sprint disruptions

## The Ask

Analyze the sprint data and produce:

1. **Sprint Health Dashboard** — a structured overview covering:
   - Velocity vs. commitment (story points completed vs. planned, with burn rate)
   - Burndown trajectory: are we on track to finish by Friday? If not, how many points are at risk?
   - Blocked items: list each blocked ticket, how long it's been blocked, root cause, and who needs to unblock it
   - Scope creep analysis: identify tickets added mid-sprint, their total point cost, and impact on the original commitment

2. **Today's Standup Summary** — a concise, ready-to-post summary covering:
   - What shipped since yesterday
   - What's in progress and expected to ship today
   - What's blocked and needs attention
   - Any flags the team should know about
   - Keep this tight — this is what I'd paste into our #dev-standup Slack channel

3. **Risk Assessment** — identify tickets unlikely to complete by sprint end based on:
   - Current velocity and remaining capacity
   - Blocked items with no clear resolution
   - In-progress items that haven't moved in 2+ days
   - Dependencies between tickets

4. **Sprint Retrospective Data Pack** — quantitative data for our retro:
   - Cycle time distribution (time from In Progress to Done for completed tickets)
   - Stories completed vs. committed (original commitment vs. actual)
   - Unplanned work percentage (mid-sprint additions as % of total points)
   - Blocked time analysis (total days lost to blockers across all tickets)

5. **Recommended Actions** — what should I, as PM, do right now? Prioritize ruthlessly. What gets cut, what gets escalated, what needs a conversation today?

## Why This Matters

PMs at Thrive spend 37% of their time on sprint management — the target is under 20%. This kind of analysis currently takes 30-45 minutes of clicking through Jira, cross-referencing in spreadsheets, and writing summaries by hand. If Claude can do it in 2 minutes from a CSV export, that's hours back per week for every PM on the team.

## Iteration Hooks

After the first analysis, try these:
- "Format the standup summary as a Slack message with emoji status indicators."
- "One of the blocked tickets just got unblocked — TM-2421 moved to In Progress. Regenerate the risk assessment."
- "The stakeholder wants to add another urgent ticket (5 points). Show me the trade-off — what do we cut?"
- "Generate a sprint-end status email for my engineering manager with a candid assessment of what shipped, what didn't, and why."
- "Compare this sprint's health to a 'healthy' baseline — what would a clean sprint look like with this team?"

## Stretch Goals

- Ask Claude to generate a Jira query (JQL) that would surface the at-risk tickets in Jira directly
- Create a template: "Build me a reusable sprint health prompt that I can run every morning with a fresh CSV export"
- Generate a proposed sprint plan for next sprint based on what's carrying over and the team's actual velocity
