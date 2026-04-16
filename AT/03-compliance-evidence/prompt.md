# Compliance Evidence Gathering Accelerator

## Context Frame

I'm VP of Tech Ops at Thrive Market. Every quarter, my team manually collects evidence for SOX and PCI audits — screenshots, spreadsheet exports, access lists — and it's one of the most painful processes we run. We're piloting Vanta ($80K/year) for continuous compliance monitoring, but right now most evidence collection is still done by hand. Our last audit had three findings, two of which trace directly back to evidence collection delays.

I've got three files for you to work with:
- `quarterly_evidence_log.csv` — 40 evidence items from the last SOX/PCI audit cycle
- `control_framework.md` — our 15 key controls with descriptions, data sources, and evidence formats
- `audit_findings.md` — the 3 findings from our last audit, with root causes and remediation status

## The Ask

Help me build the case and the plan for automating evidence collection:

1. **Evidence collection time analysis** — Total hours spent last quarter. Where are the bottlenecks? Break it down by collection method (manual screenshot vs. API export vs. manual spreadsheet). Which controls take the most time?

2. **Automation opportunity map** — For each of the 15 controls, classify: can Vanta auto-collect it, does it need Lumos, does it need a custom integration, or does it stay manual? Be specific about what "auto-collect" means for each one.

3. **Continuous monitoring dashboard design** — If I could watch compliance posture in real-time, what would I want to see? Design the dashboard: what metrics, what cadence (daily/weekly/quarterly), what alerts. Think about what Vanta + Lumos together could surface.

4. **Remediation plan for open findings** — Take the 3 audit findings and design the fix. Not just "do better" — the specific process change, tool configuration, or automation that prevents recurrence.

5. **Projected impact** — Current state hours vs. automated state hours for quarterly audit prep. What does the $80K Vanta investment actually buy us in time saved and risk reduced?

## Why This Matters

Audit prep shouldn't be a fire drill. Right now we spend the last 3 weeks of every quarter scrambling to collect evidence that should have been generated continuously. And the findings from last audit — terminated employees with lingering access, late access reviews — those aren't evidence problems, they're process problems that evidence collection would have caught earlier. This is Initiative #4 on our Tech Ops AI Strategy.

## Iteration Hooks

After the first pass, try these:
- "Map each audit finding to the specific evidence collection failure that caused it — then design the monitoring rule that would have caught it in real-time"
- "Build a Vanta configuration spec: for each control that Vanta can monitor, what's the exact integration, data source, and alert threshold?"
- "Create a quarterly audit prep runbook: week-by-week checklist of what to collect, verify, and package for the auditors"

## Stretch Goals

- Design the auditor-ready evidence package: what format, what structure, what summary reports would make the auditor's job easier (and make our audit go faster)?
- Model the compliance risk score: given current automation coverage, what's our exposure? Which unmonitored controls represent the highest risk?
- Draft the executive summary for the CFO: justify the $80K Vanta investment in terms of audit findings prevented, hours saved, and risk reduction
