# Training Scenario Generator

## Context Frame

I'm VP of Member Services at Thrive Market. New hire training is one of my most expensive operational bottlenecks — every training session pulls experienced agents or leads off the floor, reducing our coverage capacity. We train in cohorts of 4-6 new hires, and each cohort needs 2 weeks of supervised practice before they're cleared for solo work.

I want to build a library of realistic training scenarios that new agents can practice against independently — like a "Test Member" simulator. Each scenario should feel like a real member contact, with the kind of nuance and hidden complexity that separates a good agent from a great one. The scenarios need to map to our actual policies, tools (Magento, Sierra, Zendesk), and QA scoring rubric.

I'm attaching three files:
- **common_scenarios.md** — our top 10 member contact types with expected resolution steps
- **resolution_policies.md** — Thrive's actual policies on refunds, cancellations, escalations, etc.
- **qa_rubric.md** — the scoring criteria we use to evaluate agent performance

## The Ask

Generate a training scenario library with the following:

1. **15 realistic training scenarios** — 5 Easy, 5 Medium, 5 Hard. Each scenario includes:
   - Member profile (name, membership type, tenure, order history summary)
   - Contact channel (chat, email, or phone)
   - Opening message from the member (written in a natural, realistic voice)
   - Hidden complexity (the thing that makes this scenario tricky — not visible in the opening message)
   - Expected resolution path (step-by-step what a good agent would do)
   - Key policy to apply (reference to specific policy from resolution_policies.md)
   - Common mistakes new agents make on this type of scenario

2. **Scoring rubric per scenario** — Mapped to the QA rubric categories, with scenario-specific criteria for what "meets expectations" and "exceeds expectations" looks like

3. **Gold standard response** — For each scenario, write the ideal agent response (first reply) that would score 100% on the rubric

4. **Difficulty progression notes** — Explain what makes each difficulty level harder than the previous (so trainers understand the pedagogy)

## Why This Matters

Every hour a lead spends running mock scenarios is an hour they're not handling real member contacts or coaching live agents. If I can give new hires a library of 15 scenarios they can practice independently — with clear rubrics and model answers — I can cut supervised training time by 30-40% and get agents to solo work faster.

## Iteration Hooks

- "Generate 5 more scenarios that combine two issues in a single contact — e.g., a member calling about a missing item who ALSO wants to cancel their membership"
- "Now create a version of these scenarios formatted as a chatbot script — the member's lines are pre-written and the trainee types the agent responses"
- "Add a 'red herring' variant for each Hard scenario where the member describes the wrong issue and the agent needs to diagnose the real problem"
- "Generate a scenario that requires the agent to use Sierra's handoff protocol"

## Stretch Goals

- Build a scenario scoring calculator where a trainer can input yes/no for each rubric item and get an auto-calculated score
- Create a "weekly scenario challenge" — one scenario per day for a 5-day training week, progressively harder
- Generate scenarios in Spanish for bilingual agent training
- Design a "shadow scoring" exercise where new hires score a pre-written bad response and identify what went wrong
