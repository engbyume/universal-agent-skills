# Sources and provenance

This catalog was refreshed from the installed skill directories, plugin metadata, and the local skills lockfile on 2026-10-12.

## Included upstream repositories

| Repository | Why it is included |
| --- | --- |
| [obra/superpowers](https://github.com/obra/superpowers) | Present in the skills lockfile. |
| [vercel-labs/agent-browser](https://github.com/vercel-labs/agent-browser) | Present in the skills lockfile and used as a general browser automation capability. |
| [vercel-labs/agent-desktop](https://github.com/vercel-labs/agent-desktop) | User-requested cross-platform desktop automation skill, reviewed at the Apache-2.0 v1.2.0 release commit `2b0a7334fc111730454b726e6800aa41cdafc093`; the third-party skill body is not copied into this catalog. |
| [browser-use/browser-use](https://github.com/browser-use/browser-use) | Present in the skills lockfile and used for browser automation workflows. |
| [anthropics/skills](https://github.com/anthropics/skills) | Installed Git repository containing general-purpose document, design, planning, and developer skills. |
| [robabby/claude-skills](https://github.com/robabby/claude-skills) | Installed Git repository containing memory, workflow, coding, testing, and quality skills, including the YAML-frontmatter memory architecture documented in this catalog. |
| [deonmenezes/mantishack](https://github.com/deonmenezes/mantishack) | Installed Git repository containing an authorized security workflow. |
| [vercel-labs/opensrc](https://github.com/vercel-labs/opensrc) | Installed Git repository containing a general source-inspection skill. |
| [nextlevelbuilder/ui-ux-pro-max-skill](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill) | Installed Git repository containing general UI/UX design intelligence. |
| [shadcn-ui/ui](https://github.com/shadcn-ui/ui) | User-requested shadcn skill pinned to commit `d2fba50ee5b9113008b5bb908563527b7efd2f27`; local adapted copy passed complete static review and is not mirrored here. |
| [cookiy-ai/user-research-skill](https://github.com/cookiy-ai/user-research-skill) | Installed Git repository containing a general user-research workflow. |
| [bradautomates/claude-video](https://github.com/bradautomates/claude-video) | Installed Git repository containing a general video analysis workflow. |
| [yvgude/lean-ctx](https://github.com/yvgude/lean-ctx) | Installed context tools with bounded raw-CLI and retry-safe modes plus a writable native fallback for MCP failures (2026-09-29). |
| [DannyMac180/sol-advisor](https://github.com/DannyMac180/sol-advisor) | Installed Codex plugin with public repository metadata; cataloged for risk-gated role routing, cost-aware selection, and parent-owned verification. The local routing overlay uses Luna / Max by default, Sol / High for hard work, and Astra / High for very complex short work; it does not change upstream. |
| [olsenbrands/sol-foreman](https://github.com/olsenbrands/sol-foreman) | Upstream source for the former local Sol Foreman workflow; its license is retained. This catalog publishes the owner-approved Progressive Codex Model Router adaptation as a separate redacted first-party package. Upstream remains unchanged. |
| [Graphify-Labs/graphify](https://github.com/Graphify-Labs/graphify) | GitHub source verified from the installed skill documentation. |
| [Nanako0129/sepia](https://github.com/Nanako0129/sepia) | Scoped `skills/sepia` package installed after static audit; repository-level CI workflow quarantined. A local writing adapter combines structure-aware narrative and professional-prose routes with conditional surface-style and formatting checks plus evidence-gated model guidance; upstream unchanged. |
| [ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd) | `skills/i-have-adhd` installed after universal static audit; active copy is mandatory for agent responses. |
| [engbyume/codex-harness-free-model-router](https://github.com/engbyume/codex-harness-free-model-router) | Public standalone package for a provider-neutral, user-configured Codex model router, local daemon, fallback panel, real availability tracking, and optional provider client-header support; snapshot updated at commit `b591882` (2026-09-08). |
| [engbyume/codex-recursive-self-improvement](https://github.com/engbyume/codex-recursive-self-improvement) | Public standalone package for mandatory post-action learning and programmatic tool calling audits for ChatGPT and the Codex harness; snapshot at commit `fc52786` (2026-09-12). |
| [DietrichGebert/ponytail](https://github.com/DietrichGebert/ponytail) | Existing local skill passed static audit and is mandatory for simplicity and YAGNI decisions. |
| [headroomlabs-ai/headroom](https://github.com/headroomlabs-ai/headroom) | Official Headroom source installed as a local compression tool; use it as a mutually exclusive alternative to Lean CTX and RTK. |
| [rtk-ai/rtk](https://github.com/rtk-ai/rtk) | Official Rust Token Killer source built and installed as a command-output optimizer; bundled agent skills were not installed. |

| [apify/agent-skills](https://github.com/apify/agent-skills) | Official Apify-maintained scraper skill installed from skills/apify-ultimate-scraper at audited commit d522584df6d01746d76b0c674f375cc7d48a838f; local safeguards cover login, tokens, target authorization, and billable runs. |
| [rebelytics/one-skill-to-rule-them-all](https://github.com/rebelytics/one-skill-to-rule-them-all) | Audited at commit `56e890712273ce231b478adc56ee2eb81101c3d6`; its Task Observer workflow informed a Codex-native, hook-free package for prompt-start, material-change, and end audits. Added 2026-10-14 after public-safety review. |
| [NVIDIA/skillspector](https://github.com/NVIDIA/skillspector) | Apache-2.0 scanner source updated to verified main commit `3fb77b4cc9a97724481a6745157efcbfb20e2f32`; focused parser and reference-resolution regression tests passed. The cataloged skill-inspector adaptation remains sourced from commit `4c52fbb83bbca0dd13f2685453c9b661d8c95bf8`. |
| [garrytan/gbrain](https://github.com/garrytan/gbrain) | Owner-requested, redacted local-first memory adapter based on upstream commit 44eb0493ff2776f04d6616b1a526657702f7544a; it does not enable automatic capture, provider calls, or machine-specific configuration. |

## Referenced tools

| Repository | Use in this catalog |
| --- | --- |
| [beenuar/AiSOC](https://github.com/beenuar/AiSOC) | Referenced by Securitymaxxing for a mandatory applicability check on operational SOC telemetry and incident work. Current main was reviewed at `010a3981bfc791266d62aaa31531f05798531efd`; no product code, telemetry, credentials, or deployment configuration is copied here. |

## Explicitly approved local entries

These entries have no claimed upstream repository. The descriptions are public-safe, and approved first-party packages are under skills/.

| Skill | Why it is included |
| --- | --- |
| Codex Usage Fallback Router | Explicitly approved local skill for usage checks, approved free-model fallbacks, and a local model switcher. |
| Eval Loop | Explicitly approved local skill for bounded verification after changes. |
| Autonomous Skill Routing | Explicitly approved local skill for compact index-based skill discovery. |
| Agent Mentor | Explicitly approved local skill for authority, scope, and runtime evidence checks. |
| Jeremy Batch | Explicitly approved local skill for batching independent operations. |
| Composio CLI | Explicitly approved local skill for mandatory Composio discovery and schema guidance; tool calls remain task-scoped. |
| Usage Limit Resume | Explicitly approved local skill for bounded reset capture and continuation, with a parent-owned final review through Progressive Codex Model Router after standard capacity returns. Existing review state values are preserved for compatibility. |
| Designmaxxing | First-party portable UI design skill for public-product goal discovery, direct implementation, Computer Use by default for Codex UI review and interaction testing, shadcn/Base UI design systems, push-based live UX, accessibility, approved asset sourcing, unique-by-default website design, mandatory Awwwards (https://www.awwwards.com/) inspiration research, and conditional Platform Architecture routing. Updated 2026-10-18. |
| Securitymaxxing | First-party portable application-security skill with 70 core checks and 23 conditional platform and lifecycle checks, pre-build and post-build guidance, authorized testing limits, and preferred web stack plus Appify/Firecrawl research guidance. Updated 2026-10-17. |
| Platform Architecture | First-party conditional guidance for backend, distributed systems, push-based realtime updates, data consistency, delivery, observability, recovery, and public-product service selection; routes detailed work to existing specialists. Added 2026-10-17. |
| Agent-Managed CI/CD | Public-safe first-party release workflow with deployment patterns, health checks, rollback, and explicit release gates. Added 2026-10-17. |
| Skill Inspector | Public-safe Apache-2.0 adaptation for mandatory Skillspector intake scanning, coverage review, source triage, and source-confirmed malware removal. |
| Universal Skill Audit | Public-safe first-party guidance for skill-source provenance, mandatory Skillspector scans, complete coverage, and evidence-based install decisions. |
| FitLab Verification | Explicitly approved project-local verification catalog entry. The catalog stores only a redacted summary; the detailed feature map stays with the application. Updated 2026-10-19. |
| Progressive Codex Model Router | Explicitly approved public-safe first-party adaptation of a foreman workflow. It keeps the parent on GPT-6 Luna / max, routes Codex subagents by task and cost, and aggregates their results. It contains no private paths or runtime settings. |

## Methodology

1. Enumerate installed skill directories and resolve their Git repositories.
2. Check the local skills lockfile for GitHub sources that are not represented by a local repository.
3. Keep public GitHub origins that could be verified, plus explicitly approved local skills with redacted entries.
4. Categorize each skill by its primary job and write a short description from its installed metadata.
5. Scan the final catalog for credentials, private prompts, machine paths, and excluded platform or service names.
6. Keep usage-saving process skills mandatory, route connector and specialized skills by task or condition, select one canonical source for duplicate manifests, and use a compact routing index instead of scanning every skill body.

General agent capabilities such as browser automation, context compression, graph-based knowledge organization, and source inspection are retained because they are reusable agent workflows, not integrations for one hosted vendor. Service wrappers and platform-specific skills remain excluded even when their repositories are public.

## Provenance notes

- 2026-11-09: Aligned Usage Limit Resume final-review guidance with the parent-Luna, child-only Codex routing rule; preserved its serialized review action for compatibility.
- 2026-11-09: Added the owner-approved Progressive Codex Model Router package with child-only model routing, task-class routes, and Plus usage guidance. The public package is self-contained and excludes local orchestration helpers.
- 2026-10-17: Added the pinned shadcn/ui source link. Its audited local adaptation is installed in Codex-compatible runtimes; third-party instructions are not copied into this library.

- 2026-10-15: Added the Apache-2.0 NVIDIA Skillspector source and two public-safe intake skills. The local intake route now requires no-LLM scans and source review for every skill change.
- 2026-10-12: Added a portable autonomy and hook-free fallback check for active skills, including routine authorized work, genuine action boundaries, and complete inventory audits.

- Repository links are upstream links, not copies or forks created by this catalog.
- On September 28, 2026, redacted local agent instructions were clarified to separate
  user authorization from goal-state evidence, avoid repeated continuation prompts,
  checkpoint at first-compaction thresholds, and avoid guessing active model identity.
  No upstream repository was changed by that local work.
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
