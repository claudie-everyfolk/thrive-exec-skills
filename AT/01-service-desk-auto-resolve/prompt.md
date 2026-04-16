# Service Desk Ticket Classifier & Auto-Resolver

## Context Frame

I'm VP of Tech Ops at Thrive Market, an e-commerce grocery company. My IT Ops team handles service desk tickets across our HQ and three fulfillment centers (Batesville, Reno, and FC3). We use Freshworks as our service desk platform and we're already testing auto-response logic for L1 tickets. A huge chunk of our ticket volume is predictable stuff — password resets, access requests, standard hardware issues at the FCs — and I want to figure out exactly how much we can safely automate.

I've got three files for you to work with:
- `service_desk_tickets.csv` — 120 real-ish tickets from the last quarter
- `resolution_templates.md` — our standard resolution scripts for the top 10 ticket types
- `escalation_rules.md` — when to auto-resolve vs. when to escalate (includes SOX/PCI constraints)

## The Ask

Analyze the ticket data and build me a complete automation strategy:

1. **Ticket classification analysis** — Break down the distribution by category, location, priority. What percentage is auto-resolvable? What's the average resolution time by category?

2. **Auto-response drafts** — For the top 10 ticket types, draft the actual auto-response messages that would go to the requester. Use the resolution templates as a base but make them human-friendly. Each response should include: what's happening, what the user needs to do (if anything), and expected resolution time.

3. **Escalation decision tree** — Build a clear decision tree: given a ticket's attributes (category, requester, systems involved, priority), should it be auto-resolved, auto-resolved-with-notification, or escalated? Encode the SOX/PCI rules from the escalation file.

4. **Hours saved projection** — Based on the resolution times in the data, estimate weekly hours saved if we automate Phase 1 ticket types.

5. **Phase 1 automation scope** — Recommend which ticket types to automate first, ranked by (volume x confidence x simplicity). Be specific about what "automate" means for each one — full auto-resolve, auto-triage-and-assign, or auto-respond-with-manual-close.

## Why This Matters

This is Initiative #1 on our Tech Ops AI Strategy (Q2-Q4). If we get this right, we free up L1 analysts to handle the complex stuff and cut mean-time-to-resolution for the easy stuff from hours to minutes. The FC teams especially — they can't wait 4 hours for a pack-station reimage when they're running shifts.

## Iteration Hooks

After the first pass, try these:
- "Stress-test the escalation decision tree with edge cases — what happens when a contractor at a FC requests access to a SOX system?"
- "Rewrite the auto-responses for FC employees specifically — they're on the floor, reading on a phone, keep it ultra-short"
- "Build a confidence scoring model — for each ticket, how confident should the system be before auto-resolving vs. queuing for review?"

## Stretch Goals

- Design the Freshworks automation workflow: trigger conditions, auto-categorization rules, response templates, escalation routing
- Create a monitoring dashboard spec: what metrics should we track weekly to know the automation is working (false positive rate, escalation rate, MTTR by category)
- Draft the change management communication to the IT Ops team explaining the new automation and how their role shifts from L1 resolution to L1 oversight
