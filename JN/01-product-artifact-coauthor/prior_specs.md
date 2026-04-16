# Prior Product Specs — Team Format Reference

---

## Spec 1: Smart Reorder Suggestions

**Author:** Priya Ramirez, PM — Discovery & Personalization
**Last Updated:** February 12, 2026
**Status:** In Development (Sprint 4 of 6)

### Problem Statement

Members reorder the same 15-20 products regularly but must navigate to order history, find items, and add them individually. This creates 3-4 minutes of friction per reorder session. Amplitude data shows 62% of orders contain at least 5 previously purchased items, and "reorder" is the 4th most common search query. We're leaving conversion on the table by not surfacing reorder suggestions proactively.

### Success Metrics

| Metric | Current | Target | Measurement |
|--------|---------|--------|-------------|
| Reorder completion rate | 34% (of members who visit order history) | 50% | Amplitude funnel: order_history_viewed → reorder_item_added → checkout_completed |
| Time from login to first add-to-cart (returning members) | 3.8 min | 2.5 min | Amplitude: session_start → add_to_cart (first), filtered to members with 2+ prior orders |
| Average order value (reorder sessions) | $67 | $72 | Amplitude: order_completed.total_value where session contains reorder_suggestion_interaction |

### User Stories

**US-1: Homepage Reorder Module**
As a returning member, I want to see my frequently purchased items on the homepage so I can quickly add them to my cart without searching.

Acceptance Criteria:
- [ ] Module appears below the hero banner for members with 2+ completed orders
- [ ] Shows top 8 products by purchase frequency, ordered by last purchase date (most recent first)
- [ ] Each product card shows: product image, name, size, price, and "Add to Cart" button
- [ ] "Add to Cart" adds the item without navigating away from the homepage
- [ ] If a product is out of stock, show "Out of Stock" badge and disable the add button
- [ ] If a product's price changed >10% since last purchase, show the old price with strikethrough
- [ ] Module is dismissible — "Hide for now" collapses it for the session; "Don't show again" suppresses it permanently (stored on member profile)
- [ ] On mobile, module is horizontally scrollable with peek (shows 2.5 cards)

**US-2: Post-Checkout Reorder Prompt**
As a member who just completed an order, I want to be reminded of items I usually buy but didn't include so I can add them before my order ships.

Acceptance Criteria:
- [ ] Prompt appears on the order confirmation page, below the order summary
- [ ] Shows up to 5 "You usually order these" products not in the current order
- [ ] "Add to Next Order" creates a saved cart (not a new order) for the member's next session
- [ ] Only appears if the member has 3+ prior orders (to ensure meaningful purchase history)
- [ ] Does not appear if the current order total exceeds $150 (avoid overwhelming high-value orders)
- [ ] Tracks: reorder_prompt_shown, reorder_prompt_item_added, reorder_prompt_dismissed

**US-3: Reorder from Order History**
As a member viewing my order history, I want to reorder an entire past order with one click so I can replenish my staples quickly.

Acceptance Criteria:
- [ ] "Reorder All" button on each past order in order history
- [ ] Adds all in-stock items from that order to cart; shows a toast listing any out-of-stock items skipped
- [ ] If the cart already has items, "Reorder All" merges (does not replace)
- [ ] Price differences are shown in a confirmation modal before adding: "3 items have new prices" with old → new breakdown
- [ ] Works on web and mobile with the same behavior

### Technical Considerations

- Reorder suggestions powered by a lightweight frequency model running in Snowflake, materialized nightly as a member-level table. Algolia not involved — this is a direct DB read.
- Homepage module fetched via a new `/api/reorder-suggestions` endpoint. Response cached at the CDN for 1 hour per member (cache key: member_id + date).
- "Don't show again" preference stored in the member profile service (existing `preferences` JSON field).
- Mobile implementation: React Native `FlatList` with horizontal scroll. Cards are the same `ProductCard` component used elsewhere, with an added `source: 'reorder_suggestion'` tracking prop.

### Open Questions

| Question | Recommended Owner | Status |
|----------|-------------------|--------|
| Should we include subscription items in reorder suggestions, or only one-time purchases? | Priya (PM) + Subscriptions team | Open |
| What's the minimum purchase history needed for meaningful suggestions? (Currently set to 2 orders) | Data Science | Open — need analysis |
| Should reorder suggestions factor in purchase cadence? (e.g., suggest coffee every 2 weeks) | Data Science | Backlog — V2 candidate |

### Launch Plan

- **Phase 1 (Sprint 4-5):** Homepage reorder module, behind Optimizely feature flag. 50/50 A/B test for 2 weeks. Primary metric: reorder completion rate. Guardrail: overall conversion rate does not decrease by >1%.
- **Phase 2 (Sprint 6):** Post-checkout prompt, rolled out to 100% if Phase 1 metrics are positive.
- **Phase 3 (Backlog):** Order history "Reorder All" — lower priority, ships when engineering capacity allows.

