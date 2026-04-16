# Compliance Requirements for Access Provisioning — Thrive Market

These requirements apply to all access provisioning and deprovisioning actions. They are derived from Thrive Market's SOX and PCI compliance frameworks and are non-negotiable.

---

## SOX Requirements

### Separation of Duties (SoD)
- No single person may both request and approve access to a SOX-controlled system
- The person provisioning access must not be the same person who approved it
- Financial system access (NetSuite, Coupa, Anaplan) requires dual approval: direct manager + system owner
- Any automation that provisions SOX system access must enforce this three-party separation (requester ≠ approver ≠ provisioner)

### Approval Workflows
- **Manager approval** required for all access requests (SOX and non-SOX)
- **System owner approval** additionally required for SOX-controlled systems
- **Written evidence** of both approvals must be retained — verbal approval is not sufficient for audit
- Approvals must be timestamped and attributable to a named individual
- Approval evidence must be stored in Lumos or an equivalent governance platform

### Evidence Logging
- Every provisioning and deprovisioning action must generate an audit log entry
- Log must include: who requested, who approved, who provisioned, what access, when, and to which system
- Logs must be immutable — no deletion or modification after creation
- Retention period: 7 years minimum
- Quarterly review of all provisioning logs by Compliance team

### Access Review Cadence
- **Quarterly:** Full access review of all SOX-controlled systems
- **Monthly:** Review of privileged access (admin roles) across all systems
- **Upon role change:** Immediate review — old role access must be revoked within 48 hours
- **Upon termination:** All access must be revoked within 24 hours

---

## PCI Requirements

### Cardholder Data Environment (CDE) Access
- Systems that store, process, or transmit cardholder data (Stripe, payment processing) require Security team approval
- PCI-scoped access must follow least-privilege principle — no broader access than the specific job requires
- Multi-factor authentication is mandatory for all CDE access
- Access to CDE must be reviewed quarterly and re-justified

### Unique Identification
- Every account must map to exactly one individual — no shared accounts for PCI-scoped systems
- Service accounts must have a named owner and documented justification
- Generic admin accounts are prohibited

---

## Termination SLAs

| Timeline | Requirement |
|----------|-------------|
| Immediate (same day) | Disable Okta SSO (cascades to all SSO-linked apps) |
| Within 4 hours | Revoke access to all non-SSO systems (WMS, manual-provision systems) |
| Within 24 hours | Complete deprovisioning of all system access, including SOX and PCI systems |
| Within 48 hours | Remote lock/wipe of company devices |
| Within 5 business days | Equipment return initiated (shipping label sent or HQ drop-off scheduled) |

**For involuntary terminations:** Okta must be disabled within 1 hour of HR notification. Security team must be alerted for immediate monitoring.

---

## Onboarding SLAs

| Timeline | Requirement |
|----------|-------------|
| Day -3 (before start) | Baseline accounts created (Okta, Google Workspace, Slack, Zoom, Dayforce) |
| Day 1 (start date) | Role-specific access provisioned and verified |
| Day 1 + 4 hours | SOX system access requests submitted (if applicable) — not provisioned, just initiated |
| Day 1 + 48 hours | SOX system access provisioned (after dual approval received) |
| Day 3 | All access verified by hiring manager — confirmation ticket closed |

---

## Role Change Requirements

- Role change must trigger a **full access delta review**
- Access from the old role that is not part of the new role must be revoked within 48 hours
- New role access is provisioned per standard onboarding SLA
- **No access accumulation** — employees must not retain access from previous roles unless explicitly justified and approved
- SOX-controlled access from the old role must be revoked immediately upon role change effective date, regardless of new role requirements (re-provisioning follows standard SOX approval if needed in the new role)

---

## Automation Constraints

Any automated provisioning system must:
1. **Enforce approval workflows** — automation can draft requests and queue them, but SOX/PCI access cannot be auto-approved
2. **Generate audit-grade logs** — every automated action logged with system-generated timestamp, the triggering event (Workday hire record, manager approval), and the resulting access change
3. **Support manual override** — any automated action must be reversible by an authorized admin within 15 minutes
4. **Pass quarterly validation** — Compliance team reviews automation rules quarterly to ensure they match current policy
5. **Alert on anomalies** — unexpected access patterns (e.g., non-finance employee getting NetSuite access) must trigger an alert, not silent provisioning
6. **Separate prod from staging** — automation that works in a test environment must go through a formal change management review before running against production Okta/systems

---

## Audit Evidence Requirements for Provisioning

For each access provisioning event, the following evidence must be collectible on demand:
- Request record (who, what, when, why)
- Approval chain (manager + system owner for SOX)
- Provisioning confirmation (system log showing access was granted)
- Verification record (hiring manager confirmed access is correct and working)
- For deprovisioning: confirmation that access was successfully revoked (not just that the request was submitted)
