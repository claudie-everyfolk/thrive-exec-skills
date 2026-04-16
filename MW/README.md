# Michael Winslow — Exercise Package (Facilitator Guide)

**Role:** Director, Platform & SRE at Thrive Market
**Workshop:** Hands-on Claude Code for Engineering Leaders

---

## Participant Context

Michael owns the Engineering AI Strategy at Thrive Market. His team runs on Claude Enterprise (200 seats, $50K/yr + tokens), GitHub Copilot, New Relic ($550K/yr), Backstage/Trellis, Rootly, and DX. He has already demonstrated serious AI wins: 70% alert volume reduction, spec-driven development via OpenSpec, autonomous PR merging, and access review automation covering 90% of the Astronomer process. His Q2-Q4 roadmap includes continuous alert triage, access management automation, Project Genome (knowledge graph), paved path for non-engineer deployment, CodeRabbit rollout, Claude license governance, and an AI Buddy Program.

These exercises are designed to hit his live initiatives, not hypothetical scenarios.

---

## Exercise Overview

| # | Exercise | Maps To | Time | Difficulty |
|---|----------|---------|------|------------|
| 01 | Incident Pattern Analyzer & Runbook Generator | Continuous Alert Triage & On-Call Automation (Q2-Q4) | 25-30 min | Medium |
| 02 | Access Management Automation Scoper | Access Management Automation Dojo (Q2-Q4) | 25-30 min | Medium |
| 03 | Claude License Governance & ROI Dashboard | Claude License Governance (Q2) | 25-30 min | Medium-Hard |

---

## Facilitation Notes

### Exercise 1: Incident Pattern Analyzer & Runbook Generator

**What it proves:** Claude Code can ingest incident history + service catalog + alert rules, find patterns a human would take hours to spot, and generate actionable runbooks — not generic ones, but ones tuned to Thrive's specific services and failure modes.

**Key coaching moments:**
- When Claude identifies the noisiest services, ask: "How does this compare to your real environment?"
- The alert_rules.json has intentionally miscalibrated thresholds (catalog-search CPU at 60%, payment-gateway error rate at 0.1%). Watch for whether Claude catches these.
- Push toward the iteration hook: "Now ask it to estimate on-call hours saved if the top 5 runbooks were automated via Rootly."

**Watch for:** Participants who paste the prompt and stop. The iteration hooks are where the real value lives — runbook quality improves dramatically when you feed back "our SREs would also check X" or "we use Rootly, format these as Rootly playbooks."

### Exercise 2: Access Management Automation Scoper

**What it proves:** Claude Code can take messy access request data, apply policy logic, and produce a phased automation plan with risk scoring — the exact scoping exercise that normally takes a week of meetings.

**Key coaching moments:**
- The data has clear automation tiers baked in. See if Claude independently identifies the 60/25/15 split.
- The audit findings file creates urgency. Good prompts will connect stale access findings to the automation roadmap.
- Stretch goal: SOX-controlled systems (Netsuite, Snowflake) require human approval by policy. See if Claude respects this constraint or tries to automate everything.

**Watch for:** The decision tree deliverable is the hardest part. If someone gets a flat list instead of a tree, coach them to ask Claude to "output as a mermaid diagram" or "structure as if/then rules."

### Exercise 3: Claude License Governance & ROI Dashboard

**What it proves:** Claude Code can correlate usage data with engineering outcomes, find which teams are getting value and which aren't, and produce an executive-ready recommendation — the kind of analysis that justifies or kills a $360K/yr tool investment.

**Key coaching moments:**
- The DORA metrics are designed so 3-4 teams show clear correlation with Claude usage and 2-3 show none. See if participants catch this.
- The tool overlap file is the strategic lever. Push toward: "Given these overlaps, what's the optimal tool allocation per team?"
- The executive summary stretch goal is where this gets real. Ask: "Would you send this to your VP?"

**Watch for:** People who focus only on cost cutting. The real insight is reallocation — moving seats from low-value teams to high-value ones, not just cutting.

---

## General Tips

- All exercises use cross-referenced synthetic data. Service names, team names, and systems are consistent across files within each exercise.
- Each prompt.md is paste-ready. Participants should paste it into Claude Code with the data files in the same directory.
- Encourage participants to deviate from the prompt after the first pass. The best learning happens when they adapt the output to their real environment.
- Michael will likely move fast given his existing AI maturity. Have him try the stretch goals and then freestyle with his own data if time permits.
