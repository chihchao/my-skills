# My Claude Code Skills

A personal collection of Claude Code skills. Each skill lives in `skills/<skill-name>/` and contains a `SKILL.md` plus any supporting resources.

## How to install a skill

Copy the skill directory into your project's `.claude/skills/`:

```bash
cp -r skills/<skill-name> /path/to/your-project/.claude/skills/
```

Claude Code will automatically discover and load any skill found in `.claude/skills/<skill-name>/SKILL.md`.

---

## Skills

### [architecture-diagram](skills/architecture-diagram/)

Create polished system/infrastructure/cloud/network topology diagrams as self-contained HTML+SVG files or standalone `.svg` files. Supports dark theme (default) and light theme.

**Trigger:** Ask for a system, infrastructure, cloud, security, or network topology diagram.

**Output formats:** `.html` (default, includes export toolbar for PNG/PDF) · `.svg`

**Features:**
- Dark / light theme with full color palette
- Export toolbar built into HTML output (PNG, PDF via html2canvas + jsPDF)
- Includes a `resources/template.html` to use as a starting point

---
