# Product Context: Current State

## Existing Dietary Filter Infrastructure

- **Search filters:** Members can filter search results by 8 dietary categories (Keto, Paleo, Vegan, Vegetarian, Gluten-Free, Dairy-Free, Organic, Non-GMO). These are faceted filters powered by Algolia.
- **Category page filters:** Same 8 dietary filters available on category pages, but usage is lower (12% of category page sessions vs. 40% of search sessions).
- **No personalization layer:** Filters are session-based and require manual selection each time. No dietary preferences are stored on the member profile.
- **Product tagging:** Current dietary tags are maintained by our merchandising team in the PIM. Coverage is approximately 70% of catalog for basic tags (Vegan, Gluten-Free), dropping to ~45% for specialized tags (Keto, Paleo, Whole30).

## Syndigo PIM Launch (April 20, 2026)

- Enriched product attributes including validated dietary and allergen tags
- Expected coverage: 85% of active SKUs with dietary classification
- New attributes: GLP-1 Friendly, Mediterranean, Low-Sugar, Whole30 (not currently in our taxonomy)
- Data format: standardized GDSN attributes, ingested nightly via API
- **Dependency:** Product data team estimates 2-week validation period post-launch before data is production-ready (target: May 4)

## Key Metrics (Current State)

| Metric | Value | Source |
|--------|-------|--------|
| First-order conversion (new members) | 32% | Amplitude, trailing 90 days |
| Browse-to-cart time (mobile) | 8.2 min | Amplitude, trailing 30 days |
| Browse-to-cart time (desktop) | 6.1 min | Amplitude, trailing 30 days |
| 90-day member retention | 71% | Amplitude cohort analysis |
| Members using dietary filters (1+ per session) | 40% | Amplitude, trailing 30 days |
| Average filters applied per search session | 1.7 | Amplitude, trailing 30 days |
| Search-to-cart conversion | 24% | Amplitude, trailing 30 days |
| Mobile traffic share | 65% | Amplitude, trailing 30 days |
| iOS vs. Android split | 58% / 42% | Amplitude, trailing 30 days |
| Active SKU count | 6,200 | PIM, as of March 2026 |
| Avg. products viewed before first add-to-cart | 14.3 (mobile), 11.1 (desktop) | Amplitude, trailing 30 days |

## Traffic & Engagement Patterns

- **Homepage:** 72% of sessions start here. Average time on homepage: 45 seconds. "Shop by Category" tiles are the #1 click target (38% of homepage clicks).
- **Search:** 61% of sessions include at least one search. Average 2.3 searches per session.
- **Category pages:** 44% of sessions include category page views. "Snacks & Sweets" and "Pantry Staples" are top 2 categories by traffic.
- **Email:** Weekly "New Arrivals" email has 34% open rate, 8% click rate. No personalization beyond first name.

## Technical Stack (Relevant)

- **Search:** Algolia (primary search and browse ranking)
- **Analytics:** Amplitude (product analytics), Snowflake (data warehouse), Domo (BI dashboards)
- **Email:** Braze (marketing automation and transactional email)
- **PIM:** Syndigo (product information management — launching enriched data April 20)
- **Experimentation:** Optimizely (A/B testing and feature flags)
- **Mobile:** React Native (shared codebase for iOS and Android)
- **Web:** Next.js

## Team & Capacity

- Product & Design team: 4 PMs, 6 designers
- Relevant engineering squad ("Discovery & Personalization"): 2 frontend, 2 backend, 1 mobile, 1 QA
- Current sprint velocity: ~34 story points per 2-week sprint
- Q2 is loaded: Syndigo PIM integration, checkout redesign, and this initiative are all in the roadmap
