# Standard FBP Analytical Frameworks

These are the analytical frameworks our Finance Business Partners use regularly. Any analysis Claude produces should follow these standards for consistency.

---

## Framework 1: Cohort Retention Curves

**Purpose:** Track how member cohorts retain over time to identify trends, diagnose churn, and forecast future revenue.

**Standard methodology:**
- Define cohort by signup month (e.g., "Apr 2025 cohort" = all members who signed up in April 2025)
- Month 0 = signup month (always 100%)
- Retention = % of cohort members who placed at least 1 order in Month N
- Display as a cohort triangle with months across the top and cohort vintage down the side
- Color-code: Green (>70%), Yellow (50-70%), Red (<50%)

**Key metrics to calculate:**
- M1 retention (first-month drop-off — strongest predictor of long-term retention)
- M3 retention (early stabilization signal)
- M6 retention (medium-term health)
- M12 retention (annual retention proxy)
- Cohort "half-life" — the month at which 50% of the cohort has churned

**Benchmarks (Thrive internal):**
- Target M1 retention: 75%
- Target M6 retention: 55%
- Target M12 retention: 45%
- Auto-ship members typically retain 15-20 percentage points higher at every interval

---

## Framework 2: LTV by Acquisition Channel

**Purpose:** Determine which acquisition channels produce the highest-value members to optimize marketing spend allocation.

**Standard methodology:**
- LTV = Cumulative revenue per member through Month N (typically 6-month and 12-month windows)
- Calculate by acquisition channel: Organic, Paid Social, Referral, Influencer, SEM, Email
- Include both membership fee revenue (allocated monthly) and merchandise revenue
- Use actual observed data for months available; project remaining months using the cohort's retention curve

**Key metrics to calculate:**
- 6-month observed LTV by channel
- 12-month projected LTV by channel (use retention curve to extrapolate)
- Blended CAC by channel
- LTV/CAC ratio by channel
- Payback period by channel (month at which cumulative revenue exceeds CAC)

**Benchmarks (Thrive internal):**
- Target overall LTV/CAC: >8.0x at 12 months
- Target payback period: <4 months
- Channels below 5.0x LTV/CAC should be flagged for review
- Organic and Referral typically have $0 or near-$0 CAC (attribute to brand spend separately)

---

## Framework 3: Category Penetration by Cohort Vintage

**Purpose:** Understand how product category purchasing evolves over a member's lifecycle and whether newer cohorts behave differently from older ones.

**Standard methodology:**
- Category penetration = % of a cohort's orders that include at least one item from category X
- Group cohorts into vintage buckets: Recent (last 3 months), Mid (4-8 months ago), Mature (9+ months ago)
- Compare penetration rates across categories: Pantry, Snacks, Vitamins & Supplements, Beauty & Personal Care, Fresh, Beverages, Household
- Analyze both cross-sectional (snapshot) and longitudinal (how a single cohort's mix changes over time)

**Key metrics to calculate:**
- Category penetration rate by cohort vintage
- Average basket composition (% of revenue from each category)
- Category adoption velocity — how quickly new cohorts try each category
- "Fresh uplift" — how Fresh category adoption affects other category purchasing
- Cross-sell intensity — average number of distinct categories per order, by cohort age

**Benchmarks (Thrive internal):**
- Target: Members purchasing from 3+ categories by Month 3
- Fresh members should show 15%+ higher penetration in Pantry and Snacks (basket building)
- Vitamins & Supplements is typically the last category adopted (high consideration purchase)
- Household category is seasonally driven — normalize for Q4 holiday spikes

---

## Framework 4: Seasonal Decomposition

**Purpose:** Separate trend from seasonality to understand true underlying growth.

**Standard methodology:**
- Use 12-month trailing data minimum
- Decompose into: Trend (long-term direction), Seasonal (recurring monthly patterns), Residual (unexplained variance)
- Apply to: Revenue, Order Volume, AOV, Member Signups, Retention
- Use multiplicative decomposition for revenue (seasonal effects are proportional to level)
- Use additive decomposition for retention rates (seasonal effects are absolute)

**Key seasonal patterns at Thrive:**
- January: Highest signup month (New Year's resolutions) — typically 130% of average
- June-July: Summer slump in order frequency — typically 85% of average
- November: Holiday spike + Black Friday — typically 145% of average
- December: Gift memberships inflate new member numbers but these cohorts have lower retention

---

## Visualization Standards

All charts and visualizations should follow these conventions:

- **Color palette:** Use a blue-green gradient for sequential data; use distinct colors for categorical comparisons
- **Labels:** Every axis must be labeled. Include units (%, $, #). Title every chart.
- **Annotations:** Call out key insights directly on the chart where possible
- **Benchmarks:** Show target/benchmark lines as dashed horizontal lines
- **Time series:** Always show at least 6 months of history for context
- **Tables:** Include both absolute numbers and percentages. Right-align numbers. Use commas for thousands.
