# Nick (CEO) — Exercise Package

## Facilitator Guide

**Participant:** Nick, CEO of Thrive Market
**Level:** Executive / Board-level synthesis
**Theme:** Cross-functional AI strategy — synthesizing 9 functional strategies into unified company direction

These exercises are designed for a CEO who oversees all functions and just received AI strategy documents from 8 direct reports. The work is cross-functional by design: synthesizing, governing, and planning across all 9 functions rather than going deep into any one.

---

## Exercise Overview

| # | Exercise | Core Skill | Time Estimate | Difficulty |
|---|----------|-----------|---------------|------------|
| 01 | AI ROI Synthesizer | Multi-source data synthesis → board narrative | 30-40 min | Medium-High |
| 02 | AI Governance & Risk Framework | Policy design from incident data + stakeholder requests | 35-45 min | High |
| 03 | Workforce Planning Scenario Modeler | Scenario modeling + sensitive workforce communication | 35-45 min | High |

**Recommended order:** 01 → 02 → 03 (builds from "what are we doing" → "how do we govern it" → "what does it mean for our people")

---

## Exercise 1: Cross-Functional AI ROI Synthesizer

**What it teaches:**
- Feeding Claude multiple data files that cross-reference each other
- Getting Claude to synthesize across sources, not just summarize each one
- Producing board-ready narratives from raw operational data
- Iterating on output framing (skeptical board member, CFO lens, etc.)

**Data files:**
- `functional_ai_summary.csv` — 9 rows, one per function. Maturity ratings, spend, hours saved, top initiative.
- `initiative_roadmap.csv` — 27 rows (3 per function). Cross-functional dependencies, timelines, risk levels.
- `ai_spend_detail.md` — Full spend breakdown. Includes the tension between Sierra ($700K) and Claude's cost growth.

**Key cross-references the participant should discover:**
- Member Services has the highest spend ($715K) AND highest hours saved (28/wk) — is that good ROI or overspend?
- Operations is at maturity 4 with only $142K spend — best ROI per dollar
- Finance is at maturity 2 with its top initiative blocked on SOX compliance — a governance problem, not a tech problem
- The initiative roadmap reveals 8 cross-functional dependencies, meaning initiatives can't be evaluated in isolation

**Watch for:**
- Does the participant push Claude beyond summarization into actual strategic recommendations?
- Do they use the iteration hooks to stress-test the narrative for different audiences?
- Do they catch that some "savings" are projected, not realized?

---

## Exercise 2: AI Governance & Risk Framework

**What it teaches:**
- Designing policy from real incident data (not theoretical frameworks)
- Balancing innovation speed with risk management
- Creating tiered approaches (not one-size-fits-all governance)
- Synthesizing competing stakeholder requests into coherent policy

**Data files:**
- `risk_incidents.csv` — 15 real incidents. Range from critical (revenue data in consumer Gemini) to low (redundant tool subscriptions). Includes the fabricated "40% of members are parents" stat.
- `current_policies.md` — Deliberately sparse. Shows the gap between what exists and what's needed.
- `functional_requests.md` — 9 functions each asking for different things. Some conflict (Legal wants mandatory review; Operations wants speed).

**Key tensions the participant should navigate:**
- Legal wants every AI output attorney-reviewed. That's not scalable. The tiered approach must address this.
- Engineering wants a "paved path" for non-engineers building AI tools — but Operations already built Mission Control without guardrails.
- Finance is blocked on 3 initiatives because SOX compliance + AI has no framework. This is costing real money.
- The Claude vs. Gemini question: Gemini is free but has no enterprise data protections. The Finance analyst who pasted revenue data into consumer Gemini is Exhibit A.

**Watch for:**
- Does the governance framework enable rather than just restrict?
- Does the participant think about the "AI captains" concept from Operations as a governance mechanism?
- Do they address the consumer vs. enterprise AI tool distinction?
- Is the quick-reference guide actually simple enough for a non-technical employee?

---

## Exercise 3: Workforce Planning Scenario Modeler

**What it teaches:**
- Scenario modeling with realistic constraints
- Sensitive communication about AI's workforce impact
- Financial modeling (investment vs. savings)
- Strategic framing for board audiences

**Data files:**
- `current_headcount.csv` — 40 rows covering all functions by sub-team. Includes AI-amenability percentages grounded in the functional strategy data (e.g., QA Analysts at 75%, AP/AR at 80%, Member Service Agents at 68%).
- `initiative_impact.csv` — 27 rows linking each initiative to specific roles affected. Includes workforce actions: retrain, attrit, reduce, or maintain.
- `growth_scenarios.md` — Three detailed scenarios. The Aggressive scenario is deliberately honest about the human cost.

**Key cross-references:**
- `initiative_impact.csv` references roles from `current_headcount.csv` — the numbers should reconcile
- The Member Services scenario is the most dramatic: 48 agents today, potentially 36 in the aggressive scenario
- New roles created (AI Quality Specialist, Knowledge Engineer, etc.) should map to the skills gaps identified in the initiative impacts
- The financial model must account for AI spend growth ($1.3M → $1.8M or $2.4M) offsetting headcount savings

**Watch for:**
- Does the participant lead with the "multiplier" narrative or default to cost-cutting framing?
- Do they engage with the ethical complexity of the Member Services scenario?
- Is the hiring plan specific enough to actually execute (not just "hire AI talent")?
- Do they use the iteration hooks to stress-test for specific audiences (VP Member Services, CFO, board)?

---

## General Facilitation Notes

**These exercises are intentionally connected.** The data is consistent across all three:
- The same 9 functions appear in all exercises
- Spend numbers in Exercise 1 align with the risk incidents in Exercise 2
- Headcount in Exercise 3 corresponds to the initiative roadmaps in Exercise 1
- The governance gaps in Exercise 2 explain why Finance initiatives in Exercise 1 are blocked

**If the participant finishes early**, guide them to the iteration hooks. Each exercise has 3-4 hooks that push the analysis in new directions. The stretch goals (interactive dashboards, scenario modelers) are legitimate Claude Code projects that extend the work.

**The meta-lesson for a CEO:** Claude Code is not just a coding tool. With the right data and the right prompt, it's a strategic thinking partner. These exercises show how a CEO can use it for the kind of cross-functional synthesis work that typically requires a strategy team or an expensive consulting engagement.
