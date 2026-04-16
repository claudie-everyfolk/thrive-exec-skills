# Audit Findings — Q4 2025 SOX/PCI Audit

Three findings identified during the most recent external audit. Severity rated by the auditors.

---

## Finding 1: Quarterly Access Review Completed Late

**Control:** SOX-01 (User Access Reviews)
**Severity:** Moderate
**Finding Date:** 2025-12-15

**Description:**
The Q3 2025 quarterly user access review for financially significant applications was completed 14 days past the deadline. The review was due September 30 and completed October 14. This represents a gap in the control during which inappropriate access could have existed undetected.

**Systems Affected:** NetSuite, Coupa, Anaplan, Snowflake

**Root Cause:**
The access review process is largely manual. IT Ops must export user lists from Lumos, cross-reference against Okta assignments, distribute review lists to 12 system owners across Finance, Engineering, and IT, collect sign-offs, and compile results. The process has no automated tracking — it's managed via email and a shared spreadsheet. Three system owners didn't respond to the initial request, and there was no escalation mechanism until the IT Ops manager manually followed up after the deadline had already passed.

**Remediation Status:** In progress
**Remediation Actions:**
1. *(Complete)* Established Slack-based reminders for system owners 2 weeks before and 1 week before the review deadline
2. *(In progress)* Configuring Lumos automated review campaigns with built-in escalation if a reviewer doesn't respond within 5 business days
3. *(Planned)* Evaluating Vanta integration for continuous access monitoring to supplement quarterly point-in-time reviews

**Management Response:**
IT Ops acknowledges the finding. The manual process doesn't scale with our current number of SOX-controlled systems (4) and system owners (12). Automation through Lumos review campaigns and Vanta continuous monitoring is expected to resolve this by Q2 2026.

---

## Finding 2: Terminated Employees Retained GitHub Access

**Control:** SOX-05 (Termination Access Removal)
**Severity:** High
**Finding Date:** 2025-12-15

**Description:**
Two terminated employees were found to still have active GitHub organization access at the time of the quarterly access review. Employee A was terminated on August 8, 2025, and their GitHub access was not revoked until the Q3 access review on October 14, 2025 (67 days post-termination). Employee B was terminated on September 3, 2025, and their GitHub access was not revoked until October 14, 2025 (41 days post-termination). Both employees had access to private code repositories.

**Systems Affected:** GitHub Enterprise

**Root Cause:**
GitHub is not integrated with Okta SSO for access provisioning/deprovisioning. When Okta is disabled during offboarding (via Wursta automation), GitHub access is unaffected because GitHub uses separate authentication. The offboarding checklist includes a manual step to revoke GitHub access, but this step was missed for both employees. The manual step has no verification — there's no automated check that confirms GitHub access was actually revoked after an offboarding.

Additionally, GitHub was not included in the Lumos access review scope until this finding was identified. The quarterly review that eventually caught the issue was expanded specifically because of a separate concern raised by Engineering.

**Remediation Status:** In progress
**Remediation Actions:**
1. *(Complete)* Added GitHub to the Lumos-managed access review scope
2. *(Complete)* Added a verification step in the Wursta offboarding workflow: after Okta disable, a Freshworks ticket is auto-created to verify GitHub access revocation
3. *(In progress)* Evaluating GitHub Enterprise SCIM integration to enable automated deprovisioning via Okta
4. *(Planned)* Implementing Vanta continuous monitoring for terminated user access across all systems

**Management Response:**
This finding is taken seriously. The gap exists because GitHub sits outside our SSO-based deprovisioning cascade. Short-term fix (verification ticket) is in place. Long-term fix (SCIM integration) will bring GitHub into the automated deprovisioning flow by Q2 2026.

---

## Finding 3: No Evidence of Quarterly Privileged Access Review for AWS Root

**Control:** SOX-02 (Privileged Access Review)
**Severity:** High
**Finding Date:** 2025-12-15

**Description:**
The auditors requested evidence of the quarterly review of privileged access to AWS, specifically the AWS root account and IAM admin users. While the IT Ops team could demonstrate that monthly reviews of Okta admin roles and NetSuite admin roles were conducted, no documented evidence existed for a review of AWS IAM privileged users or the AWS root account access during Q2 or Q3 2025.

**Systems Affected:** AWS (IAM)

**Root Cause:**
The privileged access review process was designed around Okta-visible admin roles. AWS IAM privileges are not visible in Okta or Lumos — they exist in a separate identity layer. The Security team was conducting informal reviews of AWS IAM users but not documenting them in the standard evidence format (no spreadsheet, no sign-off, no timestamp). The review process did not have a checklist that included non-Okta identity systems.

Additionally, the evidence collection process for SOX-02 only pulled from Okta admin console exports. AWS IAM was not on the evidence collection checklist, so even if a review had occurred, the evidence would not have been captured in the audit package.

**Remediation Status:** In progress
**Remediation Actions:**
1. *(Complete)* Created a comprehensive privileged access inventory that includes all identity systems: Okta, AWS IAM, GitHub org owners, NetSuite admin, Snowflake account admin
2. *(Complete)* Added AWS IAM privileged user export to the monthly evidence collection checklist
3. *(In progress)* Configuring AWS IAM Access Analyzer to generate automated reports on privileged access
4. *(Planned)* Integrating AWS IAM with Lumos for unified privileged access visibility
5. *(Planned)* Vanta continuous monitoring of AWS privileged access with alerting on any changes

**Management Response:**
The gap was caused by an incomplete control scope — our privileged access review process didn't cover AWS IAM because it sits outside our primary identity platform (Okta). We've expanded the scope and are investing in tooling (Lumos + Vanta + AWS Access Analyzer) to ensure full coverage. The goal is continuous monitoring of all privileged access across all identity systems by Q3 2026.

---

## Summary

| # | Finding | Control | Severity | Root Cause Theme | Status |
|---|---------|---------|----------|------------------|--------|
| 1 | Access review 14 days late | SOX-01 | Moderate | Manual process, no escalation mechanism | In progress |
| 2 | 2 terminated employees had GitHub access 41-67 days post-term | SOX-05 | High | GitHub outside SSO cascade, manual step missed | In progress |
| 3 | No documented AWS privileged access review for 2 quarters | SOX-02 | High | Incomplete scope — AWS IAM not in evidence collection | In progress |

**Common thread:** All three findings trace to manual processes with incomplete scope and no automated verification. The evidence collection process was designed for a simpler environment (Okta-centric) and hasn't kept up with the growth of the system landscape.
