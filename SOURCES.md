# Sources and provenance

This catalog was refreshed from the installed skill directories, plugin metadata, and the local skills lockfile on 2026-09-07.

## Included upstream repositories

| Repository | Why it is included |
| --- | --- |
| [obra/superpowers](https://github.com/obra/superpowers) | Present in the skills lockfile. |
| [vercel-labs/agent-browser](https://github.com/vercel-labs/agent-browser) | Present in the skills lockfile and used as a general browser automation capability. |
| [browser-use/browser-use](https://github.com/browser-use/browser-use) | Present in the skills lockfile and used for browser automation workflows. |
| [anthropics/skills](https://github.com/anthropics/skills) | Installed Git repository containing general-purpose document, design, planning, and developer skills. |
| [robabby/claude-skills](https://github.com/robabby/claude-skills) | Installed Git repository containing memory, workflow, coding, testing, and quality skills, including the YAML-frontmatter memory architecture documented in this catalog. |
| [deonmenezes/mantishack](https://github.com/deonmenezes/mantishack) | Installed Git repository containing an authorized security workflow. |
| [vercel-labs/opensrc](https://github.com/vercel-labs/opensrc) | Installed Git repository containing a general source-inspection skill. |
| [nextlevelbuilder/ui-ux-pro-max-skill](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill) | Installed Git repository containing general UI/UX design intelligence. |
| [cookiy-ai/user-research-skill](https://github.com/cookiy-ai/user-research-skill) | Installed Git repository containing a general user-research workflow. |
| [bradautomates/claude-video](https://github.com/bradautomates/claude-video) | Installed Git repository containing a general video analysis workflow. |
| [yvgude/lean-ctx](https://github.com/yvgude/lean-ctx) | Explicit GitHub source in the installed skill documentation. |
| [DannyMac180/sol-advisor](https://github.com/DannyMac180/sol-advisor) | Installed Codex plugin with public repository metadata; public-safe lane contract update recorded 2026-09-10. |
| [olsenbrands/sol-foreman](https://github.com/olsenbrands/sol-foreman) | `skills/sol-foreman` audited at commit `25b5f143e5e04b0ed54c36be99c48ceb1d783a33`; retained as a per-request coordination skill with a public-safe lane contract update recorded 2026-09-10. |
| [Graphify-Labs/graphify](https://github.com/Graphify-Labs/graphify) | GitHub source verified from the installed skill documentation. |
| [Nanako0129/sepia](https://github.com/Nanako0129/sepia) | Scoped `skills/sepia` package installed after static audit; repository-level CI workflow quarantined. |
| [ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd) | `skills/i-have-adhd` installed after universal static audit; active copy is mandatory for agent responses. |
| [engbyume/codex-harness-free-model-router](https://github.com/engbyume/codex-harness-free-model-router) | Public standalone package for a provider-neutral, user-configured Codex model router, local daemon, fallback panel, real availability tracking, and optional provider client-header support; snapshot updated at commit `b591882` (2026-09-08). |
| [engbyume/codex-recursive-self-improvement](https://github.com/engbyume/codex-recursive-self-improvement) | Public standalone package for mandatory post-action learning and programmatic tool calling audits for ChatGPT and the Codex harness; snapshot at commit `fc52786` (2026-09-12). |

## Explicitly approved local entries

These entries have no claimed upstream repository. The catalog stores only public-safe descriptions.

| Skill | Why it is included |
| --- | --- |
| Codex Usage Fallback Router | Explicitly approved local skill for usage checks and approved model fallback routing. |
| Eval Loop | Explicitly approved local skill for bounded verification after changes. |
| Autonomous Skill Routing | Explicitly approved local skill for compact index-based skill discovery. |
| Agent Mentor | Explicitly approved local skill for authority, scope, and runtime evidence checks. |
| Jeremy Batch | Explicitly approved local skill for batching independent operations. |
| Composio CLI | Explicitly approved local skill for mandatory Composio discovery and schema guidance; tool calls remain task-scoped. |
| Usage Limit Resume | Explicitly approved local skill for bounded reset capture and continuation. |

## Methodology

1. Enumerate installed skill directories and resolve their Git repositories.
2. Check the local skills lockfile for GitHub sources that are not represented by a local repository.
3. Keep public GitHub origins that could be verified, plus explicitly approved local skills with redacted entries.
4. Categorize each skill by its primary job and write a short description from its installed metadata.
5. Scan the final catalog for credentials, private prompts, machine paths, and excluded platform or service names.
6. Keep usage-saving process skills mandatory, route connector and specialized skills by task or condition, select one canonical source for duplicate manifests, and use a compact routing index instead of scanning every skill body.

General agent capabilities such as browser automation, context compression, graph-based knowledge organization, and source inspection are retained because they are reusable agent workflows, not integrations for one hosted vendor. Service wrappers and platform-specific skills remain excluded even when their repositories are public.

## Provenance notes

- Repository links are upstream links, not copies or forks created by this catalog.
- The YAML Wiki Framework guide is a descriptive synthesis for agents and users. It does not copy the upstream repository's private/local configuration or reproduce research-paper text.
- Paper links are public reference links: [Generative Agents](https://arxiv.org/abs/2304.03442) and [Mem0](https://arxiv.org/abs/2504.19413). They are labeled as conceptual inspiration only.
- `source_snapshot` values in `skills.json` are local commit identifiers where the source repository was available locally. They are provenance markers, not claims that the catalog vendors a particular version.
- Monorepo entries include their subpath so a reader can find the original skill in the upstream repository.
- The public catalog intentionally avoids local filesystem paths, secrets, credentials, environment files, raw prompts, and bundled third-party code.

## Exclusions

The following are not cataloged:

- **Aside skills:** bundled Aside resources and `aside-*` skills, per request.
- **Unapproved local or private operating skills:** personal mentor, workspace, memory, and machine-operation instructions where no public GitHub origin was verified and no explicit redacted-entry approval exists.
- **Tool or service-specific skills:** Anytype, Firecrawl, Higgsfield, Composio, Google Stitch, Unusual Whales, OfficeCLI, Scrapling, and other hosted-service or single-tool wrappers.
- **Open Pencil:** excluded because it is a skill tightly coupled to the OpenPencil editor, despite having a public repository.
- **Unverified local skills:** skills with no GitHub remote, lockfile entry, or explicit upstream repository metadata.

The policy favors omission over guessing. If a future install records a clear public GitHub source and the skill is general-purpose, add it with a short description and provenance note.
