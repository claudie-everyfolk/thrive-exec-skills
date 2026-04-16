# Non-Engineer App Deployment Evaluator

## Context Frame

I'm the CTO at Thrive Market. We're a membership-based online grocery company selling organic and natural products. Our engineering team is about 70 people. We use Claude Enterprise (200 seats across the company), and something interesting is happening: non-engineers are building internal apps. Two employees outside engineering have already shipped functional tools — one in merchandising, one in member support. More requests are coming in. I need to get ahead of this before it becomes shadow IT.

Our platform team can currently support: EC2 hosting, Okta SSO integration, secrets management via AWS Secrets Manager, GitHub repo provisioning, and basic CI/CD. But we don't yet have self-service database provisioning, custom domains, monitoring for non-eng apps, or a standardized review process.

I'm giving you three files:
- `internal_app_requests.csv` — 12 app ideas submitted by non-engineers across the company
- `platform_capabilities.md` — what we can and can't support today for non-engineer deployments
- `security_checklist.md` — our security requirements by data sensitivity tier

## The Ask

1. **Evaluation matrix.** Score each of the 12 app requests on: feasibility (can we support this today?), risk (data sensitivity, auth complexity, external exposure), business value (impact and urgency), and implementation complexity. Use a clear scoring system and rank them.

2. **Recommended approval path per app.** Based on the security tier each app falls into, map each request to its path: self-serve, light review, full security review, or engineering-owned. Be specific about why.

3. **"Paved path" definition.** Define what the standard non-engineer deployment looks like at Thrive Market. What's the tech stack, what guardrails are in place, what's the onboarding process, what are the hard limits? This should be something I can publish as an internal doc.

4. **Platform gap analysis.** What capabilities does my platform team need to build to support the top-priority app requests? Prioritize by how many requests each gap blocks.

5. **Governance policy recommendation.** Draft a one-page policy: who can deploy what, with what guardrails, and what triggers a review. This should balance enabling innovation with protecting the business.

## Why This Matters

Non-engineers building internal tools is the future I want — it's the whole point of the "Vibe Coding Paved Path" initiative. But uncontrolled app sprawl with PII access, unmonitored infrastructure, and no security review is a liability. I need the framework before the flood, not after.

## Iteration Hooks

- "Now create an onboarding checklist a non-engineer would follow to deploy their first app"
- "Draft the Slack announcement explaining this new policy to the company"
- "Which of these 12 apps could be built in a single afternoon with Claude? Flag the quick wins"
- "Design the lightweight review process — who reviews, what they check, SLA for turnaround"

## Stretch Goals

- Design a "Vibe Coding Paved Path" architecture diagram: from idea submission to production deployment, including automated security scanning, SSO integration, and monitoring
- Propose a tiered support model: what does the platform team owe non-engineer app builders? (SLA for infrastructure, not for their code)
- Calculate the ROI of enabling non-engineer app building vs hiring contractors to build the same tools
