# Onboarding/Offboarding Automation Audit

## Context Frame

I'm VP of Tech Ops at Thrive Market. Onboarding and offboarding access setup consumes about 30% of my IT Ops team's time. We've already partially automated offboarding through Wursta (handles access revocation and equipment return workflows), but onboarding is still almost entirely manual — my team provisions each new hire's accounts one by one. With our growth trajectory, this doesn't scale.

I've got three files for you to work with:
- `employee_transitions.csv` — 60 employee transitions over the last 3 months (onboards, offboards, role changes)
- `system_access_matrix.md` — which systems each role/department needs
- `compliance_requirements.md` — SOX requirements that constrain what we can automate

## The Ask

Give me a complete picture of where we are and where we need to go:

1. **Current state analysis** — What's the average time to complete each transition type (onboard vs. offboard vs. role change)? Break it down by department. What's the error rate? How do manual vs. automated steps compare?

2. **Gap analysis** — Which onboarding steps are still manual and why? Where are the errors concentrated? What's the gap between our onboarding process and our (partially automated) offboarding process?

3. **Automation blueprint** — Design the target state. Which systems should we automate first? What's the integration architecture (Lumos + Workday + Freshworks)? Give me a sequenced rollout plan — Phase 1, 2, 3 with clear milestones.

4. **Risk assessment** — Which automations touch SOX-controlled systems? Where do we need approval workflows baked in? What could go wrong if we automate too aggressively?

5. **Projected impact** — Time savings per month, error reduction targets, and the breakeven point for building the automation vs. continuing manual work.

## Why This Matters

This is Initiative #2 on our Tech Ops AI Strategy. The cost isn't just analyst hours — it's the downstream impact of provisioning errors. A new hire waiting 3 days for Snowflake access because someone missed a step, or worse, an employee keeping access to financial systems after a role change because the deprovisioning was manual and someone forgot. That's a compliance risk, not just an efficiency problem.

## Iteration Hooks

After the first pass, try these:
- "Cross-reference the transitions data with the access matrix — find every instance where the systems provisioned don't match what the role should have had"
- "Design the Workday-triggered automation flow: when a new hire record is created in Workday, what's the exact sequence of API calls to provision everything?"
- "Model the worst-case scenario: what happens if the automation provisions the wrong access level for a SOX system? Design the rollback procedure"

## Stretch Goals

- Design the self-service onboarding portal: what would the new hire's Day 1 experience look like if 80% of provisioning was automated?
- Create a role change playbook: when someone moves departments, what's the delta between their old and new access that needs to change?
- Draft the Lumos integration spec: what data needs to flow between Workday, Lumos, Okta, and Freshworks to fully automate provisioning?
