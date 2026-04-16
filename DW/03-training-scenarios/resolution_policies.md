# Resolution Policies — Thrive Market Member Services

*Last updated: April 1, 2026*

---

## 1. Refund Policy

### General Refund Rules
- All refunds processed to original payment method
- Refund processing time: 3-5 business days after approval
- Members receive email confirmation when refund is initiated
- Maximum refund amount = original charge amount (no over-refunding)

### Refund by Issue Type

| Issue | Refund Threshold | Auto-Approve? | Notes |
|---|---|---|---|
| Missing item (under $15) | Full item value | Yes — L1 agent | No investigation needed |
| Missing item ($15-$50) | Full item value | Yes — L1 agent | Create investigation ticket |
| Missing item ($50+) | Full item value | No — L2 required | Must complete investigation first |
| Damaged/spoiled (perishable) | Full item value | Yes — L1 agent | No return required |
| Damaged (non-perishable, under $30) | Full item value | Yes — L1 agent | No return required |
| Damaged (non-perishable, $30+) | Full item value | Yes — L1 agent | Return required for refund |
| Wrong item received | Full item value | Yes — L1 agent | Reship correct item + keep wrong item if under $20 |
| Duplicate charge | Duplicate amount | Yes — L1 agent | Process immediately |
| Membership (within window) | Full membership fee | Yes — L1 agent | See membership refund window below |
| Membership (outside window) | N/A | No — L2 required | Save attempt first |

### Fraud Flags (Internal — Never Communicate to Member)
- 3+ missing item claims in 90 days → flag for review
- 3+ "not received" claims in 6 months → flag for review
- Refund total exceeding 40% of total spend in last 6 months → flag for review
- Flagged accounts: process normally but add internal tag `FRAUD-REVIEW` to ticket

---

## 2. Membership Cancellation Policy

### Membership Types
- **Monthly**: $12/month, billed on enrollment date each month
- **Annual**: $60/year, billed on enrollment anniversary date
- **Gift membership**: Prepaid, no auto-renewal

### Refund Eligibility Window
- **Monthly**: Full refund if cancelled within 48 hours of charge. No refund after 48 hours.
- **Annual**: Full refund if cancelled within 14 days of charge. Pro-rated refund (unused months) if cancelled within 30 days. No refund after 30 days.
- **Gift**: Non-refundable. Can be transferred to another email.

### Save Offers (Use ONE per interaction — do not stack)

| Cancellation Reason | Save Offer | Approval Level |
|---|---|---|
| Too expensive | 50% off next month (monthly) or $20 credit (annual) | L1 auto-approve |
| Not ordering enough | Free shipping for next 3 orders | L1 auto-approve |
| Product selection poor | $15 credit to try new categories + personalized recs | L1 auto-approve |
| Bad experience (specific incident) | $25 credit + apology | L1 auto-approve |
| Bad experience (multiple incidents) | $50 credit + apology + L2 follow-up | L2 required |
| Moving/lifestyle change | Pause membership up to 3 months | L1 auto-approve |
| Just want to cancel (no reason) | $10 credit | L1 auto-approve |

### Cancellation Process
1. Process cancellation in Magento → Membership Management → Cancel
2. System sends automated cancellation confirmation email
3. Membership remains active until end of current billing period
4. All active product subscriptions are cancelled automatically
5. Member retains access to order history and can re-enroll anytime
6. Tag ticket with specific cancellation reason code

---

## 3. Shipping Policies

### Standard Shipping
- Free on orders $49+ (for members)
- $5.95 flat rate on orders under $49
- Estimated delivery: 3-7 business days
- Carrier: FedEx (East Coast), ColdPack Logistics (West Coast frozen), FreshShip (regional)

### Perishable/Frozen Shipping
- Ships Monday-Wednesday only (to avoid weekend transit)
- Insulated packaging with dry ice or gel packs
- If perishable arrives compromised: full refund, no return required
- Frozen items arriving thawed: full refund + $5 credit for inconvenience

### Address Changes
- Before shipment ("Processing" status): Free address change in Magento
- After shipment: $5 redirect fee (FedEx/UPS only). USPS does not support redirect.
- P.O. Boxes: Not supported for frozen/perishable orders

### Lost/Not Received Packages
- Under $50: Instant refund or reship (L1 agent discretion)
- $50-$100: Refund/reship + carrier claim filed
- $100+: L2 investigation required (5 business day SLA)

---

## 4. Product Return Policy

### Non-Perishable Items
- 30-day return window from delivery date
- Item must be unopened and in original packaging
- Member initiates return via website or agent
- Prepaid return label generated automatically
- Refund processed within 3 business days of receiving return

### Perishable Items
- No return required — refund or replacement only
- Photo evidence required for quality complaints (agent requests photo via chat/email)
- If no photo available: approve refund for first occurrence; require photo for subsequent claims

### Exceptions
- Clearance items: Final sale, no returns
- Personal care items (opened): No returns for hygiene reasons
- Supplements: Returnable within 30 days even if opened (regulatory requirement)

---

## 5. Escalation Triggers

### Immediate Escalation to L2
- Member threatens legal action
- Member mentions filing a chargeback
- Allergen safety concern
- Order value $100+ with missing/damaged claim
- Member has 3+ contacts about the same issue
- Agent cannot resolve within 15 minutes

### Escalation to Team Lead
- Member requests a supervisor/manager
- Agent is unsure about policy applicability
- Novel situation not covered by existing policy

### Escalation to Finance
- Duplicate charges not matching system records
- Refund amount exceeds $200
- Chargeback dispute received

---

## 6. Sierra AI Handoff Protocol

### When Sierra Transfers to Human Agent
- Sierra transfers when confidence score drops below 70%
- Sierra transfers when member explicitly requests a human
- Sierra transfers on any billing/payment issue over $50
- Sierra transfers on all cancellation requests (save attempt requires human)

### Agent Receiving Sierra Handoff
1. Read the Sierra conversation summary (auto-populated in Zendesk ticket)
2. Do NOT ask the member to repeat information Sierra already collected
3. Acknowledge the context: "I see you've been chatting about [issue]. Let me pick up right where Sierra left off."
4. If Sierra provided incorrect information: correct it gently without blaming Sierra ("Let me clarify that for you — here's the accurate information...")
5. Tag ticket with `SIERRA-HANDOFF` for reporting

---

## 7. Credit and Goodwill Policy

### Agent-Approved Credits (No L2 Needed)
- Up to $15 credit for service recovery (any reason)
- Up to $25 credit for documented service failure
- Free shipping on next order (one-time)
- 10% off next subscription order

### L2-Required Credits
- $25-$50 credit
- Free month of membership
- Any credit for a flagged account

### Credits NOT Allowed
- Cash refund to a different payment method
- Credits exceeding total order value
- Credits to accounts with active fraud flags (without fraud team clearance)

### Monthly Credit Cap
- No member should receive more than $75 in total credits in a rolling 30-day period
- If a member is approaching the cap, route to L2 for review
