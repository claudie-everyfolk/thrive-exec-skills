# Incident Pattern Analyzer & Runbook Generator

I'm a Director of Platform & SRE at an e-commerce company running 15+ microservices. We recently achieved a 70% alert volume reduction in one focused session, and now I want to systematically scale that pattern across all services. I have our incident history, service catalog, and current alert rules.

## Context Frame

We use New Relic for observability, Rootly for incident management, and Backstage/Trellis as our service catalog. Our on-call rotation covers ~168 hours/week across the team, and alert fatigue is our biggest operational drag. We've proven we can dramatically reduce noise — now I need a repeatable, data-driven approach.

The three files in this directory are:
- `incident_history.csv` — 50 resolved incidents from the last 6 months with timing, severity, root cause, and resolution data
- `service_catalog.md` — Our 15 microservices with ownership, tier, SLA, dependencies, and known issues
- `alert_rules.json` — Current alerting configuration across all services, including thresholds

## The Ask

Analyze all three files together and produce:

1. **Pattern Analysis** — Which incidents repeat? Which services generate the most noise? What's our MTTR by root cause category? Where are the clusters?

2. **Auto-Generated Runbooks** — For the top 10 incident patterns, generate structured runbooks with: symptoms/trigger, likely root cause, step-by-step resolution, escalation criteria, and prevention recommendations. Format these so an on-call engineer at 2am can follow them.

3. **Alert Rule Recommendations** — Review our current alert rules against the incident data. Flag rules that are too sensitive (generating false positives), rules that are missing (incidents with no corresponding alert), and thresholds that need tuning. Be specific — give me the exact threshold changes.

4. **On-Call Impact Projection** — Based on the incident patterns and proposed runbook coverage, estimate how many on-call hours per month we'd save if these runbooks were automated.

## Why This Matters

Every unnecessary page costs us engineer productivity and morale. We've proven the 70% reduction is possible — this analysis turns a one-time win into a systematic program. The runbooks become the foundation for Rootly automation playbooks.

## Iteration Hooks

After reviewing the initial output, try these follow-ups:
- "Reformat the top 3 runbooks as Rootly playbook YAML with automated steps"
- "Cross-reference the alert rules against the service catalog SLAs — are any T1 services under-monitored?"
- "Generate a weekly incident review template that uses these patterns as the agenda structure"
- "Which services would benefit most from adding synthetic monitoring based on the gap analysis?"

## Stretch Goals

- Build a dependency-aware blast radius map: when order-service goes down, what's the cascade?
- Create an incident retrospective template that maps to the pattern categories you identified
- Design an alert health scorecard that could run monthly to track noise reduction progress
