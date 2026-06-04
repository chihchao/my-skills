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

### [notebooklm](skills/notebooklm/)

連接 NotebookLM MCP（AntiGravity 版）。安裝 `notebooklm-mcp-cli`、瀏覽器 OAuth 登入，並將 MCP 伺服器註冊到 AntiGravity 設定。

**Trigger:** 說「連接 NotebookLM」或「設定 NotebookLM」時載入。

**Source:** [mathruffian-dot/antigravity-lazy-pack](https://github.com/mathruffian-dot/antigravity-lazy-pack)

---

### [ai-draw](skills/ai-draw/)

生圖指引（AntiGravity 版）。提供內建生圖（無需 API Key）與 OpenAI API 兩條路線，以及建議的中文提示格式。

**Trigger:** 說「生圖」「畫圖」或「產生圖片」時載入。

**Source:** [mathruffian-dot/antigravity-lazy-pack](https://github.com/mathruffian-dot/antigravity-lazy-pack)

---

## 核心原則

- **不放私人資料**：不放 NotebookLM ID、生成圖片、API key、token 等
- **走 OAuth 登入**，不複製 cookie 或 session token

---
