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

### [vercel](skills/vercel/)

使用 Vercel CLI 部署與管理專案。涵蓋預覽／正式部署、環境變數管理、日誌查看與 rollback。

**Trigger:** 說「部署到 Vercel」「vercel deploy」「vercel 設定」時載入。

**版本:** `vercel@52.0.0`

---

### [github-cli](skills/github-cli/)

使用 GitHub CLI (`gh`) 操作 PR、Issue、Release 與 Actions。

**Trigger:** 說「建立 PR」「gh pr」「github issue」「查看 CI」時載入。

**版本:** `gh@2.91.0`

---

### [firebase](skills/firebase/)

使用 Firebase CLI 部署與管理 Firebase 服務（Hosting、Functions、Firestore rules 等）。涵蓋 Emulator 本地開發與多環境部署。

**Trigger:** 說「部署到 Firebase」「firebase deploy」「開 emulator」時載入。

**版本:** `firebase@15.19.0`

---

### [skill-creator](skills/skill-creator/)

Create new skills, modify and improve existing skills, and measure skill performance.

**Trigger:** Use when creating a skill from scratch, editing/optimizing an existing skill, running evals, benchmarking performance, or optimizing a skill's description for better triggering accuracy.

**Source:** [anthropics/skills](https://github.com/anthropics/skills/tree/main/skills/skill-creator)

---

## 核心原則

- **不放私人資料**：不放 NotebookLM ID、生成圖片、API key、token 等
- **走 OAuth 登入**，不複製 cookie 或 session token

---
