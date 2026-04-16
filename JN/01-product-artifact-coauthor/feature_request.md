# Feature Request: Shop by Diet Personalization

**From:** Elena Marcos, SVP of Product
**Date:** March 28, 2026
**Priority:** High — Q2 roadmap commitment

## Vision

We want to add a "Shop by Diet" personalization experience. Members select their dietary preferences (Keto, Paleo, GLP-1 Friendly, Vegan, Vegetarian, Gluten-Free, Dairy-Free, Whole30, Low-Sugar, Mediterranean) during onboarding or in account settings, and the entire browse/search experience adapts to surface the most relevant products first.

## Scope

This should impact:
- **Onboarding flow** — new members select dietary preferences as part of signup (after membership selection, before first browse)
- **Homepage** — personalized "For Your Diet" module, diet-specific collections, and reordered category tiles
- **Search results** — diet-matching products boosted in ranking, with a visible "Matches Your Diet" badge
- **Category pages** — default sort influenced by dietary preferences, with a toggle to show all vs. diet-matched
- **Email recommendations** — weekly "New for You" email adapts product picks based on diet profile

## Goals

- Increase first-order conversion by 15% for new members (current: 32%)
- Reduce average browse-to-cart time by 20% (current: 8.2 minutes on mobile, 6.1 minutes on desktop)
- Increase member retention at 90 days by 5% (current: 71%)
- Drive 40%+ adoption of dietary preferences within 6 months of launch

## Non-Goals

- This is NOT a meal planning feature — we're personalizing product discovery, not creating meal plans
- We are NOT building a recommendation engine from scratch — this layers on top of existing search/browse infrastructure
- Dietary preferences are self-reported, not inferred — we are not analyzing purchase history to guess diets (yet)

## Context

- Amplitude data shows 40% of members already use dietary filters manually at least once per session
- Our customer research team heard "I wish the site just knew what I eat" in 6 of 10 recent member interviews
- Syndigo PIM is launching April 20 with enriched product attributes including validated dietary tags for 85% of our catalog
- GLP-1 is the fastest-growing dietary segment — we're seeing 300% YoY growth in GLP-1-related search queries
- Competitor activity: Instacart launched a GLP-1 meal planning feature in Q1 2026

## Open Items from Leadership

- Should we allow members to set preferences for multiple household members (e.g., "I'm Keto but my partner is Vegetarian")?
- How do we handle products that are borderline (e.g., a product that's "mostly" Keto but has 7g net carbs)?
- What's the right balance between personalization and discovery? We don't want to create a filter bubble where members never see new categories.
