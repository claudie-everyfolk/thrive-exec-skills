# Andrew Tang — VP Tech Ops, Thrive Market
## Claude Code Workshop: Exercise Facilitator Guide

**Participant context:** Andrew leads Tech Ops spanning IT Ops, Ecomm Ops, and Security & Compliance across HQ and 3 fulfillment centers (Batesville, Reno, and a third FC). His team manages Automox, Kandji, Lumos, Freshworks, and Vanta. He authored Thrive's Tech Ops AI Strategy with 5 key initiatives for Q2-Q4.

---

## Exercises Overview

| # | Exercise | Time | Key Skill |
|---|----------|------|-----------|
| 01 | Service Desk Ticket Classifier & Auto-Resolver | 25-30 min | Data analysis → decision framework → automation design |
| 02 | Onboarding/Offboarding Automation Audit | 25-30 min | Process gap analysis → blueprint → risk assessment |
| 03 | Compliance Evidence Gathering Accelerator | 25-30 min | Audit analysis → automation mapping → dashboard design |

## Exercise Sequence & Facilitation Notes

### Exercise 1: Service Desk Auto-Resolve
**Why this first:** Most tangible, closest to work Andrew's team is already doing (Freshworks auto-response testing). Quick wins build momentum.

**Setup:** Have Andrew paste `prompt.md` into Claude Code. The 3 data files simulate a realistic quarter of service desk tickets plus the operational context (resolution templates, escalation rules) his team actually uses.

**Watch for:**
- Does he iterate on the classification logic? (Iteration Hook 1)
- Does he push toward the escalation decision tree? That's the highest-value deliverable for his team.
- The stretch goal around Freshworks API integration is real — if he gets there, it connects directly to his Q2-Q4 Initiative #1.

**Key talking points:**
- The 120-ticket dataset has deliberate patterns: ~40% password/access (high auto-resolve confidence), ~20% FC hardware (medium confidence, location-specific), remainder varied. Claude should surface this.
- Escalation rules encode real SOX/PCI constraints. Good test of whether the model respects compliance boundaries.

### Exercise 2: Onboarding/Offboarding Automation Audit
**Why second:** Builds on the process-thinking from Exercise 1 but shifts to a more strategic deliverable (automation blueprint vs. tactical auto-responses).

**Setup:** Same paste-and-go. The system access matrix is the critical context file — it defines what "correct provisioning" looks like per role.

**Watch for:**
- Does he ask Claude to cross-reference the transition data against the access matrix? That's where the real gaps surface.
- The error rate in the data is deliberately higher for onboarding (~15%) vs. offboarding (~5%) — reflects that offboarding is partially automated via Wursta.
- SOX compliance requirements add real constraints to what can be automated without approval workflows.

**Key talking points:**
- The gap between onboarding (manual) and offboarding (partially automated) is the story in the data.
- Integration sequence matters: Lumos + Workday + Freshworks have different API maturity levels. A good blueprint acknowledges this.

### Exercise 3: Compliance Evidence Gathering Accelerator
**Why third:** Most strategic exercise. Connects to the $80K Vanta investment and ongoing audit burden.

**Setup:** The audit findings file contains real-style findings with root causes. The control framework maps each control to its data source and evidence format.

**Watch for:**
- Does he connect the audit findings to the evidence collection gaps? (e.g., "terminated employees still had GitHub access" → the evidence collection for that control was manual screenshots, done late)
- The continuous monitoring dashboard design is the stretch deliverable — it's what Vanta should eventually provide, so designing it first helps evaluate the tool.

**Key talking points:**
- 40 evidence items at an average of 2-4 hours each = significant quarterly burden. The automation opportunity is real.
- Three audit findings map directly to automation gaps. Good exercise in root cause → solution mapping.
- Vanta vs. Lumos vs. manual: not everything can be automated, and the analysis should be honest about that.

## General Facilitation Tips

1. **Let him drive.** These prompts are self-contained. Your job is to point out when Claude produces something worth iterating on, not to lecture.
2. **Iteration is the lesson.** The prompts have built-in iteration hooks. If Andrew gets a good first pass and stops, nudge: "What would you change about that classification?" or "Ask it to stress-test the escalation rules."
3. **Connect to his real initiatives.** Every exercise maps to one of his 5 Q2-Q4 initiatives. Make those connections explicit when they come up naturally.
4. **The $30K/month Claude cost is an elephant.** If it comes up, it's a great segue: these exercises show how to get structured value from AI instead of ad-hoc usage that's hard to measure.

## Data File Cross-References

Files are designed to work together within each exercise:
- **Exercise 1:** Tickets reference locations and categories that appear in the resolution templates and escalation rules
- **Exercise 2:** Employee transitions reference systems and roles that appear in the access matrix; compliance requirements constrain the automation blueprint
- **Exercise 3:** Evidence log references controls from the framework; audit findings trace back to specific evidence collection failures
