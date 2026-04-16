# Control Framework — Thrive Market SOX & PCI Controls

15 key controls reviewed during quarterly audits. Each control has a defined data source, evidence format, and collection owner.

---

## SOX Controls

### SOX-01: User Access Reviews
**Description:** Quarterly review of all user access to financially significant applications (NetSuite, Coupa, Anaplan, Snowflake) to ensure access is appropriate for current role.
**Data Source:** Lumos (access review campaigns), Okta (current assignments)
**Evidence Format:** Lumos campaign report showing all users reviewed, decisions made (approve/revoke), reviewer name, and completion date
**Collection Owner:** IT Ops
**Current Method:** Export from Lumos + manual reconciliation with Okta user list in spreadsheet
**Frequency:** Quarterly

### SOX-02: Privileged Access Review
**Description:** Monthly review of admin and privileged access across all systems. Verify that privileged users have business justification and manager approval.
**Data Source:** Okta (admin roles), AWS IAM (admin users), GitHub (org owners), NetSuite (admin roles)
**Evidence Format:** Spreadsheet listing all privileged accounts, system, access level, business justification, and manager sign-off
**Collection Owner:** Security Team
**Current Method:** Manual export from each system's admin console, compiled into master spreadsheet
**Frequency:** Monthly

### SOX-03: Change Management Approvals
**Description:** All changes to production financial systems require documented approval before deployment. Evidence of pre-deployment approval for every production change.
**Data Source:** Jira (change tickets), GitHub (PR approvals), NetSuite (customization log)
**Evidence Format:** Sample of 25 production changes with matching approval records (Jira ticket linked to PR, approved before merge)
**Collection Owner:** Engineering
**Current Method:** Manual sampling — pull 25 random changes, screenshot Jira + GitHub for each
**Frequency:** Quarterly (sample-based)

### SOX-04: Separation of Duties
**Description:** No single individual has the ability to both initiate and approve financial transactions. Access controls enforce separation between transaction entry and approval.
**Data Source:** NetSuite (role assignments), Coupa (approval chains)
**Evidence Format:** Role matrix showing separation of entry and approval permissions, plus test results (attempt to self-approve a transaction — should fail)
**Collection Owner:** Finance + IT Ops
**Current Method:** Manual role export from NetSuite and Coupa, manual test execution with screenshots
**Frequency:** Quarterly

### SOX-05: Termination Access Removal
**Description:** All system access is removed within 24 hours of employment termination. Evidence that deprovisioning was timely and complete.
**Data Source:** Workday (termination dates), Okta (disable timestamps), Lumos (deprovisioning logs)
**Evidence Format:** Report matching termination dates to Okta disable timestamps, showing all were within 24-hour SLA
**Collection Owner:** IT Ops
**Current Method:** Manual cross-reference of Workday termination report with Okta admin logs in spreadsheet
**Frequency:** Quarterly (all terminations in period)

### SOX-06: New Access Provisioning Approval
**Description:** All access provisioning to SOX-controlled systems has documented dual approval (manager + system owner) before access is granted.
**Data Source:** Lumos (approval workflows), Freshworks (access request tickets)
**Evidence Format:** Sample of all SOX system provisioning events with matching approval records
**Collection Owner:** IT Ops
**Current Method:** Pull provisioning events from Okta logs, match to Freshworks tickets for approval evidence
**Frequency:** Quarterly

### SOX-07: Financial Close Reconciliation
**Description:** Monthly financial close process includes reconciliation of sub-ledger to general ledger with documented review and approval.
**Data Source:** NetSuite (reconciliation reports), Google Drive (review sign-offs)
**Evidence Format:** Monthly reconciliation reports with reviewer signatures/approvals
**Collection Owner:** Finance
**Current Method:** Finance team uploads reconciliation PDFs to Drive; IT exports the folder listing with timestamps
**Frequency:** Monthly (collected quarterly)

---

## PCI Controls

