---
name: architecture-diagram
description: Create polished architecture diagrams (dark or light theme) as self-contained HTML+SVG files, or as standalone .svg files. Use when the user asks for system, infrastructure, cloud, security, or network topology diagrams. Default to dark theme and .html output unless the user requests otherwise.
---

# Architecture Diagram Skill

Create professional technical architecture diagrams as self-contained HTML files with inline SVG graphics and CSS styling.

> **Version 1.1** · MIT License · Authored by [Cocoon AI](mailto:hello@cocoon-ai.com)

## Themes

Two themes are available. **Default: dark.** Use light when the user explicitly asks for it (e.g. "light theme", "淺色系", "light mode").

### Dark Theme (default)

#### Color Palette

| Component Type | Fill (rgba) | Stroke |
|---------------|-------------|--------|
| Frontend | `rgba(8, 51, 68, 0.4)` | `#22d3ee` (cyan-400) |
| Backend | `rgba(6, 78, 59, 0.4)` | `#34d399` (emerald-400) |
| Database | `rgba(76, 29, 149, 0.4)` | `#a78bfa` (violet-400) |
| AWS/Cloud | `rgba(120, 53, 15, 0.3)` | `#fbbf24` (amber-400) |
| Security | `rgba(136, 19, 55, 0.4)` | `#fb7185` (rose-400) |
| Message Bus | `rgba(251, 146, 60, 0.3)` | `#fb923c` (orange-400) |
| External/Generic | `rgba(30, 41, 59, 0.5)` | `#94a3b8` (slate-400) |

#### Dark CSS Base

```css
body { background: #020617; color: #e2e8f0; }
.header h1 { color: #f1f5f9; }
.pulse-dot { background: #22d3ee; }
.toolbar-toggle { background: #1e293b; border: 1px solid #334155; color: #94a3b8; }
.toolbar-toggle:hover { background: #334155; color: #e2e8f0; }
.toolbar-actions { background: #1e293b; border: 1px solid #334155; }
.toolbar-actions button { color: #94a3b8; }
.toolbar-actions button:hover { background: #334155; color: #e2e8f0; }
.diagram-card { background: #0f172a; border: 1px solid #1e293b; }
.card { background: #0f172a; border: 1px solid #1e293b; }
.card h3 { color: #f1f5f9; }
.card ul li { color: #64748b; }
.footer { color: #334155; border-top: 1px solid #1e293b; }
```

#### Dark SVG Background

```svg
<!-- SVG background -->
<rect width="W" height="H" fill="#020617"/>
<rect width="W" height="H" fill="url(#grid)"/>
<!-- Grid stroke color -->
<path ... stroke="#1e293b" stroke-width="0.5"/>
```

#### Dark Component Masking (opaque underlay)

```svg
<rect x="X" y="Y" width="W" height="H" rx="6" fill="#0f172a"/>
<rect x="X" y="Y" width="W" height="H" rx="6" fill="rgba(76, 29, 149, 0.4)" stroke="#a78bfa" stroke-width="1.5"/>
```

#### Dark Component Label Colors

- Component name: `fill="white"`
- Sublabel / detail text: `fill="#94a3b8"`
- Tech stack highlight text: use stroke color at -200 lightness step (e.g. `#67e8f9` for frontend, `#6ee7b7` for backend)
- Divider line: use stroke color darkened (e.g. `#1e4a5c` for frontend, `#1a4a36` for backend)
- Legend / annotation text: `fill="#64748b"` or `fill="#475569"`

#### Dark Info Card Dot Colors

```css
.card-dot.cyan    { background: #22d3ee; }
.card-dot.emerald { background: #34d399; }
.card-dot.violet  { background: #a78bfa; }
```

---

### Light Theme

Use when the user requests light/淺色/bright mode.

#### Light Color Palette

| Component Type | Fill (rgba) | Stroke | Label Color |
|---------------|-------------|--------|-------------|
| Frontend | `rgba(224, 242, 254, 0.85)` | `#0284c7` (sky-600) | `#0c4a6e` (sky-950) |
| Backend | `rgba(209, 250, 229, 0.85)` | `#059669` (emerald-600) | `#064e3b` (emerald-950) |
| Database | `rgba(237, 233, 254, 0.85)` | `#7c3aed` (violet-600) | `#2e1065` (violet-950) |
| AWS/Cloud | `rgba(254, 243, 199, 0.85)` | `#d97706` (amber-600) | `#78350f` (amber-950) |
| Security | `rgba(255, 228, 230, 0.85)` | `#e11d48` (rose-600) | `#881337` (rose-950) |
| Message Bus | `rgba(255, 237, 213, 0.85)` | `#ea580c` (orange-600) | `#7c2d12` (orange-950) |
| External/Generic | `rgba(241, 245, 249, 0.9)` | `#64748b` (slate-500) | `#0f172a` (slate-900) |

