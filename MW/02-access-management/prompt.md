# Access Management Automation Scoper

I'm a Director of Platform & SRE at an e-commerce company. We've already automated 90% of one access review process (Astronomer) using rule-based provisioning, and we're projected to save 273 hours/year by expanding this approach. I need to scope Phase 1 of a broader access management automation program.

## Context Frame

Our access management today is mostly manual — ticket-based requests through ServiceNow, approved by managers, fulfilled by IT or platform engineers. The process follows predictable patterns: new hire gets role X in systems A, B, C based on job title; departing employee gets deprovisioned from everything; role changes follow a mapping table. We use Okta as our IdP, and systems include AWS, GitHub, Snowflake, Datadog, Netsuite, and several internal tools.

The three files in this directory are:
- `access_requests.csv` — 100 access requests from the last 3 months with request type, system, timing, and an auto_eligible flag indicating our initial assessment
- `access_policies.md` — Current access policies by system, role mappings, approval requirements, and SOX controls
- `recent_audit_findings.md` — 3 recent audit findings that illustrate the risk of manual processes

## The Ask

Analyze all three files and produce:

1. **Automation Opportunity Analysis** — Categorize every request type by automation tier: Tier 1 (fully automatable, no human needed), Tier 2 (automatable with human approval step), Tier 3 (requires human judgment). Show the volume and time savings for each tier.

2. **Decision Tree for Automated Provisioning** — Build a structured decision tree that could be implemented as code: given a request type, system, role, and requester attributes, what's the automated path? Include the approval gates and SOX checkpoints.

3. **Risk Assessment by System** — For each system, assess: what's the blast radius if automation makes a mistake? Which systems are safe to auto-provision vs. which need a human in the loop regardless of request simplicity?

4. **Projected Time Savings** — Calculate hours saved per month by automation tier. Show current state vs. automated state. Factor in the audit findings — how much audit remediation time does automation eliminate?

5. **Phase 1 Recommendation** — Which 5-10 request types should we automate first? Rank by: volume x time savings x low risk. Be specific — give me the request type, system, current process, and proposed automated flow.

## Why This Matters

273 hours/year is just the beginning. Beyond time savings, every manual access change is an audit risk — stale access, delayed deprovisioning, inconsistent role assignments. The audit findings in the data prove this. Automation doesn't just save time; it makes us continuously compliant.

## Iteration Hooks

After reviewing the initial output, try these follow-ups:
- "Generate an Okta workflow definition for the top 3 Tier 1 automations"
- "Map the decision tree to a mermaid diagram I can put in our Backstage docs"
- "What's the SOX auditor going to ask about this automation? Draft the control narrative"
- "Design the exception handling flow — what happens when automation can't decide?"

## Stretch Goals

- Draft the ServiceNow integration spec for automated ticket resolution
- Create a compliance dashboard schema that tracks automated vs. manual fulfillment rates
- Design the access review automation that would have caught the audit findings before auditors did
