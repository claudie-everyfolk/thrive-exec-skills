# Merchandising Brief Generator

## Context Frame

I'm April Lane, Chief Merchant at Thrive Market. We run promotional sales that merchandise 50-300 brands into themed daily experiences for our members -- each day gets a homepage takeover, a dedicated email, and curated product collections. Planning these campaigns is one of the most time-intensive parts of my team's work: we balance category diversity, margin targets, member preferences, trending dietary movements, and new brand discovery across a multi-day calendar.

We recently piloted AI-assisted brief generation for our June campaign and saw promising results. Now I want to push further with a complete 5-day sale brief generated from our brand data, campaign parameters, and historical performance.

## The Ask

Using the attached files -- `sale_brands.csv` (80 participating brands), `sale_parameters.md` (campaign brief and merchandising principles), and `past_sale_performance.csv` (data from a prior similar sale) -- please:

1. **Build a 5-day theme calendar** with a distinct daily theme, a one-line rationale for why that theme works on that day of the sale, and which dietary/lifestyle trends it taps into. Day 1 should lead with value and new brands. The arc across 5 days should tell a story.

2. **Assign brands to each day** in three tiers: Hero Brands (3-5 per day, highest visibility), Supporting Brands (8-12 per day, strong catalog fill), and Discovery Picks (2-3 per day, new-to-Thrive brands members haven't seen). Every brand in the CSV should be assigned to exactly one day.

3. **Write a creative brief outline for each day** that includes: a headline angle (what the email subject line leans into), 3-5 key products to photograph for hero imagery, the member benefit to emphasize (savings, discovery, health outcome), and a tone/voice note for the copywriting team.

4. **Add performance predictions** for each day based on the past sale data: expected relative revenue (index to daily average), which categories will over/underperform based on historical click rates, and any risks to flag (e.g., a day that's too niche or too broad).

5. **Produce a brand placement summary** -- a single table with every brand, its assigned day, its tier, and a one-line rationale for the placement.

6. **Flag any gaps or imbalances** -- categories that are over- or under-represented on any given day, margin mix concerns, or days that might underperform based on historical patterns.

## Why This Matters

Our merchandising team spends 15-20 hours assembling a sale brief like this -- pulling from multiple spreadsheets, debating brand placement, checking category balance, and writing creative direction. If Claude Code can produce a strong first draft in 30 minutes, we can shift that time toward creative refinement and member experience testing.

## Iteration Hooks

- Ask Claude to swap two days' themes and see how brand assignments ripple
- Request a "GLP-1 friendly" overlay that tags which products on each day align with GLP-1 medication dietary guidance
- Ask for an alternative Day 1 strategy that leads with premium/aspirational instead of value
- Request the creative brief in a format your copywriting team can directly use (specific headline options, Instagram caption drafts)

## Stretch Goals

- Have Claude generate mock email subject lines (3 options per day) with predicted open-rate ranking based on the past sale data patterns
- Ask Claude to identify the 10 brands most at risk of underperforming and suggest promotional tactics (deeper discount, bundle, influencer callout)
- Request a member segment analysis -- which days appeal most to keto members vs. vegan members vs. families