#### Light CSS Base

```css
body { background: #f1f5f9; color: #0f172a; }
.header h1 { color: #0f172a; }
.pulse-dot { background: #0284c7; }
.toolbar-toggle { background: #ffffff; border: 1px solid #e2e8f0; color: #64748b; box-shadow: 0 1px 2px rgba(0,0,0,0.05); }
.toolbar-toggle:hover { background: #f1f5f9; color: #0f172a; }
.toolbar-actions { background: #ffffff; border: 1px solid #e2e8f0; box-shadow: 0 4px 12px rgba(0,0,0,0.08); }
.toolbar-actions button { color: #64748b; }
.toolbar-actions button:hover { background: #f1f5f9; color: #0f172a; }
.diagram-card { background: #ffffff; border: 1px solid #e2e8f0; box-shadow: 0 1px 3px rgba(0,0,0,0.06); }
.card { background: #ffffff; border: 1px solid #e2e8f0; box-shadow: 0 1px 3px rgba(0,0,0,0.05); }
.card h3 { color: #0f172a; }
.card ul li { color: #64748b; }
.footer { color: #94a3b8; border-top: 1px solid #e2e8f0; }
```

#### Light SVG Background

```svg
<!-- SVG background -->
<rect width="W" height="H" fill="#f8fafc"/>
<rect width="W" height="H" fill="url(#grid)"/>
<!-- Grid stroke color -->
<path ... stroke="#e2e8f0" stroke-width="0.5"/>
```

#### Light Component Masking (opaque underlay)

Use `#f8fafc` (not `#0f172a`) as the opaque underlay rect:

```svg
<rect x="X" y="Y" width="W" height="H" rx="6" fill="#f8fafc"/>
<rect x="X" y="Y" width="W" height="H" rx="6" fill="rgba(237, 233, 254, 0.85)" stroke="#7c3aed" stroke-width="1.5"/>
```

#### Light Component Label Colors

- Component name: use the **Label Color** from the palette table above (dark tint of the component color)
- Sublabel / detail text: `fill="#64748b"`
- Tech stack highlight text: use the stroke color directly (e.g. `#0284c7` for frontend, `#059669` for backend)
- Divider line: use the stroke color lightened to -200 step (e.g. `#bae6fd` for frontend, `#a7f3d0` for backend, `#ddd6fe` for database)
- Legend / annotation text: `fill="#64748b"` or `fill="#94a3b8"`

#### Light Info Card Dot Colors

```css
.card-dot.cyan    { background: #0284c7; }
.card-dot.emerald { background: #059669; }
.card-dot.violet  { background: #7c3aed; }
```

#### Light Arrow Colors

```svg
<marker id="arrow-sky"     ...><polygon ... fill="#0284c7"/></marker>
<marker id="arrow-emerald" ...><polygon ... fill="#059669"/></marker>
<marker id="arrow-violet"  ...><polygon ... fill="#7c3aed"/></marker>
<marker id="arrow"         ...><polygon ... fill="#94a3b8"/></marker>
```

---

## Design System

### Typography

Use JetBrains Mono for all text (monospace, technical aesthetic):
```html
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;600;700&display=swap" rel="stylesheet">
```

Font sizes: 12px for component names, 9px for sublabels, 8px for annotations, 7px for tiny labels.

### Visual Elements

**Background:** `#020617` (slate-950) with subtle grid pattern:
```svg
<pattern id="grid" width="40" height="40" patternUnits="userSpaceOnUse">
  <path d="M 40 0 L 0 0 0 40" fill="none" stroke="#1e293b" stroke-width="0.5"/>
</pattern>
```

**Component boxes:** Rounded rectangles (`rx="6"`) with 1.5px stroke, semi-transparent fills.

**Security groups:** Dashed stroke (`stroke-dasharray="4,4"`), transparent fill, rose color.

**Region boundaries:** Larger dashed stroke (`stroke-dasharray="8,4"`), amber color, `rx="12"`.

**Arrows:** Use SVG marker for arrowheads:
```svg
<marker id="arrowhead" markerWidth="10" markerHeight="7" refX="9" refY="3.5" orient="auto">
  <polygon points="0 0, 10 3.5, 0 7" fill="#64748b" />
</marker>
```

