# VOM Deep Dive Synthesizer

## Context Frame

I'm VP of Member Services at Thrive Market, an e-commerce membership grocery company. My team of ~80 agents (HQ + BPO sites in Manila and Bogota) handles member contacts across chat, email, and phone. Sierra AI resolves 68% of contacts automatically, so the tickets that reach human agents tend to be more complex or emotionally charged.

Right now, Voice of Member (VOM) reporting is painfully manual. My leads comb through tickets grouped by Reason for Contact, looking for emerging themes, volume spikes, and actionable patterns. This takes hours each week and the output quality varies by whoever writes it. We already proved Claude can cut this work by 50% for one analyst — now I want to scale that across the full ticket dataset.

I'm attaching three files:
- **zendesk_tickets.csv** — 150 recent tickets with full metadata and member messages
- **product_catalog_context.md** — recent changes to our product catalog, promotions, and systems that might explain ticket patterns
- **prior_vom_report.md** — last month's VOM report, which is the format and depth I want you to match

## The Ask

Analyze the attached ticket data and produce a VOM brief that matches the format of the prior report. Specifically:

1. **Themed VOM brief** — Group tickets into themes (matching the prior report's structure), with ticket counts, representative quotes, and trend indicators (up/down/new vs. last month's themes)
2. **Emerging issue detection** — Identify any new themes or clusters NOT present in last month's report. These are the early warnings I care most about.
3. **Ticket volume by Reason for Contact** — Show volume breakdown with week-over-week trend where the data allows
4. **Top 5 actionable findings** — Each finding should include: what's happening, how many tickets, specific ticket IDs as evidence, and a concrete recommendation
5. **Cross-functional routing** — For each major finding, tell me which team owns the fix: Product, Ops, Marketing, Engineering, or Member Services
6. **Severity ranking** — Rank all identified issues by a severity score considering volume, member sentiment (CSAT), and business impact

## Why This Matters

VOM is how my leadership team hears the member's voice. If this report is late, shallow, or misses an emerging issue, we're flying blind. The frozen category expansion, the new promo code system, and the redesigned renewal emails are all recent changes that could be generating new contact patterns — I need to see that signal fast.

## Iteration Hooks

- "Now pull out just the findings that need executive attention — 3 bullet points max for my VP-level readout"
- "Compare the themes you found against last month's report and write a delta summary: what's new, what's improving, what's getting worse"
- "Which of these issues, if unresolved for another 2 weeks, would generate the most incremental ticket volume? Quantify it."
- "Generate a Slack-ready summary I can drop into #member-services for the team"

## Stretch Goals

- Build a severity-scoring formula I can reuse each week (inputs: ticket volume, avg CSAT for that theme, trend direction, days since first appearance)
- Create a "watch list" of issues that aren't high-volume yet but show early acceleration
- Draft the cross-functional email I'd send to Product and Engineering with the top 3 issues and supporting data
