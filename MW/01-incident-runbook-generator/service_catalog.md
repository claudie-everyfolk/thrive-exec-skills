# Thrive Market Service Catalog

## T1 — Business Critical (99.95% SLA)

### order-service
- **Team:** Order Platform
- **Owner:** J. Martinez
- **Description:** Core order lifecycle management — cart checkout, order creation, payment orchestration, order status tracking
- **Dependencies:** payment-gateway, inventory-sync, membership-api, fulfillment-router, promotion-engine
- **Infrastructure:** EKS (us-east-1 primary, us-west-2 failover), RDS PostgreSQL (multi-AZ), ElastiCache Redis
- **Known Issues:** Frequent deployment regressions due to high change velocity; memory leak in validation module (ticket PLAT-2847); feature flag dependency management is manual

### payment-gateway
- **Team:** Payments
- **Owner:** S. Chen
- **Description:** Payment processing, fraud detection, refunds, Apple Pay/Google Pay integration
- **Dependencies:** Stripe (primary processor), Adyen (fallback), order-service, membership-api
- **Infrastructure:** EKS, RDS PostgreSQL, dedicated PCI-compliant subnet
- **Known Issues:** Connection pool sizing historically undersized (fixed with PgBouncer in March); Apple Pay SDK version sensitivity

### membership-api
- **Team:** Member Experience
- **Owner:** R. Patel
- **Description:** Membership management, subscription billing, member profiles, benefits/perks engine
- **Dependencies:** payment-gateway, notification-service, Recurly (subscription billing)
- **Infrastructure:** EKS, RDS PostgreSQL (primary + read replica), ElastiCache
- **Known Issues:** Analytics queries on read replica cause contention (recurring); annual renewal batch jobs conflict with live traffic

---

## T2 — High Priority (99.9% SLA)

### api-gateway
- **Team:** Platform Engineering
- **Owner:** A. Okonkwo
- **Description:** Nginx-based API gateway — routing, rate limiting, auth middleware, SSL termination
- **Dependencies:** All downstream services
- **Infrastructure:** EKS, deployed across 3 AZs
- **Known Issues:** Config drift during deployments (rate limits, timeouts, SSL certs); mobile client compatibility gaps in auth middleware

### catalog-search
- **Team:** Product Discovery
- **Owner:** K. Yamamoto
- **Description:** Product search, filtering, faceted navigation powered by Elasticsearch
- **Dependencies:** inventory-sync, recommendation-engine, product feed (external)
- **Infrastructure:** EKS, Elasticsearch cluster (6 nodes), S3 for product images
- **Known Issues:** CPU spikes during product feed sync (should run off-peak); Elasticsearch index bloat from undeleted variants; auto-scaling handles most load spikes but alerts fire unnecessarily

### fulfillment-router
- **Team:** Logistics
- **Owner:** M. Thompson
- **Description:** Routes orders to optimal fulfillment center based on inventory, proximity, and shipping speed
- **Dependencies:** warehouse-api, inventory-sync, shipping-calculator
- **Infrastructure:** EKS, SQS queues, DynamoDB for routing rules
- **Known Issues:** Warehouse-api rate limits cause queue depth buildup; no advance notification for warehouse maintenance windows

### notification-service
- **Team:** Member Experience
- **Owner:** R. Patel
- **Description:** Transactional and marketing notifications — email (SendGrid/SES), push, SMS
- **Dependencies:** SendGrid (primary email), AWS SES (fallback), SNS for push
- **Infrastructure:** EKS, SQS queues, DynamoDB for delivery tracking
- **Known Issues:** Queue saturation during promo blasts; dead letter queue overflow when poison messages enter retry loops; SendGrid outages require manual failover to SES

### inventory-sync
- **Team:** Logistics
- **Owner:** M. Thompson
- **Description:** Real-time inventory synchronization between warehouse systems, ERP, and product catalog
- **Dependencies:** warehouse-api, catalog-search, external ERP (NetSuite)
- **Infrastructure:** EKS, RDS PostgreSQL, Step Functions for batch sync
- **Known Issues:** Third-party data quality (duplicate SKUs, negative quantities, future timestamps); idempotency gaps in sync pipeline

---

## T3 — Standard (99.5% SLA)

### recommendation-engine
- **Team:** Product Discovery
- **Owner:** K. Yamamoto
- **Description:** ML-powered product recommendations — collaborative filtering, trending, personalized picks
- **Dependencies:** catalog-search, membership-api, Airflow (model refresh)
- **Infrastructure:** EKS, SageMaker endpoints, S3 for model artifacts
- **Known Issues:** Model refresh cron has failed silently twice (timezone misconfiguration); stale models serve degraded recommendations for hours before detection

### promotion-engine
- **Team:** Growth
- **Owner:** L. Garcia
- **Description:** Promo code validation, discount calculation, stacking rules, member-exclusive offers
- **Dependencies:** membership-api, order-service
- **Infrastructure:** EKS, RDS PostgreSQL, ElastiCache for promo code lookups
- **Known Issues:** Holiday promo stacking logic is fragile; tested primarily in staging which doesn't reflect production promo volume

### shipping-calculator
- **Team:** Logistics
- **Owner:** M. Thompson
- **Description:** Real-time shipping rate calculation from UPS, FedEx, USPS; handles free shipping thresholds
- **Dependencies:** UPS API, FedEx API, USPS API, fulfillment-router
- **Infrastructure:** EKS, ElastiCache for rate caching
- **Known Issues:** Carrier API instability (currency issues with UPS, latency with FedEx); fallback to cached rates needs tuning

### warehouse-api
- **Team:** Logistics
- **Owner:** M. Thompson
- **Description:** Interface to physical warehouse management systems — pick/pack/ship, inventory counts, receiving
- **Dependencies:** External WMS, inventory-sync, fulfillment-router
- **Infrastructure:** EKS, RDS PostgreSQL
- **Known Issues:** EKS node disk pressure (PVC sizing); rate limits are conservative and trip circuit breakers in fulfillment-router; no maintenance window notifications to upstream services

### user-preferences
- **Team:** Member Experience
- **Owner:** R. Patel
- **Description:** Dietary preferences, allergen filters, shopping lists, saved items
- **Dependencies:** membership-api, catalog-search
- **Infrastructure:** EKS, DynamoDB
- **Known Issues:** None significant; low incident volume

### content-cms
- **Team:** Marketing
- **Owner:** L. Garcia
- **Description:** Headless CMS for editorial content, recipes, buying guides, landing pages
- **Dependencies:** catalog-search (product embeds), S3/CloudFront for assets
- **Infrastructure:** EKS, MongoDB
- **Known Issues:** Occasional slow builds during large content publishes; not operationally critical

### analytics-pipeline
- **Team:** Data Engineering
- **Owner:** D. Nguyen
- **Description:** Event ingestion, transformation, and loading into Snowflake for reporting and ML training
- **Dependencies:** All services (event producers), Snowflake, Airflow, Firehose
- **Infrastructure:** Kinesis Firehose, Airflow on MWAA, Snowflake
- **Known Issues:** Airflow DAG failures are often silent; analytics queries sometimes leak to production replicas instead of Snowflake
