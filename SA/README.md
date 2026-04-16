# Sacha (CTO) — Facilitator Guide

## Participant Profile

**Role:** CTO, Thrive Market
**Scope:** Engineering organization (~70 engineers), platform strategy, AI tool investment, operational excellence
**Current AI Stack:** Claude Enterprise (200 seats, $50K/yr + tokens), GitHub Copilot, New Relic ($550K/yr), Backstage/Trellis, Rootly
**Key Priorities:** Project Genome (persistent knowledge graph), autonomous SRE tier, "Vibe Coding Paved Path" for non-engineers
**Notable Wins:** 70% alert volume reduction in one focused session; two non-engineers already built functional internal apps

**Facilitation Note:** Sacha thinks at the platform/infrastructure level. These exercises are designed for someone who builds systems that other teams use — not individual contributor tasks. Every exercise produces artifacts a CTO would actually present to their VP of Engineering, share at a leadership offsite, or use to justify budget.

---

## Exercises

### Exercise 1: Alert Triage & Runbook Generator
**Directory:** `01-alert-triage/`
**Complexity:** Medium-High
**Time Estimate:** 25-35 minutes
**What it produces:** Alert noise analysis, suppression rules, auto-generated runbooks, projected on-call savings

**Why this lands:** They already proved 70% reduction in one session. This exercise gives Sacha the playbook to systematize that win across the entire org. The data has clear patterns waiting to be found — repeat offenders, auto-resolve candidates, deploy-correlated spikes.

**Support Notes:**
- If stuck on where to start: suggest loading alert_history.csv first and asking Claude to identify repeat patterns
- The incident_history.json cross-references with alert_history.csv via service names and related_incident_id — point this out if they're not connecting the datasets
- Good stretch: ask Claude to generate the runbooks in a format that could be imported into Rootly

---

### Exercise 2: Non-Engineer App Deployment Evaluator
**Directory:** `02-app-deployment-evaluator/`
**Complexity:** Medium
**Time Estimate:** 20-30 minutes
**What it produces:** App evaluation matrix, approval paths, paved path definition, platform gap analysis, governance policy

**Why this lands:** Two non-engineers already built apps. The question isn't "should we allow this" — it's "how do we enable this safely at scale before it becomes shadow IT." This is a governance + platform problem, which is exactly where a CTO should be spending time.

**Support Notes:**
- The security_checklist.md maps directly to the app requests — each request falls into a tier. If they're not using this file, nudge them
- platform_capabilities.md has explicit "can't yet support" items that should surface as gaps
- The real win is when they produce a one-page policy they could actually send to the org

---

### Exercise 3: Engineering AI Investment Analyzer
**Directory:** `03-ai-investment-analyzer/`
**Complexity:** High
**Time Estimate:** 30-40 minutes
**What it produces:** ROI analysis, team adoption scorecard, seat optimization plan, investment recommendations, DORA correlation analysis

**Why this lands:** $600K+ in AI tooling spend. Board and CFO want ROI numbers. This exercise produces the actual analysis Sacha could present at the next budget review. The data shows real patterns — some teams thriving, others with expensive shelfware.

**Support Notes:**
- The ai_tool_usage.csv and engineering_metrics.csv share team_name and week columns — the correlation analysis is the high-value output
- tool_inventory.md has tools at different lifecycle stages (established, trial, evaluating) — the recommendation should treat these differently
- If they finish fast: push toward the "build vs buy" analysis for New Relic AI vs Claude-powered observability

---

## General Facilitation Tips

1. **Let Sacha drive.** CTOs have strong opinions about how to approach problems. Don't over-prescribe the workflow.
2. **The data files cross-reference intentionally.** Each exercise has 2-4 files that connect. The magic happens when Claude synthesizes across them.
3. **Push toward artifacts, not analysis.** The goal isn't "interesting insights" — it's "something I can use Monday morning."
4. **If they finish early:** Every prompt.md has Stretch Goals designed for exactly this scenario.
