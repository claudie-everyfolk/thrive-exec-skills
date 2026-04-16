# Escalation Rules — Thrive Market IT Ops Service Desk

These rules govern when a ticket can be auto-resolved versus when it must be escalated to a human analyst or specialist team.

---

## Auto-Resolve Criteria (ALL must be true)

A ticket may be auto-resolved if:
1. The ticket category matches a known resolution template
2. The requester is a verified active employee (status = Active in Workday)
3. No PII is included in the ticket description
4. The request does not involve a SOX-controlled system (unless it's read-only access matching the user's role)
5. The request does not involve production infrastructure (AWS, GCP, database servers)
6. Priority is Low or Medium
7. The requester is not a contractor or vendor (contractors require manual verification)

---

## Mandatory Escalation Triggers

### Priority-Based
- **Urgent priority** — always escalate to on-call analyst
- **High priority from FC location** — escalate to FC IT lead within 15 minutes (production impact)

### Requester-Based
- **Executive (Director+)** — auto-resolve is OK for standard requests, but send a courtesy notification to the IT Ops manager
- **Contractor / Vendor** — always manual review; verify access scope with hiring manager before provisioning
- **Terminated employee** — if a ticket comes from someone flagged as terminated in Workday, escalate immediately to Security team

### System-Based
- **SOX-controlled systems** (NetSuite, Snowflake write access, financial reporting tools) — require dual approval (manager + system owner). Never auto-resolve.
- **PCI-scoped systems** (payment processing, cardholder data environments) — require Security team sign-off. Never auto-resolve.
- **Production infrastructure** (AWS console, GCP, database admin, CI/CD pipelines) — escalate to DevOps/Platform team
- **GitHub organization admin** — escalate to Engineering Lead for approval
- **Admin/privileged access** to any system — escalate to Security team regardless of system classification

### Content-Based
- **PII detected** in ticket description (SSN, credit card numbers, personal addresses) — escalate to Security team, do not include PII in any auto-response
- **Compliance-related language** ("audit," "SOX," "PCI," "evidence," "finding") — route to Compliance team
- **Security incident language** ("breach," "unauthorized," "compromised," "phishing") — escalate to Security team immediately

### Location-Based
- **Fulfillment center hardware** at High/Urgent priority — escalate to FC IT lead (production line impact)
- **Remote employee device lost/stolen** — escalate to Security team (remote wipe required)

---

## Auto-Resolve with Notification (Hybrid)

These can be auto-resolved but require a notification to a specific person:
- **New hire provisioning** — auto-resolve per access matrix, notify hiring manager of what was provisioned
- **Role change access update** — auto-resolve standard access changes, notify both old and new manager
- **Equipment return initiation** — auto-resolve shipping label generation, notify HR of offboarding status

---

## Escalation Routing

| Escalation Type | Route To | SLA |
|-----------------|----------|-----|
| SOX system access | Compliance + Manager | 24 hours |
| PCI system access | Security Team | 24 hours |
| Production infrastructure | DevOps/Platform | 4 hours |
| Security incident | Security Team | 1 hour |
| FC production impact | FC IT Lead | 15 minutes |
| Executive courtesy | IT Ops Manager | Notification only |
| Contractor access | Hiring Manager | 24 hours |
| Device lost/stolen | Security Team | 1 hour |
| Unrecognized category | L2 Analyst | 4 hours |

---

## Decision Priority

When multiple rules apply, use this priority order:
1. Security incident → Security Team (highest priority)
2. PII detected → Security Team
3. Terminated employee → Security Team
4. PCI system → Security Team
5. SOX system → Compliance + Manager
6. Production infrastructure → DevOps/Platform
7. FC production impact → FC IT Lead
8. Contractor/vendor → Hiring Manager
9. Executive → Auto-resolve + notification
10. Standard → Auto-resolve (lowest priority)

---

## Review Cadence

- **Weekly:** Review auto-resolved tickets for false positives (tickets that should have been escalated)
- **Monthly:** Update escalation rules based on new ticket patterns and audit findings
- **Quarterly:** Full review aligned with SOX/PCI audit prep
