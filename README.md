# Skill → OpenClaw Converter

Convert Claude Code skills to OpenClaw skill format.

## Install

```bash
curl -sL https://raw.githubusercontent.com/quipxi/skill-to-openclaw/main/install.sh | bash
```

Requires: Node.js 18+, Git

## Usage

```bash
# From GitHub
skill-to-openclaw owner/repo

# From local path
skill-to-openclaw ./my-skill
```

## Example

```bash
$ skill-to-openclaw ParthJadhav/app-store-screenshots

🔄 Converting: ParthJadhav/app-store-screenshots
📦 Cloning...
📄 Found: skills/app-store-screenshots/SKILL.md
✨ Skill: app-store-screenshots
✅ Saved to: ~/.openclaw/skills/app-store-screenshots

Restart OpenClaw or run: openclaw skills sync
```

## Options

- `--name` — Custom skill name
- `--force` — Overwrite existing
- `--dry-run` — Preview only

## License

MIT
