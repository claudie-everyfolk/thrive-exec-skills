# AI Tool Overlap Analysis — Claude vs. Gemini vs. Copilot vs. Cortex

Last updated: 2026-03-20

---

## Current Tool Inventory

| Tool | Cost Model | Current Spend | Seats/Licenses |
|------|-----------|---------------|----------------|
| **Claude Enterprise** | $250/seat/mo + token overage | ~$30,000/mo ($50K base + tokens) | 200 seats |
| **GitHub Copilot Business** | $19/seat/mo | ~$3,420/mo | 180 seats |
| **Gemini (Google Workspace)** | Included in Workspace plan | $0 incremental | All employees |
| **Cortex (New Relic AI)** | Included in New Relic contract | $0 incremental (part of $550K/yr) | All New Relic users |

---

## Capability Overlap Matrix

### Code Generation & Completion

| Capability | Claude | Gemini | Copilot | Cortex |
|-----------|--------|--------|---------|--------|
| Inline code completion | Good (via IDE plugin) | Good (via IDE plugin) | Excellent (purpose-built) | N/A |
| Multi-file code generation | Excellent | Good | Limited | N/A |
| Code refactoring | Excellent | Good | Good | N/A |
| Code review / PR analysis | Excellent | Good | Good (Copilot PR) | N/A |
| Test generation | Excellent | Good | Good | N/A |
| Spec-driven development | Excellent (our primary use) | Possible but less reliable | N/A | N/A |

**Recommendation:** Copilot wins for inline completion (it's in the flow). Claude wins for complex multi-file work, spec-driven development, and code review. Gemini is redundant here unless someone doesn't have a Claude or Copilot seat.

### Documentation & Writing

| Capability | Claude | Gemini | Copilot | Cortex |
|-----------|--------|--------|---------|--------|
| Technical documentation | Excellent | Good | Limited | N/A |
| API documentation | Excellent | Good | Limited | N/A |
| Compliance/policy writing | Excellent | Good | N/A | N/A |
| Email/comms drafting | Good | Good (integrated with Gmail) | N/A | N/A |
| Meeting summaries | Good | Excellent (integrated with Meet) | N/A | N/A |

**Recommendation:** Gemini is sufficient for most writing tasks, especially when integrated with Google Workspace (email, docs, meet summaries). Claude is stronger for technical documentation and compliance writing. Teams that primarily use Claude for drafting emails or meeting notes could switch to Gemini at zero incremental cost.

### Data Analysis & Investigation

| Capability | Claude | Gemini | Copilot | Cortex |
|-----------|--------|--------|---------|--------|
| SQL generation/optimization | Excellent | Good | Limited | N/A |
| Data quality analysis | Excellent | Good | N/A | N/A |
| Log analysis / debugging | Excellent | Limited | N/A | Good (native to New Relic) |
| Incident investigation | Excellent (our custom skill) | Limited | N/A | Good (NRQL-aware) |
| Financial modeling | Good | Good (Sheets integration) | N/A | N/A |
| A/B test analysis | Good | Good | N/A | N/A |

**Recommendation:** Claude is clearly superior for complex analysis, SQL work, and incident investigation. Cortex handles New Relic-specific queries well but can't do cross-system analysis. Gemini is adequate for spreadsheet-based analysis. Teams doing primarily A/B test analysis or basic financial modeling could use Gemini.

### Security & Compliance

| Capability | Claude | Gemini | Copilot | Cortex |
|-----------|--------|--------|---------|--------|
| Vulnerability analysis | Excellent | Limited | Limited | N/A |
| Security code review | Excellent | Limited | Good (basic) | N/A |
| Compliance documentation | Excellent | Good | N/A | N/A |
| Incident forensics | Excellent | Limited | N/A | Limited |
| PCI/SOX documentation | Excellent | Limited | N/A | N/A |

**Recommendation:** Claude is the clear winner for security work. No overlap worth exploiting here — security team should keep Claude.

### Observability & Operations

| Capability | Claude | Gemini | Copilot | Cortex |
|-----------|--------|--------|---------|--------|
| Alert triage | Excellent (custom skill) | N/A | N/A | Good (native) |
| Runbook generation | Excellent | Limited | N/A | Limited |
| Infrastructure-as-code | Excellent | Limited | Good | N/A |
| Performance investigation | Excellent (custom skill) | N/A | N/A | Excellent (native) |
| Dashboard creation | Good | Good (Looker integration) | N/A | Good (native) |

**Recommendation:** Platform/SRE work is Claude's strongest ROI area. Cortex is useful for in-context New Relic queries but Claude handles the complex cross-system investigation. No substitution recommended for Platform Engineering.

---

## Team-by-Team Tool Fit Assessment

| Team | Primary Claude Use | Substitutable? | Recommended Primary Tool |
|------|-------------------|----------------|------------------------|
| Platform Engineering | Incident investigation, IaC, alert triage | No — unique capabilities | Claude |
| Order Platform | Spec-driven dev, code gen, bug investigation | Partially — Copilot for code gen | Claude + Copilot |
| Payments | Code gen, PCI compliance, security review | No — compliance needs Claude | Claude |
| Product Discovery | Search optimization, ML docs, data analysis | Partially — data analysis via Gemini | Claude (reduced seats) |
| Member Experience | Code gen, API docs, bug investigation | Partially — docs via Gemini | Claude (reduced seats) |
| Logistics | Code gen, integration testing | Yes — primarily Copilot use cases | Copilot + Gemini |
| Data Engineering | SQL gen, pipeline debugging, data quality | Partially — basic SQL via Gemini | Claude |
| Growth | A/B test analysis, copy generation | Yes — Gemini handles both well | Gemini |
| Marketing | Content drafting, email copy | Yes — Gemini with Workspace integration | Gemini |
| Finance | Financial modeling, report generation | Mostly — Sheets + Gemini sufficient | Gemini |
| QA Engineering | Test gen, test automation, bug reproduction | Partially — basic test gen via Copilot | Claude (reduced seats) |
| Security | Vuln analysis, code security review, forensics | No — unique capabilities | Claude |

---

## Cost Optimization Scenarios

### Scenario A: Status Quo
- Claude: $30,000/mo (200 seats)
- Copilot: $3,420/mo (180 seats)
- Total incremental AI tooling: $33,420/mo ($401K/yr)

### Scenario B: Optimized Allocation (recommended)
- Claude: ~$20,000/mo (130-140 seats — cut idle, redirect to Gemini)
- Copilot: $3,420/mo (180 seats — no change)
- Total incremental: ~$23,420/mo ($281K/yr)
- **Savings: ~$120K/yr**

### Scenario C: Aggressive Cut
- Claude: ~$12,500/mo (80 seats — engineering-only, power users)
- Copilot: $3,420/mo (180 seats)
- Total incremental: ~$15,920/mo ($191K/yr)
- **Savings: ~$210K/yr**
- **Risk:** Loses Claude access for teams showing growth trajectory; may slow adoption curve

---

## Notes

- Token overage is currently ~$5K/mo on top of seat costs, driven primarily by Platform Engineering and Data Engineering heavy usage
- Gemini quality has improved significantly in last 2 months — re-evaluate substitutability quarterly
- Copilot Workspace (multi-file) is in preview — could reduce Claude's code gen advantage when GA
- Cortex capabilities are expanding with each New Relic release — monitor for overlap with Claude's incident investigation skill