### PCI-01: Network Segmentation Validation
**Description:** Cardholder data environment (CDE) is properly segmented from the rest of the network. Annual penetration test validates segmentation.
**Data Source:** AWS (VPC configurations, security groups), Pen test vendor report
**Evidence Format:** VPC diagram + security group rules export, plus annual pen test report confirming segmentation
**Collection Owner:** Security Team
**Current Method:** Manual screenshot of AWS VPC console, manual security group export, vendor provides PDF report
**Frequency:** Annual (pen test) + quarterly (configuration review)

### PCI-02: Encryption at Rest
**Description:** All cardholder data is encrypted at rest using industry-standard encryption (AES-256 or equivalent).
**Data Source:** AWS (RDS encryption settings, S3 bucket policies, EBS volume settings)
**Evidence Format:** AWS console exports showing encryption enabled on all relevant resources
**Collection Owner:** Security Team + Engineering
**Current Method:** Manual screenshot of each RDS instance, S3 bucket, and EBS volume encryption settings
**Frequency:** Quarterly

### PCI-03: Vulnerability Scanning
**Description:** Internal and external vulnerability scans conducted quarterly. Critical and high vulnerabilities remediated within 30 days.
**Data Source:** Qualys (scan reports), Jira (remediation tickets)
**Evidence Format:** Quarterly scan summary + remediation evidence for any critical/high findings
**Collection Owner:** Security Team
**Current Method:** Export Qualys PDF report, manually match critical findings to Jira remediation tickets
**Frequency:** Quarterly

### PCI-04: Access to Cardholder Data
**Description:** Access to systems storing cardholder data is restricted to personnel with a documented business need. All access is reviewed quarterly.
**Data Source:** AWS IAM (CDE resource policies), Okta (app assignments for payment systems), Stripe (user list)
**Evidence Format:** User access list for all CDE systems with business justification for each user
**Collection Owner:** Security Team
**Current Method:** Manual export from each CDE system, compiled into spreadsheet with justification column filled manually
**Frequency:** Quarterly

### PCI-05: Security Logging and Monitoring
**Description:** Security events across CDE are logged and monitored. Logs are retained for 12 months, with 3 months immediately available.
**Data Source:** AWS CloudTrail (CDE account), CloudWatch (alert rules), SIEM
**Evidence Format:** CloudTrail configuration export, sample of security alerts and response records, log retention policy confirmation
**Collection Owner:** Security Team
**Current Method:** CloudTrail console screenshot, manual export of alert history, written attestation of retention policy
**Frequency:** Quarterly

---

## General IT Controls

### GIT-01: Backup Verification
**Description:** Critical system backups are performed daily and tested monthly. Recovery point objective (RPO) and recovery time objective (RTO) are met.
**Data Source:** AWS (RDS automated backups, S3 cross-region replication), Backup test logs
**Evidence Format:** Backup configuration screenshots, monthly restore test results with timestamps and success/failure status
**Collection Owner:** Engineering + IT Ops
**Current Method:** Manual screenshot of AWS backup configurations, monthly restore test documented in Confluence page
**Frequency:** Monthly (test) + Quarterly (audit evidence)

### GIT-02: Endpoint Protection
**Description:** All company endpoints have active endpoint protection (antivirus/EDR) and are managed via MDM. Compliance rate ≥ 98%.
**Data Source:** Kandji (macOS devices), Automox (Windows devices — FC stations), CrowdStrike (EDR)
**Evidence Format:** MDM compliance dashboard export showing device count, compliance rate, and non-compliant device list
**Collection Owner:** IT Ops
**Current Method:** Manual export from Kandji and Automox dashboards, combined into single compliance spreadsheet. CrowdStrike coverage report pulled separately.
**Frequency:** Monthly

### GIT-03: Incident Response Testing
**Description:** Incident response plan is tested at least annually through tabletop exercise or simulated incident. Results documented with lessons learned.
**Data Source:** Internal documentation (IR plan, tabletop exercise report)
**Evidence Format:** Dated tabletop exercise report with participants, scenario, findings, and remediation actions
**Collection Owner:** Security Team
**Current Method:** Security team runs annual tabletop; report written in Google Docs, PDF exported for auditors
**Frequency:** Annual
