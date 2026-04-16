# Thrive Market — Platform Capabilities for Non-Engineer Deployments

## What We Can Support Today

### Hosting
- **EC2 instances** via Terraform templates (t3.medium default, auto-scaling available)
- Pre-configured AMIs with Python 3.11, Node 20, and common dependencies
- Apps deploy behind internal ALB (Application Load Balancer) — internal network only by default
- SSL termination handled at ALB level

### Authentication & Authorization
- **Okta SSO** integration via SAML — any internal app can be added to the Okta app catalog
- Group-based access control through Okta groups (e.g., "merchandising-team", "finance-team")
- No custom RBAC framework yet — Okta groups are the only authorization mechanism

### Secrets Management
- **AWS Secrets Manager** for API keys, database credentials, third-party tokens
- Secrets are scoped per application (app can only read its own secrets)
- Rotation policies available but not enforced for non-eng apps

### Source Control & CI/CD
- **GitHub repo provisioning** — platform team creates repo with standard template (README, .gitignore, Dockerfile, basic CI)
- **GitHub Actions** CI pipeline: lint, test, build Docker image, deploy to EC2
- Deployment is push-to-main with manual approval gate for production

### Networking
- Internal apps accessible via Tailscale or VPN only (no public internet exposure)
- DNS via internal Route53 zone (e.g., `appname.internal.thrivemarket.com`)
- No custom domain support for internal apps

### Data Access
- **Snowflake** read-only access can be provisioned per-app (scoped to specific schemas/tables)
- Snowflake credentials stored in Secrets Manager
- No write access to Snowflake for non-eng apps

---

## What We CANNOT Support Yet

### Database Provisioning
- No self-service database (RDS, DynamoDB) provisioning
- Apps that need their own persistent storage must request an engineering ticket (current SLA: 2-3 weeks)
- Workaround: some teams use SQLite or local file storage, which is fragile and not backed up

### Custom Domains
- No process for assigning custom internal domains beyond the standard pattern
- No external (public-facing) domain support for non-eng apps

### Monitoring & Alerting
- **No monitoring for non-eng apps.** New Relic is configured only for engineering-owned services
- No health check endpoints required or enforced
- No alerting pipeline — if a non-eng app goes down, nobody knows until a user complains
- Gap: no visibility into non-eng app resource usage (CPU, memory, cost)

### External API Gateway
- No managed API gateway for outbound API calls (Netsuite, Greenhouse, Klaviyo, etc.)
- Each app manages its own API keys and rate limiting
- No centralized rate limit monitoring or cost tracking for third-party API usage

### App Lifecycle Management
- No process for decommissioning apps that are no longer used
- No inventory of deployed non-eng apps (we don't know what's running)
- No cost allocation — non-eng app infrastructure costs are absorbed into platform team budget

### Security Scanning
- No automated security scanning for non-eng app code
- No dependency vulnerability scanning (Snyk/Dependabot not configured for non-eng repos)
- No penetration testing or security review process for non-eng apps

---

## Current Non-Engineer App Inventory

| App | Builder | Status | Hosting | Known Issues |
|-----|---------|--------|---------|--------------|
| Margin Calculator v1 | Maria Santos (Merchandising) | Running | EC2 (manually provisioned) | No monitoring, hardcoded Netsuite credentials in env vars, no SSO |
| Member Triage Helper | Derek Chang (Member Support) | Running | EC2 (manually provisioned) | Queries Snowflake directly with shared credentials, no auth, PII exposure risk |

These two apps were built before any formal process existed. Both need to be brought into compliance.
