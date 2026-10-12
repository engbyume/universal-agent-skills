# Jeremy's Agent Skills

A personal catalog of AI-agent skills, with a small set of explicitly approved first-party skill packages.

This repository is a catalog plus a small set of explicitly approved first-party skill packages. It does not mirror third-party skill instructions. Catalog entries contain short descriptions, categories, provenance notes, and links to upstream repositories. First-party packages contain portable, redacted guidance. The repository excludes private prompts, credentials, environment files, and local configuration.

## What is included

Catalog entries for upstream skills are included only when their source can be traced to a public GitHub repository through one or more of:

- a Git remote on the installed source repository
- the local skills lockfile
- an explicit repository or installation link in the skill's own metadata

First-party skill packages may be published only with explicit owner approval and a public-safety review. They must not contain private paths, personal data, raw prompts, credentials, or local runtime configuration.

The catalog includes task-oriented skills that are useful across agent runtimes, such as memory workflows, context efficiency, planning, research, writing, design, documents, security, and verification. First-party skills appear as redacted entries; a package is included only with explicit owner approval.

## What is intentionally excluded

The catalog does not include:

- Aside skills or other bundled platform skills
- Third-party skills with no verifiable GitHub source
- Unapproved local-only skills and user-specific private operating instructions
- Vendor or service integration skills that are tied to a single product or hosted tool
- Private files, `.env` files, API keys, cookies, prompts, or machine-specific paths

The exclusion policy is deliberately conservative. A repository may be public and still be left out if the installed skill is primarily a wrapper for a particular service or local runtime.

## Categories

- **Memory and knowledge**: recall, retention, reflection, vault workflows, graph-based knowledge organization
- **Agent efficiency**: context compression, batching, workflow improvement, and process optimization
- **Planning and quality**: brainstorming, skill creation, testing, security review, and verification loops
- **Research and investigation**: user research, deep investigation, and evidence-oriented analysis
- **Writing and communication**: anti-slop writing, internal communications, and documentation co-authoring
- **Creative and visual work**: algorithmic art, canvas design, frontend design, themes, and design intelligence
- **Documents and data**: PDF, DOCX, PPTX, XLSX, and office-document workflows
- **Developer workflows**: API development, MCP server building, web artifact creation, and web app testing
- **Media analysis**: video inspection and transcript-assisted visual analysis
- **Security**: defensive and authorized security review workflows

## Files

- [`skills.json`](skills.json): machine-readable catalog
- [`SOURCES.md`](SOURCES.md): source repositories and provenance notes
- [`skills/`](skills/): explicitly approved, redacted first-party skill packages
- [`frameworks/yaml-wiki-framework.md`](frameworks/yaml-wiki-framework.md): user and agent guide with a copyable prompt
- [`frameworks/yaml-wiki-framework.yaml`](frameworks/yaml-wiki-framework.yaml): machine-readable framework contract
- [`frameworks/skill-autonomy-compatibility.md`](frameworks/skill-autonomy-compatibility.md): routine autonomy, genuine action boundaries, and hook-free skill checks

### YAML Wiki Framework

The catalog includes a descriptive YAML Wiki Framework based on the public `robabby/claude-skills` memory system. It covers Markdown notes, YAML frontmatter, typed memory, wiki-links, hydration, recall, reflection, handoffs, and link checks. Its two research-paper references are labeled as conceptual inspirations only, not as explicit upstream citations.

## Updating the catalog

When adding a public-source skill, verify the original GitHub repository first and link to it rather than copying its instructions. An explicitly approved first-party skill may include a portable, redacted package. Add a concise catalog entry and category, and do not claim an external upstream source. Exclude private prompts, personal data, credentials, machine paths, and local configuration.

## Attribution

All skill names, descriptions, and linked repositories belong to their respective authors. This catalog is an organizational index and is not affiliated with the upstream projects.
