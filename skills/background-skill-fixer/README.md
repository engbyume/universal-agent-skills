# Background Skill Fixer

A standalone agent skill for repairing a capability failure while the parent continues the user's task with its authorized fallback.

The skill directs one isolated background agent to find and fix the root cause in the failed skill, verify the repair, and return it to the parent for acceptance. It preserves real access, safety, consent, and publication gates.

See [SKILL.md](SKILL.md) for the complete workflow.

## Package

This repository contains instruction files only. It has no scripts or runtime dependencies.

## License

MIT. See [LICENSE](LICENSE).
