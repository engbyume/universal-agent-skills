# YAML Wiki Framework

A human-readable, agent-friendly knowledge framework built from Markdown notes, YAML frontmatter, wiki-links, and a small set of memory operations.

This framework is based on the installed `robabby/claude-skills` memory system and is documented here as a descriptive public guide. It does not copy private vault content or machine-specific paths.

## What the framework does

The YAML wiki gives an agent and a person a shared knowledge surface:

- **YAML frontmatter** makes notes structured, searchable, and portable.
- **Markdown bodies** keep the actual knowledge readable by humans.
- **Wiki-links** connect related notes and make navigation explicit.
- **Typed memory** separates events, facts, procedures, and decisions.
- **Importance and concepts** improve retrieval and prioritization.
- **Hydration** loads relevant context at the beginning of work.
- **Recall** finds prior knowledge by content, concepts, and type.
- **Reflection** consolidates useful session learning instead of saving everything.
- **Link checks** expose broken connections and orphaned notes.

## Copyable agent prompt

```text
You are working inside a YAML Wiki: a human-readable knowledge system made of Markdown notes with YAML frontmatter and explicit wiki-links.

Treat the wiki as shared working memory, not as an unquestioned authority. Read relevant current-state and decision notes before making decisions. Preserve manual edits. When sources conflict, report the conflict and prefer the freshest authoritative source.

When creating or updating a note:
1. Use Markdown for the body and valid YAML frontmatter for metadata.
2. Give the note a specific title and one clear purpose.
3. Choose exactly one memory type: episodic, semantic, procedural, or strategic.
4. Add a created date, an importance score from 0.0 to 1.0, searchable concepts, and a source label.
5. Link to related notes with [[wiki-links]] when the relationship is meaningful.
6. Separate confirmed facts from inferences, plans, and open questions.
7. Do not store credentials, tokens, cookies, private prompts, or unnecessary personal data.
8. Do not create duplicate notes when an existing note can be updated safely.

Memory types:
- episodic: what happened, including notable events and failures
- semantic: facts, definitions, specifications, and stable knowledge
- procedural: repeatable methods, workflows, and troubleshooting patterns
- strategic: decisions, priorities, plans, and their rationale

Session behavior:
- At session start, hydrate from current state, recent relevant memories, and the decision register.
- During work, recall before asking the user to repeat context and remember only durable insights.
- At session end, reflect on decisions, new patterns, unfinished work, and mistakes worth avoiding.
- Before a context reset, create a concise pickup handoff with current state, completed work, open work, and next actions.

User-facing behavior:
- Explain what was found, changed, or left unresolved in plain language.
- Show the note title and links when a memory is created or updated.
- Ask before changing a canonical or heavily edited note when authority is unclear.
- Never pretend that an inference is a stored fact or that a plan is a completed outcome.
```

## Note template

```markdown
---
created: 2026-08-03
type: strategic
importance: 0.85
concepts: [yaml-wiki, memory, retrieval]
source: explicit
---

# A specific note title

State the durable knowledge in plain language.

## Evidence

- Link to a source or related note: [[Related Note]]

## Uncertainty

State what is inferred, unresolved, or time-sensitive.
```

## Suggested wiki structure

```text
Areas/AI/
├── Context/
│   ├── Current State.md
│   └── Decision Register.md
├── Memory/
│   ├── Episodic/
│   ├── Semantic/
│   ├── Procedural/
│   └── Strategic/
└── Collaboration/
    └── Sessions/
```

## User workflow

1. Start with current state and the decision register.
2. Search before recreating context.
3. Save only durable decisions, facts, procedures, and meaningful events.
4. Link related notes as the wiki grows.
5. Review and consolidate periodically.
6. Run link checks before reorganizing or archiving.

## Agent workflow

`hydrate -> recall -> work -> remember -> reflect -> pickup`

The framework is deliberately storage-agnostic. Obsidian is a natural implementation because it supports Markdown, YAML frontmatter, and wiki-links, but the same contract can be used by another filesystem-backed or database-backed agent memory layer.

## Conceptual inspiration

The framework's architecture is conceptually aligned with these papers:

1. [Generative Agents: Interactive Simulacra of Human Behavior](https://arxiv.org/abs/2304.03442), Park et al. (2023). The relevant conceptual parallel is the cycle of observations, retrieval, reflection, and durable memory.
2. [Mem0: Building Production-Ready AI Agents with Scalable Long-Term Memory](https://arxiv.org/abs/2504.19413). The relevant conceptual parallel is structured, scoped, long-term memory for agents under bounded context windows.

These are inspiration references, not claims that the upstream `robabby/claude-skills` project explicitly cites or implements either paper. This guide does not reproduce either paper's text.
