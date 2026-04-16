# Product Artifact Co-Author

## Context Frame

I'm a PM at Thrive Market, a membership-based online grocery focused on organic and natural products. We're building a "Shop by Diet" personalization feature and I need to write the product spec. I have:

- `@feature_request.md` — the original feature request from leadership with goals and scope
- `@product_context.md` — current product state, data points, and technical context
- `@prior_specs.md` — two recent specs from our team showing our standard format

## The Ask

Write a complete product spec for the "Shop by Diet" personalization feature. Match the format and structure from our prior specs exactly — same sections, same level of detail, same tone.

The spec should include:
1. **Problem Statement** — grounded in the data from product_context.md
2. **Success Metrics** — specific, measurable, tied to the goals in the feature request
3. **User Stories with Acceptance Criteria** — cover onboarding flow, browse adaptation, search adaptation, email personalization, and settings management. Make acceptance criteria specific enough that engineering and QA can work from them directly.
4. **Technical Considerations** — reference the Syndigo PIM launch, existing dietary filter infrastructure, and mobile-first requirements (65% of traffic)
5. **Open Questions** — with recommended owners for each
6. **Launch Plan** — phased rollout with experiment design

Additionally, generate:
- An **instrumentation plan** listing every Amplitude event we should track, with event name, trigger condition, and key properties
- A **RICE prioritization score** with explicit rationale for each dimension, using real numbers from product_context.md
- A **suggested experiment design** for the rollout — what to test, control vs. treatment, sample size considerations, and primary/guardrail metrics

## Why This Matters

Our PM team spends significant time on structured documents like this. A strong first draft at 50-60% readiness means I can focus my time on the judgment calls — scoping trade-offs, stakeholder alignment, edge cases — instead of formatting and boilerplate. This is the difference between a PM who writes specs and a PM who ships products.

## Iteration Hooks

After the first draft, try these follow-ups to refine:
- "The acceptance criteria for multi-diet members (e.g., someone who's both Keto and Gluten-Free) need more edge case coverage. Expand those."
- "Add a section on accessibility requirements for the dietary preference selector."
- "Rewrite the launch plan assuming we can't use Syndigo PIM data until June — what changes?"
- "Generate a one-page executive summary I can use in our product review meeting."
- "Create a JIRA ticket breakdown from the user stories — title, type, story points estimate, and suggested sprint."

## Stretch Goals

- Ask Claude to identify gaps: "What's missing from this spec that would block engineering from starting?"
- Generate a competitive analysis section: "How do Amazon Fresh, Instacart, and Misfits Market handle dietary personalization?"
- Create a data dependency map showing which parts of the feature are blocked on Syndigo PIM vs. can ship with existing data
