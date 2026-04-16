# Campaign Performance Narrative

## Context Frame

I'm the CMO at Thrive Market, a membership-based online grocery for organic and natural products. Every Monday morning I need to brief my leadership team — and often the CEO — on marketing performance. Our Member Engagement team already uses Cortex AI for weekly revenue narratives at the channel level, but I need the strategic layer on top: what happened, why it matters, what we do next.

I'm giving you three files:
- **weekly_channel_performance.csv** — 4 weeks of channel-level performance data (current week + 3 prior)
- **campaign_calendar.md** — what campaigns and tests ran this week
- **competitive_signals.md** — observed competitor moves and market context

## The Ask

1. **Executive performance brief:** Identify the top 3 performance drivers this week (what moved the needle and why) and the top 3 concerns with hypothesized root causes. Don't just describe what happened — explain WHY it likely happened by connecting data to campaigns and market context.

2. **Channel-by-channel analysis:** For each channel, show week-over-week trends and flag any anomalies (defined as >15% WoW change in any key metric). For each anomaly, hypothesize a cause based on the campaign calendar and competitive signals.

3. **Competitive context overlay:** Map our channel performance to competitor moves. Where are we winning despite competitive pressure? Where are competitors likely taking share? Which competitive moves require a response vs. which are noise?

4. **Recommended actions for coming week:** 5-7 specific, prioritized actions with expected impact. Each should tie to a finding from the analysis. Format: Action → Rationale → Expected Impact → Owner suggestion.

5. **CEO Slack summary:** One paragraph (max 100 words) that captures the week's story — suitable for dropping directly into the #leadership channel. No jargon, no hedge words, just the headline.

## Why This Matters

I spend 2-3 hours every Monday morning synthesizing this narrative manually from Looker, channel dashboards, and team Slack threads. If I can get 80% of this from a prompt and then refine, I reclaim Monday morning for strategy instead of reporting. The CEO summary alone is worth it — that message sets the tone for the entire leadership team's week.

## Iteration Hooks

- Swap in our actual Looker/GA4 export and re-run with real numbers
- Generate this as a formatted Slack post with channel-specific thread replies
- Add budget reallocation recommendations with specific dollar amounts
- Build a template that auto-generates this from a Google Sheets data dump every Monday

## Stretch Goals

- Create a "narrative memory" that tracks recurring themes week over week
- Build a competitive monitoring dashboard that feeds into this brief
- Generate the brief in both "CMO detail" and "CEO headline" versions automatically
- Add cohort-level analysis (new members vs. returning vs. lapsed)
