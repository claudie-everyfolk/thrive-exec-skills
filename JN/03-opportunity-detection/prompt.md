# Opportunity Detection & Signal Aggregator

## Context Frame

I'm a PM at Thrive Market, a membership-based online grocery focused on organic and natural products. I want to shift from reactive product management to proactive opportunity detection. I have three data sources:

- `@amplitude_product_metrics.csv` — 8 weeks of key product event data with weekly trends and anomalies
- `@nps_feedback.csv` — 50 recent NPS responses with verbatim comments, scores, and member context
- `@competitive_intel.md` — recent competitive moves from Amazon Fresh, Instacart, Imperfect Foods, and Misfits Market

## The Ask

Synthesize across all three data sources and produce:

1. **Top 5 Opportunity Brief** — ranked by estimated impact. For each opportunity:
   - Signal source(s) — which data file(s) and what specific evidence
   - Quantified evidence — numbers, not vibes
   - Estimated impact — revenue, conversion, retention, or engagement (with rough sizing)
   - Confidence level — High / Medium / Low, with reasoning
   - Recommended next step — a specific action, not "investigate further"

2. **Anomaly Report** — identify every significant anomaly in the product metrics data:
   - What changed and when
   - Hypothesized root cause (cross-reference with NPS feedback and competitive moves where possible)
   - Severity: is this a fire to fight or an opportunity to seize?
   - Recommended response with timeline

3. **Competitive Threat Assessment** — map each competitive move to our product roadmap:
   - Which of our planned initiatives does this affect?
   - Are we ahead, behind, or at parity?
   - What's the urgency? (Immediate response needed / Watch closely / Not a threat)
   - Specific recommendations for how to respond

4. **NPS Theme Analysis** — cluster the verbatim feedback into themes:
   - Theme name, number of mentions, average NPS score for that theme
   - Representative quotes
   - Product implications — what would we build or change?
   - Which themes correlate with detractors (0-6) vs. promoters (9-10)?

5. **Recommended Discovery Sprints** — for the top 3 opportunities, outline a 1-week discovery sprint:
   - Objective and key question to answer
   - Methods (user interviews, data analysis, prototype testing, etc.)
   - Who to involve (PM, design, engineering, data)
   - Expected output (decision document, prototype, experiment design, etc.)
   - Go/no-go criteria for moving to build

## Why This Matters

PMs currently spend 18% of their time on discovery and strategy — the target is 30%+. The bottleneck isn't willingness, it's the manual effort of pulling data from Amplitude, reading NPS comments, tracking competitor moves, and synthesizing it all into something actionable. If AI can do the aggregation and pattern-matching, PMs can focus on the judgment calls: which opportunities to pursue, how to frame them, and what to build.

## Iteration Hooks

After the initial analysis, try these:
- "The GLP-1 opportunity looks strong. Expand it into a full PRD outline with user stories."
- "Cross-reference the mobile performance issues in NPS with the Amplitude data — is there a specific flow that's broken?"
- "Our CEO is asking about the Instacart GLP-1 move. Write me a 3-paragraph competitive response memo."
- "Prioritize the top 5 opportunities using the RICE framework with our team's actual capacity (34 points/sprint, 6 engineers)."
- "Generate a weekly opportunity detection prompt I can run every Monday morning with fresh data exports."

## Stretch Goals

- Ask Claude to identify signals that DON'T appear in the data: "What opportunities might we be missing because we're not tracking the right events?"
- Generate a monitoring plan: "What Amplitude events and NPS questions should we add to catch these opportunities earlier next time?"
- Create an executive summary: "Summarize the top 3 findings in a format I can present in our weekly product leadership meeting — 5 minutes max"