**Arrow z-order:** Draw connection arrows early in the SVG (after the background grid) so they render behind component boxes. SVG elements are painted in document order, so arrows drawn first will appear behind shapes drawn later.

**Masking arrows behind transparent fills:** Since component boxes use semi-transparent fills (`rgba(..., 0.4)`), arrows behind them will show through. To fully mask arrows, draw an opaque background rect (e.g., `fill="#0f172a"`) at the same position before drawing the semi-transparent styled rect on top:
```svg
<!-- Opaque background to mask arrows -->
<rect x="X" y="Y" width="W" height="H" rx="6" fill="#0f172a"/>
<!-- Styled component on top -->
<rect x="X" y="Y" width="W" height="H" rx="6" fill="rgba(76, 29, 149, 0.4)" stroke="#a78bfa" stroke-width="1.5"/>
```

**Auth/security flows:** Dashed lines in rose color (`#fb7185`).

**Message buses / Event buses:** Small connector elements between services. Use orange color (`#fb923c` stroke, `rgba(251, 146, 60, 0.3)` fill):
```svg
<rect x="X" y="Y" width="120" height="20" rx="4" fill="rgba(251, 146, 60, 0.3)" stroke="#fb923c" stroke-width="1"/>
<text x="CENTER_X" y="Y+14" fill="#fb923c" font-size="7" text-anchor="middle">Kafka / RabbitMQ</text>
```

### Spacing Rules

**CRITICAL:** When stacking components vertically, ensure proper spacing to avoid overlaps:

- **Standard component height:** 60px for services, 80-120px for larger components
- **Minimum vertical gap between components:** 40px
- **Inline connectors (message buses):** Place IN the gap between components, not overlapping

**Example vertical layout:**
```
Component A: y=70,  height=60  → ends at y=130
Gap:         y=130 to y=170   → 40px gap, place bus at y=140 (20px tall)
Component B: y=170, height=60  → ends at y=230
```

**Wrong:** Placing a message bus at y=160 when Component B starts at y=170 (causes overlap)
**Right:** Placing a message bus at y=140, centered in the 40px gap (y=130 to y=170)

### Legend Placement

**CRITICAL:** Place legends OUTSIDE all boundary boxes (region boundaries, cluster boundaries, security groups).

- Calculate where all boundaries end (y position + height)
- Place legend at least 20px below the lowest boundary
- Expand SVG viewBox height if needed to accommodate

**Example:**
```
Kubernetes Cluster: y=30, height=460 → ends at y=490
Legend should start at: y=510 or below
SVG viewBox height: at least 560 to fit legend
```

**Wrong:** Legend at y=470 inside a cluster boundary that ends at y=490
**Right:** Legend at y=510, below the cluster boundary, with viewBox height extended

### Layout Structure

1. **Header** - Title with pulsing dot indicator, subtitle, and export toolbar
2. **Main SVG diagram** - Contained in rounded border card
3. **Summary cards** - Grid of 3 cards below diagram with key details
4. **Footer** - Minimal metadata line

### Export Toolbar (built-in)

Every diagram ships with a single unobtrusive `⋯` toggle in the header. Click it to reveal three buttons — 📋 Copy (high-DPI PNG to clipboard, scale: 2), 🖼️ PNG (high-DPI PNG download), 📄 PDF (PNG embedded in a one-page PDF via jsPDF). The toolbar collapses back to the icon by default so it doesn't clutter the diagram. All three formats use the same html2canvas capture (with the toolbar excluded and 32px padding around the content), so PDF preserves the dark theme without going through the browser's print dialog.

When generating a new diagram, keep these intact in the template:
- The two CDN scripts in `<head>` (pinned versions, with Subresource Integrity hashes and `crossorigin="anonymous"`):
  - `https://cdn.jsdelivr.net/npm/html2canvas@1.4.1/dist/html2canvas.min.js` — `integrity="sha384-ZZ1pncU3bQe8y31yfZdMFdSpttDoPmOZg2wguVK9almUodir1PghgT0eY7Mrty8H"`
  - `https://cdn.jsdelivr.net/npm/jspdf@2.5.2/dist/jspdf.umd.min.js` — `integrity="sha384-en/ztfPSRkGfME4KIm05joYXynqzUgbsG5nMrj/xEFAHXkeZfO3yMK8QQ+mP7p1/"`
  - SRI ensures generated diagrams are tamper-resistant against CDN compromise. Do not modify the hashes; if the version is bumped, the new hash must be computed fresh.
