# Top 10 Member Contact Scenarios — Thrive Market

## 1. Missing Item from Order

**Frequency:** ~18% of contacts
**Channel:** Primarily chat, some email
**Expected resolution steps:**
1. Verify member identity and pull up order in Magento (order number or email lookup)
2. Confirm which item(s) are missing by reviewing order line items with the member
3. Check fulfillment status in Magento — was the item picked and packed?
4. If item was packed but missing on arrival: issue refund or reship (member's choice)
5. If item was out of stock at fulfillment: issue refund + $5 credit for inconvenience
6. If order value of missing item is under $15: instant refund, no further investigation needed
7. If order value of missing item is $15+: create a fulfillment investigation ticket (Tag: MISSING-ITEM-INVESTIGATE)
8. Confirm resolution with member, offer anything else

**Tools used:** Magento order lookup, Zendesk ticket creation, refund processing
**Avg handle time:** 6 min (chat), 4 min (email)

---

## 2. Membership Auto-Renewal Refund Request

**Frequency:** ~12% of contacts
**Channel:** Chat and phone (rarely email — members want this resolved immediately)
**Expected resolution steps:**
1. Verify member identity
2. Pull up membership details in Magento: type (monthly/annual), renewal date, last charge date
3. Confirm the charge the member is disputing
4. Check if within refund eligibility window (see resolution_policies.md)
5. If eligible: process refund and confirm membership status (cancelled or downgraded per member preference)
6. If NOT eligible: explain policy, offer save incentive (see save offers in resolution_policies.md)
7. If member insists on refund outside window: escalate to L2 with notes
8. Never promise a refund you can't confirm in the system

**Tools used:** Magento membership management, payment processor, Zendesk
**Avg handle time:** 9 min (chat), 7 min (phone)

---

## 3. Product Quality Complaint (Spoiled/Damaged)

**Frequency:** ~10% of contacts
**Channel:** Email (often with photos), chat
**Expected resolution steps:**
1. Verify member identity and order
2. Ask for details: which product, what's wrong, do they have photos
3. If photos provided: review and document in ticket
4. Check product against known quality alerts (internal list updated weekly)
5. For perishable items: no return needed — issue refund or replacement
6. For non-perishable damaged items: offer refund or replacement; return only if item value >$30
7. If this is the member's 3rd+ quality complaint in 90 days: flag for QA review (potential fraud pattern)
8. Log product SKU in quality tracker for category team review

**Tools used:** Magento, quality tracker spreadsheet, Zendesk
**Avg handle time:** 8 min (chat), 5 min (email)

---

## 4. Promo Code Not Applying

**Frequency:** ~9% of contacts
**Channel:** Chat (real-time during checkout)
**Expected resolution steps:**
1. Verify member identity
2. Ask which promo code and where they received it
3. Look up promo code in the promo management system: is it active? What are the terms?
4. Check if member's cart meets code requirements (minimum order, eligible categories, first-order-only, etc.)
5. If code should work but doesn't: manually apply discount as a price adjustment in Magento
6. If code is expired or member doesn't qualify: explain clearly, offer alternative active promo if available
7. If it's a system bug (code valid, cart qualifies, still fails): escalate to Engineering via Zendesk (Tag: PROMO-BUG) and manually apply discount
8. Confirm adjusted total with member before they place order

**Tools used:** Promo management system, Magento price adjustment, Zendesk
**Avg handle time:** 7 min

---

## 5. Address Change After Order Placed

**Frequency:** ~6% of contacts
**Channel:** Chat and phone (time-sensitive)
**Expected resolution steps:**
1. Verify member identity and order
2. Check order status in Magento: is it still in processing or already shipped?
3. If still processing (status: "Processing" or "Pending"): update address in Magento and confirm with member
4. If already shipped: cannot change address. Options:
   a. If carrier supports redirect (FedEx, UPS): initiate redirect request (member pays $5 redirect fee)
   b. If carrier doesn't support redirect: advise member to watch tracking and contact carrier directly
   c. If order is high value ($75+): escalate to L2 for manual intervention
5. Update member's default address in their profile if they request it
6. Confirm next steps with member

**Tools used:** Magento order management, carrier tracking portals
**Avg handle time:** 5 min (if still processing), 10 min (if shipped)

---

## 6. Subscription Skip/Pause Request

**Frequency:** ~7% of contacts
**Channel:** Chat (most common), some email
**Expected resolution steps:**
1. Verify member identity
2. Pull up subscription details in Magento: which subscription, next delivery date, frequency
3. Confirm what the member wants: skip next delivery, pause for X weeks, or cancel subscription entirely
4. If skip: skip next delivery in system, confirm new next-delivery date
5. If pause: set pause duration (max 8 weeks), confirm resume date
6. If cancel subscription (not membership): process cancellation, confirm no further charges for that subscription
7. Distinguish between product subscription and membership — members often confuse these
8. If member seems like they might churn: offer a one-time discount on next subscription order (10% off)

**Tools used:** Magento subscription management, Zendesk
**Avg handle time:** 5 min

---

## 7. Duplicate Charge on Credit Card

**Frequency:** ~4% of contacts
**Channel:** Phone and chat (members are usually upset)
**Expected resolution steps:**
1. Verify member identity
2. Ask for details: approximate charge amount, date, last 4 of card
3. Pull up order history in Magento and payment processor — look for duplicate transactions
4. If duplicate found: process refund for the duplicate charge immediately
5. If no duplicate in our system: check if it's a pending authorization (common with card updates or failed transactions) — these drop off in 3-5 business days
6. If member's bank shows two posted charges and we only show one: escalate to Finance team (Tag: DUPLICATE-CHARGE-FINANCE)
7. Never tell the member to "just dispute it with your bank" — we handle it
8. Provide reference number for the refund or investigation

**Tools used:** Magento, payment processor dashboard, Zendesk
**Avg handle time:** 10 min

---

## 8. Delivery Exception — Package Marked Delivered but Not Received

**Frequency:** ~5% of contacts
**Channel:** Chat and phone
**Expected resolution steps:**
1. Verify member identity and order
2. Pull tracking details — confirm carrier and delivery timestamp
3. Ask member to check: mailroom, front desk, neighbors, alternative delivery locations
4. If delivery was today: ask member to wait 24 hours (packages sometimes marked delivered early by carrier)
5. If delivery was 24+ hours ago and still not found:
   a. Order value under $50: issue full refund or reship, no investigation needed
   b. Order value $50-$100: issue refund/reship + file carrier claim
   c. Order value $100+: escalate to L2 for investigation before refund
6. If member has 3+ "not received" claims in 6 months: flag for fraud review (do NOT tell the member this)
7. Document everything in the ticket with tracking screenshots

**Tools used:** Carrier tracking portals, Magento, Zendesk
**Avg handle time:** 8 min

---

## 9. Allergen Concern About a Product

**Frequency:** ~3% of contacts
**Channel:** Email and chat
**Expected resolution steps:**
1. Verify member identity
2. Identify the specific product and the allergen concern
3. Pull up product details in catalog — check listed ingredients and allergen warnings
4. If allergen is clearly listed: confirm with member, explain where to find allergen info on product pages
5. If allergen info is unclear or missing: DO NOT make claims about allergen content. Tell member: "I want to make sure you get accurate information. Let me escalate this to our product team for verification."
6. Escalate to Product team (Tag: ALLERGEN-VERIFY) with product SKU, member's specific concern
7. Set expectation: product team responds within 24 hours
8. NEVER say "it should be fine" or "it probably doesn't contain [allergen]" — liability issue

**Tools used:** Product catalog, Zendesk escalation, product team queue
**Avg handle time:** 6 min

---

## 10. Request to Cancel Membership with Save Attempt

**Frequency:** ~8% of contacts
**Channel:** Phone (most common), chat
**Expected resolution steps:**
1. Verify member identity
2. Ask why they want to cancel — listen genuinely, don't jump to the save script
3. Pull up membership details: type, tenure, total spend, last order date
4. Based on cancellation reason, offer appropriate save incentive (see resolution_policies.md):
   - Price concern → offer discounted rate
   - Not ordering enough → offer free shipping for 3 months
   - Product selection → offer category suggestions based on their purchase history
   - Bad experience → apologize specifically, offer credit
5. If member accepts save offer: process the offer, confirm in writing
6. If member declines and insists on cancellation: process immediately. Do not push more than once.
7. Confirm: membership ends on [date], any remaining subscription orders will be cancelled, refund eligibility per policy
8. Send cancellation confirmation email
9. Tag ticket with cancellation reason for reporting

**Tools used:** Magento membership management, Zendesk, email system
**Avg handle time:** 12 min (phone), 9 min (chat)
