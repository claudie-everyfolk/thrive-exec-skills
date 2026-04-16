# System Access Matrix — Thrive Market

Standard system access by department and role. This matrix defines what "correctly provisioned" looks like for each role. All roles get baseline access. Role-specific access is additive.

---

## Baseline Access (All Employees)

Every employee regardless of role receives:
- Okta (SSO portal)
- Google Workspace (email, Drive, Calendar, Meet)
- Slack
- Zoom
- Dayforce (timekeeping/HR self-service)

---

## Engineering

| Role | Additional Systems | SOX Flag | Notes |
|------|-------------------|----------|-------|
| Software Engineer | GitHub, Jira, Confluence, Datadog, Sentry, Docker Desktop, PagerDuty | No | Standard dev toolkit |
| Senior Software Engineer | GitHub, Jira, Confluence, Datadog, Sentry, Docker Desktop, PagerDuty, Terraform Cloud (staging) | No | Staging infra access only |
| Staff Engineer | GitHub, Jira, Confluence, Datadog, Sentry, Docker Desktop, PagerDuty, Terraform Cloud (staging + prod), AWS Console (read-only) | Yes (AWS) | Prod access requires DevOps lead approval |
| Engineering Manager | GitHub, Jira, Confluence, Datadog, Sentry, PagerDuty, Domo, Lattice | No | Domo for eng metrics |
| Data Engineer | GitHub, Jira, Confluence, Snowflake (read + write), Airflow, dbt Cloud, Datadog | Yes (Snowflake write) | Snowflake write is SOX-controlled |
| Data Analyst | GitHub (read-only), Jira, Confluence, Snowflake (read-only), Domo, Amplitude | No | Read-only analytics access |

---

## Marketing

| Role | Additional Systems | SOX Flag | Notes |
|------|-------------------|----------|-------|
| Marketing Analyst | Amplitude, Domo, Google Analytics 4, Snowflake (read-only) | No | Analytics only |
| Marketing Manager | Amplitude, Domo, Google Analytics 4, Hootsuite, Canva Pro, Figma | No | Full marketing toolkit |
| Content Manager | Contentful, Canva Pro, Figma, Loom Pro, WordPress | No | CMS + creative tools |
| Growth Marketing | Amplitude, Google Analytics 4, Google Ads, Meta Ads Manager, Braze | No | Ad platforms + engagement |
| Marketing VP | Amplitude, Domo, Google Analytics 4, Hootsuite, Canva Pro, Figma, Snowflake (read-only), Lattice | No | Full suite + analytics |

---

## Finance

| Role | Additional Systems | SOX Flag | Notes |
|------|-------------------|----------|-------|
| FP&A Analyst | Domo, Anaplan, Snowflake (read-only), SAP Concur | Yes (Anaplan) | Anaplan for financial modeling — SOX-adjacent |
| Accounting Specialist | NetSuite, Coupa, SAP Concur, Expensify | Yes (NetSuite, Coupa) | SOX core — dual approval required |
| Senior Accountant | NetSuite (full), Coupa, SAP Concur, Expensify, Snowflake (read-only), Domo | Yes (NetSuite, Coupa) | Full financial system access |
| Finance Manager | NetSuite (full), Coupa, Anaplan, SAP Concur, Expensify, Domo, Snowflake (read-only), Lattice | Yes (NetSuite, Coupa, Anaplan) | Management + reporting |
| Finance VP | All finance systems, Stripe (read-only), Bloomberg Terminal | Yes (all) | Requires Finance VP approval for all SOX systems |

---

## Product

| Role | Additional Systems | SOX Flag | Notes |
|------|-------------------|----------|-------|
| Product Manager | Jira, Confluence, Amplitude, Mixpanel, Figma, Contentful (read-only), Domo | No | Standard PM toolkit |
| Product Designer | Jira, Figma, Maze, UserTesting, Loom Pro | No | Design + research tools |
| Product Analyst | Jira, Amplitude, Mixpanel, Snowflake (read-only), Domo | No | Analytics focused |

---

## Sales

| Role | Additional Systems | SOX Flag | Notes |
|------|-------------------|----------|-------|
| Account Executive | Salesforce, HubSpot, Gong, Outreach.io, LinkedIn Sales Navigator | No | Full sales stack |
| Sales Manager | Salesforce, HubSpot, Gong, Outreach.io, LinkedIn Sales Navigator, Domo, Lattice | No | Management + reporting |
| Sales Operations | Salesforce (admin), HubSpot (admin), Gong (admin), Domo | No | Admin access for config |

---

## Customer Service

| Role | Additional Systems | SOX Flag | Notes |
|------|-------------------|----------|-------|
| CS Agent | Freshworks, Ring Central | No | Basic support toolkit |
| Senior CS Agent | Freshworks, Ring Central, Zendesk (pilot), Grammarly Business, TextExpander | No | Extended toolkit |
| CS QA Lead | Freshworks (admin), Ring Central, Zendesk (pilot), Domo | No | Admin for quality review |
| CS Manager | Freshworks (admin), Ring Central (admin), Domo, Lattice | No | Full management access |

---

## HR

| Role | Additional Systems | SOX Flag | Notes |
|------|-------------------|----------|-------|
| HR Coordinator | Workday, BambooHR, Lattice | No | Day-to-day HR operations |
| HR Manager | Workday (admin), BambooHR (admin), Lattice (admin), Lumos (viewer) | No | Admin access + governance visibility |
| HR Director | Workday (admin), BambooHR (admin), Lattice (admin), Lumos (admin), Domo | No | Full suite + analytics |

---

## Legal

| Role | Additional Systems | SOX Flag | Notes |
|------|-------------------|----------|-------|
| Paralegal | CLM (contract management), Google Vault, Confluence | No | Contract + legal ops |
| Legal Counsel | CLM (admin), Google Vault (admin), Confluence, e-Discovery platform | No | Full legal toolkit |
| Legal VP | All legal systems, NetSuite (read-only for contract financials), Domo | Yes (NetSuite read) | Financial visibility for contracts |

---

## FC Operations

| Role | Additional Systems | SOX Flag | Notes |
|------|-------------------|----------|-------|
| FC Associate | WMS (warehouse management), Dayforce (already baseline) | No | Minimal — floor-level access |
| Pack-Station Operator | WMS, Pack-Station Client (auto-provisioned via Automox imaging) | No | Station access via device, not individual account |
| Receiving Clerk | WMS, Receiving Module | No | Inbound logistics |
| FC Shift Lead | WMS (supervisor), Dayforce (supervisor), Slack (FC channel) | No | Supervisory WMS access |
| FC Operations Manager | WMS (admin), Dayforce (admin), Slack, Domo, Lattice | No | Full FC management |
| FC IT Technician | WMS (read-only), Automox (admin), Freshworks (agent), Slack | No | IT support at FC |

---

## Provisioning Notes

1. **Okta group membership** drives most access. Assign employee to the right Okta group → apps auto-provision.
2. **Exceptions:** Some systems aren't yet integrated with Okta SSO (Zendesk pilot, WMS, some FC-specific tools). These require manual provisioning.
3. **SOX systems** always require explicit approval regardless of role match. The matrix defines what someone *should* have — approval is still needed for SOX-flagged items.
4. **License-limited systems** (Figma, Canva Pro, Loom Pro, LinkedIn Sales Navigator, Bloomberg) — check seat availability before provisioning. May require budget approval.
5. **FC employees** have simpler access profiles but provisioning is complicated by on-site device setup (Automox imaging, local WMS client install, hardware peripherals).
