# Thrive Market — Service Catalog

| Service | Team Owner | Tier | SLA (uptime) | Dependencies | Known Issues | Last Deploy |
|---------|-----------|------|-------------|--------------|--------------|-------------|
| order-service | Commerce Core | T1-Critical | 99.95% | payment-gateway, inventory-api, membership-api | Memory leak under sustained load >500 rps; tracked in JIRA-4421 | 2026-04-14 |
| payment-gateway | Commerce Core | T1-Critical | 99.99% | Stripe API, order-service, fraud-detection | Stripe webhook retry storms during outages | 2026-04-10 |
| membership-api | Growth Platform | T1-Critical | 99.95% | user-auth, billing-service, Recurly API | Cache invalidation race condition on plan changes | 2026-04-12 |
| catalog-search | Discovery | T2-Important | 99.9% | Elasticsearch cluster, product-ingestion, recommendation-engine | Slow query performance on filtered facet searches >50ms p99 | 2026-04-15 |
| fulfillment-router | Supply Chain | T1-Critical | 99.95% | warehouse-api, shipping-calculator, inventory-api | Occasional routing failures when DC capacity data is stale | 2026-04-11 |
| inventory-api | Supply Chain | T2-Important | 99.9% | Snowflake, warehouse-api, product-ingestion | Nightly sync job occasionally times out on large batches | 2026-04-13 |
| recommendation-engine | Discovery | T2-Important | 99.9% | catalog-search, user-profile-service, ML model server | Cold start latency after deployment ~45s | 2026-04-08 |
| user-auth | Platform | T1-Critical | 99.99% | Okta, Redis cluster, membership-api | Token refresh race condition under high concurrency | 2026-04-09 |
| notification-service | Platform | T3-Internal | 99.5% | SES, SNS, user-profile-service | SES rate limiting during promotional blasts | 2026-04-07 |
| warehouse-api | Supply Chain | T2-Important | 99.9% | Netsuite, fulfillment-router, inventory-api | Netsuite API rate limits hit during peak sync windows | 2026-04-14 |
| product-ingestion | Discovery | T3-Internal | 99.5% | Magento, catalog-search, inventory-api | Duplicate SKU handling fragile; manual dedup needed ~weekly | 2026-04-06 |
| billing-service | Commerce Core | T2-Important | 99.9% | Recurly API, membership-api, payment-gateway | Proration calculation off by pennies on mid-cycle plan changes | 2026-04-12 |
| shipping-calculator | Supply Chain | T3-Internal | 99.5% | FedEx/UPS/USPS APIs, fulfillment-router | Carrier API timeouts spike during holiday surges | 2026-04-05 |
| user-profile-service | Growth Platform | T2-Important | 99.9% | user-auth, Snowflake, recommendation-engine | Profile merge logic doesn't handle duplicate emails gracefully | 2026-04-11 |
| fraud-detection | Commerce Core | T2-Important | 99.9% | payment-gateway, order-service, ML model server | Model retraining pipeline occasionally produces stale models | 2026-04-10 |

## Tier Definitions

- **T1-Critical**: Direct revenue impact. Outage = customers cannot browse, buy, or manage memberships. 15-minute response SLA, 1-hour resolution target.
- **T2-Important**: Degraded experience or operational impact. Outage = reduced functionality but core purchase flow still works. 30-minute response SLA, 4-hour resolution target.
- **T3-Internal**: Internal tools and batch processes. Outage = internal workflow disruption. Next business day response, best-effort resolution.
