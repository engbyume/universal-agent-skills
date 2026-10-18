---
name: platform-architecture
description: Conditional backend, database, distributed-systems, deployment, and operations guidance for websites, apps, games, APIs, and AI services. Use when choosing system boundaries, traffic patterns, data consistency, scaling, delivery, or recovery practices.
---

# Platform Architecture

## Purpose and selection rules

Use this skill to choose architecture patterns that solve measured product needs. It is a decision guide, not a checklist that every project must implement.

- At the start of a new public website or app project, clarify the product goal, audience, success outcome, existing tools and data, and launch needs before selecting services. Reuse details already supplied and ask only for material gaps.
- Recommend relevant provider accounts and integrations, such as a cloud, CRM, identity, payments, analytics, or email service, and explain fit, sign-in needs, and cost. Tell the user before the first provider login. Never request credentials in chat or create accounts or paid resources without authorization.
- Prefer one current supported path. Do not add fallback implementations or backward-compatibility layers for hypothetical clients or versions. Preserve real user data and verified external contracts.

- Preserve the working stack unless the user asks for a change or evidence shows a real constraint.
- Define workload, data sensitivity, tenant boundaries, traffic, latency and availability needs, recovery objectives, operating capacity, and cost limits before adding infrastructure.
- Prefer the smallest architecture that meets those constraints. Do not add microservices, sharding, Kubernetes, multi-region deployment, or a service mesh for appearance.
- For new web products, use the user's stack preferences: React, TypeScript, Tailwind, and shadcn where they fit; Python, FastAPI, SQLAlchemy, and PostgreSQL for new back ends; managed PostgreSQL on AWS, GCP, or Azure. Do not default to Supabase.
- Compare current official provider features and pricing. RDS, ECR, ECS, a load balancer, and Amplify are options, not automatic requirements. Tell the user before a first cloud login is needed. Do not create paid resources without approval for the specific scope and cost.
- Appify is preferred for general scraping or downloads when available. Use Firecrawl for known-URL extraction or multi-page crawls. These are research tools, not runtime services.

## Request paths, caching, and protocols

- Use a reverse proxy for traffic forwarding and edge policy. Use a load balancer to distribute requests across healthy instances. Use an API gateway when shared routing, authentication, quotas, or API policy are needed. Keep business logic in the application.
- Add service discovery when instances change dynamically or static addresses become unreliable. Prefer managed discovery when it meets the need.
- Use a CDN for static or safely cacheable content. Define edge-cache keys, TTLs, invalidation, stale-data behavior, and tenant or authorization boundaries before sharing cached responses.
- Apply rate limiting to abuse-sensitive, costly, or capacity-limited actions. Choose the key and quota from the threat model. A process-local limiter does not coordinate across replicas.
- Choose DNS, TCP or UDP, HTTP/2 or HTTP/3, and gRPC from client support, protocol needs, and measured performance.
- When a product feature requires user-visible live data, use server push or a managed subscription instead of client polling. Choose WebSockets for two-way or high-frequency interaction, Server-Sent Events for one-way server updates, or a platform's reactive subscription when it fits the data model. Do not use periodic polling or long polling as a fallback for live UI.
- Convex reactive queries and Supabase Realtime are examples, not default backend choices. Preserve the managed PostgreSQL preference by comparing cloud-native options such as AWS AppSync subscriptions or Azure Web PubSub when they fit better.
- Authorize subscriptions on the server and scope channels to the user or tenant. Clean up subscriptions, reconnect with bounded backoff, detect missed events, and refresh from the authorized source of truth after reconnect. Compare connection, message, fan-out, and egress costs.
- Add API versioning only when multiple consumers or a published contract require it. Do not create version shims for hypothetical clients. State any required support window and use semantic versioning for packages or contracts when it fits. Keep webhooks authenticated, bounded, idempotent, and safe to retry.

## Reliability and asynchronous work

- Set explicit timeouts and an end-to-end deadline for each request.
- Retry only transient failures, with bounded attempts, exponential backoff, jitter, cancellation, and the remaining deadline. Do not retry permanent errors or non-idempotent actions without deduplication.
- Use circuit breakers when repeated downstream failures could exhaust local resources. Define open and recovery behavior. Add a degraded mode only when the product requires it; do not add generic fallback paths for hypothetical failures.
- Use message queues for durable asynchronous work and backpressure. Use pub/sub when one event needs independent subscribers. Event-driven architecture fits when producers and consumers need temporal or ownership separation.
- Expect duplicate delivery unless the system proves otherwise. Make consumers idempotent, align acknowledgements with durable processing, bound payloads and retention, and monitor queue depth and age.
- Use dead-letter queues or quarantine for poison messages. Restrict replay access and make reprocessing safe.
- Use cron jobs for scheduled work when their cadence is sufficient. Make jobs idempotent, define overlap behavior, set timeouts, and record missed runs.
- Prefer a database transaction plus an outbox or inbox to an assumed distributed transaction across a database and broker. Use a Saga Pattern when a multi-step operation needs explicit compensating actions and visible intermediate state.
- Treat exactly-once processing as an end-to-end property to demonstrate. A broker guarantee alone does not make side effects exactly once.

