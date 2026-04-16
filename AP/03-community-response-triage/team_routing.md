# Thrive Market Community Response — Team Routing

## Routing Teams

### CS Team (Customer Service)
**Slack channel:** #cs-escalations
**Lead:** Maria Chen
**SLA:** 4 hours for High, 24 hours for Standard

**Handles:**
- Order issues (missing items, wrong items, damaged products)
- Shipping delays and tracking problems
- General membership questions (how-to, account management)
- Product availability inquiries
- Return and refund requests
- Replacement orders

**Escalation path:** If unresolved after 2 attempts → CS Team Lead (Maria Chen directly)

---

### CS Team + Billing Specialist
**Slack channel:** #billing-escalations
**Lead:** James Park
**SLA:** 4 hours

**Handles:**
- Double charges and unauthorized billing
- Membership cancellation issues
- Refund processing delays
- Auto-renewal disputes
- Promotional credit problems (referral credits, gift cards)
- Payment method issues

**Escalation path:** If potential chargeback or >$100 disputed → Finance Team

---

### PR Team
**Slack channel:** #pr-alerts
**Lead:** Sophie Martinez
**SLA:** 1 hour for media mentions, 4 hours for negative press references

**Handles:**
- Journalist inquiries or mentions
- Negative press/article references in comments
- Viral negative content (>1000 engagements on a negative comment/post)
- Requests for company statements
- Crisis communication triggers
- Employee/workplace allegations

**Escalation path:** If national media or potential viral moment → VP Communications + CMO

---

### Marketing Team
**Slack channel:** #social-marketing
**Lead:** Devon Park
**SLA:** 24 hours

**Handles:**
- Positive UGC repost opportunities (high-quality member content)
- Influencer/creator mentions (both positive and negative)
- Brand sentiment monitoring
- Competitor comparison comments (factual responses only)
- Community engagement opportunities
- Trend identification and reporting

**Escalation path:** Negative influencer (>50K followers) experience → CMO office

---

### Product Team
**Slack channel:** #product-feedback
**Lead:** Aisha Williams
**SLA:** 48 hours (logged, not necessarily responded to publicly)

**Handles:**
- App bugs and crashes
- Website functionality issues
- Feature requests
- Inventory/stock availability system issues
- Search and filtering problems
- Checkout flow issues

**Escalation path:** Widespread outage or >5 reports of same bug in 24 hours → Engineering Lead

---

### Legal Team
**Slack channel:** #legal-urgent (private channel)
**Lead:** Thomas Reed
**SLA:** 1 hour

**Handles:**
- Health/safety claims (allergic reactions, illness, contamination)
- Regulatory mentions (FDA, FTC, state AG)
- Lawsuit threats or legal action mentions
- Misleading advertising claims that could have legal exposure
- Data privacy complaints
- Intellectual property issues

**Escalation path:** Any active medical emergency → Legal + CEO office simultaneously

---

### Quality Assurance Team
**Slack channel:** #qa-alerts
**Lead:** Rachel Kim
**SLA:** 2 hours

**Handles:**
- Expired product reports
- Allergen mislabeling reports
- Product contamination concerns
- Packaging integrity issues (items not sealed, leaking)
- Product recall coordination

**Escalation path:** Any allergen mislabeling → Legal Team simultaneously. Any pattern (3+ reports on same SKU) → VP Operations

---

## Routing Decision Tree

```
Is it about food safety or allergens?
├── YES → Legal + QA Team (CRITICAL — 1 hour SLA)
└── NO ↓

Is it about billing, charges, or cancellation?
├── YES → CS Team + Billing Specialist (HIGH — 4 hour SLA)
└── NO ↓

Does it mention media, press, or journalists?
├── YES → PR Team (HIGH — 1 hour SLA)
└── NO ↓

Is it about a product defect, expiration, or contamination?
├── YES → QA Team + CS Team (HIGH — 2 hour SLA)
└── NO ↓

Is it an app bug or website issue?
├── YES → Product Team (STANDARD — 48 hour SLA)
└── NO ↓

Is it a shipping or order fulfillment issue?
├── YES → CS Team (STANDARD — 24 hour SLA)
└── NO ↓

Is it positive UGC or influencer content?
├── YES → Marketing Team (STANDARD — 24 hour SLA)
└── NO ↓

Is it a general question or neutral comparison?
├── YES → CS Team (LOW — 48 hour SLA)
└── NO ↓

Is it trolling or bad-faith engagement?
└── YES → Monitor only. Do not respond unless factual correction needed.
```

## Cross-Routing Rules

Some comments require multiple teams. When routing to multiple teams:
1. **Primary team** owns the public response
2. **Secondary team(s)** receive an internal notification with context
3. The public response should NEVER reference internal team routing ("I'm sending this to our QA team" — just say "I'm looking into this")

### Common Cross-Routes
| Scenario | Primary | Secondary |
|---|---|---|
| Expired product + customer wants refund | CS Team | QA Team |
| Allergen issue + legal threat | Legal | QA + CS |
| Negative influencer experience | Marketing | CS Team |
| Billing issue mentioned in press | PR Team | Billing |
| App bug causing failed orders | Product | CS Team |
| Viral positive UGC | Marketing | PR (awareness) |
