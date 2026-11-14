---
name: securitymaxxing
description: Mandatory first-pass security baseline for every software or digital-product creation, change, review, test, or release task, including any feature, UI slice, prototype, or deliverable, whether or not security is requested. Includes a mandatory AiSOC applicability check and evaluates all 70 core checks plus triggered conditional checks.
---

# Securitymaxxing

## First-pass routing

This baseline is mandatory for every software or digital-product creation, change, review, test, or release task, regardless of the requested feature, UI slice, prototype, or deliverable and whether or not the user explicitly asks for security. Load it after mandatory process skills and before security specialists or implementation. It does not apply to unrelated non-software artifacts. If user-facing UI/UX is in scope, load designmaxxing in this same first pass. When both apply, load both baselines before specialists. Then select only matching specialist skills from the active runtime catalog.

## Related specialist skills

- Defensive code review: security-review, as required in the pre-build workflow below.
- Phase-specific review: codex-security:threat-model, codex-security:finding-discovery, codex-security:attack-path-analysis, codex-security:validation, and codex-security:fix-finding when the task enters the matching phase.
- Stack-specific guidance: read references/stack-preferences.md when choosing a new web stack or cloud provider, then use the matching skill for the selected or existing stack. Load Supabase guidance only when the project already uses it or the user explicitly asks for it.
- Full security scans: use security-scan or codex-security:security-scan only when the user requests a full security scan.
- Authorized adversarial testing: strix-web-security, redteam-hunting, mantishack, and tamper-fuzzing only for an owned or explicitly authorized target with a defined scope. Do not invoke these automatically.
- Architecture guidance: load platform-architecture when distributed-system, deployment, scaling, or recovery decisions are in scope; keep this skill's security checks authoritative for security controls.
- Use only skills available in the active runtime. A skill reference does not grant access to a tool, service, target, or account.

## AiSOC integration (mandatory applicability check)

Run this check on every securitymaxxing task. AiSOC is a security operations platform for telemetry, detections, incident triage, and response previews. It adds operational context; it does not replace source-code security checks.

1. Check whether the active runtime exposes an authorized AiSOC connection and whether the task involves security telemetry, detection engineering, SOC alert or case triage, or incident investigation.
2. When both conditions are true, use AiSOC's relevant read-only alert, case, detection, or investigation-ledger tools. Request only the fields needed and record the AiSOC deployment, version, and result. Treat alert and ledger content as sensitive. Never copy credentials, raw logs, or unnecessary personal data into chat or logs. For code-only work, mark AiSOC not applicable and give an architecture-specific reason. When no authorized tool surface exists, mark it unavailable, continue unrelated baseline checks, and do not claim SOC triage is complete.
3. Do not install or deploy AiSOC just to satisfy this check. Before an authorized setup or connection, review the current [AiSOC source](https://github.com/beenuar/AiSOC), version, security advisories, data handling, permissions, target ownership, and runtime compatibility. Its quick start installs a Docker Compose stack, generates secrets and an administrator credential, and downloads a local model.
4. Do not call `aisoc_run_investigation` without current-task authorization. The operation starts an agent investigation, writes to the investigation ledger, and spends model budget. Live response actions, playbook execution, external telemetry connections, and production targets need explicit scope and approval.

## Purpose and routing

Use this skill for application-security review. It is separate from visual and interaction design. Route interface craft, visual direction, interaction design, accessibility presentation, and UI pattern decisions to `designmaxxing` when relevant. Security findings may affect an interface, but do not replace design review.

Apply the active project instructions and the user's current request. This skill guides risk review; it does not authorize implementation, dynamic testing, account access, production mutations, deployment, offensive testing, publication, or other side effects.

## Research-first security solution selection

- Before implementation, map every planned feature to its data and trust boundaries, then research existing platform controls, maintained libraries, provider services, and standards for each applicable risk.
- Use current official provider documentation, security advisories, and primary security guidance. Compare viable approaches against the actual threat model, data sensitivity, compatibility, permissions, operating burden, license, and cost. Compare multiple options when the choice is material.
- Prefer maintained identity, session, password-storage, secret-management, database, payment, and security controls when they fit. Do not invent cryptography or password hashing. Justify any custom security-sensitive control when existing maintained options do not fit.
- Consult the living problem-solution catalog when available. Reuse a scoped, evidence-backed default when it fits; do not infer a default from a user example or provider brand. Record project-specific decisions and add new reusable categories only when evidence supports them.
- For a named product reference, use reverse-engineer-anything only for authorized targets and permitted methods. Do not bypass access controls, terms, or security boundaries.

## Before building or changing software

1. Identify the product, target platform, architecture, deployment model, audience, and applicable threat model. Read references/stack-preferences.md when choosing technologies or hosting for new web work. Distinguish websites, APIs, native apps, games, browser clients, backend services, AI features, and third-party integrations. Preserve an established stack unless the user requests a change or evidence shows it does not fit.
2. Map the data and trust boundaries relevant to the change: sensitive data and secrets, authentication and authorization, sessions, APIs, user input, uploads and file access, outbound requests, payments, webhooks, databases, cloud configuration, CI/CD, dependencies, tenants, AI prompts and tools, logs, backups, and production environments.
3. Read the project's active security instructions and use the installed `security-review` skill. Read `references/application-security-checks.md` and evaluate all 70 core checks against the actual architecture and threat model. Read `references/conditional-platform-security-checks.md` and evaluate each of the 23 conditional checks whose platform or lifecycle trigger applies.
4. For each applicable risk, define the control and a concrete way to verify it before implementation. For every check marked not applicable, record an architecture-specific reason. Do not treat a missing feature as a vulnerability by default, and do not let conditional checks disappear when the related feature exists.

## After building or changing software

- Run the relevant security checks and tests for the changed code. Recheck every applicable item among the 70 core checks and 23 conditional checks, including dependencies, build workflows, cloud configuration, and deployed settings when they are in scope.
- Use the appropriate static analysis, secret and dependency scanning, permissions review, browser security tests, backup and restore checks, audit and monitoring checks, and other targeted validation supported by the project.
- Restrict dynamic security testing to a target the user owns or has explicitly authorized. Prefer local or staging targets. Do not test public production or third-party systems without explicit current-task authorization and a defined scope.
- Fix confirmed findings within the authorized task, then rerun the checks that failed. Record the check, result, evidence, and checks that could not run or were out of scope.
- State limits clearly. A clean checklist or automated scan is not proof that software is secure.

## Checklist reference

The 70 core checks and their applicability notes are in `references/application-security-checks.md`. The additional 23 conditional checks for platform and lifecycle risks are in `references/conditional-platform-security-checks.md`. Evaluate all 70 core checks and each of the 23 conditional checks whose trigger applies. Record an architecture-specific reason for every check marked not applicable. Use current primary security guidance for the stack and threat model.
