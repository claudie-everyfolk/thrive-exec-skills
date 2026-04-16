# QA Scoring Rubric — Thrive Market Member Services

*Version 3.2 | Last updated: March 2026*

---

## Scoring Overview

Each member interaction is scored on 5 categories. Total possible score: 100 points.

| Category | Weight | Max Points |
|---|---|---|
| Policy Accuracy | 30% | 30 |
| Resolution Completeness | 25% | 25 |
| Communication & Professionalism | 20% | 20 |
| Efficiency | 15% | 15 |
| Documentation | 10% | 10 |
| **Total** | **100%** | **100** |

---

## Category 1: Policy Accuracy (30 points)

*Did the agent follow the correct policy and apply it accurately?*

| Score | Criteria |
|---|---|
| 30 (Exceeds) | Correct policy applied flawlessly. Agent proactively addressed related policy implications the member didn't ask about (e.g., mentioning subscription cancellation when processing membership cancellation). |
| 24 (Meets) | Correct policy applied with no errors. All required steps followed. |
| 18 (Partial) | Correct policy identified but minor application error (e.g., offered wrong save amount, missed a step). |
| 12 (Below) | Wrong policy applied or significant error in application (e.g., approved refund outside eligibility window without escalation). |
| 0 (Critical) | Policy violation that creates business risk (e.g., made allergen safety claim, promised refund on flagged account, shared internal fraud indicators). |

**Key evaluation questions:**
- Did the agent identify the correct issue type?
- Was the right refund threshold applied?
- Were escalation triggers recognized?
- Was the save offer appropriate for the cancellation reason?

---

## Category 2: Resolution Completeness (25 points)

*Was the member's issue fully resolved? Were all necessary follow-up actions taken?*

| Score | Criteria |
|---|---|
| 25 (Exceeds) | Issue fully resolved AND agent anticipated a related need (e.g., updated default address while processing address change, offered to check other orders from same shipment). |
| 20 (Meets) | Issue fully resolved. All system actions completed. Confirmation provided to member. |
| 15 (Partial) | Issue mostly resolved but missing a step (e.g., refund processed but no confirmation email sent, or didn't offer reship option). |
| 10 (Below) | Issue not fully resolved. Member would need to contact again to complete resolution. |
| 0 (Critical) | Issue unresolved and no path to resolution provided. Member left worse off than before contact. |

**Key evaluation questions:**
- Is there anything the member would need to call back about?
- Were all system actions completed (refund, ticket creation, tags)?
- Did the agent confirm the resolution with the member?
- Were next steps clearly communicated?

---

## Category 3: Communication & Professionalism (20 points)

*How well did the agent communicate? Was the tone appropriate?*

| Score | Criteria |
|---|---|
| 20 (Exceeds) | Warm, empathetic, natural tone. Personalized the interaction (used member's name, referenced their specific situation). Made the member feel heard before jumping to resolution. |
| 16 (Meets) | Professional, clear, and friendly. Appropriate empathy. No robotic or scripted-sounding language. |
| 12 (Partial) | Generally professional but either too robotic/scripted OR too casual. Minor tone issues. |
| 8 (Below) | Communication unclear, confusing, or inappropriate tone (dismissive, overly casual, or argumentative). |
| 0 (Critical) | Rude, hostile, or made statements that could be interpreted as discriminatory. Shared information that shouldn't be shared with members. |

**Key evaluation questions:**
- Did the agent acknowledge the member's frustration before problem-solving?
- Was language clear and jargon-free?
- Did the agent avoid saying "unfortunately" more than once?
- Was the closing warm and inviting (not just "Is there anything else?")?

---

## Category 4: Efficiency (15 points)

*Did the agent resolve the issue in a timely manner without unnecessary steps?*

| Score | Criteria |
|---|---|
| 15 (Exceeds) | Resolved well under AHT target. No unnecessary questions or steps. Used available tools efficiently (didn't ask member for info already in the system). |
| 12 (Meets) | Resolved within AHT target. Reasonable workflow with no wasted steps. |
| 9 (Partial) | Slightly over AHT target OR had 1-2 unnecessary steps (e.g., asked for info already visible in the account). |
| 6 (Below) | Significantly over AHT target. Multiple unnecessary steps or long holds. |
| 0 (Critical) | Excessive handle time due to lack of knowledge or inability to use tools. Member expressed frustration about wait time. |

### AHT Targets by Contact Type

| Contact Type | Chat Target | Phone Target | Email Target |
|---|---|---|---|
| Missing item | 6 min | 5 min | 4 min |
| Membership/billing | 9 min | 7 min | 6 min |
| Product quality | 8 min | 6 min | 5 min |
| Promo code | 7 min | 6 min | 5 min |
| Address change | 5 min | 4 min | 4 min |
| Subscription management | 5 min | 4 min | 4 min |
| Duplicate charge | 10 min | 8 min | 7 min |
| Delivery exception | 8 min | 7 min | 6 min |
| Allergen concern | 6 min | 5 min | 5 min |
| Cancellation (with save) | 12 min | 10 min | 8 min |

---

## Category 5: Documentation (10 points)

*Did the agent properly document the interaction in Zendesk?*

| Score | Criteria |
|---|---|
| 10 (Exceeds) | Comprehensive ticket notes: issue summary, actions taken, outcome, relevant context for future reference. Correct tags applied. Would be completely clear to any agent who picks up this ticket later. |
| 8 (Meets) | Adequate documentation. Issue and resolution noted. Correct tags applied. |
| 6 (Partial) | Documentation exists but missing key details (e.g., no resolution noted, or wrong tags). |
| 4 (Below) | Minimal documentation. Another agent would struggle to understand what happened. |
| 0 (Critical) | No documentation. Ticket left blank or with only auto-populated fields. |

**Required ticket fields:**
- Issue type tag (e.g., MISSING-ITEM, MEMBERSHIP-CANCEL, PROMO-BUG)
- Resolution type (refund, reship, credit, escalation, information provided)
- Resolution amount (if monetary)
- Internal notes summarizing what happened and any follow-up needed
- Sierra handoff tag (if applicable)
- Fraud flag (if applicable — internal only)

---

## Overall Performance Thresholds

| Rating | Score Range | Implications |
|---|---|---|
| Exceptional | 90-100 | Eligible for mentor role, featured in team recognition |
| Meets Expectations | 75-89 | Standard performance, on track |
| Needs Improvement | 60-74 | Coaching plan initiated, additional QA reviews scheduled |
| Below Standard | Below 60 | Performance improvement plan, supervised queue only |

### First-Contact Resolution (FCR) Targets
- Overall FCR target: 82%
- Chat FCR target: 85%
- Phone FCR target: 80%
- Email FCR target: 75% (lower due to async nature)

### Monthly QA Cadence
- Each agent: minimum 5 interactions reviewed per month
- New agents (first 90 days): minimum 10 interactions reviewed per month
- Agents on coaching plans: minimum 8 interactions reviewed per month
