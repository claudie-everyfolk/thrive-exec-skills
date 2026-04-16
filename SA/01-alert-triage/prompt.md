# Alert Triage & Runbook Generator

## Context Frame

I'm the CTO at Thrive Market, a membership-based online grocery company focused on organic and natural products. We run about 70 engineers across a microservices architecture. Our observability stack is anchored by New Relic ($550K/year), and we use Rootly for incident management.

Last quarter, one of our SRE leads ran a focused session analyzing alert patterns and achieved a 70% reduction in alert volume for a single service cluster. That was manual, one-off work. I want to systematize that approach across our entire service portfolio.

I'm giving you three files:
- `alert_history.csv` — 200 alerts over the last 30 days across our services
- `service_catalog.md` — our 15 core services with ownership, tier, SLA, and dependency info
- `incident_history.json` — 20 resolved incidents with root causes and resolution steps

## The Ask

1. **Alert noise analysis.** Identify which alerts are signal vs noise. Find the repeat offenders, auto-resolve candidates, and deploy-correlated spikes. Show me the 80/20 — which services and alert types generate the most toil for the least value?

2. **Suppression rule recommendations.** For alerts you'd suppress or consolidate, give me specific rules with clear justification. I need to hand these to my SRE team and have them implement by end of week.

3. **Auto-generated runbooks for the top 10 alert patterns.** Each runbook should include: symptoms, likely root cause, step-by-step resolution, escalation criteria, and which past incidents informed the runbook. Pull resolution steps from the incident history where available.

4. **Projected on-call time savings.** Based on the alert patterns and resolution times, estimate how many hours per week my on-call engineers spend on alerts that could be suppressed, auto-resolved, or handled by a runbook. Give me a before/after comparison.

5. **Priority-ranked service hygiene list.** Which services need the most urgent alert cleanup? Rank by a combination of alert volume, noise ratio, and service tier.

## Why This Matters

On-call burnout is a retention risk. Every false alert at 3am erodes trust in the system and costs us senior engineers. We proved the approach works — now I need it scaled across the org with repeatable methodology, not tribal knowledge.

## Iteration Hooks

- "Now generate these runbooks in markdown format I could import into Rootly"
- "Cross-reference the alert patterns with deploy times — are we seeing post-deploy alert storms?"
- "Which of these services should move to a fully autonomous remediation tier where alerts auto-heal without paging anyone?"
- "Build me a weekly alert hygiene scorecard template I can review with the SRE team"

## Stretch Goals

- Design the alert lifecycle for Project Genome: how would a persistent knowledge graph of our architecture automatically update suppression rules as services change?
- Propose an autonomous SRE tier architecture where the top 5 auto-resolve alert patterns are handled by automated remediation with no human in the loop
- Calculate the dollar cost of alert noise (engineer hourly rate x wasted on-call hours) to build the business case for the observability team
