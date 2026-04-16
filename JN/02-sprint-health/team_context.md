# Team Context — Sprint 14

## Team Composition

| Name | Role | Capacity Notes |
|------|------|---------------|
| Alex Kim | Frontend Engineer (Web) | Full capacity. Senior — handles complex UI work and code reviews. |
| Jordan Liu | Frontend Engineer (Web/Mobile) | Full capacity days 1-2, 6-10. **Out sick days 3-5** (lost 3 days). Handles React Native mobile work. |
| Sam Patel | Backend Engineer | Full capacity. Owns the preferences API and Algolia integration. |
| Priya Singh | Backend Engineer | Full capacity days 1-4. **Pulled to production incident day 4 afternoon + day 5 morning** (lost ~1 day). Owns Syndigo pipeline work. |
| Diego Torres | Mobile Engineer (React Native) | Full capacity. Primary mobile engineer but also supports backend when needed. |
| Rachel Wen | QA Engineer | Full capacity. Runs regression suite and writes test cases. Typically validates 2-3 stories per day. |

## Standard Velocity

- **Historical average:** 34 story points per 2-week sprint (last 4 sprints: 32, 36, 35, 33)
- **This sprint's commitment:** 38 story points (slightly aggressive due to carryover from Sprint 13)
- **Adjusted capacity estimate:** ~30-32 points given Jordan's sick days and the production incident

## Mid-Sprint Disruptions

### Jordan Out Sick (Days 3-5)
- Jordan is the only engineer with deep React Native expertise on this squad
- Mobile implementation of dietary filter persistence (TM-2418) was assigned to Jordan and couldn't start until Day 6
- Diego picked up some mobile work but had his own backend tickets
- Impact: ~5 story points of mobile work delayed by 3 days

### Production Incident — Checkout Price Calculation Bug (Day 4)
- Severity: P1 — some members were charged incorrect amounts on orders with subscription + one-time items
- Priya and Alex were pulled off sprint work for ~4 hours each (Day 4 afternoon)
- Priya continued incident follow-up for ~2 hours on Day 5 morning
- Root cause: a race condition in the discount stacking logic (not our squad's code, but our engineers were on-call)
- Impact: ~1.5 days of lost capacity across two engineers

### Stakeholder Scope Addition (Day 5)
- VP of Marketing requested 3 "urgent" tickets added mid-sprint:
  - TM-2430: "Add UTM tracking to dietary filter chip clicks" (2 points)
  - TM-2431: "Email preference center — add dietary interests section" (5 points)
  - TM-2432: "Homepage banner A/B test for GLP-1 collection launch" (3 points)
- Total: 10 additional story points added on Day 5
- PM (me) pushed back on TM-2431 (5 points) — agreed to move it to Sprint 15 backlog
- TM-2430 and TM-2432 accepted as they support a time-sensitive marketing campaign launching April 18
- Net addition: 5 story points mid-sprint

## Communication Norms

- **Daily standup:** async in #disc-pers-standup Slack channel, posted by 10:00 AM ET
- **Sprint board:** Jira board "DISC-PERS Sprint 14"
- **Blocked items:** engineer posts in #disc-pers-standup and DMs PM immediately
- **Scope changes:** require PM approval; anything >3 points requires PM + engineering lead alignment
