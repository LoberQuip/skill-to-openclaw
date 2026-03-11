# Skill → OpenClaw Converter

Convert Claude Code skills to OpenClaw skill format with a single command.

## Why?

Claude Code has hundreds of community skills. Most work great in OpenClaw but need a format conversion. This tool bridges that gap.

**Use when:**
- You find a cool Claude Code skill and want to use it in OpenClaw
- You're migrating from Claude Code to OpenClaw
- You want to share your OpenClaw skills with Claude Code users

## Install

```bash
curl -sL https://raw.githubusercontent.com/quipxi/skill-to-openclaw/main/install.sh | bash
```

Requires: Node.js 18+, Git

## Quick Start

```bash
# From GitHub
skill-to-openclaw owner/repo

# From local path
skill-to-openclaw ./my-claude-skill
```

## Example

```bash
$ skill-to-openclaw ParthJadhav/app-store-screenshots

🔄 Converting: ParthJadhav/app-store-screenshots
📦 Cloning ParthJadhav/app-store-screenshots...
📄 Found: skills/app-store-screenshots/SKILL.md
✨ Skill: app-store-screenshots
📝 Description: Use when building App Store screenshot pages...
🏷️  Triggers: app store, screenshots, marketing assets
✅ Saved to: ~/.openclaw/skills/app-store-screenshots

Restart OpenClaw or run: openclaw skills sync
```

## What It Does

1. **Input** — Accepts GitHub repo (owner/repo), full URL, or local path
2. **Parse** — Finds SKILL.md, extracts name, description, triggers from frontmatter
3. **Copy** — Copies supporting files (mockups, scripts, assets)
4. **Convert** — Rewrites SKILL.md in OpenClaw format
5. **Save** — Writes to `~/.openclaw/skills/[name]/`

## Options

| Flag | Description | Example |
|------|-------------|---------|
| `--name` | Custom output name | `--name my-skill` |
| `--force` | Overwrite existing skill | `--force` |
| `--dry-run` | Preview without writing | `--dry-run` |

## How It Works

Claude Code skills have this format:
```yaml
---
name: my-skill
description: Use when... Triggers on: foo, bar
---

# Instructions...
```

OpenClaw skills need:
```yaml
---
description: Use when...
Triggers: foo, bar
---

# Instructions...
```

The tool parses the frontmatter, extracts triggers, and rewrites for OpenClaw.

## Related

- [alirezarezvani/claude-skills](https://github.com/alirezarezvani/claude-skills) — 170+ skills that already work on both Claude Code and OpenClaw natively

## License

MIT
