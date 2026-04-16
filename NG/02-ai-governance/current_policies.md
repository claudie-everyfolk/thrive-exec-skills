# Thrive Market — Current AI Policies & Governance (As-Is State)

*Compiled April 2026. This document captures what actually exists today — not aspirations.*

---

## What We Have

### 1. Gemini Acceptable Use Policy
- Issued: November 2025
- Scope: Google Gemini usage across the company
- Key provisions:
  - Do not paste customer PII into Gemini consumer interface
  - Do not use Gemini for final versions of customer-facing content
  - Gemini outputs are "drafts" and require human review
- Enforcement: Honor system. No monitoring or audit.
- Gap: Policy predates Claude Enterprise rollout. Does not address Claude, Sierra, or any other AI tool.

### 2. Claude Enterprise License Agreement
- Signed: September 2025 (50 Engineering seats), expanded January 2026 (100+ seats across functions)
- Data handling: Enterprise tier — Anthropic does not train on our data, conversations not stored beyond 90-day retention
- Key terms: SOC 2 Type II compliant, data encrypted at rest and in transit
- Gap: The license agreement is a vendor contract, not an internal usage policy. It says what Anthropic will do with our data, not what our employees should do with Claude.

### 3. SOX Controls (Financial Processes)
- Existing requirement: All financial reporting processes require documented human review chain
- AI implication: Any AI-assisted financial process must have a human reviewer who signs off on the output
- Current interpretation: Legal has informally advised Finance that AI cannot be the "preparer" or "reviewer" in any SOX-controlled workflow — it can only assist a human who takes ownership
- Gap: "Assist" is undefined. Can AI prepare a reconciliation if a human reviews it? Can AI flag exceptions if a human validates? No formal guidance exists.

### 4. CCPA/Privacy Requirements
- Existing requirement: Member data subject to CCPA. Members can request deletion. Data use must align with stated privacy policy.
- AI implication: Member data used to train or fine-tune AI models would violate privacy commitments. Passing member data to third-party AI APIs may constitute a "sale" under CCPA.
- Current interpretation: Sierra processes member data under a BAA-equivalent agreement. Claude Enterprise has enterprise data handling. But ad-hoc use of member data in free/consumer AI tools is a violation.
- Gap: No monitoring for whether employees paste member data into unauthorized tools.

### 5. General Employee Handbook
- Section on "Technology Use": Generic — covers appropriate use of company systems, no AI-specific language
- Last updated: 2024
- Gap: Predates AI adoption entirely.

---

## What We Don't Have

1. **No AI governance committee** — No cross-functional body owns AI policy, risk, or investment decisions.

2. **No AI output review policy** — No formal tiering of which AI outputs require human review and at what level. Current review is ad-hoc and function-dependent.

3. **No AI tool approval process** — No centralized vetting or procurement for AI tools. Functions buy and adopt independently. Marketing has 17 AI tools; no one reviewed them collectively.

4. **No AI disclosure/attribution policy** — No requirement to disclose when work is AI-assisted. The Operations forecast incident showed this gap clearly.

5. **No AI spend governance** — No approval thresholds for AI tool purchases. No central budget. Claude Enterprise scaling from $50K to projected $360K with no formal approval.

6. **No AI incident reporting process** — The 15 incidents in our tracking sheet were captured informally. No standard process for reporting, categorizing, or learning from AI failures.

7. **No AI training requirements** — No onboarding or ongoing training for employees using AI tools. Each function handles its own (or doesn't).

8. **No AI vendor risk assessment** — Sierra handles 68% of member contacts. What's our fallback if Sierra has an outage? No vendor concentration risk assessment exists.

9. **No guidance on consumer vs. enterprise AI** — Employees use free Gemini alongside enterprise Claude with no understanding of the data handling differences.

10. **No AI ethics principles** — No stated company position on AI use in hiring (Covey), customer interactions (Sierra), or content creation (Marketing).
