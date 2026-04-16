# Doug Willoughby - Exercise Package (VP of Member Services, Thrive Market)

## Facilitator Guide

**Participant context:** Doug oversees the full member services operation at Thrive Market -- ~80 agents across HQ and BPO sites (Manila, Bogota), Sierra AI handling 68% of contacts, 165+ knowledge articles, Zendesk as the ticketing system. His pain points are manual VOM reporting, slow WFM scheduling, and trainer-dependent new hire onboarding.

**Session format:** 3 exercises, ~30-45 min each. Each exercise is self-contained with a paste-ready prompt and synthetic data files. Doug pastes the prompt into Claude Code, attaches the data files, and iterates from there.

---

## Exercise Overview

| # | Exercise | Time | Key Skill |
|---|----------|------|-----------|
| 01 | VOM Deep Dive Synthesizer | 30-40 min | Analytical synthesis from messy ticket data |
| 02 | Scheduling CSV Generator | 35-45 min | Constraint-based generation with real-world rules |
| 03 | Training Scenario Generator | 30-40 min | Domain-aware content generation for agent training |

---

## Exercise Details

### 01 - VOM Deep Dive Synthesizer
**Pain point:** Voice of Member reporting is manual -- leads comb through tickets by Reason for Contact. Claude already cut this by 50% for one user.

**What Doug does:**
1. Pastes `prompt.md` into Claude Code
2. Attaches `zendesk_tickets.csv`, `product_catalog_context.md`, `prior_vom_report.md`
3. Gets a themed VOM brief, emerging issue detection, cross-functional routing

**Facilitator notes:**
- The CSV has intentional clusters (frozen items thawed, promo code failures, auto-renewal surprises) -- Claude should surface these
- The prior VOM report gives Claude the format to match. Watch whether Doug asks Claude to deviate from that format
- Good iteration hook: "Now compare this week to last month's report and flag what changed"

### 02 - Scheduling CSV Generator
**Pain point:** Scheduling for Zendesk WFM takes 15 min/day for HQ (11 agents), up to 1 hr/site/day for BPO (~70 agents).

**What Doug does:**
1. Pastes `prompt.md` into Claude Code
2. Attaches `agent_roster.csv`, `coverage_requirements.csv`, `zendesk_wfm_schema.md`, `scheduling_rules.md`
3. Gets a valid Zendesk WFM CSV for a full week plus gap analysis

**Facilitator notes:**
- The roster has intentional conflicts (overlapping PTO requests, insufficient bilingual agents for peak voice)
- Coverage requirements show weekend patterns differ from weekday -- Claude needs to handle both
- The stretch goal of "what if 3 agents call in sick" is where this gets powerful

### 03 - Training Scenario Generator
**Pain point:** New hire training depends on pulling trainers/leads from their regular work. A "Test Member" chatbot for self-led practice would free up senior agents.

**What Doug does:**
1. Pastes `prompt.md` into Claude Code
2. Attaches `common_scenarios.md`, `resolution_policies.md`, `qa_rubric.md`
3. Gets 15 training scenarios with scoring rubrics and gold-standard responses

**Facilitator notes:**
- Scenarios should reference Thrive-specific tools (Magento, Sierra) and policies
- The "hidden complexity" in each scenario is the teaching moment -- watch whether Doug iterates to add more
- Good stretch: "Now generate a scenario that combines two issues in one contact"

---

## Iteration Coaching Tips

- After each exercise completes, ask: "What would you change about the output?"
- Encourage Doug to paste the output back and ask Claude to refine specific sections
- If output is too long, have Doug ask for an executive summary version
- If output misses something, have Doug add context to the prompt rather than starting over

---

## File Inventory

```
DW/
├── README.md                          (this file)
├── 01-vom-synthesizer/
│   ├── prompt.md                      (paste-ready prompt)
│   ├── zendesk_tickets.csv            (150 tickets with realistic clusters)
│   ├── product_catalog_context.md     (recent product/feature changes)
│   └── prior_vom_report.md            (last month's VOM report format)
├── 02-scheduling-csv/
│   ├── prompt.md                      (paste-ready prompt)
│   ├── agent_roster.csv               (30 agents across 3 sites)
│   ├── coverage_requirements.csv      (hourly coverage needs by day)
│   ├── zendesk_wfm_schema.md          (exact CSV format for upload)
│   └── scheduling_rules.md            (business rules and constraints)
└── 03-training-scenarios/
    ├── prompt.md                      (paste-ready prompt)
    ├── common_scenarios.md            (top 10 contact scenarios)
    ├── resolution_policies.md         (Thrive policies and procedures)
    └── qa_rubric.md                   (scoring criteria for agent performance)
```
