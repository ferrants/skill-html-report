# Components Reference

All components work with either theme. Copy HTML and corresponding CSS into your document. Components use CSS custom properties from the theme, so they adapt automatically.

---

## Shared Components

### Google Fonts Import

Always include in `<head>`:

```html
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">
```

### Reset

```css
* { box-sizing: border-box; margin: 0; padding: 0; }
```

---

## One-Pager Components (Portrait)

### Header with Accent Border

```html
<header class="header">
  <div class="header-title">Document Title</div>
  <div class="header-subtitle">Optional subtitle or date</div>
</header>
```

```css
.header {
  padding-bottom: var(--space-md);
  border-bottom: 3px solid var(--color-primary);
  margin-bottom: var(--space-lg);
}
.header-title {
  font-size: 24px;
  font-weight: 700;
  color: var(--color-text);
  letter-spacing: -0.5px;
}
.header-subtitle {
  font-size: 13px;
  color: var(--color-text-muted);
  margin-top: 4px;
}
```

### Title Block

```html
<h1 class="page-title">Your Document Title</h1>
<p class="page-subtitle">A subtitle or brief description</p>
<div class="title-rule"></div>
```

```css
.page-title {
  font-size: 28px; font-weight: 700; color: var(--color-text);
  margin-bottom: var(--space-xs); line-height: 1.1;
}
.page-subtitle {
  font-size: 15px; color: var(--color-text-muted); margin-bottom: var(--space-sm);
}
.title-rule {
  width: 80px; height: 3px;
  background: var(--color-primary);
  margin-bottom: var(--space-lg); border-radius: 2px;
}
```

### Info Cards

Four color variants: `card-blue`, `card-green`, `card-purple`, `card-orange`. Use for visual variety and grouping.

```html
<div class="info-card card-blue">
  <div class="info-header">
    <div class="info-number">01</div>
    <div class="info-title">Card Title</div>
  </div>
  <div class="info-content">
    <p>Main content explaining the concept.</p>
  </div>
</div>
```

```css
.info-card {
  border-left: 4px solid var(--color-accent);
  border-radius: var(--radius-sm);
  padding: var(--space-sm) var(--space-md);
  margin-bottom: var(--space-md);
  background: var(--color-surface);
}
.info-card.card-blue   { border-left-color: var(--color-primary); background: rgba(37, 99, 235, 0.05); }
.info-card.card-green  { border-left-color: var(--color-green); background: rgba(5, 150, 105, 0.05); }
.info-card.card-purple { border-left-color: var(--color-secondary); background: rgba(124, 58, 237, 0.05); }
.info-card.card-orange { border-left-color: var(--color-orange); background: rgba(234, 88, 12, 0.05); }

.info-header { display: flex; align-items: baseline; gap: var(--space-sm); margin-bottom: var(--space-xs); }
.info-number { font-size: 11px; font-weight: 700; letter-spacing: 0.06em; color: var(--color-primary); }
.card-green .info-number  { color: var(--color-green); }
.card-purple .info-number { color: var(--color-secondary); }
.card-orange .info-number { color: var(--color-orange); }

.info-title { font-size: 18px; font-weight: 600; color: var(--color-text); }

.info-content { font-size: 14px; color: var(--color-text); line-height: 1.5; }
.info-content p { margin-bottom: var(--space-xs); }
.info-content p:last-child { margin-bottom: 0; }
```

### Code / Highlight Blocks

Use inside info cards or standalone. Monospace blocks for code, data, or key quotes.

```html
<div class="code-block">
  <span class="code-label">Example</span>Content here in monospace. Preserves whitespace.</div>
```

```css
.code-block {
  background: var(--color-tint);
  border: 1px solid var(--color-border);
  border-radius: var(--radius-sm);
  padding: var(--space-xs) var(--space-sm);
  margin: var(--space-xs) 0;
  font-family: "SF Mono", Monaco, "Cascadia Code", "Roboto Mono", Consolas, monospace;
  font-size: 12px; line-height: 1.4;
  color: var(--color-text);
  white-space: pre-wrap; word-wrap: break-word;
}
.code-block:last-child { margin-bottom: 0; }
.code-label {
  font-family: var(--font-main);
  font-size: 10px; font-weight: 600;
  text-transform: uppercase; letter-spacing: 0.06em;
  margin-bottom: 2px; display: block;
  color: var(--color-primary);
}
.card-green .code-label  { color: var(--color-green); }
.card-purple .code-label { color: var(--color-secondary); }
.card-orange .code-label { color: var(--color-orange); }
```

