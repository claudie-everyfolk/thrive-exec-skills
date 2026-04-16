# Recent Audit Findings — Access Management

Audit period: Q4 2025
Auditor: Internal Audit + Deloitte (SOX compliance)

---

## Finding 1: Stale Production Access — Two Former Team Members

**Severity:** High
**System:** AWS (production account)
**Date discovered:** 2025-12-18

**Description:**
During the quarterly AWS production access review, two user accounts were found with active production access belonging to employees who transferred to non-engineering roles 45+ days prior:

- **User A** (transferred from Backend Engineering to Product Management on 2025-11-01): Still had `developer-admin` role in production AWS account. Last console login was 2025-10-28, but programmatic access keys were still active.
- **User B** (transferred from SRE to Technical Writing on 2025-11-10): Still had `sre-admin` role in production AWS account. No login activity since transfer, but the access was never revoked.

**Root cause:** Internal transfers do not trigger the standard offboarding checklist. The HR system only triggers deprovisioning on full termination, not on department changes. Manager of the new team has no visibility into what access the transferring employee had in their previous role.

**Risk:** Excessive privilege. Both users had production write access they no longer needed. If either account were compromised, an attacker would have had production admin access.

**Remediation:**
- Immediately revoked both users' production access (completed 2025-12-18)
- Rotated access keys for User A
- Manual review of all internal transfers in last 6 months (completed 2025-12-22 — no additional findings)

**Auditor recommendation:** Implement automated access adjustment triggered by HR department transfer events. Internal transfers should trigger a "soft offboarding" that revokes all role-specific access and requires the new manager to re-provision only what's needed.

---

## Finding 2: Overly Broad Service Account Permissions

**Severity:** Medium
**System:** AWS (production account)
**Date discovered:** 2025-12-20

**Description:**
Service account `SVC-legacy-etl` was found with `AdministratorAccess` policy attached in the production AWS account. This service account was originally created in 2023 for a one-time data migration from the legacy e-commerce platform. The migration was completed in March 2024, but the service account was never deprovisioned or scoped down.

**Details:**
- Service account has not been used since 2024-03-15 (9 months of inactivity)
- `AdministratorAccess` grants full control over all AWS resources in the production account
- No owner was listed in the service account documentation
- Access keys had never been rotated

**Root cause:** No lifecycle management process for service accounts. Service accounts are created for projects but there is no review mechanism to decommission them when the project ends. The quarterly access review process covers human users but does not include service accounts.

**Risk:** A dormant service account with admin access is a high-value target. If the access keys were leaked (e.g., committed to a repo, logged in plain text), an attacker would have full production access.

**Remediation:**
- Immediately disabled the service account and rotated all keys (completed 2025-12-20)
- Deleted the service account after confirming no active dependencies (completed 2025-12-23)
- Initiated a full audit of all service accounts across all AWS accounts (in progress)

**Auditor recommendation:** Establish a service account lifecycle policy: mandatory owner, expiration date, quarterly review, and automated alerting on inactive service accounts (no API calls in 90+ days).

---

## Finding 3: Access Review Completed Late

**Severity:** Low (procedural)
**System:** Snowflake (finance schemas)
**Date discovered:** 2026-01-05

**Description:**
The monthly Snowflake finance schema access review for December 2025 was completed on January 3, 2026 — 3 days past the policy deadline of December 31. The review was assigned to the Finance Data Lead who was on PTO from December 23 to January 2. No backup reviewer was designated.

**Details:**
- The review itself found no issues — all users had appropriate access
- However, the 3-day gap means there was a period where access was not formally validated
- SOX controls require documented evidence that reviews are completed on schedule
- This is the second time in 4 quarters that a Snowflake finance review was completed late (previous: September 2025, 1 day late)

**Root cause:** Access review assignments are manual and do not account for PTO schedules. There is no automated escalation when a review deadline is approaching and the assigned reviewer has not started.

**Risk:** Procedural — no actual access issues found, but repeated late reviews signal a control weakness that auditors flag as a pattern.

**Remediation:**
- December review completed and documented on 2026-01-03
- Designated backup reviewers for all SOX-controlled access reviews (completed 2026-01-10)

**Auditor recommendation:** Automate access review scheduling with PTO-awareness and automatic escalation. Consider continuous access monitoring that flags anomalies in real-time rather than relying solely on periodic manual reviews.
