# Jeremy's Agent Skills

A personal catalog of AI-agent skills that were installed from public GitHub repositories.

This repository is a **catalog, not a mirror**. It contains short descriptions, categories, provenance notes, and links back to the original repositories. It does not copy third-party skill instructions, bundled scripts, private prompts, credentials, environment files, or local configuration.

## What is included

A skill is included only when its source can be traced to a public GitHub repository through one or more of:

- a Git remote on the installed source repository
- the local skills lockfile
- an explicit repository or installation link in the skill's own metadata

The catalog includes task-oriented skills that are useful across agent runtimes, such as memory workflows, context efficiency, planning, research, writing, design, documents, security, and verification.

## What is intentionally excluded

The catalog does not include:

- Aside skills or other bundled platform skills
- Skills with no verifiable GitHub source
- Local-only skills and Jeremy-specific private operating instructions
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

## Updating the catalog

When adding a skill, verify the original GitHub repository first. Add a concise description, a category, the installed skill name, and a source link. Do not copy the skill's implementation into this repository.

## Attribution

All skill names, descriptions, and linked repositories belong to their respective authors. This catalog is an organizational index and is not affiliated with the upstream projects.