### Footer (One-Pager)

```html
<footer class="page-footer">
  <div class="footer-left">Document Title</div>
  <div class="footer-right">Page 1</div>
</footer>
```

```css
.page-footer {
  margin-top: var(--space-lg);
  padding-top: var(--space-md);
  border-top: 1px solid var(--color-border);
  display: flex; justify-content: space-between; align-items: center;
  font-size: 12px; color: var(--color-text-muted);
}
```

---

## Slide Report Components (Landscape)

### Slide Page Container

Every slide is exactly 1280x720px.

```css
.report-page {
  width: 1280px;
  height: 720px;
  margin: 0 auto 40px;
  background: var(--color-surface);
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.12);
  padding: 20px 28px 28px;
  position: relative;
  overflow: hidden;
}
```

### Report Header

```html
<header class="report-header">
  <div>
    <div class="report-title">Report Title</div>
    <div class="report-subtitle">Context &mdash; Date</div>
  </div>
  <div class="logo-container">
    <!-- Optional: logo or brand text -->
    <span class="brand-text">Company</span>
  </div>
</header>
```

```css
.report-header {
  display: flex; justify-content: space-between; align-items: flex-start;
  margin-bottom: 12px;
}
.report-title { font-size: 26px; font-weight: 600; color: var(--color-text); }
.report-subtitle { font-size: 13px; margin-top: 3px; color: var(--color-text-muted); }
.logo-container { display: flex; gap: 12px; align-items: center; }
.brand-text { font-size: 18px; font-weight: 700; color: var(--color-primary); letter-spacing: -0.5px; }
.logo-img { height: 48px; width: auto; max-width: 150px; object-fit: contain; }
```

### Layout: Rows & Columns

```html
<div class="row">
  <div class="col-2-3"><!-- Wide column (2/3) --></div>
  <div class="col-1-3"><!-- Narrow column (1/3) --></div>
</div>

<div class="row">
  <div class="col-1-2"><!-- Half --></div>
  <div class="col-1-2"><!-- Half --></div>
</div>
```

```css
.row { display: flex; gap: 14px; margin-bottom: 12px; }
.col-2-3 { flex: 2; }
.col-1-3 { flex: 1; }
.col-1-2 { flex: 1; }
.col-full { flex: 1 1 100%; }
```

### Cards

Three header styles: default (primary color), accent (secondary), and muted.

```html
<!-- Default card -->
<div class="card">
  <div class="card-header">Section Title</div>
  <div class="card-body">Content here</div>
</div>

<!-- Accent card -->
<div class="card">
  <div class="card-header-accent">Highlighted Section</div>
  <div class="card-body">Content here</div>
</div>

<!-- Warning card -->
<div class="card">
  <div class="card-header-warning">Attention Needed</div>
  <div class="card-body">Content here</div>
</div>
```

```css
.card {
  border: 1px solid var(--color-border); border-radius: var(--radius-md);
  overflow: hidden; background: var(--color-surface);
}
.card + .card { margin-top: 8px; }

.card-header {
  background: var(--color-primary); color: #fff;
  padding: 5px 10px;
  font-size: 12px; font-weight: 600; text-transform: uppercase; letter-spacing: 0.5px;
}
.card-header-accent {
  background: var(--color-secondary); color: #fff;
  padding: 5px 10px;
  font-size: 12px; font-weight: 600; text-transform: uppercase; letter-spacing: 0.5px;
}
.card-header-warning {
  background: var(--color-orange); color: #fff;
  padding: 5px 10px;
  font-size: 12px; font-weight: 600; text-transform: uppercase; letter-spacing: 0.5px;
}
.card-body { padding: 8px 10px; font-size: 12px; color: var(--color-text); }
```

### Tables

Two styles: bordered (default) and borderless (for simple lists).

```html
<!-- Bordered table -->
<table>
  <tr>
    <th style="width:30%;">Column A</th>
    <th>Column B</th>
    <th style="width:15%;">Status</th>
  </tr>
  <tr>
    <td><strong>Row item</strong></td>
    <td>Description text</td>
    <td><span class="badge badge-green">Done</span></td>
  </tr>
</table>

<!-- Borderless table (for lists inside cards) -->
<table class="no-border-table">
  <tr>
    <td style="width:34%;"><strong>Label</strong></td>
    <td>Value or description</td>
  </tr>
</table>
```