---

## Spec 2: Enhanced Product Search with Autocomplete

**Author:** Marcus Chen, PM — Discovery & Personalization
**Last Updated:** January 22, 2026
**Status:** Shipped (January 30, 2026)

### Problem Statement

Our search autocomplete shows only product name matches, missing opportunities to guide members toward categories, brands, and dietary filters. Amplitude data shows 28% of searches result in zero clicks on autocomplete suggestions, and members who use autocomplete convert at 31% vs. 19% for those who submit a full search. Improving autocomplete relevance directly impacts conversion.

### Success Metrics

| Metric | Current | Target | Measurement |
|--------|---------|--------|-------------|
| Autocomplete suggestion click rate | 42% | 55% | Amplitude: search_autocomplete_shown → search_autocomplete_clicked |
| Zero-result search rate | 6.2% | 4.0% | Amplitude: search_executed where results_count = 0 |
| Search-to-cart conversion | 24% | 28% | Amplitude funnel: search_executed → add_to_cart |

### User Stories

**US-1: Category & Brand Suggestions**
As a member typing a search query, I want to see matching categories and brands alongside product suggestions so I can navigate to the right section faster.

Acceptance Criteria:
- [ ] Autocomplete dropdown has three sections: "Products" (top 5), "Categories" (top 2), "Brands" (top 2)
- [ ] Category suggestions link to the category page with the search term pre-filled as a filter
- [ ] Brand suggestions link to the brand page
- [ ] Sections only appear if there are relevant matches (no empty sections)
- [ ] Products section always appears first; Categories and Brands appear below
- [ ] Autocomplete triggers after 2 characters (down from current 3)
- [ ] Response time: <150ms p95 from Algolia

**US-2: Dietary Quick Filters in Search**
As a member searching for products, I want to see relevant dietary filter chips below the search bar so I can narrow results without opening the full filter panel.

Acceptance Criteria:
- [ ] After a search is executed, show up to 4 dietary filter chips below the search bar
- [ ] Chips are ordered by relevance to the query (e.g., searching "protein bars" surfaces "Keto" and "Gluten-Free" first)
- [ ] Tapping a chip applies the filter immediately without a page reload (client-side filtering via Algolia)
- [ ] Active chips show a filled state with an "X" to remove
- [ ] Chips are scrollable horizontally on mobile if more than 3
- [ ] Tracks: dietary_chip_shown (with chip_name, query), dietary_chip_tapped, dietary_chip_removed

**US-3: Recent & Trending Searches**
As a member tapping the search bar, I want to see my recent searches and trending searches so I can quickly find what I'm looking for or discover popular items.

Acceptance Criteria:
- [ ] Empty-state search bar shows two sections: "Recent" (last 5 searches) and "Trending" (top 5 site-wide)
- [ ] Recent searches are stored locally (localStorage on web, AsyncStorage on mobile) — no backend call
- [ ] Trending searches are computed hourly from Amplitude search data, served via a static JSON file on CDN
- [ ] Tapping a recent/trending item executes that search immediately
- [ ] "Clear Recent" link removes all recent searches
- [ ] On mobile, this view replaces the keyboard autocomplete (search bar focuses, recent/trending appears, keyboard stays up)

### Technical Considerations

- Algolia Query Suggestions index configured with product, category, and brand sources. Existing Algolia plan supports this — no cost increase.
- Dietary chip relevance powered by a static mapping table (query_keyword → suggested_diets) maintained in the CMS. Not ML-based — simple and maintainable.
- Trending searches: Amplitude Cohort export → S3 → CDN. Hourly cron job, 5-minute compute.
- Mobile: Autocomplete dropdown is a custom component (not native keyboard suggestions). Ensure it handles notch/safe area on iOS.

### Open Questions

| Question | Recommended Owner | Status |
|----------|-------------------|--------|
| Should autocomplete show product images? Adds visual richness but increases dropdown load time. | Marcus (PM) + Frontend lead | Decided: No images in V1, revisit based on engagement data |
| How do we handle misspellings in autocomplete? Algolia has typo tolerance but it sometimes surfaces irrelevant matches. | Search engineering | Resolved: Algolia typo tolerance set to "min" (1 typo allowed for words >4 chars) |

### Launch Plan

- **Phase 1:** Category & Brand suggestions + Recent/Trending searches. Shipped behind feature flag, 50/50 A/B test for 10 days. Results: autocomplete click rate +9pp (42% → 51%), search-to-cart +2.1pp. Rolled to 100%.
- **Phase 2:** Dietary quick filter chips. Shipped January 30. Monitoring for 2 weeks before declaring success.
