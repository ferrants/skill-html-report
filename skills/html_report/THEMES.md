# Themes

## Clean Light (Recommended Default)

Best for: one-pagers, handouts, printed reports, professional documents. Works in both portrait and landscape.

```css
:root {
  /* Core palette */
  --color-bg: #F7F9FC;
  --color-surface: #FFFFFF;
  --color-tint: #EEF2FA;
  --color-text: #111827;
  --color-text-muted: #6B7280;
  --color-border: #D9E1EE;

  /* Accent colors */
  --color-primary: #2563EB;
  --color-primary-dark: #1D4ED8;
  --color-secondary: #7C3AED;
  --color-teal: #0D9488;
  --color-green: #059669;
  --color-amber: #D97706;
  --color-red: #DC2626;
  --color-orange: #EA580C;

  /* Semantic */
  --color-accent: var(--color-primary);
  --color-success: var(--color-green);
  --color-warning: var(--color-amber);
  --color-danger: var(--color-red);

  --font-main: "Inter", system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;

  --space-xs: 6px;
  --space-sm: 10px;
  --space-md: 16px;
  --space-lg: 24px;
  --space-xl: 36px;

  --radius-sm: 4px;
  --radius-md: 8px;
  --radius-lg: 12px;
}
```

### One-pager body styles (portrait)

```css
body {
  font-family: var(--font-main);
  font-size: 15px;
  line-height: 1.5;
  background: var(--color-bg);
  color: var(--color-text);
  padding: var(--space-lg);
  max-width: 8.5in;
  margin: 0 auto;
}
```

### Slide report body styles (landscape)

```css
body {
  margin: 0;
  padding: 20px;
  background: var(--color-bg);
  font-family: var(--font-main);
  color: var(--color-text);
}
```

### One-pager print styles

```css
@page {
  size: Letter portrait;
  margin: 0.5in;
}

@media print {
  html, body {
    margin: 0;
    padding: 0;
    -webkit-print-color-adjust: exact;
    print-color-adjust: exact;
  }
  body {
    padding: 0.4in;
    background: #fff;
  }
}
```

### Slide report print styles

```css
@media print {
  @page {
    size: Letter landscape;
    margin: 0;
  }
  body { background: #fff; padding: 0; }
  .report-page {
    page-break-after: always;
    break-after: page;
    box-shadow: none;
    margin: 0;
    width: 100%;
    height: auto;
    -webkit-print-color-adjust: exact;
    print-color-adjust: exact;
  }
}
```

---

## Dark Presentation

Best for: screen-first reports, tech audiences, slide decks viewed on monitors or projectors. Landscape orientation.

```css
:root {
  /* Core palette */
  --color-bg: #0F1117;
  --color-surface: #1A1D27;
  --color-tint: #242836;
  --color-text: #FFFFFF;
  --color-text-muted: #9CA3AF;
  --color-border: rgba(255, 255, 255, 0.1);

  /* Accent colors */
  --color-primary: #3B82F6;
  --color-primary-dark: #2563EB;
  --color-secondary: #8B5CF6;
  --color-teal: #14B8A6;
  --color-green: #10B981;
  --color-amber: #F59E0B;
  --color-red: #EF4444;
  --color-orange: #F97316;

  /* Semantic */
  --color-accent: var(--color-primary);
  --color-success: var(--color-green);
  --color-warning: var(--color-amber);
  --color-danger: var(--color-red);

  --font-main: "Inter", system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;

  --space-xs: 6px;
  --space-sm: 10px;
  --space-md: 16px;
  --space-lg: 24px;
  --space-xl: 36px;

  --radius-sm: 4px;
  --radius-md: 8px;
  --radius-lg: 12px;
}
```

### Slide page structure

```css
body {
  margin: 0;
  padding: 20px;
  background: #111;
  font-family: var(--font-main);
  color: var(--color-text);
}

.report-page {
  width: 1280px;
  height: 720px;
  margin: 0 auto 40px;
  background: var(--color-bg);
  box-shadow: 0 0 30px rgba(0, 0, 0, 0.5);
  padding: 20px 28px 28px;
  position: relative;
  overflow: hidden;
}
```

### Print styles

```css
@media print {
  @page {
    size: Letter landscape;
    margin: 0;
  }
  body { background: var(--color-bg); padding: 0; }
  .report-page {
    page-break-after: always;
    break-after: page;
    box-shadow: none;
    margin: 0;
    width: 100%;
    height: auto;
    -webkit-print-color-adjust: exact;
    print-color-adjust: exact;
  }
}
```