```css
table { width: 100%; border-collapse: collapse; font-size: 11px; color: var(--color-text); }
th, td { border: 1px solid var(--color-border); padding: 4px 6px; vertical-align: top; }
th {
  background: var(--color-tint); font-weight: 600; text-align: left;
  color: var(--color-text-muted); font-size: 10px; text-transform: uppercase; letter-spacing: 0.5px;
}
.no-border-table th, .no-border-table td { border: none; border-bottom: 1px solid var(--color-border); }
```

### Badges

Inline status indicators for tables and labels.

```html
<span class="badge badge-green">Complete</span>
<span class="badge badge-amber">In Progress</span>
<span class="badge badge-red">Urgent</span>
<span class="badge badge-blue">Active</span>
<span class="badge badge-purple">Review</span>
<span class="badge badge-muted">Not Started</span>
```

```css
.badge {
  display: inline-block; padding: 2px 8px; border-radius: 999px;
  font-size: 10px; font-weight: 600; color: #fff;
}
.badge-green  { background: var(--color-green); }
.badge-amber  { background: var(--color-amber); color: #111; }
.badge-red    { background: var(--color-red); }
.badge-blue   { background: var(--color-primary); }
.badge-purple { background: var(--color-secondary); }
.badge-muted  { background: #9CA3AF; }
```

### Status Box

Large callout for primary status on a page.

```html
<div class="status-box">
  <div class="status-label">Current Status</div>
  <div class="status-value">On Track</div>
  <div class="status-detail">Brief summary of where things stand.</div>
</div>
```

```css
.status-box {
  border: 1px solid var(--color-border); border-radius: var(--radius-md);
  padding: 10px 12px; margin-bottom: 10px;
  background: var(--color-tint);
}
.status-label { font-weight: 600; color: var(--color-primary); font-size: 11px; margin-bottom: 3px; }
.status-value { font-size: 18px; font-weight: 700; color: var(--color-green); }
.status-detail { font-size: 11px; margin-top: 4px; color: var(--color-text-muted); }
```

### Callout / Impact Box

Highlighted block for key warnings, insights, or opportunities.

```html
<!-- Info callout -->
<div class="callout callout-info">
  <strong>Key Insight:</strong> Description of important finding.
</div>

<!-- Warning callout -->
<div class="callout callout-warning">
  <strong>Warning:</strong> Description of risk or concern.
</div>

<!-- Success callout -->
<div class="callout callout-success">
  <strong>Win:</strong> Description of positive outcome.
</div>
```

```css
.callout {
  border-radius: var(--radius-md); padding: 8px 12px;
  margin: 8px 0; font-size: 12px;
}
.callout-info {
  background: rgba(37, 99, 235, 0.08); border: 1px solid rgba(37, 99, 235, 0.2);
}
.callout-info strong { color: var(--color-primary); }
.callout-warning {
  background: rgba(217, 119, 6, 0.08); border: 1px solid rgba(217, 119, 6, 0.2);
}
.callout-warning strong { color: var(--color-amber); }
.callout-success {
  background: rgba(5, 150, 105, 0.08); border: 1px solid rgba(5, 150, 105, 0.2);
}
.callout-success strong { color: var(--color-green); }
```

### Metric Grid

For KPI / number callouts. Usually 2-4 columns.

```html
<div class="metric-grid">
  <div class="metric-item">
    <div class="metric-value">42</div>
    <div class="metric-label">Total Items</div>
  </div>
  <div class="metric-item">
    <div class="metric-value">93%</div>
    <div class="metric-label">Completion Rate</div>
  </div>
  <div class="metric-item">
    <div class="metric-value">$1.2M</div>
    <div class="metric-label">Revenue</div>
  </div>
</div>
```

```css
.metric-grid {
  display: grid; grid-template-columns: repeat(3, 1fr);
  gap: 8px; margin-top: 6px;
}
.metric-item {
  border: 1px solid var(--color-border); border-radius: var(--radius-md);
  padding: 10px; text-align: center; background: var(--color-tint);
}
.metric-value { font-size: 22px; font-weight: 700; color: var(--color-primary); }
.metric-label { font-size: 10px; color: var(--color-text-muted); margin-top: 3px; }
```

