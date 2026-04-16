# Sprint 14 Goals — Discovery & Personalization Squad

**Sprint Dates:** April 6 – April 17, 2026
**Sprint Theme:** Search Relevance & Dietary Foundations

---

## Goal 1: Ship Dietary Filter Persistence (Must-Have)

**Description:** Members who apply dietary filters during search should have those filters remembered for their next session. This is the foundational building block for the Shop by Diet initiative — if we can't persist a filter preference, we can't personalize anything.

**Success Criteria:**
- [ ] Dietary filter selections saved to member profile via the preferences API
- [ ] Filters auto-applied on next search session (with a dismissible "Filtering by: Keto, Gluten-Free" banner)
- [ ] Works on web and mobile (React Native)
- [ ] Behind Optimizely feature flag, ready for A/B test in Sprint 15

**Key Tickets:** TM-2415, TM-2416, TM-2417, TM-2418, TM-2422

**Current Assessment (Day 8):** Backend API done. Frontend web implementation in review. Mobile implementation blocked on a React Native upgrade issue. Feature flag integration not started yet. **At risk** — mobile + feature flag may slip.

---

## Goal 2: Reduce Zero-Result Searches by 30% (Should-Have)

**Description:** Zero-result searches are at 6.2%. We're adding synonym mappings and fuzzy matching improvements to Algolia to bring this under 4.3%. This was a key finding from the Enhanced Search spec post-launch analysis.

**Success Criteria:**
- [ ] 200+ synonym mappings added to Algolia (covering top zero-result queries from last 90 days)
- [ ] Fuzzy matching threshold tuned from "strict" to "min" for queries >3 characters
- [ ] Zero-result rate measured over 3 days post-deploy is <4.5%
- [ ] No degradation in search relevance (measured by search-to-cart conversion holding steady ±1%)

**Key Tickets:** TM-2419, TM-2420, TM-2421, TM-2427

**Current Assessment (Day 8):** Synonym mappings done (TM-2419 shipped). Fuzzy matching config change deployed (TM-2420 shipped). QA validation in progress (TM-2421 was blocked on staging environment issue, now cleared). Search relevance monitoring ticket not started. **Mostly on track** — monitoring may push to Sprint 15 but core work is done.

---

## Goal 3: Syndigo PIM Data Pipeline — Staging Validation (Nice-to-Have)

**Description:** Syndigo PIM launches April 20. We need the data ingestion pipeline validated in staging before launch. This sprint, we're connecting to the Syndigo sandbox API, ingesting sample data, and validating the dietary attribute mapping.

**Success Criteria:**
- [ ] Staging pipeline successfully ingests Syndigo sandbox data nightly
- [ ] Dietary attributes mapped to our internal taxonomy (10 diet types)
- [ ] Data quality report generated: coverage %, unmapped attributes, edge cases
- [ ] Product data team signs off on mapping quality

**Key Tickets:** TM-2423, TM-2424, TM-2425, TM-2428

**Current Assessment (Day 8):** Pipeline connected and ingesting (TM-2423 done). Attribute mapping in progress (TM-2424) — more complex than estimated, 15 Syndigo attributes map to our 10 categories with overlap. Data quality report not started. **At risk** — mapping complexity may push quality report and sign-off to Sprint 15.
