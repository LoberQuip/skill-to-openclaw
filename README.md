# Skill → OpenClaw Converter

<p align="center">
  <a href="https://www.npmjs.com/package/skill-to-openclaw"><img src="https://img.shields.io/npm/v/skill-to-openclaw" alt="npm"></a>
  <a href="https://github.com/quipxi/skill-to-openclaw/blob/main/LICENSE"><img src="https://img.shields.io/github/license/quipxi/skill-to-openclaw" alt="License"></a>
</p>

Convert Claude Code skills to OpenClaw skill format with a single command. Bridge the gap between the Claude Code ecosystem and OpenClaw.

## Why This Tool?

Claude Code has hundreds of community skills. Most work great in OpenClaw but need a format conversion. This tool automates that process.

**Use when:**
- You found a cool Claude Code skill and want to use it in OpenClaw
- You're migrating from Claude Code to OpenClaw
- You want to share your OpenClaw skills with Claude Code users

## Install

```bash
# Quick install
curl -sL https://raw.githubusercontent.com/quipxi/skill-to-openclaw/main/install.sh | bash

# Or manually
git clone https://github.com/quipxi/skill-to-openclaw.git ~/skill-to-openclaw
ln -sf ~/skill-to-openclaw/skill-to-openclaw.js ~/.local/bin/skill-to-openclaw
```

Requires: Node.js 18+, Git

## Usage

```bash
# From GitHub
skill-to-openclaw owner/repo
skill-to-openclaw https://github.com/owner/repo

# From local path
skill-to-openclaw ./my-claude-skill

# With custom name
skill-to-openclaw owner/repo --name my-skill

# Overwrite existing
skill-to-openclaw owner/repo --force

# Preview without writing
skill-to-openclaw owner/repo --dry-run
```

## Demo

```bash
$ skill-to-openclaw ParthJadhav/app-store-screenshots

🔄 Converting: ParthJadhav/app-store-screenshots
📦 Cloning ParthJadhav/app-store-screenshots...
📄 Found: skills/app-store-screenshots/SKILL.md
✨ Skill: app-store-screenshots
📝 Description: Use when building App Store screenshot pages...
🏷️  Triggers: app store, screenshots, marketing assets
✅ Saved to: ~/.openclaw/skills/app-store-screensshots
🎉 Skill "app-store-screenshots" ready!

Restart OpenClaw or run: openclaw skills sync
```

## What It Does

1. **Input** — Accepts GitHub repo, URL, or local path
2. **Parse** — Finds SKILL.md, extracts name, description, triggers
3. **Copy** — Copies supporting files (mockups, scripts, assets)
4. **Convert** — Rewrites SKILL.md in OpenClaw format
5. **Save** — Writes to `~/.openclaw/skills/[name]/`

## Options

| Flag | Description |
|------|-------------|
| `-n, --name` | Output skill name |
| `-f, --force` | Overwrite existing skill |
| `-d, --dry-run` | Preview without writing |
| `-h, --help` | Show help |

## Related

- [alirezarezvani/claude-skills](https://github.com/alirezarezvani/claude-skills) — 170+ skills that work on both platforms natively
- [skill-porter](https://github.com/jduncan-rva/skill-porter) — Convert between Claude Code and Gemini CLI

## License

MIT