## Data consistency and concurrency

- Choose consistency per operation. CAP describes tradeoffs during a network partition; it is not a choice among three simultaneous guarantees.
- State where eventual consistency is acceptable, how stale reads appear, and how retries or reconciliation converge. Account for clock skew across nodes; do not assume wall clocks are globally synchronized for ordering or lock correctness.
- Replication and read replicas help availability or read capacity only when lag and failover are acceptable. Route read-after-write flows to the primary when needed.
- Use partitioning when table size, retention, and query plans benefit from pruning. Shard only when a single PostgreSQL instance no longer meets measured needs and the added routing, rebalancing, joins, and transaction costs are acceptable.
- Use leader election only when one active coordinator is necessary and the selected system has safe leases or consensus. Fence stale leaders from writes.
- Use optimistic locking for low-contention updates with version checks. Use pessimistic locking for short critical sections that need exclusion.
- Use distributed locks only with a lease, expiry, owner identity, and fencing token. Prefer a database constraint or transaction when it can enforce the invariant.
- Prevent race conditions with atomic operations, constraints, and transactions. Keep transactions short and acquire locks consistently to reduce deadlocks. Retry deadlocks only when the full transaction is safe to retry.
- Use postgres-patterns for detailed PostgreSQL indexing, query plans, pooling, migrations, and lock mechanics.

## Performance, capacity, and runtime

- Measure latency, throughput, and tail latency. Track P99 latency so averages do not hide slow requests.
- Use database indexing and query optimization based on measured query plans and workload. Detect and remove N+1 queries, oversized responses, and cache invalidation issues before scaling.
- Budget connection pooling across all application replicas against database limits. Pooling does not create database capacity.
- Scale vertically when a larger instance is the simplest fit. Scale horizontally when work can be spread safely. Add autoscaling only with meaningful signals, safe startup and shutdown, and limits.
- Add backpressure when producers can outpace consumers. Bound queues, concurrency, request sizes, and memory use.
- For managed runtimes, account for cold starts, concurrency, execution time, storage, networking, and serverless limits before choosing serverless.
- Investigate memory leaks, garbage-collection pauses, and thread-safety issues with runtime tools and measurements. Horizontal scaling does not fix a leak or shared-state race.
- Optimize cost using measured workload and provider pricing. Include idle capacity, data transfer, logs, replicas, backups, and operations.

## Delivery, observability, and recovery

- Use CI/CD for repeatable builds and checks, and promote the same artifact through environments. Pin dependencies in lockfiles and review updates. Support only the versions required by real users and contracts. Key build caching on all inputs and reject untrusted cache artifacts.
- Use infrastructure as code when repeatable environments or auditability justify it. Terraform and Helm fit their corresponding infrastructure needs; review state access, plans, chart versions, and rollback.
- Use Docker when a container boundary improves portability. Choose Kubernetes only when orchestration benefits justify its cost; consider managed container services when sufficient.
- Use feature flags to separate deployment from release where gradual exposure or fast disablement helps. Assign owners and remove stale flags.
- Choose rolling deployments, canary releases, or blue-green deployment only when release risk, capacity, or uptime needs justify them. Keep an operational rollback plan where it reduces release risk. Avoid code-level backward-compatibility layers for hypothetical versions; use direct schema changes when safe and data-preserving migrations when existing records or external contracts require them.
- Define health checks and separate liveness from readiness where supported. Readiness controls traffic; liveness restarts a stuck process. Avoid restart loops during dependency outages.
- Instrument logs, metrics, and distributed traces without recording secrets or unnecessary personal data. Monitoring alerts need an owner and runbook.
- Define SLIs, SLOs, and error budgets where reliability commitments justify them. Use actionable alerts tied to user impact.
- For production incidents, define on-call ownership. Record incidents and postmortems with impact, causes, detection gaps, and corrective work.
- Define disaster recovery objectives for important data. Protect backups, test restores, define failover, and use multi-region deployment only when tested objectives justify cost.
- Run chaos engineering only in controlled, authorized environments with a scoped hypothesis, safety limits, and rollback. It does not replace backup or restore tests.

## Related skills

- Use backend-patterns and postgres-patterns for detailed implementation guidance.
- Use agent-managed-cicd for project checks, release gates, rollback plans, and post-release verification.
- Use securitymaxxing for secrets, IAM, OAuth, JWT rotation, TLS, encryption, CORS, CSRF, SQL injection, XSS, SSRF, WAF, DDoS, and conditional security checks.
- Use provider-specific skills only after selecting a provider or when the project already uses it.
