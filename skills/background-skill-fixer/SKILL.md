---
name: background-skill-fixer
description: This skill should be used after an agent skill fails an intended capability following its bounded retries and the parent selects a safe fallback. It starts one isolated background repair while the parent continues the current task.
---

# Background Skill Fixer

Repair a skill when it fails a promised capability and the parent must use an authorized fallback. Keep the user's current task moving while one isolated background agent fixes the skill's root cause for future use.

## Trigger

Use this skill only after all of the following are true:

- A specific skill or its documented tool path failed to perform a capability it promises.
- The failure has observable evidence, such as a tool error, missing control, incorrect action, or repeated inability to complete a defined step.
- The parent selected a safe, authorized fallback or can continue safely while repair proceeds.

Do not treat a permission denial, missing credential, user consent requirement, unavailable account, provider outage, missing user data, or unsupported runtime feature as a skill defect. Preserve the relevant gate. Do not use a fallback to bypass authentication, access controls, legal consent, paid-use approval, production boundaries, or user intent.

Do not trigger Background Skill Fixer because Background Skill Fixer itself failed. Do not start a second fixer for the same skill and failure while one repair is already active. Combine duplicate observations into the existing repair task when possible.

## Keep the current task moving

1. Follow the failed skill's documented recovery procedure first.
2. If it has no retry rule and the failed operation is safe and repeatable, make one initial attempt and at most two targeted retries. Change the hypothesis or input for each retry, then inspect the resulting state. Stop early when the result shows an access, consent, safety, or service-availability gate.
3. For state-changing actions, inspect current state before any retry. Never repeat a click, send, write, purchase, deletion, or other mutation blindly.
4. Once a safe, authorized fallback is selected, use it immediately. Do not wait for the repair agent before continuing the user's task.
5. Start one background repair agent in parallel, if the runtime supports it. The parent remains responsible for the original task and final acceptance.

Example: if a desktop automation skill cannot detect a Word control after targeted retries, the parent can use an authorized native UI fallback such as Computer Use to finish the requested edit. In parallel, the repair agent investigates the desktop skill's detection path using a disposable fixture. It does not edit the user's active document.

## Isolate the repair agent

Use the runtime's native background-agent or subagent mechanism. Check for an existing repair task with the same skill and failure before starting another one. Do not create nested agents.

Give the child a concise task envelope with:

- The skill name and its canonical source path or repository.
- The exact capability that failed, observed error or behavior, attempts already made, and fallback now in use.
- The smallest relevant skill files, references, interface schema, and test fixture.
- Allowed and forbidden tools, exact write scope, verification steps, stop rule, and return format.

Use the active model-routing rules to select the least costly capable child. Provide only the context needed for repair. Do not send raw private prompts, credentials, cookies, tokens, or unrelated user data.

Give the child an isolated worktree, branch, or staged copy that contains only the skill source and its focused regression check. The child must not edit the parent task's files, user documents, application state, shared configuration, credentials, or external services. If the runtime cannot provide an isolated write area, keep the child read-only and have it return a patch for the parent to apply. If no background-agent capability exists, continue the original task and report that the repair could not run in parallel.

## Find and fix the root cause

1. Reproduce the failure safely with a disposable fixture or a minimal synthetic case. Use the user's actual data only when it is essential and already authorized.
2. Trace the skill's trigger, instructions, linked references, scripts, tool mapping, current interface, and retry/fallback logic. Separate an instruction defect from a runtime, version, permission, account, or service problem.
3. Identify the underlying cause before editing. Prefer a small change that corrects the decision, selector, interface mapping, or recovery logic. Do not add a one-off toggle, repeated retry, or general fallback layer that only hides the symptom.
4. Add or update a focused regression check when the skill supports one. Verify both the original failing scenario and a nearby successful scenario. Keep the repair bounded to three targeted correction attempts.
5. If the source belongs to a third party, do not edit or publish to its upstream repository. Repair only an authorized, user-owned local overlay. If there is no writable overlay, return a proposed patch and stop that repair branch.

## Validate and integrate

Return the repair to the parent for review. Do not report the skill as fixed or activate the patch until the parent confirms the root cause, inspects the diff, and reruns the important check.

Before activating or installing a changed skill, follow the active source and security gate. Where required, run the source audit, Skillspector with complete coverage, the skill validator, and an authoring review. Keep a local or private scan offline. Resolve every high, critical, or YARA finding against source. Leave the skill inactive if analysis is incomplete or a required gate fails.

Integrate the verified change into the canonical user-owned skill source. Use the runtime's skill linker to update existing roots without replacing conflicting destinations. Follow the user's current public-library policy for first-party skills, publish only public-safe content, and verify the remote copy. Never modify a read-only preservation mirror or claim a future task will use the fix until the active source and links are confirmed.

If the background repair is still running when the original task reaches its end, do not hold the user task open indefinitely. Report the repair as pending, keep using the fallback, and do not claim the future fix is active until integration passes.

If a decision blocks only the repair branch, return `blocked` to the parent and keep the original task moving. Ask the user only if the original task also has no safe, useful path forward. Follow the runtime's global blocking-question and email policy when that rare case occurs.

## Return status

Return one of these statuses to the parent:

- `fixed`: root cause corrected, focused regression check passed, and parent accepted integration.
- `candidate`: a plausible patch exists, but review, testing, security scan, or integration remains.
- `not_skill_failure`: evidence points to missing authority, unavailable service, changed environment, or another non-skill cause.
- `blocked`: no safe isolated repair path exists without access, consent, credentials, or a user decision.

Include the root cause, evidence, changed paths, checks and results, active-source/link status, and any remaining blocker. The parent continues the user's task through the authorized fallback independently of this status.
