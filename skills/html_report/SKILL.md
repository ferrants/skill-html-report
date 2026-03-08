---
name: html_report
description: "Generate professional HTML reports and documents optimized for printing to PDF — one-pagers, slide decks, dashboards, and multi-page reports."
---

# HTML Report Generator

## Quick Start

1. Determine document type: **one-pager** (portrait) or **slide report** (landscape)
2. Choose theme: **Clean Light** or **Dark Presentation** — see [THEMES.md](THEMES.md)
3. Assemble components from [COMPONENTS.md](COMPONENTS.md)
4. Generate a single self-contained HTML file (all CSS inline in `<style>`)

## Document Types

### One-Pager / Handout (Letter portrait)
- Theme: **Clean Light** (recommended) or Dark Presentation
- Max-width: 8.5in, single continuous page
- Use for: tip sheets, checklists, guides, summaries, handouts, one-page reports
- Components: header, title block, content cards, info blocks, tables, footer

### Slide-Style Report (Landscape)
- Theme: **Clean Light** or **Dark Presentation**
- Fixed dimensions: 1280x720px per "page"
- Use for: status reports, audits, strategy decks, quarterly reviews, dashboards
- Components: report header, cards, tables, badges, metric grids, timelines, progress bars, callouts, footer

## Workflow

1. **Pick theme** based on document type and user preference
2. **Build the skeleton**: `<!DOCTYPE html>` + theme CSS from [THEMES.md](THEMES.md) + `<body>`
3. **Add header**: title and optional branding
4. **Add content sections**: choose components from [COMPONENTS.md](COMPONENTS.md)
5. **Add footer**: context line with page info
6. **Verify**: all CSS is in `<style>` block, no external dependencies except Google Fonts (Inter)

## Rules

- **Self-contained** — one `.html` file, no external CSS/JS
- **Always include** `<link>` for Inter font from Google Fonts
- **Always include** print styles with `-webkit-print-color-adjust: exact` and `print-color-adjust: exact`
- **Use CSS custom properties** (`:root` vars) for all colors — makes theming easy
- **Use semantic HTML** (`<header>`, `<footer>`, `<section>`)
- **Keep text concise** — these are visual documents, not essays
- **Content must fit** — for slide reports, nothing should overflow the 1280x720 page. Adjust font sizes and spacing to fit.
- **Match component patterns** exactly from [COMPONENTS.md](COMPONENTS.md)

## Reference Files

- [THEMES.md](THEMES.md) — Full CSS variable sets for each theme
- [COMPONENTS.md](COMPONENTS.md) — HTML/CSS snippets for every component
- [REFERENCE.html](REFERENCE.html) — Complete working example with all components