- `id="report-container"` on the outermost `.container` div (this is what gets captured)
- `.toolbar` markup with `.toolbar-actions` (collapsed by default) and `.toolbar-toggle` (the `⋯` button)
- `.toolbar` CSS + `@media print { .toolbar { display: none !important; } }`
- `copyAsImage()`, `downloadPNG()`, and `downloadPDF()` script before `</body>`, all using `getBoundingClientRect()` + `html2canvas(document.body, { x, y, width, height, ignoreElements })` to capture a precise rect with breathing room and no toolbar

Caveats: clipboard API needs a user gesture and a secure context (https/file/localhost). SVG `<foreignObject>` renders inconsistently in html2canvas — stick to plain `<svg>` shapes and `<text>`. Bump `scale: 2` to `3` or `4` for higher-res output.

### Component Box Pattern

```svg
<rect x="X" y="Y" width="W" height="H" rx="6" fill="FILL_COLOR" stroke="STROKE_COLOR" stroke-width="1.5"/>
<text x="CENTER_X" y="Y+20" fill="white" font-size="11" font-weight="600" text-anchor="middle">LABEL</text>
<text x="CENTER_X" y="Y+36" fill="#94a3b8" font-size="9" text-anchor="middle">sublabel</text>
```

### Info Card Pattern

```html
<div class="card">
  <div class="card-header">
    <div class="card-dot COLOR"></div>
    <h3>Title</h3>
  </div>
  <ul>
    <li>• Item one</li>
    <li>• Item two</li>
  </ul>
</div>
```

## Template

Copy and customize the template at `resources/template.html`. Key customization points:

1. Update the `<title>` and header text
2. Modify SVG viewBox dimensions if needed (default: `1000 x 680`)
3. Add/remove/reposition component boxes
4. Draw connection arrows between components
5. Update the three summary cards
6. Update footer metadata

## Output Formats

### HTML output (default)

Use when the user does not specify a format, or asks for `.html`.

Produce a single self-contained `.html` file with:
- Embedded CSS (no external stylesheets except Google Fonts)
- Inline SVG (no external images)
- Header, summary cards, footer, and export toolbar (PNG / PDF)

The file renders correctly when opened directly in any modern browser. The export toolbar uses two CDN scripts (html2canvas and jsPDF) — no other JavaScript dependencies.

### SVG output

Use when the user explicitly asks for an `.svg` file (e.g. "output svg", "產生 svg", "svg 檔").

Produce a standalone `.svg` file. Constraints and rules:

**Root element:**
```svg
<svg xmlns="http://www.w3.org/2000/svg"
     viewBox="0 0 WIDTH HEIGHT"
     width="WIDTH" height="HEIGHT">
```

Always include both `viewBox` and explicit `width`/`height` so the file renders correctly in browsers, Figma, and image viewers.

**Fonts:** Embed a `<style>` block inside `<svg>` with a Google Fonts `@import` and a monospace fallback:
```svg
<defs>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;600;700');
    text { font-family: 'JetBrains Mono', 'Courier New', monospace; }
  </style>
</defs>
```

**No JavaScript:** SVG files must not contain `<script>` tags. The export toolbar is omitted entirely.

**No HTML elements:** Everything must be SVG primitives (`<rect>`, `<text>`, `<line>`, `<path>`, `<circle>`, `<ellipse>`, `<marker>`, `<pattern>`, `<defs>`). No `<div>`, `<button>`, or HTML wrappers.

**Title and subtitle:** Since there is no HTML header, embed title and subtitle as SVG `<text>` elements at the top of the diagram:
```svg
<!-- Pulse dot (animated via CSS inside <style>) -->
<circle id="pulse" cx="30" cy="30" r="5" fill="#22d3ee"/>
<text x="44" y="34" fill="#f1f5f9" font-size="16" font-weight="700">Diagram Title</text>
<text x="44" y="50" fill="#64748b" font-size="10">subtitle text</text>
```

For the pulse animation, add this inside the `<style>` block:
```css
#pulse { animation: pulse 2s infinite; }
@keyframes pulse { 0%,100%{opacity:1;r:5} 50%{opacity:0.5;r:6.5} }
```

**Layout:** Reserve ~60px at the top for the title row. Shift all diagram content down by that amount (e.g. components start at `y=80` instead of `y=20`).

**Summary cards:** Omit the HTML summary card grid. If a legend is needed, render it as SVG `<rect>` + `<text>` elements inside the SVG (same legend rules as HTML output — place outside all boundary boxes).

**Theme:** Dark and light palettes apply identically to SVG output. Use the same colors from the `## Themes` section.

**File size:** SVG output is purely declarative — no CDN scripts, no base64 images. The file will be small and fully portable.
