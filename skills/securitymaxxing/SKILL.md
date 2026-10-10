---
name: securitymaxxing
description: Use when planning, building, reviewing, testing, or preparing a website, app, game, API, AI feature, or other software for release and security risks need assessment.
---

# Securitymaxxing

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
