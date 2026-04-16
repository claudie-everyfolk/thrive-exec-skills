# Creative Fatigue Detector & Brief Generator

## Context Frame

I'm the CMO at Thrive Market, a membership-based online grocery for organic and natural products. My creative team currently tests 10-15 ad variants per week on Meta, but we need to scale to 100+ differentiated variants per month to stay competitive. We've built a creative diversity matrix that maps message framing, visual treatments, and audience angles — but we're drowning in manual performance monitoring. By the time we catch fatigue, we've already wasted spend.

I'm giving you three files:
- **ad_performance.csv** — 30 ad creatives tracked over 14 days with daily performance metrics
- **creative_taxonomy.md** — our creative diversity matrix (message frames, visual treatments, audience angles)
- **brand_guidelines.md** — Thrive's brand voice, visual standards, and hard don'ts

## The Ask

1. **Fatigue analysis:** Flag every ad where CTR has declined >20% from its peak, OR frequency has exceeded 3.5, OR CPA has increased >25% from its best day. For each flagged ad, show the trajectory (peak vs. current) and days since peak performance.

2. **Fatigue heatmap:** Build a matrix showing fatigue rates by creative type (static/video/UGC/carousel) crossed with persona target. Which combinations are burning out fastest? Which are most durable?

3. **5 replacement creative briefs:** For each fatigued slot, generate a new creative brief that uses a DIFFERENT combination from the diversity matrix than the ad it replaces. Each brief should specify: message frame, visual treatment, audience angle, headline concept, body copy direction, CTA, and suggested format. No two briefs should share the same message frame.

4. **Predicted performance notes:** For each replacement brief, explain WHY you chose that specific matrix combination — what signal from the data suggests this angle has headroom.

5. **Rotation schedule:** Recommend a 4-week creative rotation calendar that staggers new creatives to avoid simultaneous fatigue across the portfolio. Include recommended kill criteria for each new creative.

## Why This Matters

We spend $2M+/month on Meta. Every day a fatigued creative runs is wasted budget. But the bigger cost is creative team time — if we can auto-detect fatigue and generate on-brand replacement briefs, we free up 15-20 hours/week of creative strategy time and can actually hit the 100+ variant target.

## Iteration Hooks

- Swap in our actual Meta Ads Manager export and re-run the fatigue analysis
- Generate briefs specifically for a single audience segment (e.g., GLP-1 community)
- Build a Notion or Sheets template for the rotation calendar that the media buying team can maintain
- Add a "creative diversity score" that measures how well our active portfolio covers the taxonomy matrix

## Stretch Goals

- Build a monitoring script that flags fatigue daily from a CSV export
- Create a creative brief template that feeds directly into our design tool workflow
- Model the expected spend savings from catching fatigue 2 days earlier across the portfolio
