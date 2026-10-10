---
name: securitymaxxing
description: First-pass application-security baseline for planning, building, changing, reviewing, testing, or preparing software for release. Load before matching security specialists and run applicable pre-build and post-build checks for websites, apps, games, APIs, and AI features.
---

# Securitymaxxing

## First-pass routing

Load this baseline after mandatory process skills and before security specialists or implementation for software planning, building, changing, reviewing, testing, and release preparation. If user-facing UI/UX is in scope, load designmaxxing in this same first pass. When both apply, load both baselines before specialists. Then select only matching specialist skills from the active runtime catalog.

## Related specialist skills

- Defensive code review: security-review, as required in the pre-build workflow below.
- Phase-specific review: codex-security:threat-model, codex-security:finding-discovery, codex-security:attack-path-analysis, codex-security:validation, and codex-security:fix-finding when the task enters the matching phase.
- Stack-specific guidance: supabase:supabase, build-web-apps:stripe-best-practices, vercel:auth, vercel:payments, or the matching skill for the stack in use.
- Full security scans: use security-scan or codex-security:security-scan only when the user requests a full security scan.
- Authorized adversarial testing: strix-web-security, redteam-hunting, mantishack, and tamper-fuzzing only for an owned or explicitly authorized target with a defined scope. Do not invoke these automatically.
- Use only skills available in the active runtime. A skill reference does not grant access to a tool, service, target, or account.

## Purpose and routing

Use this skill for application-security review. It is separate from visual and interaction design. Route interface craft, visual direction, interaction design, accessibility presentation, and UI pattern decisions to `designmaxxing` when relevant. Security findings may affect an interface, but do not replace design review.

Apply the active project instructions and the user's current request. This skill guides risk review; it does not authorize implementation, external testing, deployment, publication, or other side effects.

## Before building or changing software

1. Identify the product, target platform, architecture, deployment model, audience, and applicable threat model. Distinguish websites, APIs, native apps, games, browser clients, backend services, AI features, and third-party integrations.
2. Map the data and trust boundaries relevant to the change: sensitive data and secrets, authentication and authorization, sessions, APIs, user input, uploads and file access, outbound requests, payments, webhooks, databases, cloud configuration, CI/CD, dependencies, tenants, AI prompts and tools, logs, backups, and production environments.
3. Read the project's active security instructions and use the installed `security-review` skill. Read `references/application-security-checks.md` and evaluate all 70 checks against the actual architecture and threat model.
4. For each applicable risk, define the control and a concrete way to verify it before implementation. Mark checks as not applicable only with a reason. Do not treat a missing feature as a vulnerability by default, and do not let conditional checks disappear when the related feature exists.

## After building or changing software

- Run the relevant security checks and tests for the changed code. Recheck every applicable item in the 70-check list, including dependencies, build workflows, cloud configuration, and deployed settings when they are in scope.
- Use the appropriate static analysis, secret and dependency scanning, permissions review, browser security tests, backup and restore checks, audit and monitoring checks, and other targeted validation supported by the project.
- Restrict dynamic security testing to a target the user owns or has explicitly authorized. Prefer local or staging targets. Do not test public production or third-party systems without explicit current-task authorization and a defined scope.
- Fix confirmed findings within the authorized task, then rerun the checks that failed. Record the check, result, evidence, and checks that could not run or were out of scope.
- State limits clearly. A clean checklist or automated scan is not proof that software is secure.

## Checklist reference

The complete 70-check list and its applicability notes are in `references/application-security-checks.md`. Keep the list intact when extending this skill. Use current primary security guidance for the stack and threat model.
