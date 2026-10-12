# Skill autonomy compatibility

Use this check for active skills across supported agent runtimes. A skill should let an agent complete ordinary work that the user has already authorized while keeping real authorization and safety boundaries intact.

## Routine-work scenario

Give the skill a clear, reversible task within the user's stated scope. It passes when the agent:

- starts useful work without asking for the same authorization again;
- does not require a forced wait, subagent, connector, evaluator, paid service, or lifecycle hook when an available local method is enough;
- uses a practical fallback when an optional tool is missing; and
- reports any unverified layer accurately.

## Boundary scenario

When the requested next step lacks authority or requires a real gate, the skill must stop only that step. Examples include a missing user decision, credentials or access, legal or consent requirements, paid use, external sends or publication, production changes, security operations that require separate authority or access, and destructive actions. The agent should continue safe independent work when possible.

Security and consent checks are not autonomy failures when they protect a real boundary. Do not make a skill pass by bypassing authentication, access controls, consent, user decisions, or platform hook trust.

## Repair and disablement

- Remove redundant approval prompts, forced waits, and hard dependencies on optional tools from the active user-owned skill.
- Do not add or enable lifecycle hooks merely to activate, test, or enforce a skill. If optional hook setup requires platform trust review, use the hook-free path and continue.
- Use a manual or deterministic check when an evaluator or subagent is unavailable. Do not install a new paid or external dependency only to test a skill.
- If a narrow correction cannot preserve a real boundary, disable only the incompatible route for the current runtime when a safe alternative preserves that boundary.
- If no safe equivalent exists, keep the skill available for its intended gated condition, stop only the gated action, and continue other authorized work. Do not weaken the boundary or disable unrelated runtimes.
- Treat a current user request or applicable standing instruction as authorization for its stated scope. Do not ask again for reversible work already authorized.

## Coverage and evidence

Test every skill selected for a task for unnecessary routine-work blockers. Test every new, installed, created, or materially updated skill with both scenarios above. During a full inventory audit, test every active routing entry and record its result before claiming the audit is complete.

Choose the smallest useful test for the skill type: behavioral scenarios for action rules, retrieval checks for reference skills, and structural or deterministic checks when they provide adequate evidence. Record pass, fix, conditional, or disable-for-runtime status with the test and its limits.
