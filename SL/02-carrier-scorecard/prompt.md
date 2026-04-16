# Carrier Scorecard Builder

## Context Frame

I'm the COO at Thrive Market, an e-commerce grocery company with 3 fulfillment centers (Batesville IN, Reno NV, and a third location). We ship to members nationwide using a mix of carriers. Our transportation team currently spends hours each month manually compiling carrier performance data from multiple sources into one-pager reviews for QBRs. I want to automate this into a repeatable scorecard process.

## The Ask

Using the attached data files (`carrier_delivery_performance.csv`, `carrier_claims.csv`, `member_feedback.csv`, and `carrier_contracts.md`):

1. **One-page scorecard per carrier** — For each of our 8 carriers, build a structured scorecard showing: KPI summary with trend arrows (improving/declining/stable), SLA compliance vs. contract commitments, cost analysis (cost per package, total spend, cost trend), member satisfaction score derived from survey data, and claims summary (volume, resolution rate, average days to resolve).
2. **Network-level comparison table** — Rank all 8 carriers by a composite score that weights on-time delivery (35%), cost efficiency (25%), damage/claims rate (20%), and member satisfaction (20%). Show where each carrier stands relative to the network average.
3. **Exception flags** — Automatically flag any carrier breaching their contractual SLA thresholds. Show which specific SLAs are at risk and by how much.
4. **QBR talking points per carrier** — For each carrier, generate 3-5 bullet points a transportation manager could walk into a quarterly review with. Include specific data points, trends, and leverage points for negotiation.
5. **Recommended actions** — For each carrier, recommend one of: Renegotiate (performance warrants better terms), Increase Volume (strong performer, shift more packages), Reduce Allocation (underperforming, shift packages away), Put On Watch (trending poorly, needs monitoring), or Maintain (performing to expectation).

## Why This Matters

We spend $XX million annually on last-mile delivery. A 1% improvement in carrier mix optimization or a successful rate renegotiation on underperforming carriers saves real money. Right now the data exists but it takes a week of manual work to compile for QBRs. This should be ready in minutes.

## Iteration Hooks

- "Break out performance by FC origin — are carriers performing differently out of Batesville vs. Reno?"
- "Add a cost-per-package trend chart for each carrier over the 12 weeks"
- "Which carrier should we shift volume TO if we reduce allocation from the worst performer?"
- "Calculate the dollar impact if we moved 20% of our worst carrier's volume to our best carrier"

## Stretch Goals

- Build this as an HTML dashboard I could share with the transportation team
- Generate a draft email to our worst-performing carrier citing specific data points
- Create a carrier risk matrix (2x2: cost vs. quality) visualization
