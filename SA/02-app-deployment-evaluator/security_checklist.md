# Thrive Market — Security Requirements by Data Sensitivity Tier

## Tier Overview

| Tier | Data Sensitivity | Approval Path | Turnaround SLA |
|------|-----------------|---------------|----------------|
| Tier 1 | No PII, no auth, read-only internal data | Self-serve | Immediate (automated) |
| Tier 2 | Internal auth required, no PII, internal data | Light review | 2 business days |
| Tier 3 | PII or financial data involved | Full security review | 5-10 business days |
| Tier 4 | External-facing or customer-accessible | Engineering ownership required | N/A (becomes eng project) |

---

## Tier 1 — Self-Serve

**Profile:** Internal dashboard reading from Snowflake or Google Sheets. No user authentication beyond VPN/Tailscale network access. No PII. No external API keys.

**Requirements:**
- [ ] App runs on internal network only (Tailscale/VPN)
- [ ] No PII in any data source accessed
- [ ] Read-only data access (no writes to any system of record)
- [ ] Source code in GitHub (platform team template)
- [ ] Basic README documenting what the app does and who maintains it

**Examples:** Shipping cost analyzer (Snowflake read-only), warehouse capacity planner (Snowflake + Google Sheets read-only)

---

## Tier 2 — Light Review

**Profile:** Internal app requiring Okta SSO for access control. May access third-party APIs (Netsuite, Klaviyo, etc.) but does not handle PII. Internal users only.

**Requirements (all Tier 1 requirements plus):**
- [ ] Okta SSO integrated (SAML)
- [ ] Access scoped to appropriate Okta group
- [ ] API keys stored in AWS Secrets Manager (not in code, not in env vars)
- [ ] Third-party API access documented (which APIs, what scopes, rate limits)
- [ ] No hardcoded credentials anywhere in codebase
- [ ] Light review by platform team engineer (checklist review, not code audit)

**Reviewer:** Any platform team engineer
**Review scope:** Architecture check, secrets handling, auth config, data access scope

**Examples:** Product margin calculator (Netsuite + Magento via API, Okta auth), campaign performance tracker (Snowflake + Klaviyo API, Okta auth)

---

## Tier 3 — Full Security Review

**Profile:** App handles PII (member emails, names, addresses, payment info) or financial data (invoices, payment amounts, refund decisions). May involve write operations to systems of record.

**Requirements (all Tier 2 requirements plus):**
- [ ] Data classification completed (what PII fields, where stored, retention policy)
- [ ] Access logging enabled (who accessed what PII, when)
- [ ] PII masked in logs (no member emails, names, or IDs in application logs)
- [ ] Snowflake access scoped to minimum necessary tables/columns
- [ ] Write operations require additional approval from data owner
- [ ] Dependency vulnerability scan (Snyk or equivalent) — no critical/high vulns
- [ ] Security review by security team (architecture + code review)
- [ ] Data retention policy documented and implemented
- [ ] Incident response plan: what happens if this app leaks PII?

**Reviewer:** Security team lead + platform team engineer
**Review scope:** Full architecture review, code audit for PII handling, secrets audit, access control verification, data flow diagram review

**Examples:** Member lookup dashboard (PII: member emails, order history), refund approval dashboard (PII + financial: member info, refund amounts), contract clause extractor (PII in uploaded documents)

---

## Tier 4 — Engineering Ownership Required

**Profile:** App is accessible to external users (customers, vendors, public internet) or processes data that could cause material harm if exposed. These are not "non-engineer apps" — they are engineering projects.

**Requirements:**
- Engineering team owns the app (assigned to a team in Backstage/Trellis)
- Full SDLC applies: code review, staging environment, load testing, monitoring, alerting
- New Relic instrumentation required
- Penetration testing before launch
- SOC 2 compliance verification

**Trigger conditions (any one = Tier 4):**
- App accessible from public internet
- App processes payment card data
- App sends communications to customers (email, SMS, push)
- App modifies customer-facing data (prices, inventory counts, order status)

**Examples:** Social proof widget on marketing site (public-facing), any app that sends emails to members

---

## Classification Decision Tree

```
Is the app accessible from the public internet?
  YES → Tier 4 (engineering ownership)
  NO ↓

Does the app handle PII or financial data?
  YES → Tier 3 (full security review)
  NO ↓

Does the app require user authentication beyond network access?
  YES → Tier 2 (light review)
  NO ↓

Tier 1 (self-serve)
```

---

## Escalation

If a non-engineer app is found running without appropriate tier review:
1. App is not immediately shut down (avoid disrupting business operations)
2. Platform team contacts the app builder within 24 hours
3. Retroactive review scheduled within 1 week
4. If Tier 3+ and not in compliance, app access restricted to builder only until review completes

**Current known compliance gaps:** See platform_capabilities.md for two existing apps that predate this framework.
