# Thrive Market — Access Management Policies

Last updated: 2025-11-15

---

## General Principles

- All access follows least-privilege: users get the minimum access required for their role.
- All provisioning requests require manager approval via ServiceNow.
- Deprovisioning is triggered by HR system on termination/transfer date.
- Access reviews are conducted quarterly for all systems; monthly for SOX-controlled systems.
- Temporary/elevated access expires automatically after the approved duration.

---

## System-Specific Policies

### GitHub

| Job Title | Default Role | Repos | Approval |
|-----------|-------------|-------|----------|
| Software Engineer (any level) | developer | Team repos only | Manager |
| Senior Engineer / Tech Lead | maintainer | Team repos + shared libs | Manager |
| Engineering Manager | maintainer | Team repos + shared libs | Director |
| DevOps / SRE | developer | Platform repos + team repos | Manager |
| QA Engineer | developer | Team repos (read) + QA repos (write) | Manager |
| Contractor | developer | Specific repos only (named in ticket) | Manager + Legal |
| External Collaborator | outside-collaborator | Named repos only — time-limited | VP Engineering |

**Admin access:** Org-level admin requires VP Engineering approval. Maximum 5 org admins at any time.

**Offboarding:** GitHub access must be revoked within 4 hours of termination notification. For involuntary terminations, revoke within 1 hour.

---

### AWS

| Job Title | Default Role | Account | Approval |
|-----------|-------------|---------|----------|
| Software Engineer (L1-L3) | developer-readonly | Staging only | Manager |
| Senior Engineer (L4+) | developer-readonly | Staging + prod read | Manager |
| SRE / DevOps / Infrastructure | sre-admin | Staging + production | Manager + Director |
| Data Analyst | data-readonly | Data lake (S3 + Athena) | Manager |
| ML Engineer | ml-engineer | SageMaker + S3 + staging | Manager |
| Data Engineering Lead | data-admin | Snowflake infra + data lake | Director |

**Production admin access:** Requires Director approval + documented justification. Reviewed monthly.

**Temporary elevated access:** For incident response, on-call lead can approve temporary production access for up to 4 hours. Must be logged and reviewed.

**Service accounts:** Require platform team owner + security review. Scoped to minimum necessary permissions. Reviewed quarterly.

**SOX note:** AWS production accounts that touch financial data (order processing, payment, membership billing) are SOX-controlled. Changes require change management approval.

---

### Snowflake

| Job Title | Default Role | Schemas | Approval |
|-----------|-------------|---------|----------|
| Data Analyst | analyst | Read access to assigned schemas | Manager |
| Data Engineer | analyst + write | Assigned schemas + staging | Manager |
| Data Engineering Lead | admin | All schemas | Director |
| Finance Analyst | finance-readonly | Finance schemas only | CFO Office |

**SOX-controlled:** Finance schemas (revenue, billing, membership_transactions) require CFO Office approval for any access changes. Monthly access review required.

**Admin access:** Maximum 3 Snowflake admins. Requires Director + Security approval.

---

### Okta

| Event | Action | Approval |
|-------|--------|----------|
| New hire | Auto-provision SSO with department group | HR system (auto) |
| Termination | Disable account + revoke all sessions | HR system (auto) |
| Department transfer | Update group membership | Manager (new team) |

**Note:** Okta provisioning is partially automated via HR system integration. SSO group assignment still requires manual verification for non-standard roles.

---

### Datadog

| Job Title | Default Role | Approval |
|-----------|-------------|----------|
| Any engineer (default) | viewer | Manager |
| SRE / DevOps / On-call | editor | Manager |
| Team Lead / Manager | editor | Director |
| Platform Lead | admin | Director |

**API keys:** Managed by platform team only. Rotation required quarterly.

**Note:** Datadog access is low-risk — viewer access is standard for all engineers. Editor access for on-call is standard. Admin is restricted.

---

### Netsuite

| Job Title | Default Role | Approval |
|-----------|-------------|----------|
| Finance team (AP/AR) | ap-clerk / ar-clerk | CFO Office |
| Controller | controller | CFO + CEO |
| Operations viewer | viewer | Ops Manager + CFO Office |
| External auditor | auditor (read-only, time-limited) | CFO Office |

**SOX-controlled:** ALL Netsuite access changes require CFO Office approval. Monthly access review. Segregation of duties enforced: no single user can create + approve transactions.

**Offboarding:** Netsuite access must be revoked within 2 hours of termination notification (finance data sensitivity).

---

### PagerDuty

| Job Title | Default Role | Approval |
|-----------|-------------|----------|
| SRE / DevOps | responder | Manager |
| On-call engineer | responder | On-call lead |
| Engineering Manager | manager | Director |

**Note:** PagerDuty access is straightforward — add to on-call schedule on provision, remove on deprovision. Low-risk system.

---

## Offboarding Checklist

When an employee departs, the following must be completed in order:

1. **Okta** — Disable SSO account (blocks access to all SSO-integrated systems)
2. **GitHub** — Remove from org (revokes all repo access)
3. **AWS** — Delete IAM user / remove from SSO groups
4. **Snowflake** — Disable user account
5. **Datadog** — Remove user
6. **Netsuite** — Disable user (if applicable)
7. **PagerDuty** — Remove from schedules
8. **Service accounts** — Rotate any shared credentials the user had access to

**SLA:** Standard offboarding within 24 hours. Involuntary termination within 1 hour for critical systems (Okta, GitHub, AWS), 4 hours for remaining.

---

## Access Review Schedule

| System | Review Frequency | Reviewer | SOX Scope |
|--------|-----------------|----------|-----------|
| AWS (production) | Monthly | Platform Director | Yes |
| Snowflake (finance schemas) | Monthly | CFO Office | Yes |
| Netsuite | Monthly | CFO Office | Yes |
| GitHub | Quarterly | Engineering Managers | No |
| Datadog | Quarterly | Platform Team | No |
| Okta | Quarterly | IT + HR | No |
| PagerDuty | Quarterly | On-call Lead | No |
