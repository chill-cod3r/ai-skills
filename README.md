# AI Skills

Reusable AI workflow skills with generated target formats for Claude, Codex, and GitHub Copilot-style instructions.

## Repository Layout

Each skill lives in its own folder. The canonical source is `base.md`, and target-specific wrappers are generated from it.

```text
ship/
├── base.md
├── claude.md
├── codex/
│   └── SKILL.md
└── copilot/
    ├── AGENTS.md
    └── .github/
        └── copilot-instructions.md
```

The repo root may also contain a generated compatibility copy like `ship.md` for easy linking and browsing.

## Skills

### anti-slop

Writing-style guardrail skill for newsletters and posts that strips AI-sounding phrasing, cliché transitions, and corporate buzzwords in favor of concrete, direct, human-sounding writing.

- Canonical source: [anti-slop/base.md](anti-slop/base.md)
- Claude wrapper: [anti-slop/claude.md](anti-slop/claude.md)
- Codex wrapper: [anti-slop/codex/SKILL.md](anti-slop/codex/SKILL.md)
- Copilot wrapper: [anti-slop/copilot/AGENTS.md](anti-slop/copilot/AGENTS.md)
- Compatibility copy: [anti-slop.md](anti-slop.md)

### ship

End-to-end workflow for planning, PRD generation, implementation, verification, and explicit user acceptance with audit-grade evidence.

- Canonical source: [ship/base.md](ship/base.md)
- Claude wrapper: [ship/claude.md](ship/claude.md)
- Codex wrapper: [ship/codex/SKILL.md](ship/codex/SKILL.md)
- Copilot wrapper: [ship/copilot/AGENTS.md](ship/copilot/AGENTS.md)
- Compatibility copy: [ship.md](ship.md)

## Generate Wrappers

Regenerate all target formats from the canonical `base.md` files:

```bash
python3 scripts/generate_skill_formats.py
```

## Tool Notes

- **Claude Code**: use the generated `claude.md` file or the compatibility copy if you want a flat skill file.
- **Codex**: use the generated `SKILL.md` file inside the skill folder.
- **GitHub Copilot / Copilot CLI**: use the generated instruction wrappers under `copilot/`. Copilot does not use the same native skill format as Claude or Codex, so this repo generates instruction-style adapters instead.
