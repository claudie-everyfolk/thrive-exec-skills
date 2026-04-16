# Thrive Market — Contract Risk Tolerance Framework

**Version:** 2.1
**Last Updated:** April 2026
**Owner:** Office of the General Counsel

---

## Risk Classification

Every contract clause that deviates from the playbook is classified into one of three risk levels:

### Green — Matches Playbook
The clause aligns with Thrive Market's standard position or is more favorable to Thrive. No action required beyond documentation.

### Yellow — Deviates but Negotiable
The clause deviates from the playbook but represents a commercially reasonable position that could be accepted with appropriate approval. Requires negotiation attempt first; acceptance requires approval per the escalation matrix below.

### Red — Must Escalate to GC
The clause represents a material risk to Thrive Market that cannot be accepted without General Counsel review. These are typically provisions that create uncapped liability, broad indemnification exposure, data rights concerns, or significant deviations from legal or regulatory requirements.

---

## Escalation Matrix by Contract Value

| Annual Contract Value | Yellow Items | Red Items |
|----------------------|-------------|-----------|
| **< $50,000** | Associate Counsel may approve | Senior Counsel approval required |
| **$50,000 – $250,000** | Senior Counsel approval required | GC approval required |
| **> $250,000** | GC approval required | GC + CFO approval required |

**Note:** Contract value includes all fees payable during the initial term (subscription + estimated professional services). For multi-year commitments, use total contract value, not annualized.

---

## Automatic Red Flags

The following provisions are automatically classified as **Red** regardless of contract value:

1. **Unlimited Customer liability** for any category of obligation
2. **Perpetual, irrevocable data license** to Customer Data beyond aggregated/anonymized use during the term
3. **No termination for convenience** for Customer
4. **Indemnification for regulatory actions** — Customer should never indemnify a vendor for regulatory investigations or penalties
5. **Unilateral vendor assignment** without Customer consent or termination right
6. **Non-US data processing** without explicit approval and appropriate safeguards
7. **Price escalation exceeding 6%** annually without cap
8. **Warranty disclaimers** that eliminate implied warranty of non-infringement
9. **IP ownership** — vendor claims ownership of custom work product built for Customer
10. **Data retention post-termination** exceeding 30 days without explicit agreement

---

## Scoring Methodology

For contract triage purposes, the overall risk score is determined by the highest-risk clause:

- If **any clause is Red** → Overall score is **Red**
- If **no Red clauses but any Yellow** → Overall score is **Yellow**
- If **all clauses are Green** → Overall score is **Green**

---

## Review SLA by Risk Level

| Overall Score | Initial Review | Redline Turnaround | Approval Turnaround |
|--------------|---------------|-------------------|---------------------|
| **Green** | 1 business day | N/A | Auto-approved at reviewer level |
| **Yellow** | 2 business days | 3 business days | Per escalation matrix |
| **Red** | 1 business day (priority) | 3 business days | Per escalation matrix + 2 business days for GC review |

---

## Documentation Requirements

All contract reviews must document:
1. Clause-by-clause risk classification
2. Escalation path taken (if applicable)
3. Approval chain with dates
4. Final disposition (approved as-is, approved with modifications, rejected)
5. Any exceptions granted and business justification

Reviews are stored in the Contract Management System (DocuSign IAM) and linked to the executed agreement.

---

## Special Considerations for Technology Vendors

SaaS and technology vendor agreements require additional scrutiny on:

- **Data processing locations** — Must be US-only or pre-approved jurisdictions
- **AI/ML training** — Vendor must not use Customer Data to train machine learning models without explicit opt-in
- **SOC 2 / security certifications** — Required for any vendor processing member PII
- **Subprocessor chain** — Must have meaningful objection rights, not just notice + termination
- **API and integration dependencies** — Assess business continuity risk if vendor discontinues APIs
- **Data portability** — Must be able to export all data in standard formats upon termination

---

## Revision History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 2.1 | Apr 2026 | Legal Ops | Added AI/ML training to automatic red flags |
| 2.0 | Jan 2026 | J. Kreinberg | Revised escalation matrix, added documentation requirements |
| 1.0 | Jun 2025 | J. Kreinberg | Initial framework |
