# Business Operating System Selection Guide

**🇦🇺 Tailored for Australian Startups**

---

## Introduction

Choosing the right business operating system (BOS) is one of the most critical decisions you'll make when starting or scaling a technology business. Your BOS encompasses not just the technical infrastructure, but also the tools, processes, legal frameworks, and management systems that enable your business to operate efficiently, securely, and in compliance with regulatory requirements.

**This guide is specifically tailored for Australian startups**, with Australia-specific guidance on:
- **Business formation**: Pty Ltd registration, ASIC, ABN, ACN, GST, superannuation
- **Banking**: Australian banks and fintechs (Up, Judo, CommBank, Airwallex, Wise)
- **Accounting**: Xero (Australian standard), ERPNext, and tax compliance (BAS, STP, GST)
- **Employment law**: Fair Work Act, Modern Awards, superannuation guarantee
- **Privacy**: Australian Privacy Act, alongside GDPR and international compliance
- **VC fundraising**: Guidance on Delaware C-Corp flip for US venture capital

While the technical infrastructure and tooling recommendations are globally applicable, business formation, legal, and compliance sections prioritize Australian context.

---

## Table of Contents

1. [Technical Infrastructure](#technical-infrastructure)
2. [Business & Project Management](#business--project-management)
3. [Product Development & Design](#product-development--design)
4. [Development & Security Tools](#development--security-tools)
5. [Legal & Compliance Foundation](#legal--compliance-foundation)
6. [Infrastructure & Identity Management](#infrastructure--identity-management)
7. [Business Formation](#business-formation)
8. [Network & Security Infrastructure](#network--security-infrastructure)
9. [Operational Management Frameworks](#operational-management-frameworks)
10. [Compliance Management Systems](#compliance-management-systems)

---

## Technical Infrastructure

### Self-Hosted Infrastructure Options

Your technical infrastructure foundation determines scalability, security, and operational flexibility. Consider these options based on your technical expertise and requirements:

#### UmbrelOS
- **Best For**: Small teams, home lab environments, personal projects
- **Pros**: Simple setup, user-friendly interface, good for beginners
- **Cons**: Limited enterprise features, not suitable for production at scale
- **Use Case**: Development environments, small-scale deployments, proof-of-concepts

#### Proxmox with LXC Containers
- **Best For**: Medium to large organizations, multi-tenant environments
- **Pros**: Full virtualization + container support, enterprise features, excellent resource efficiency
- **Cons**: Steeper learning curve, requires dedicated hardware management
- **Use Case**: Production workloads, development/staging environments, infrastructure consolidation
- **Recommendation**: **Highly Recommended** for organizations with technical capacity

#### Docker
- **Best For**: Microservices architecture, development teams, rapid deployment
- **Pros**: Portable, large ecosystem, easy development-to-production workflow
- **Cons**: Requires orchestration for production, networking complexity
- **Use Case**: Application deployment, CI/CD pipelines, development environments
- **Recommendation**: **Recommended** for most modern applications

#### Kubernetes (K8s)
- **Best For**: Large-scale applications, cloud-native architectures, high-availability requirements
- **Pros**: Industry standard orchestration, auto-scaling, self-healing, extensive tooling
- **Cons**: Complex, resource-intensive, requires dedicated expertise
- **Use Case**: Production-grade microservices, multi-region deployments, enterprise applications
- **Recommendation**: **Recommended** once you reach scale (typically 5+ services or need HA)

### Infrastructure Decision Matrix

| Organization Size | Recommended Approach |
|------------------|---------------------|
| Solo/Small (1-3) | Docker Compose on VPS or UmbrelOS for experimentation |
| Small Team (4-10) | Docker Swarm or Proxmox with LXC |
| Medium (11-50) | Kubernetes (managed like GKE/EKS) or Proxmox cluster |
| Large (50+) | Kubernetes with service mesh, multi-cluster setup |

---

## Business & Project Management

### Project Management Platform

#### Jira / Atlassian Suite
- **Status**: **Recommended**
- **Components**: Jira (issue tracking), Confluence (documentation), Bitbucket (code)
- **Best For**: Engineering teams, software development, agile methodologies
- **Key Features**:
  - Advanced workflow customization
  - Sprint planning and tracking
  - Integration with development tools
  - Extensive reporting capabilities
- **Considerations**: Can be expensive at scale; learning curve for new users

#### Linear
- **Status**: Strong Alternative
- **Best For**: Fast-moving product teams, modern development workflows
- **Key Features**:
  - Exceptionally fast performance
  - Clean, intuitive interface
  - Git integration
  - Keyboard-first design
- **Considerations**: Newer platform, fewer integrations than Jira

### ERP & Business Management

#### ERPNext / Frappe Cloud
- **Status**: **Recommended**
- **Best For**: Growing businesses needing integrated business operations
- **Key Features**:
  - Complete ERP suite (accounting, inventory, HR, CRM, manufacturing)
  - Open source with cloud hosting option
  - Customizable and extensible
  - Cost-effective compared to SAP/Oracle
- **Use Case**: Financial management, inventory tracking, HR operations, customer management
- **Recommendation**: Implement early to establish good business process discipline

---

## Product Development & Design

### Design & Prototyping

#### Figma
- **Status**: Industry Standard
- **Best For**: UI/UX design, collaborative design workflows
- **Key Features**:
  - Real-time collaboration
  - Component libraries
  - Developer handoff tools
  - Design systems management
- **Recommendation**: Essential for any product team

### User Research & Feedback

#### Formbricks
- **Status**: Recommended for User Research
- **Best For**: In-app surveys, user feedback collection
- **Key Features**:
  - Open source
  - Privacy-focused
  - Embeddable surveys
  - Self-hostable
- **Use Case**: Product feedback loops, user satisfaction measurement, feature validation

---

## Development & Security Tools

### Source Control & Collaboration

#### GitHub
- **Status**: **Recommended**
- **Free Tier**: Unlimited public and private repos, unlimited collaborators, 2,000 CI/CD minutes/month, 500MB package storage
- **Components**: Source control, CI/CD (Actions), project management, code review, security scanning
- **Key Features**:
  - Industry-standard Git platform
  - GitHub Actions for CI/CD automation (free tier sufficient for most startups)
  - Advanced security features (Dependabot, secret scanning, code scanning)
  - Project management (Issues, Projects, Milestones)
  - GitHub Packages (container registry, npm, etc.)
  - GitHub Pages (free static site hosting)
  - Codespaces (cloud dev environments)
  - Large ecosystem of integrations (10,000+ apps)
- **Upgrade Path**:
  - **Team**: $4/user/month (3,000 minutes, advanced security)
  - **Enterprise**: Custom pricing (SAML SSO, audit logs)
- **Recommendation**: **Essential** - Use free tier, upgrade only if you need advanced security or more CI/CD minutes
- **Australian Context**: No data residency concerns for source code; works seamlessly from AU

### Developer Platforms & Infrastructure

#### Cloudflare
- **Status**: **Highly Recommended**
- **Free Tier**: Unlimited bandwidth, DDoS protection, SSL certificates, 100k Workers requests/day, 10GB R2 storage, DNS management
- **Use Cases**:
  1. **CDN & DDoS Protection**: Free tier protects your website and speeds up delivery
  2. **Cloudflare Workers**: Serverless edge functions (100k requests/day free)
  3. **Cloudflare Pages**: Static site hosting with CI/CD (unlimited sites, unlimited requests)
  4. **Cloudflare R2**: S3-compatible object storage (10GB free, no egress fees)
  5. **Cloudflare D1**: Serverless SQLite database (in beta, generous free tier)
  6. **DNS**: Fast, reliable DNS (free, unlimited queries)
  7. **Cloudflare Tunnel**: Secure access to local services without exposing ports
- **Key Features**:
  - Best-in-class DDoS protection (free tier same as paid)
  - Global CDN with edge caching
  - Web Application Firewall (WAF) - basic rules free
  - SSL/TLS certificates (automatic, free)
  - Analytics and insights
  - Zero egress fees on R2 (unlike AWS S3)
- **Upgrade Path**:
  - **Pro**: $20/month (advanced caching, image optimization)
  - **Business**: $200/month (custom WAF rules, PCI compliance)
- **Recommendation**: **Use the free tier immediately** - One of the best free tiers in the industry
- **Australian Context**: Great CDN performance in APAC region

#### Vercel
- **Status**: Excellent Platform (with considerations)
- **Free Tier**: Unlimited deployments, 100GB bandwidth/month, serverless functions, automatic HTTPS, preview deployments
- **Use Cases**:
  - Next.js hosting (optimized, created by Vercel)
  - Static sites and serverless functions
  - Preview deployments for every PR
  - Edge functions and middleware
- **Key Features**:
  - Zero-config deployments for Next.js, React, Vue, etc.
  - Automatic preview URLs for pull requests
  - Built-in CI/CD
  - Edge network (fast globally)
  - Analytics (Web Vitals tracking)
  - Serverless functions with zero cold starts
- **Upgrade Path**:
  - **Pro**: $20/user/month (1TB bandwidth, advanced analytics)
  - **Enterprise**: Custom (SLA, dedicated support)
- **Ethical/Political Considerations**: Some developers choose to avoid Vercel due to the company's political stances or ethical concerns. This is a personal decision. Alternatives include Cloudflare Pages, Netlify, or self-hosting.
- **Recommendation**: **Excellent platform** for Next.js and modern web apps; use free tier, evaluate alternatives if ethical concerns apply
- **Australian Context**: Good APAC performance

#### Netlify
- **Status**: Strong Alternative to Vercel
- **Free Tier**: 100GB bandwidth/month, 300 build minutes/month, forms, serverless functions
- **Use Cases**: Similar to Vercel, but framework-agnostic
- **Key Features**: Git-based deployments, instant rollbacks, split testing
- **Recommendation**: Good alternative if avoiding Vercel or not using Next.js

### Backend & Database Services

#### Supabase
- **Status**: **Highly Recommended**
- **Free Tier**: 500MB database, 1GB file storage, 50k monthly active users, 2GB bandwidth, unlimited API requests
- **What It Is**: Open-source Firebase alternative (Postgres-based)
- **Components**:
  1. **PostgreSQL Database**: Full Postgres with Row Level Security (RLS)
  2. **Authentication**: Email, OAuth (Google, GitHub, etc.), magic links, phone auth
  3. **Storage**: S3-compatible object storage for files
  4. **Realtime**: Subscribe to database changes (websockets)
  5. **Edge Functions**: Serverless Deno functions
  6. **Auto-generated APIs**: RESTful and GraphQL APIs from your schema
- **Key Features**:
  - Open-source (can self-host if needed)
  - PostgreSQL (real database, not NoSQL)
  - Built-in auth with Row Level Security
  - Realtime subscriptions
  - Auto-scaling
  - Dashboard for database management
- **Upgrade Path**:
  - **Pro**: $25/month (8GB database, 100GB bandwidth, daily backups)
  - **Team**: $599/month (custom resources)
- **Recommendation**: **Perfect for startups** - Free tier is generous, Postgres is production-ready, can self-host later
- **Australian Context**: Has Sydney region available (low latency)

#### Neon
- **Status**: Recommended for Serverless Postgres
- **Free Tier**: 0.5GB storage per project, 3 projects, unlimited compute hours (with autoscaling to zero)
- **What It Is**: Serverless Postgres with branching (like Git for databases)
- **Key Features**:
  - True serverless (scales to zero when idle)
  - Database branching (test schema changes safely)
  - Instant provisioning
  - Pay only for storage (compute is free on free tier)
  - Point-in-time recovery
- **Upgrade Path**:
  - **Launch**: $19/month (3GB storage, more projects)
  - **Scale**: $69/month (10GB storage, faster compute)
- **Recommendation**: Great for side projects and serverless apps; Supabase better if you need auth/storage/realtime
- **Australian Context**: Uses AWS regions, can select Sydney

### Authentication Services

#### Clerk
- **Status**: Recommended for Modern Auth
- **Free Tier**: 10,000 monthly active users, unlimited sign-ins
- **What It Is**: Complete user management and authentication
- **Key Features**:
  - Pre-built UI components (sign-in, sign-up, user profile)
  - Social logins (Google, GitHub, Microsoft, etc.)
  - Multi-factor authentication (SMS, TOTP)
  - User management dashboard
  - Organizations and teams support
  - Webhooks and integrations
  - Beautiful, customizable UI
- **Upgrade Path**:
  - **Pro**: $25/month (50k MAUs, advanced features)
  - **Enterprise**: Custom (SAML SSO, audit logs)
- **Recommendation**: **Best developer experience** for auth; use if you want to move fast and don't want to build auth UI
- **Australian Context**: Works globally, no specific AU region needed

#### Supabase Auth
- **Status**: Included with Supabase
- **Free Tier**: 50k monthly active users (included in Supabase free tier)
- **What It Is**: Built-in authentication for Supabase
- **Key Features**:
  - Email/password, magic links, OAuth providers
  - Phone auth (SMS/WhatsApp)
  - Row Level Security integration
  - JWT tokens
  - Self-hostable
- **Recommendation**: Use if already using Supabase; simpler than Clerk but less features
- **vs. Clerk**: Clerk has better UI components and user management dashboard; Supabase Auth better integrated with Postgres RLS

### Error Tracking & Monitoring

#### Sentry.io
- **Status**: **Industry Standard**
- **Free Tier**: 5,000 errors/month, 10k performance transactions/month, 1 user
- **What It Is**: Error tracking and performance monitoring
- **Key Features**:
  - Real-time error tracking
  - Stack traces with source maps
  - Release tracking
  - Performance monitoring (APM)
  - User feedback collection
  - Issue assignment and workflow
  - Integrations (Slack, Jira, GitHub, etc.)
  - Breadcrumbs (what user did before error)
  - Support for 100+ platforms/languages
- **Upgrade Path**:
  - **Developer**: $26/month (50k errors, unlimited users)
  - **Team**: $80/month (100k errors, advanced features)
- **Recommendation**: **Essential** - Catch errors in production before users report them; free tier sufficient for early stage
- **Australian Context**: Global edge network, low latency
- **Self-Hosted**: Open-source, can self-host if needed

#### Better Stack (formerly Logtail)
- **Status**: Recommended for Logs & Uptime
- **Free Tier**: 1GB logs/month retained for 3 days, 10 uptime monitors
- **What It Is**: Logging, uptime monitoring, and incident management
- **Key Features**:
  - Structured logging (similar to Datadog Logs)
  - SQL-based log search
  - Uptime monitoring (HTTP, ping, etc.)
  - Incident management
  - Status pages
  - Alerting (email, Slack, PagerDuty, etc.)
  - Beautiful, fast UI
- **Upgrade Path**:
  - **Startup**: $20/month (20GB logs, 30-day retention)
  - **Business**: $100/month (100GB logs, 60-day retention)
- **Recommendation**: Good alternative to expensive tools like Datadog; free tier good for small projects
- **vs. Grafana Loki**: Better Stack is SaaS (easier), Loki is self-hosted (more control)

### AI & Development Tools

#### OpenRouter
- **Status**: Recommended for LLM Access
- **Free Tier**: Free models available (e.g., Llama 3.1 8B, Mistral 7B), pay-as-you-go for others
- **What It Is**: Unified API for 100+ LLMs (OpenAI, Anthropic, Google, Meta, etc.)
- **Key Features**:
  - Single API for all major LLMs
  - Model routing (fallbacks, load balancing)
  - Pay only for what you use
  - No subscriptions
  - OpenAI-compatible API
  - Free models available
  - Provider credits (sometimes offers free credits)
- **Pricing**: Pay-per-token (prices vary by model)
  - GPT-4: ~$0.03/1k input tokens
  - Claude 3.5 Sonnet: ~$0.003/1k tokens
  - Free models: $0
- **Recommendation**: **Use this instead of direct API keys** - Gives flexibility to switch models, better rates, free tiers
- **Australian Context**: Global API, low latency
- **vs. Direct APIs**: OpenRouter often cheaper, single integration, easier to switch models

#### v0.dev (Vercel)
- **Status**: Cutting-Edge AI Tool
- **Free Tier**: Limited free generations per month (credits-based)
- **What It Is**: AI-powered UI generation from text prompts
- **Key Features**:
  - Generate React/Next.js components from descriptions
  - Tailwind CSS styling
  - Interactive preview
  - Copy/export code
  - Iterate on designs with AI
- **Use Cases**:
  - Rapid prototyping
  - Generate starter components
  - Design exploration
  - Learning React patterns
- **Upgrade Path**: Credit packs ($10-50 for more generations)
- **Recommendation**: Great for prototyping and learning; accelerates UI development
- **Note**: Part of Vercel ecosystem (see ethical considerations above)

### Security & Code Quality

#### Snyk
- **Purpose**: Dependency vulnerability scanning
- **Key Features**: Real-time monitoring, auto-fix PRs, license compliance
- **Recommendation**: **Essential** for security-conscious teams

#### SonarQube
- **Purpose**: Code quality and security analysis
- **Key Features**: Technical debt tracking, code smell detection, security hotspots
- **Recommendation**: Implement in CI/CD pipeline

#### CodeRabbit
- **Purpose**: AI-powered code review
- **Key Features**: Automated code analysis, suggestion generation, PR summaries
- **Recommendation**: Augments human code review

#### Dependabot
- **Purpose**: Automated dependency updates
- **Key Features**: Security patches, version updates, auto-generated PRs
- **Recommendation**: **Enable immediately** on all repositories

#### GitGuardian
- **Purpose**: Secrets detection and prevention
- **Key Features**: Real-time scanning, historical analysis, incident management
- **Recommendation**: **Critical** for preventing credential leaks

### Security Toolchain Checklist

- [ ] Enable Dependabot on all repositories
- [ ] Configure Snyk for dependency scanning
- [ ] Set up SonarQube in CI/CD pipeline
- [ ] Implement GitGuardian secrets scanning
- [ ] Establish code review requirements (minimum 1-2 reviewers)
- [ ] Configure branch protection rules
- [ ] Enable 2FA for all team members
- [ ] Deploy Sentry.io for error tracking (free tier)
- [ ] Set up Better Stack or similar for uptime monitoring

---

## The Free Tier Startup Stack 🎁

**You can build a production-ready startup for $0-50/month using these free tiers:**

### Essential Free Tools (Pre-Seed / Bootstrapped)

| Category | Tool | Free Tier | What You Get |
|----------|------|-----------|--------------|
| **Hosting/CDN** | Cloudflare | Unlimited | CDN, DDoS protection, SSL, Workers (100k/day), R2 storage (10GB) |
| **App Hosting** | Vercel or Cloudflare Pages | 100GB/month bandwidth | Unlimited deployments, serverless functions, preview URLs |
| **Database** | Supabase | 500MB Postgres | Database, auth, storage, realtime, 50k MAUs |
| **Auth** | Clerk or Supabase Auth | 10k MAUs / 50k MAUs | Complete auth with UI, social logins, MFA |
| **Source Control** | GitHub | Unlimited | Repos, CI/CD (2k minutes), security scanning, Pages |
| **Error Tracking** | Sentry | 5k errors/month | Real-time error tracking, performance monitoring |
| **Monitoring** | Better Stack | 1GB logs, 10 monitors | Logging, uptime monitoring, incident management |
| **LLM Access** | OpenRouter | Free models | Access to Llama, Mistral, and other open models |
| **Email** | Resend | 100 emails/day | Transactional email with good deliverability |
| **Analytics** | Plausible (self-hosted) or Cloudflare Analytics | Free | Privacy-friendly web analytics |

**Total Monthly Cost**: **$0** for early stage (up to ~10k users)

### When to Start Paying

You'll need to upgrade when you hit these limits:
- **Supabase**: >500MB database or >2GB bandwidth/month → $25/month
- **Cloudflare**: Need advanced features → $20/month (Pro tier)
- **Vercel**: >100GB bandwidth → $20/user/month
- **Sentry**: >5k errors/month → $26/month
- **Clerk**: >10k MAUs → $25/month

### Recommended Free Tier Stack by Use Case

**SaaS/Web App**:
- Vercel (hosting) + Supabase (database + auth) + Cloudflare (CDN) + Sentry (errors) + GitHub (code)
- **Cost**: $0 until significant traction

**Static Site / Marketing Site**:
- Cloudflare Pages (hosting) + GitHub (source) + Better Stack (uptime)
- **Cost**: $0 forever (if truly static)

**API / Backend**:
- Cloudflare Workers (compute) + Supabase (database) + Neon (additional DBs) + Sentry (errors)
- **Cost**: $0 for 100k requests/day

**AI-Powered App**:
- Vercel (hosting) + Supabase (database) + OpenRouter (LLMs - free models) + Clerk (auth)
- **Cost**: $0 + pay-per-use for premium LLMs

### Migration Path from Free Tier

**Stage 1: Free Tier (0-1k users)**
- Use all free tiers listed above
- Self-host when possible (Loki for logs, Prometheus for metrics)

**Stage 2: Hybrid ($50-200/month, 1k-10k users)**
- Upgrade Supabase to Pro ($25/month)
- Add Sentry Developer ($26/month)
- Keep Cloudflare free tier
- Keep Vercel free tier (or upgrade to Pro if needed)
- Self-hosted observability (Loki + Prometheus)

**Stage 3: Paid Services ($500-2000/month, 10k-100k users)**
- Supabase Team or self-hosted Postgres
- Vercel Pro or migrate to self-hosted
- Sentry Team ($80/month)
- Consider Datadog or New Relic for unified observability
- Cloudflare Pro ($20/month)

**Stage 4: Enterprise (100k+ users)**
- Self-hosted infrastructure (Kubernetes)
- Enterprise support contracts
- Dedicated customer success managers
- Custom SLAs

---

## Legal & Compliance Foundation

### Essential Legal Documents

Establishing proper legal and compliance documentation is **non-negotiable** for any serious business. These documents protect your business, your customers, and your intellectual property.

#### 1. Privacy Policy
- **Purpose**: Disclose how you collect, use, and protect user data
- **Required By**: GDPR, CCPA, and most data protection regulations
- **Key Elements**:
  - Data collection practices
  - Data usage and sharing
  - User rights (access, deletion, portability)
  - Cookie and tracking technology disclosure
  - International data transfers
- **Action**: Draft and publish before collecting any user data

#### 2. Data Processing Agreement (DPA)
- **Purpose**: Document data processing relationships for GDPR and privacy compliance
- **Required By**: GDPR (when processing data on behalf of customers), Australian Privacy Act (for B2B data handling)
- **Key Elements**:
  - Processor and controller roles clearly defined
  - Scope and purpose of data processing
  - Security measures and technical safeguards
  - Sub-processor authorization and disclosure
  - Data breach notification procedures
  - Data subject rights fulfillment process
  - Data retention and deletion obligations
  - Audit rights and compliance verification
  - Termination and data return procedures
- **Use Case**: Essential for B2B SaaS handling customer data, any service processing data on behalf of others
- **Action**: Required before processing any B2B customer data in the EU/AU

#### 3. Terms of Service (ToS)
- **Purpose**: Define the legal relationship between your business and users
- **Key Elements**:
  - Acceptable use policy
  - Intellectual property rights
  - Limitation of liability
  - Dispute resolution
  - Service availability and modifications
- **Action**: Required before accepting users/customers

#### 4. Master Services Agreement (MSA)
- **Purpose**: Standard contract terms for B2B relationships
- **Key Elements**:
  - Service scope and deliverables
  - Payment terms
  - Liability limitations
  - Warranties and representations
  - Termination conditions
- **Use Case**: Essential for consulting, SaaS, or service businesses

#### 5. Confidentiality and Invention Assignment Agreement (CIIA/PIIA)
- **Purpose**: Protect intellectual property and ensure company ownership of work product
- **Key Elements**:
  - IP assignment to company
  - Confidentiality obligations
  - Non-compete clauses (limited enforceability in Australia—consult local counsel)
  - Prior inventions disclosure
- **Action**: **All employees and contractors must sign** before starting work
- **Australian Note**: Non-compete clauses have limited enforceability; focus on IP assignment and confidentiality

#### 6. Contractor & Vendor Agreements
- **Purpose**: Define terms for independent contractors and vendor relationships
- **Key Elements**:
  - Scope of work and deliverables
  - Payment terms and schedule
  - IP ownership (work-for-hire provisions)
  - Confidentiality and NDA clauses
  - Indemnification and liability
  - Termination conditions
  - Insurance requirements (for contractors)
- **Use Case**: Engaging freelancers, contractors, service providers, or vendors
- **Action**: Required before any contractor or vendor begins work

#### 7. Employee Handbook
- **Purpose**: Document policies, expectations, and procedures for employees
- **Key Elements**:
  - Code of conduct and values
  - Work hours, leave, and benefits
  - Remote work policies
  - Security and acceptable use policies
  - Harassment and discrimination policies
  - Performance review process
  - Disciplinary procedures
  - Termination policies
- **Australian Compliance**: Must comply with Fair Work Act, Modern Awards, and National Employment Standards
- **Action**: Implement before hiring first employee

#### 8. PII Management Plan
- **Purpose**: Document how Personally Identifiable Information is handled
- **Key Elements**:
  - PII inventory and classification
  - Access controls and authorization
  - Retention and deletion policies
  - Incident response procedures
  - Third-party processor management
- **Compliance**: Required for GDPR, HIPAA, SOC 2, and other frameworks

#### 9. Information Security Management System (ISMS) Plan
- **Purpose**: Systematic approach to managing information security
- **Key Elements**:
  - Security policies and procedures
  - Risk assessment methodology
  - Asset management
  - Access control procedures
  - Incident management
  - Business continuity planning
- **Standard**: Based on ISO 27001 framework
- **Recommendation**: Start simple, build comprehensively over time

### Legal Document Priority

| Priority | Document | When to Implement |
|----------|----------|------------------|
| 1 | CIIA/PIIA | Before any work begins |
| 2 | Privacy Policy | Before collecting any data |
| 2.5 | DPA (Data Processing Agreement) | Before processing B2B customer data (EU/AU) |
| 3 | Terms of Service | Before accepting users |
| 4 | PII Management Plan | Before handling customer data |
| 4.5 | Contractor & Vendor Agreements | Before engaging contractors/vendors |
| 5 | Employee Handbook | Before hiring first employee |
| 6 | MSA | Before engaging B2B customers |
| 7 | ISMS Plan | Within first 6 months of operation |

---

## Infrastructure & Identity Management

### Cloud Infrastructure Management

#### Taikun.cloud / Foreman
- **Purpose**: Multi-cloud Kubernetes management and infrastructure automation
- **Use Case**: Managing infrastructure across multiple cloud providers
- **Best For**: Organizations with hybrid or multi-cloud strategies

### Security & Monitoring

#### Wazuh
- **Purpose**: Security monitoring, threat detection, compliance
- **Key Features**:
  - Host-based intrusion detection (HIDS)
  - Log analysis and SIEM capabilities
  - File integrity monitoring
  - Compliance reporting (PCI DSS, HIPAA, GDPR)
- **Recommendation**: **Essential** for security-conscious organizations

#### Tetragon
- **Purpose**: eBPF-based security observability and runtime enforcement
- **Key Features**:
  - Real-time security observability
  - Runtime enforcement
  - Network and process monitoring
- **Best For**: Kubernetes environments, advanced security teams

#### OpenMSP.ai (Openframe-oss-tenant)
- **Purpose**: Open-source managed service provider platform
- **Use Case**: MSPs and organizations managing multiple tenants

### Observability & Operational Monitoring

**Critical Requirement**: Structured logging, metrics collection, and distributed tracing are **foundational infrastructure requirements**, not optional add-ons. Implement from day one to enable debugging, performance optimization, and incident response.

#### Logging

**Purpose**: Centralized log aggregation, search, and analysis

**Recommended Solutions**:
- **ELK Stack** (Elasticsearch, Logstash, Kibana)
  - Industry standard, powerful search
  - Self-hostable or managed (Elastic Cloud)
  - Resource-intensive

- **Loki** (Grafana Loki)
  - Lightweight, cost-effective alternative to ELK
  - Integrates with Grafana
  - Less resource-intensive
  - **Recommended** for most startups

- **Managed Alternatives**: Datadog, New Relic, Splunk (expensive but turnkey)

**Best Practices**:
- Structured logging (JSON format)
- Correlation IDs for request tracing across services
- Log levels (DEBUG, INFO, WARN, ERROR)
- Retention policies (30-90 days minimum, 1+ year for compliance)
- Aggregation by service, environment, severity

#### Metrics Collection

**Purpose**: Time-series metrics for performance monitoring and alerting

**Recommended Solutions**:
- **Prometheus** + **Grafana**
  - Industry standard for metrics
  - Excellent for Kubernetes/containerized environments
  - Self-hostable
  - **Highly Recommended**

- **Managed Alternatives**: Datadog, New Relic, CloudWatch

**Key Metrics**:
- Application: Request rate, error rate, latency (RED metrics)
- Infrastructure: CPU, memory, disk, network (USE metrics)
- Business: User signups, transactions, revenue

**Best Practices**:
- Instrument all services from day one
- Set up alerting thresholds
- Dashboard for key metrics
- Regular review and refinement

#### Distributed Tracing

**Purpose**: Track requests across microservices and distributed systems

**Recommended Solutions**:
- **Jaeger**
  - Open-source, CNCF project
  - Good Kubernetes integration
  - Self-hostable

- **Tempo** (Grafana Tempo)
  - Lightweight, cost-effective
  - Integrates with Grafana ecosystem
  - **Recommended** if using Loki and Grafana

- **Managed Alternatives**: Datadog APM, New Relic, Honeycomb

**When You Need It**:
- Microservices architecture (3+ services)
- Performance debugging across services
- Complex request flows

**Best Practices**:
- Use OpenTelemetry for instrumentation
- Correlation IDs across all logs and traces
- Sample traces intelligently (not 100%)
- Integrate with alerting

#### Observability Stack Recommendations

**For Startups (Seed Stage)**:
- **Logging**: Grafana Loki
- **Metrics**: Prometheus + Grafana
- **Tracing**: Grafana Tempo (when needed)
- **Cost**: ~$50-200/month (self-hosted on VPS)

**For Growing Companies (Series A+)**:
- **Option 1 (Self-Hosted)**: ELK + Prometheus + Jaeger
- **Option 2 (Managed)**: Datadog or New Relic (all-in-one)
- **Cost**: $500-5000+/month depending on scale

**Instrumentation Libraries**:
- **Python**: OpenTelemetry Python
- **Node.js**: OpenTelemetry JS
- **Go**: OpenTelemetry Go
- **Java**: OpenTelemetry Java

### Identity & Access Management

#### FreeIPA
- **Purpose**: Identity, policy, and audit management for Linux/Unix
- **Key Features**:
  - Centralized authentication
  - LDAP directory
  - Kerberos authentication
  - Certificate management
- **Best For**: Organizations with significant Linux infrastructure

#### Keycloak
- **Purpose**: Open-source identity and access management
- **Key Features**:
  - Single Sign-On (SSO)
  - Identity brokering
  - User federation
  - Social login integration
  - OAuth 2.0 / OpenID Connect
- **Recommendation**: **Recommended** for application authentication

#### Microsoft 365 (M365)
- **Purpose**: Productivity suite and identity management
- **Key Features**:
  - Azure Active Directory integration
  - Office applications
  - Email and collaboration
  - Enterprise-grade security
- **Best For**: Organizations with Windows infrastructure or enterprise needs

#### OpenCode / OpenDesk.eu
- **Purpose**: Open-source digital workplace solutions
- **Best For**: Organizations prioritizing open-source and European data sovereignty

### IAM Decision Guide

| Use Case | Recommended Solution |
|----------|---------------------|
| Application authentication | Keycloak |
| Linux/Unix infrastructure | FreeIPA |
| Enterprise productivity | Microsoft 365 |
| Multi-application SSO | Keycloak + M365 integration |
| EU data sovereignty | OpenDesk.eu |

---

## Business Formation

**Note**: This guide is tailored for **Australian startups**. If you're planning to raise US venture capital, you'll likely need to establish a Delaware C-Corp later (see "VC Fundraising Considerations" below).

### Critical First Steps

#### 1. Register a Pty Ltd Company (Australia)
- **Priority**: **Do this ASAP**
- **Why Pty Ltd**:
  - Limited liability protection (separates personal and business assets)
  - Professional credibility with customers and partners
  - Required for business banking
  - Tax benefits (company tax rate 25-30% vs. individual rates)
  - Ability to raise investment
- **Registration Process**:
  - Register via **ASIC** (Australian Securities and Investments Commission)
  - Can use online services (ASIC Connect) or accountant/lawyer
  - Cost: ~$500-600 registration fee
  - Timeline: 1-3 business days
- **Requirements**:
  - Choose and reserve company name (check ASIC register)
  - Registered office address (can be home address or accountant's address)
  - At least 1 director (must be Australian resident)
  - At least 1 shareholder
  - Company constitution or adopt replaceable rules
  - ACN (Australian Company Number) issued automatically
  - ABN (Australian Business Number) - apply separately via ATO
  - TFN (Tax File Number) for the company
- **Timeline**: Complete within first 30 days of business operations

**VC Fundraising Considerations**:
- If raising from **US venture capital**, you'll typically need a **Delaware C-Corp**
- Structure: Australian Pty Ltd as operating company, Delaware C-Corp as holding company ("flip" structure)
- **When to flip**: Before first US VC round (Seed/Series A)
- **Cost**: $5,000-20,000 in legal fees for proper structure
- Consult startup lawyer familiar with AU→US flips before raising US VC

#### 2. Open a Company Bank Account
- **Priority**: **Immediately after company registration**
- **Why It Matters**:
  - Separates personal and business finances
  - Essential for accounting and taxes
  - Required for professional credibility
  - Protects limited liability shield
  - Compliance with ATO (Australian Taxation Office) requirements
- **Requirements**:
  - ASIC company registration documents
  - ACN and ABN
  - Director identification
  - Proof of business address
  - Company constitution or replaceable rules

**Banking Recommendations by Region & Stage**:

### Australia (Domestic Focus)
- **Startups / Early Stage**:
  - **Up Bank** (digital-first, excellent UX, fee-free)
  - **Judo Bank** (SME-focused, good startup support)
  - **Xero integration**: Most AU banks integrate

- **Growing / Traditional**:
  - **CommBank** (Commonwealth Bank) - Best overall for business
  - **NAB** (National Australia Bank) - Good business banking
  - **Westpac** or **ANZ** - Alternatives

- **International / Multi-Currency**:
  - **Wise Business** (formerly TransferWise) - Best FX rates, multi-currency
  - **Airwallex** (Australian fintech, great for international payments)

### If Raising US VC / International Focus
- **Stripe Atlas** + **Mercury** or **Brex** for US entity
- Keep Australian Pty Ltd with Australian bank
- Dual structure requires intercompany agreements

### Other Regions (Reference)

**United States**:
- Mercury (tech-focused, excellent for startups)
- Brex (if raising venture capital, corporate cards)
- Chase, Wells Fargo (traditional, established businesses)

**Europe**:
- Revolut Business (multi-currency, excellent FX)
- Wise Business (best international transfers)
- N26 Business (Germany/EU)
- Local challenger banks by country

**Asia-Pacific (outside AU)**:
- Wise Business (best cross-border)
- Regional digital banks (e.g., DBS in Singapore)
- Major local banks for compliance/regulation

**Latin America**:
- Local neobanks (country-specific)
- Wise Business for international
- Major regional banks (Itaú, Banco do Brasil, etc.)

**Banking Decision Factors**:
- **Startup stage**: Early-stage → digital banks (Up, Airwallex); Later → traditional (CommBank, NAB)
- **VC requirements**: US VCs may require US bank account
- **Multi-currency needs**: Wise, Airwallex for best FX rates
- **Local regulation**: Always maintain local-regulated bank for compliance
- **Integration**: Check accounting software integration (Xero, ERPNext)

### Business Formation Checklist (Australia)

- [ ] Choose company name and check ASIC availability
- [ ] Register Pty Ltd company with ASIC
- [ ] Obtain ACN (issued automatically)
- [ ] Apply for ABN via ATO
- [ ] Apply for company TFN
- [ ] Draft or adopt company constitution
- [ ] Open business bank account (Up, Judo, CommBank, or Wise)
- [ ] Set up business accounting system (Xero or ERPNext - Xero very popular in AU)
- [ ] Register for GST (if expecting $75k+ revenue, or voluntary)
- [ ] Set up PAYG withholding (if hiring employees)
- [ ] Obtain necessary business licenses and permits
- [ ] Set up business insurance (public liability, professional indemnity, cyber)
- [ ] Register domain name and trademarks (IP Australia)
- [ ] Set up super fund for directors/employees (superannuation obligations)

**Australian-Specific Compliance**:
- **Fair Work Act**: Employment law compliance
- **Superannuation Guarantee**: 11.5% (as of 2024-25) employer contributions
- **PAYG Withholding**: Tax withholding for employees
- **GST**: Register if turnover >$75k (or voluntary)
- **Single Touch Payroll (STP)**: Required for payroll reporting to ATO

---

## Network & Security Infrastructure

### VPN & Secure Access Solutions

Modern zero-trust networking requires secure, scalable remote access. Consider these options:

#### NetBird VPN
- **Type**: WireGuard-based mesh VPN
- **Best For**: Teams needing simple, secure connectivity
- **Key Features**:
  - Automatic WireGuard mesh network
  - Easy deployment
  - Self-hostable
  - Modern architecture

#### Boundary (bound0)
- **Type**: Zero-trust access management
- **Best For**: Organizations with complex access requirements
- **Key Features**:
  - Identity-based access
  - Session recording
  - Dynamic credential injection
  - Multi-cloud support

#### Tailscale / Headscale
- **Type**: WireGuard-based mesh VPN
- **Tailscale**: Commercial SaaS
- **Headscale**: Open-source, self-hosted Tailscale control server
- **Key Features**:
  - Zero-configuration mesh networking
  - MagicDNS
  - ACL-based access control
  - Excellent mobile support
- **Recommendation**: **Tailscale for ease**, **Headscale for privacy/control**

#### Pangolin (Self-Host)
- **Type**: Self-hosted VPN solution
- **Best For**: Organizations requiring full control
- **Key Features**: Complete data sovereignty, customizable

### VPN Selection Guide

| Organization Profile | Recommended Solution |
|---------------------|---------------------|
| Small team (< 10) | Tailscale (commercial) |
| Privacy-conscious, technical | Headscale |
| Complex access policies | Boundary |
| Simple mesh networking | NetBird |
| Maximum control | Pangolin or Headscale |

### Network Security Best Practices

1. **Implement Zero Trust**: Never trust, always verify
2. **Segment Networks**: Separate production, staging, and development
3. **Monitor Traffic**: Use Wazuh or similar SIEM
4. **Regular Audits**: Quarterly access reviews
5. **MFA Everywhere**: No exceptions for production access

---

## Operational Management Frameworks

### Service Management Plan (SMP)

A Service Management Plan defines how your organization delivers services to customers.

#### Key Components:
- **Service Catalog**: All services offered
- **Service Level Agreements (SLAs)**: Performance commitments
- **Incident Management**: How issues are handled
- **Change Management**: How changes are controlled
- **Problem Management**: Root cause analysis process
- **Capacity Management**: Resource planning
- **Availability Management**: Uptime and reliability targets

#### Implementation Priority: Year 1

### Quality Management System (QMS)

A QMS ensures consistent delivery of quality products and services.

#### Key Components:
- **Quality Policy**: Organization's quality commitment
- **Quality Objectives**: Measurable quality goals
- **Process Documentation**: Standard operating procedures
- **Quality Control**: Testing and validation processes
- **Continuous Improvement**: Feedback loops and metrics
- **Customer Satisfaction**: Measurement and response

#### Standards: ISO 9001
#### Implementation Priority: Year 1-2

### Human Resources Management

#### Hiring Process
**Key Stages**:
1. Role definition and job description
2. Candidate sourcing
3. Screening and initial interviews
4. Technical assessment (for technical roles)
5. Team interviews
6. Background and reference checks
7. Offer negotiation
8. Onboarding

**Best Practices**:
- Define clear hiring criteria
- Use structured interviews
- Include diverse interview panels
- Document decisions
- Provide timely feedback

#### Performance Improvement Plans (PIPs)
**Purpose**: Support struggling employees to improve performance

**Key Elements**:
- Clear performance deficiencies documented
- Specific, measurable improvement goals
- Timeline (typically 30-90 days)
- Regular check-ins and feedback
- Resources and support provided
- Consequences of non-improvement

**Best Practices**:
- Document everything
- Be fair and consistent
- Provide genuine support
- Involve HR

#### Termination Process
**Key Stages**:
1. Documentation review (PIPs, warnings, incidents)
2. Legal consultation
3. Final decision and approval
4. Termination meeting (with witness)
5. Access revocation (immediate)
6. Equipment return
7. Exit interview
8. Final paycheck and benefits paperwork

**Best Practices**:
- Ensure legal compliance
- Revoke all access immediately
- Be respectful but firm
- Document the conversation
- Have security plan if needed

---

## Compliance Management Systems

### Overview

Compliance management systems demonstrate your commitment to security, privacy, and quality. They're often required for enterprise sales and regulatory compliance.

### Personal Information Management System (PIMS)

**Purpose**: Manage and protect personal data in compliance with privacy regulations

**Key Components**:
- Personal data inventory
- Data flow mapping
- Consent management
- Data subject rights fulfillment
- Privacy impact assessments
- Vendor management
- Breach notification procedures

**Relevant Regulations**: GDPR, CCPA, CPRA, LGPD
**Implementation Timeline**: Before handling customer PII

### Quality Management System (QMS)

**Purpose**: Ensure consistent quality in products and services

**Key Components**:
- Quality policy and objectives
- Process documentation
- Quality metrics and KPIs
- Internal audits
- Corrective and preventive actions (CAPA)
- Management review

**Standard**: ISO 9001
**Implementation Timeline**: Year 1-2
**Benefits**: Customer confidence, process efficiency, continuous improvement

### Service Management System (SMS)

**Purpose**: Standardize IT service delivery

**Key Components**:
- Service catalog
- Incident management
- Problem management
- Change management
- Release management
- Service level management

**Standard**: ISO 20000
**Implementation Timeline**: Year 1-2 for IT-centric businesses
**Benefits**: Improved service quality, reduced downtime, customer satisfaction

### Information Security Management System (ISMS)

**Purpose**: Systematically manage information security risks

**Key Components**:
- Information security policy
- Risk assessment and treatment
- Asset management
- Access control
- Cryptography controls
- Physical security
- Operations security
- Communications security
- System acquisition and development security
- Supplier relationships
- Incident management
- Business continuity
- Compliance management

**Standard**: ISO 27001
**Implementation Timeline**: Year 1-2
**Benefits**: Risk reduction, regulatory compliance, customer trust, cyber insurance eligibility

### AI Risk Management Framework (AI RMF)

**Purpose**: Manage risks associated with AI systems

**Based On**: NIST AI RMF / ISO 42001

**Key Components**:
- AI system inventory
- Risk assessment for AI systems
- Bias and fairness evaluation
- Transparency and explainability
- Data governance for AI
- AI lifecycle management
- Human oversight and control
- Incident response for AI failures
- Continuous monitoring

**Implementation Timeline**: Before deploying AI systems to production
**Benefits**: Responsible AI deployment, regulatory compliance, risk mitigation

### Compliance Framework Decision Matrix

| Your Business | Priority Frameworks |
|---------------|-------------------|
| SaaS / Software | ISMS, PIMS, SMS |
| Healthcare | ISMS, PIMS, QMS + **HIPAA** (see details below) |
| Financial Services | ISMS, PIMS, QMS + industry regulations (PCI DSS, SOX, etc.) |
| AI/ML Products | ISMS, PIMS, AI RMF |
| Professional Services | QMS, SMS, ISMS |
| E-commerce | PIMS, ISMS, QMS |

### HIPAA Compliance Requirements (Healthcare Organizations)

**⚠️ Critical**: If you handle Protected Health Information (PHI) in the **United States**, HIPAA compliance is **legally required**. Non-compliance can result in fines up to $1.5M per violation category per year.

**Australian Note**: Australia has the **Privacy Act** and **My Health Records Act**, not HIPAA. Consult healthcare legal specialists for Australian health data requirements. The following is US-focused.

**HIPAA-Specific Requirements**:

1. **Business Associate Agreements (BAAs)**
   - Execute BAAs with **all vendors** that access PHI (cloud providers, SaaS tools, contractors)
   - AWS, Google Cloud, Azure provide BAAs; ensure they're signed
   - Include BAA language in vendor contracts before PHI exposure
   - Maintain registry of all business associates

2. **Audit Logging & Retention**
   - **Requirement**: Log all PHI access, modifications, and disclosures
   - **Retention**: Minimum 6 years (HIPAA requirement)
   - **SIEM Integration**: Connect logs to Wazuh or similar SIEM for monitoring
   - **Access Controls**: Who accessed what PHI, when, and why
   - **Automated Alerts**: Unusual access patterns, bulk downloads

3. **Breach Notification Procedures**
   - **Timeline**: 60 days to notify affected individuals after breach discovery
   - **Requirements**: Notify HHS (Department of Health & Human Services) and individuals
   - **Documentation**: Maintain breach response playbook
   - **Media Notification**: Required if breach affects 500+ individuals
   - **Incident Response Plan**: Test annually

4. **Encryption Standards**
   - **Data at Rest**: AES-256 encryption for all PHI storage
   - **Data in Transit**: TLS 1.2+ for all PHI transmission
   - **Key Management**: Secure key storage (AWS KMS, HSM, etc.)
   - **Laptop/Mobile**: Full-disk encryption for any device accessing PHI

5. **Access Controls & Least Privilege**
   - **Role-Based Access Control (RBAC)**: Implement for all PHI access
   - **Minimum Necessary**: Users access only PHI needed for their role
   - **MFA Required**: Multi-factor authentication for all PHI access
   - **Session Timeouts**: Automatic logout after inactivity
   - **Unique User IDs**: No shared credentials

6. **Training & Risk Assessments**
   - **HIPAA Training**: Required for all workforce members handling PHI
   - **Frequency**: Annual training minimum, document completion
   - **Risk Assessments**: Annual HIPAA risk analysis (required)
   - **Security Risk Assessment (SRA)**: Identify vulnerabilities
   - **Documentation**: Maintain all training and assessment records

**🚨 Compliance Mandate**: If you're building a US healthcare product, **consult a healthcare compliance attorney or specialist immediately**. HIPAA violations carry severe penalties.

**Resources for HIPAA Compliance**:
- **HHS HIPAA Portal**: https://www.hhs.gov/hipaa/index.html
- **HIPAA Security Rule Checklist**: https://www.hhs.gov/hipaa/for-professionals/security/guidance/index.html
- **Compliancy Group, HIPAA One**: Third-party compliance platforms
- **Legal Counsel**: Engage healthcare-specialized attorney

### Implementation Roadmap

#### Months 1-3: Foundation
- [ ] Draft Privacy Policy and Terms of Service
- [ ] Draft DPA (Data Processing Agreement) if processing B2B customer data
- [ ] Implement CIIA/PIIA for all team members
- [ ] Begin PII Management Plan
- [ ] Start basic ISMS documentation
- [ ] **Healthcare**: Execute BAAs with all vendors before handling PHI
- [ ] **Healthcare**: Implement AES-256 encryption for data at rest
- [ ] **Healthcare**: Enforce TLS 1.2+ for data in transit

#### Months 4-6: Core Systems
- [ ] Establish basic QMS processes
- [ ] Complete PIMS framework
- [ ] Implement core SMS processes (if applicable)
- [ ] Conduct initial risk assessments
- [ ] **Healthcare**: Deploy audit logging system with 6-year retention
- [ ] **Healthcare**: Integrate audit logs with SIEM (Wazuh)
- [ ] **Healthcare**: Conduct initial HIPAA Security Risk Assessment (SRA)

#### Months 7-12: Maturity
- [ ] Complete ISMS implementation
- [ ] Achieve baseline compliance with relevant frameworks
- [ ] Conduct internal audits
- [ ] If using AI: Implement AI RMF
- [ ] **Healthcare**: Document breach response plan and notification playbooks
- [ ] **Healthcare**: Implement and test 60-day breach notification procedures
- [ ] **Healthcare**: Complete HIPAA workforce training (annual requirement)
- [ ] **Healthcare**: Verify RBAC and least privilege access controls

#### Year 2+: Certification & Optimization
- [ ] Pursue ISO certifications (27001, 9001, etc.)
- [ ] Achieve SOC 2 compliance (if B2B SaaS)
- [ ] Continuous improvement and optimization
- [ ] Regular audits and reviews
- [ ] **Healthcare**: Schedule external HIPAA compliance audit and legal review
- [ ] **Healthcare**: Annual HIPAA training and risk assessment (ongoing requirement)

---

## Financial & Business Tools

### Customer Relationship Management

#### Twenty CRM
- **Type**: Open-source CRM
- **Best For**: Small to medium businesses wanting self-hosted CRM
- **Key Features**:
  - Modern interface
  - Customizable
  - Self-hostable
  - Privacy-focused
- **Use Case**: Customer pipeline management, sales tracking

### Financial Management & Accounting

**Critical Decision**: Choose between integrated ERP (ERPNext) or dedicated financial tools based on your business model and complexity.

#### Decision Framework: ERPNext vs. Dedicated Tools

**Choose ERPNext (Integrated ERP) if:**
- You sell **physical products** (need inventory management)
- You **manufacture** anything (need BOM, production planning)
- You need **CRM + Accounting + Inventory** in one system
- You're a **growing business** (10+ people) wanting unified system
- You want to **consolidate multiple tools** into one platform
- **Australian context**: Works well, though Xero is more common for pure accounting

**Choose Invoice Ninja if:**
- **Freelancer** or **solo consultant** (<5 people)
- **Services business** (consulting, agency, no inventory)
- You need **invoicing + expenses** only (not full accounting)
- You want **self-hosted** lightweight solution
- You prefer dedicated tool over full ERP

**Choose Xero (Australia-Specific) if:**
- You need **Australian tax compliance** (BAS, GST, STP, superannuation)
- You're a **services or consulting business** (no inventory/manufacturing)
- Your **accountant recommends it** (most AU accountants use Xero)
- You want **cloud-based** accounting with excellent AU bank integrations
- **Pricing**: $30-70/month AUD
- **Recommendation**: **Most popular for Australian small businesses**

**Choose QuickBooks if:**
- You're in a **US market** or have US entity
- Need US tax compliance
- **Alternative**: Less popular in Australia vs. Xero

**Choose MYOB if:**
- **Older Australian businesses** (legacy, less common for startups)
- Specific industry requirements
- **Note**: Xero has largely overtaken MYOB for startups

#### Recommended Path by Business Type

| Business Type | Team Size | Recommended Solution |
|---------------|-----------|---------------------|
| Freelancer / Consultant | 1-3 | Invoice Ninja or Xero |
| Services / Agency | 4-10 | Xero (AU) or ERPNext |
| SaaS (no inventory) | Any | Xero + Stripe Billing, or ERPNext |
| E-commerce | Any | ERPNext (inventory + accounting) |
| Manufacturing | Any | ERPNext (BOM + inventory + accounting) |
| Physical Products | Any | ERPNext (inventory + accounting) |

#### Invoice Ninja (Invoicing & Expenses)
- **Type**: Invoicing and billing
- **Best For**: Freelancers, agencies, service businesses (<10 people)
- **Key Features**:
  - Invoice generation
  - Payment processing (Stripe, PayPal)
  - Expense tracking
  - Time tracking
  - Client portal
  - Self-hostable or cloud
  - **Not full accounting** (no chart of accounts, tax reporting)
- **Pricing**: Free (self-hosted) or $10-15/month (cloud)
- **When to Use**: Simple invoicing needs, not full accounting

#### Xero (Australia - Accounting)
- **Type**: Cloud accounting platform
- **Best For**: Australian small businesses, services, consulting
- **Key Features**:
  - Full double-entry accounting
  - GST, BAS, and STP compliance
  - Superannuation integration
  - Bank reconciliation (excellent AU bank support)
  - Payroll (add-on)
  - Invoicing included
  - Accountant collaboration (most AU accountants use Xero)
- **Pricing**: $30-70/month AUD (Starter, Standard, Premium)
- **Australian Recommendation**: **Default choice for most Australian startups**
- **Website**: https://www.xero.com/au/

#### ERPNext (Integrated ERP - Accounting + Everything)
- **Type**: Full ERP suite (accounting, inventory, CRM, HR, manufacturing)
- **Best For**: Product businesses, manufacturers, growing companies wanting integration
- **Key Features**:
  - Complete accounting (chart of accounts, journal entries, financial reports)
  - Inventory management
  - CRM and sales
  - Purchase and supply chain
  - Manufacturing (BOM, work orders)
  - Payroll and HR
  - Multi-currency
  - Self-hostable or Frappe Cloud
- **Pricing**: Free (self-hosted) or $10-50/user/month (Frappe Cloud)
- **Australian Tax**: Requires configuration for AU tax compliance (GST, STP)
- **When to Use**: Need integrated business system beyond just accounting

**Our Recommendation for Australian Startups**:
- **Services/Consulting (1-10 people)**: **Xero** (industry standard in AU)
- **Product/E-commerce/Manufacturing**: **ERPNext** (integrated inventory + accounting)
- **Solo Freelancer (budget-conscious)**: **Invoice Ninja** (just invoicing, add Xero when revenue grows)

### Automation & Workflow

#### n8n
- **Type**: Workflow automation (self-hosted)
- **Best For**: Technical teams wanting full control
- **Key Features**:
  - Visual workflow builder
  - 200+ integrations
  - Self-hostable
  - No data sharing with third parties
- **Recommendation**: **Recommended** for automation needs

#### ActivePieces
- **Type**: Workflow automation (open-source)
- **Best For**: Teams wanting Zapier alternative
- **Key Features**:
  - Open source
  - Self-hostable
  - User-friendly interface
  - Growing integration library

#### Tines
- **Type**: Security automation platform
- **Best For**: Security teams, SOC automation
- **Key Features**:
  - Security-focused workflows
  - Incident response automation
  - Threat intelligence integration
- **Use Case**: Security operations, incident response

### Scheduling & Meetings

#### Cal.com
- **Type**: Open-source scheduling platform
- **Best For**: Teams wanting Calendly alternative
- **Key Features**:
  - Self-hostable
  - Calendar integration
  - Payment collection
  - Custom branding
- **Recommendation**: Excellent for customer meetings and demos

### Trust & Security Center

#### TrustCloud.ai
- **Type**: Compliance automation platform
- **Best For**: Companies pursuing SOC 2, ISO 27001, GDPR compliance
- **Key Features**:
  - Automated evidence collection
  - Policy template library
  - Continuous compliance monitoring
  - Security questionnaire automation
- **Use Case**: Accelerating compliance certification

---

## Putting It All Together

### Startup Stage Recommendations

#### Pre-Seed / Bootstrapped (0-2 people)

**🎯 Goal**: Ship fast, validate product-market fit, spend $0-50/month

**Free Tier Stack** (Recommended):
- **Hosting**: Cloudflare Pages or Vercel (100GB bandwidth free)
- **CDN**: Cloudflare (unlimited, free DDoS protection, SSL)
- **Database**: Supabase (500MB Postgres, auth, storage - free)
- **Auth**: Supabase Auth or Clerk (50k/10k MAUs free)
- **Source Control**: GitHub (unlimited repos, 2k CI/CD minutes free)
- **Error Tracking**: Sentry (5k errors/month free)
- **Monitoring**: Better Stack (1GB logs, 10 uptime monitors free)
- **Email**: Resend (100 emails/day free) or SendGrid (100/day free)
- **LLMs**: OpenRouter (free models: Llama, Mistral)
- **Analytics**: Cloudflare Analytics (free) or Plausible (self-hosted)

**Technical Infrastructure**:
- Deploy to Vercel/Cloudflare Pages (no VPS needed yet)
- OR Docker Compose on cheap VPS if self-hosting ($5-10/month)
- Structured logging from day one (use Sentry + Better Stack free tiers)

**Developer Tools** (All Free):
- GitHub (source control, CI/CD, project management, security scanning)
- GitHub Copilot (if budget allows: $10/month, huge productivity boost)
- Figma (design - free for individuals)
- v0.dev (AI UI generation - limited free credits)
- Cal.com (scheduling - self-hosted or free tier)

**Legal (Australia)**:
- Register Pty Ltd (if taking on co-founders or contractors)
- Open business bank account (Up, Judo, or CommBank)
- Privacy Policy (required before collecting data)
- Terms of Service (required before accepting users)
- CIIA for founders (before any work begins)

**Accounting**:
- Invoice Ninja (if just invoicing - free self-hosted) or
- Xero (if need full accounting - $30-70/month AUD)

**Monthly Cost Estimate**: **$0-50**
- $0 if using all free tiers
- $30-70 if using Xero
- $10 if using GitHub Copilot
- $5-10 if self-hosting on VPS instead of Vercel/Cloudflare

**Priority**: Ship product, get customers, validate with real users

**What You Can Build for Free**:
- Full-stack SaaS app (up to 10k users)
- Static/marketing website (unlimited traffic)
- API service (100k requests/day on Cloudflare Workers)
- AI-powered app (using free LLM models)

**When to Start Paying**:
- Supabase: >500MB database or >50k MAUs → $25/month
- Vercel: >100GB bandwidth → $20/month
- Sentry: >5k errors/month → $26/month
- Clerk: >10k MAUs → $25/month

**Note**: If solo and not hiring yet, you can delay Pty Ltd registration until first hire or funding round. Use sole trader structure initially if needed.

#### Seed Stage (3-10 people)

**🎯 Goal**: Professionalize operations, enable team collaboration, $200-1000/month

**Developer Platform Transition**:
- **Keep free tiers**: Cloudflare (still free), GitHub (still free), Sentry (may need upgrade)
- **Upgrade when needed**: Supabase Pro ($25/month), Vercel Pro ($20/month if >100GB)
- **Consider**: Migrate to self-hosted if hitting limits (Postgres, app hosting)

**Technical Infrastructure**:
- Docker or Proxmox (if self-hosting)
- OR continue with Vercel/Cloudflare + upgrade tiers
- Proper staging/production separation
- **Observability from day one**: Loki (logging), Prometheus + Grafana (metrics)
- VPN for infrastructure access (Tailscale or Headscale)

**Tools**:
- Jira or Linear (project management)
- ERPNext or Xero (Australian accounting)
- Twenty CRM or dedicated CRM
- n8n for automation
- Full security toolchain (Snyk, Dependabot, GitGuardian)
- **Continue using**: Sentry (upgrade to Developer $26/month if needed)

**Observability & Monitoring**:
- **Logging**: Deploy Grafana Loki for centralized logs
- **Metrics**: Prometheus + Grafana for application and infrastructure metrics
- **Instrumentation**: Add OpenTelemetry to all services
- **Alerting**: Set up alerts for errors, latency, resource usage
- **Correlation IDs**: Implement across all services for request tracing

**Legal**:
- All foundational legal docs (Privacy Policy, ToS, DPA, CIIA)
- Contractor & Vendor Agreements
- Employee Handbook
- PII Management Plan
- Basic ISMS

**Compliance**:
- Start PIMS
- Begin QMS processes

**Australian-Specific**:
- Register Pty Ltd
- Open business bank account (Up, Airwallex, or CommBank)
- Set up Xero or ERPNext for accounting
- GST registration (if >$75k revenue)
- Superannuation fund for employees

#### Series A+ (10+ people)
**Technical Infrastructure**:
- Kubernetes (managed or self-hosted)
- Multi-environment (dev/staging/prod)
- Wazuh for security monitoring
- High availability and disaster recovery

**Observability & Monitoring**:
- **Full observability stack**: ELK or Loki (logging), Prometheus (metrics), Jaeger/Tempo (tracing)
- **Or managed**: Datadog, New Relic all-in-one
- **On-call rotation**: PagerDuty or similar
- **Incident management**: Formal incident response process

**Tools**:
- Full stack as outlined in guide
- Dedicated security team
- Formal incident response
- ERPNext or enterprise ERP
- Full HR systems

**Legal & Compliance**:
- Full ISMS implementation
- SOC 2 Type II (if B2B)
- ISO 27001 preparation or certification
- Complete QMS
- SMS implementation
- AI RMF (if applicable)

**Business**:
- Formal HR processes
- Legal counsel on retainer
- Dedicated compliance team

**Australian-Specific**:
- Consider Delaware C-Corp flip if raising from US VCs
- Ensure Fair Work Act compliance
- Implement Enterprise Agreement if 15+ employees

---

## Critical Success Factors

### 1. Start With Legal Foundation (Australia)
- Register Pty Ltd before hiring or raising funds
- Implement CIIA/PIIA before any work begins (employees and contractors)
- Privacy Policy and ToS before collecting user data
- DPA before processing B2B customer data
- Contractor Agreements before engaging contractors

### 2. Security From Day One
- Enable all free security tools (Dependabot, etc.)
- Implement proper access controls
- Use VPN for all infrastructure access
- Regular security reviews

### 3. Document Everything
- Decisions
- Processes
- Incidents
- Changes

### 4. Automate Ruthlessly
- CI/CD from the start
- Infrastructure as Code
- Automated testing
- Workflow automation with n8n or similar

### 5. Build for Compliance
- Easier to start compliant than retrofit
- Document as you go
- Regular audits
- Continuous improvement

### 6. Invest in People Systems
- Clear hiring process
- Proper onboarding
- Regular feedback
- Fair, documented performance management

---

## Resources & Next Steps

### Recommended Reading
- ISO 27001 standard documentation
- NIST Cybersecurity Framework
- NIST AI Risk Management Framework
- Your industry-specific regulations (HIPAA, PCI DSS, etc.)

### Professional Services to Consider
- Legal counsel specializing in tech/startups
- Compliance consultants (for SOC 2, ISO certifications)
- Fractional CFO
- Fractional CISO (as you scale)

### Community Resources
- r/entrepreneur
- r/startups
- r/devops
- r/netsec

---

## Conclusion

Building a comprehensive business operating system is an iterative process. Start with the essentials:

### For Australian Startups:

1. **Start with free tiers** (Pre-Seed: $0-50/month)
   - Cloudflare (CDN, DDoS, SSL - free forever)
   - Vercel or Cloudflare Pages (hosting - 100GB free)
   - Supabase (database + auth - 500MB free)
   - GitHub (source control + CI/CD - 2k minutes free)
   - Sentry (error tracking - 5k errors free)
   - Better Stack (logs + uptime - 1GB free)
   - OpenRouter (free LLM models available)

2. **Legal foundation**
   - Register Pty Ltd (before hiring or funding)
   - Open business bank account (Up, Judo, CommBank, or Airwallex)
   - Implement CIIA/PIIA before any work begins
   - Draft Privacy Policy and ToS before collecting data
   - Set up Xero or ERPNext for accounting
   - Register for GST (if >$75k revenue or voluntary)

3. **Security basics** (mostly free)
   - Enable all free security tools (Dependabot, GitGuardian, Snyk free tiers)
   - Implement proper access controls
   - MFA everywhere
   - Sentry for error tracking (free tier sufficient early on)

4. **Observability from day one**
   - Structured logging (Sentry + Better Stack free tiers, then Loki)
   - Metrics (Prometheus + Grafana when self-hosting)
   - Correlation IDs across services

5. **Core infrastructure** (appropriate to your scale)
   - Pre-Seed: Vercel/Cloudflare Pages (free) or Docker Compose ($5-10/month VPS)
   - Seed: Upgrade free tiers or migrate to Docker/Proxmox
   - Series A+: Kubernetes

6. **Essential tools**
   - GitHub (source control - free)
   - Jira or Linear (project management)
   - Xero or ERPNext (accounting)
   - n8n (automation)

7. **Documentation habits**
   - Policies, procedures, decisions
   - Employee handbook
   - Contractor agreements

Then build systematically toward mature compliance and management systems as you grow. The key is to start with good foundations and iterate continuously.

### The Free Tier Advantage

**You can build a production-ready SaaS for $0-50/month** using the generous free tiers from:
- Cloudflare (CDN, Workers, Pages, R2, D1)
- Vercel or Netlify (hosting, serverless functions)
- Supabase (Postgres, auth, storage, realtime)
- GitHub (source control, CI/CD, security)
- Sentry (error tracking)
- OpenRouter (free LLM models)

This means you can **validate your idea and reach your first 1,000 users without spending money on infrastructure**. Only upgrade when you hit limits or need advanced features.

### Raising US Venture Capital?

If you're planning to raise from US VCs, consult a startup lawyer familiar with AU→US flips **before** your first fundraising round. You'll likely need to establish a Delaware C-Corp holding structure, which costs $5,000-20,000 in legal fees but is standard for US venture-backed companies.

### Remember

Your business operating system should enable your team to work efficiently, securely, and in compliance with Australian regulations—without creating unnecessary overhead. Choose tools and processes that scale with your business.

**Don't over-engineer**: Start simple (Docker Compose, Xero, GitHub), scale smartly (Kubernetes, ERPNext, full observability stack) only when needed.

---

**Document Version**: 2.1 (Australian Edition + Free Tier Focus)
**Last Updated**: 2025-11-17
**Target Audience**: Australian Startups
**Maintained By**: Community

**Version 2.1 Changes**: Added comprehensive developer platform coverage (GitHub, Cloudflare, Vercel, Supabase, Neon, Clerk, Sentry, Better Stack, OpenRouter, v0.dev) with focus on free tiers and upgrade paths.