### Timeline Bar

Visual phase indicator with colored segments.

```html
<div class="timeline-bar">
  <div class="timeline-segment phase-complete" style="flex: 2;">Phase 1<br/>Done</div>
  <div class="timeline-segment phase-current" style="flex: 2;">Phase 2<br/>Current</div>
  <div class="timeline-segment phase-upcoming" style="flex: 2;">Phase 3<br/>Next</div>
</div>
```

```css
.timeline-bar {
  display: flex; height: 40px;
  border: 1px solid var(--color-border); border-radius: var(--radius-sm);
  overflow: hidden; margin: 8px 0;
}
.timeline-segment {
  display: flex; align-items: center; justify-content: center;
  font-size: 10px; font-weight: 600; color: #fff;
  padding: 4px; text-align: center;
}
.phase-complete { background: var(--color-green); }
.phase-current  { background: var(--color-primary); }
.phase-upcoming { background: var(--color-tint); color: var(--color-text-muted); }
```

### Progress Bar

For hours used, completion percentage, or capacity displays.

```html
<div class="progress-track">
  <div class="progress-fill" style="width: 65%;"></div>
</div>
<div class="progress-labels">
  <span>65 hours used</span>
  <span>100 hours total</span>
</div>
```

```css
.progress-track {
  background: var(--color-tint); border-radius: var(--radius-sm);
  height: 20px; position: relative; overflow: hidden; margin-top: 6px;
}
.progress-fill {
  background: var(--color-primary); height: 100%; border-radius: var(--radius-sm);
}
.progress-labels {
  display: flex; justify-content: space-between;
  font-size: 10px; color: var(--color-text-muted); margin-top: 4px;
}
```

### Tag Rows

Labeled content rows with colored category tags.

```html
<div class="tag-row">
  <span class="tag tag-danger">Risk</span>
  <span>Description of the risk</span>
</div>
<div class="tag-row">
  <span class="tag tag-success">Opportunity</span>
  <span>Description of the opportunity</span>
</div>
<div class="tag-row">
  <span class="tag tag-info">Note</span>
  <span>Additional context or information</span>
</div>
```

```css
.tag-row { display: flex; gap: 6px; align-items: flex-start; margin: 4px 0; }
.tag {
  display: inline-block; padding: 1px 7px; border-radius: var(--radius-sm);
  font-size: 9px; font-weight: 700; text-transform: uppercase;
  letter-spacing: 0.3px; flex-shrink: 0; margin-top: 1px;
}
.tag-danger  { background: rgba(220, 38, 38, 0.1); color: var(--color-red); border: 1px solid rgba(220, 38, 38, 0.2); }
.tag-success { background: rgba(5, 150, 105, 0.1); color: var(--color-green); border: 1px solid rgba(5, 150, 105, 0.2); }
.tag-warning { background: rgba(217, 119, 6, 0.1); color: var(--color-amber); border: 1px solid rgba(217, 119, 6, 0.2); }
.tag-info    { background: rgba(37, 99, 235, 0.1); color: var(--color-primary); border: 1px solid rgba(37, 99, 235, 0.2); }
.tag-row span:not(.tag) { font-size: 11px; color: var(--color-text); line-height: 1.4; }
```

### Summary Box

Conclusion or bottom-line block.

```html
<div class="summary-box">
  <div class="summary-title">Summary</div>
  <div class="summary-body">
    Key takeaway text. <strong>Bold for emphasis</strong> uses accent color.
  </div>
</div>
```

```css
.summary-box {
  background: var(--color-tint);
  border: 1px solid var(--color-border); border-radius: var(--radius-md);
  padding: 10px 14px; margin-top: 8px;
}
.summary-title { font-size: 13px; font-weight: 700; color: var(--color-text); margin-bottom: 4px; }
.summary-body { font-size: 12px; line-height: 1.55; color: var(--color-text); }
.summary-body strong { color: var(--color-primary); }
```

### Footer (Slide Report)

```html
<footer class="footer">
  <div class="footer-left">Report Title &mdash; Date</div>
  <div class="footer-right">Page 1 of 3</div>
</footer>
```

```css
.footer {
  position: absolute; bottom: 8px; left: 28px; right: 28px;
  font-size: 9px; display: flex; justify-content: space-between;
  color: var(--color-text-muted);
}
```
