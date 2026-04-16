# FC Shift Handoff & Operations Brief

## Context Frame

I'm the COO at Thrive Market, an e-commerce grocery company with fulfillment centers in Batesville IN, Reno NV, and a third location. Our FC managers currently piece together shift handoffs from multiple systems — WMS throughput reports, safety logs, maintenance tickets, HR trackers, and inbound schedules. The result is inconsistent: some shifts get a thorough handoff, others get a hallway conversation. I want a structured, repeatable handoff format that any incoming shift leader can read in 5 minutes and know exactly what to focus on.

## The Ask

Using the attached data files (`shift_throughput.csv`, `shift_incidents.csv`, `pending_tasks.json`, and `inbound_schedule.md`):

1. **Shift performance summary** — How did this shift perform vs. plan? Break out by department (Pick, Pack, Ship). Show UPH vs. target, total units, headcount utilization, and any downtime that impacted throughput. Flag departments that missed target and explain why.
2. **Critical handoff items** — What does the next shift MUST know? Equipment issues still open, safety incidents that need follow-up, quality flags that could affect outbound, staffing gaps. Prioritize by urgency — what needs action in the first 30 minutes vs. first 2 hours vs. by end of shift.
3. **Prioritized task list for incoming leadership** — Pull from pending tasks and combine with shift carryover. Sort by SLA urgency: overdue first, then due today, then upcoming. Each task should show owner, due date, status, and what happens if it slips.
4. **Safety and quality flag summary** — All incidents from this shift with status and required follow-up. Any patterns worth noting (e.g., multiple pick errors from same zone, recurring equipment issue).
5. **Staffing recommendation for next shift** — Based on this shift's throughput trends, tomorrow's inbound schedule, and any known constraints (call-outs, training sessions), recommend headcount by department. Flag if overtime authorization is likely needed.

## Why This Matters

A bad handoff means the incoming shift spends the first hour figuring out what happened instead of running operations. In a 3-FC network processing 100K+ units/day, even 30 minutes of wasted ramp-up time per shift change compounds into real throughput loss. This is the difference between hitting SLA and missing it.

## Iteration Hooks

- "Generate this as a clean HTML one-pager I could print and post at the shift lead desk"
- "Add a section comparing this shift to the same shift last week — are we trending better or worse?"
- "What's the #1 risk for next shift and what would you recommend to mitigate it?"
- "Build a template version of this that a shift lead could fill in with fresh data each day"

## Stretch Goals

- Create a shift-over-shift trend dashboard showing 7 days of performance
- Generate a daily ops brief that rolls up all 3 shifts into an executive summary
- Recommend 3 process improvements based on the patterns in this data
