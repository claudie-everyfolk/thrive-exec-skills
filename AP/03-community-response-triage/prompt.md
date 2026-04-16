# Community Response Triage System

## Context Frame

I'm the CMO at Thrive Market, a membership-based online grocery for organic and natural products. Our community management team spends 40+ hours per week manually triaging and responding to comments across Meta, TrustPilot, and Reddit. We're evaluating Sprinklr and Emplifi, but before we buy another SaaS tool, I want to see what AI-native triage looks like.

I'm giving you three files:
- **social_comments.csv** — 50 real-format comments from Meta, TrustPilot, and Reddit with platform context
- **response_guidelines.md** — our social voice, escalation rules, response templates, and what NOT to say
- **team_routing.md** — who handles what, with routing logic for each category

## The Ask

1. **Classified and prioritized comment queue:** For each of the 50 comments, assign: severity (Critical / High / Medium / Low), category (from the routing taxonomy), the specific routing team, and a 1-line classification rationale. Sort the output by severity, then by timestamp.

2. **Draft responses:** Write a brand-voice response for each comment. Follow the response guidelines exactly — match the tone to the platform (TrustPilot responses are more formal, Reddit is conversational, Meta is warm and brief). For comments that require escalation, write both the public response AND the internal escalation note.

3. **Escalation flags:** Identify every comment that requires internal escalation. For each, specify: which team to route to, why it's escalated, suggested SLA (response time), and what information to include in the escalation ticket.

4. **Sentiment summary:** Aggregate the 50 comments into a sentiment breakdown — what percentage positive/neutral/negative, top 3 themes in positive sentiment, top 3 themes in negative sentiment, and any emerging patterns that deserve attention.

5. **Weekly community health score:** Create a composite score (0-100) based on: sentiment distribution, response urgency mix, escalation rate, and praise-to-complaint ratio. Include a 1-paragraph narrative of what the score means and what it would take to improve it by 5 points.

## Why This Matters

At 40+ hours per week, community management is our second-largest manual time investment after content creation. If we can auto-classify, auto-route, and auto-draft 80% of responses — with a human reviewing before posting — we cut that to 10 hours/week. That's a full headcount saved. And the consistency of brand voice across 50 daily comments would actually improve, because every response runs through the same guidelines instead of depending on which team member is on shift.

## Iteration Hooks

- Run this on our actual TrustPilot export from last week
- Build a real-time dashboard that pulls from Meta Graph API and auto-classifies
- Add competitor mention tracking (when people compare us to Misfits, Imperfect Foods, etc.)
- Create a weekly community digest that feeds into the Monday CMO brief (Exercise 02)

## Stretch Goals

- Build a live monitoring system that processes new comments every hour
- Create an escalation bot that auto-routes Critical items to the right Slack channel
- Train the system on 3 months of our actual responses to learn our specific voice patterns
- Model the cost savings: current team hours vs. AI-assisted workflow
