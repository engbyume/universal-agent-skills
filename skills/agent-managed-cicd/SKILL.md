---
name: agent-managed-cicd
description: Safely run agent-managed tests, builds, release-candidate preparation, rollback planning, and post-release verification for one explicitly chosen owned project. Use when a project needs CI/CD setup or a guarded release workflow. Do not use without a named project and release gate.
---

# Agent-Managed CI/CD

Use this skill for one explicitly named and owned project. Use an appropriate multi-repository orchestration skill when the task spans multiple repositories.

The agent can inspect, test, build, package, and prepare a release candidate. The parent agent owns the release decision. Publishing or deploying requires an explicit release gate.

## Before acting

Record a release contract:

- Project path and owner.
- Authoritative source, branch, and current commit.
- Existing test, lint, type-check, build, package, and deployment commands.
- Invariants and files that must not change.
- Release target and environment.
- Rollback artifact or previous known-good commit.
- Local evaluation, release evaluation, and post-release verification.
- Release authority: who or what is allowed to approve publication.

If the project, branch, test commands, release target, or rollback path is unclear, stop and report the missing information. Do not guess.

## Workflow

1. Inspect project instructions, CI configuration, current status, and existing scripts.
2. Run the existing checks without changing the project.
3. Make the smallest authorized change.
4. Run the eval-driven correction loop. Stop after three failed correction attempts.
5. Build or package a release candidate and record its commit, artifact path, and checksum when practical.
6. Check that the working tree contains only in-scope changes.
7. Stop at the release gate. Do not publish or deploy yet.
8. After explicit release authorization, run the provider preflight and publish or deploy through the project's existing path.
9. Verify the actual external result, such as a deployment, published artifact, health check, or release record.
10. If the post-release check fails, stop traffic or roll back only through the documented safe path. Verify the rollback result.

## Release gates

- Local tests, lint, type checks, builds, and release-candidate creation may run as ordinary project work.
- Pushes, deployments, production changes, public releases, and external notifications require an explicit release gate in the current task.
- Never treat a local artifact, draft, or successful build as proof of publication.
- Never create or change credentials, tokens, provider defaults, or unrelated deployment settings.
- Never log secrets or include them in artifacts, test output, or reports.

## Delegated work

Children may run isolated tests or inspect CI configuration when that saves time. Give each child the same objective, project path, write scope, evaluation, pass condition, retry budget, and stop rule.

Children must not publish, deploy, change release settings, rotate credentials, or approve a release. The parent reruns important checks and owns the release decision.

## Deployment and operations patterns

Choose these patterns from release risk and service needs. They do not authorize deployment or remove the release gate above.

- Select rolling, canary, or blue-green releases from rollback speed, capacity, data compatibility, and health signals. Keep feature flags separate from deployment mechanics and remove obsolete flags.
- Check application health after each rollout. Use readiness to control traffic and liveness to restart a stuck process when the platform supports both. Include a rollback path and verify its result.
- Keep schema changes backward-compatible across a rollout. Prefer expand, migrate, and contract steps so old and new versions can run together.
- Use Docker when a reproducible container boundary helps. Use Kubernetes only when scheduling, orchestration, and scaling benefits justify the operational cost.
- Use infrastructure as code when repeatable environments or auditability justify it. Review Terraform plans, state permissions, Helm chart versions, and drift before applying.
- Cache builds using keys that reflect source, toolchain, and dependencies. Pin dependencies and review updates; do not accept untrusted cache artifacts or broad upgrades without inspection.
- For production services, collect actionable logs, metrics, and distributed traces. Define relevant SLIs, SLOs, alerts, owners, and error-budget response.
- Define backups, restore verification, failover, and recovery objectives. Use multi-region deployment only when tested needs justify its cost and complexity.
- Assign production incident and on-call ownership. Record incidents and postmortems with corrective actions. Run chaos exercises only in scoped, authorized environments.
- Track latency, throughput, tail latency, cold starts, serverless limits, data transfer, and idle capacity when they affect user experience or cost.
- For system-level decisions about queues, consistency, protocols, scaling, and reliability, load platform-architecture. For security controls, load securitymaxxing.

## Required report

Return:

- `status`: pass, ready-for-release, blocked, or rolled-back
- `project`: path and commit
- `checks`: each check and result
- `candidate`: artifact path and checksum when created
- `release_gate`: approved, not approved, or not applicable
- `external_result`: observed publication or deployment state, if authorized
- `rollback`: available path and result, if used
- `remaining`: unresolved checks or next action

Do not claim a release, deployment, or rollback succeeded without observing the relevant external state.
