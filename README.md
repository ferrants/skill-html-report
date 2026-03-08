# skill-html-report

A [Claude Code](https://docs.anthropic.com/en/docs/claude-code) skill for generating professional HTML reports and documents optimized for printing to PDF.

## Install

```sh
claude plugin install /path/to/skill-html-report
```

Project-scoped (added to `.claude/plugins.json` in a repo):

```sh
claude plugin install /path/to/skill-html-report --scope project
```

## What it does

- Generates self-contained HTML files with all CSS inline — no external dependencies
- Two document formats: **single-page documents** (portrait) and **slide-style reports** (landscape, 1280x720px per page)
- Two clean themes: **Clean Light** (white/navy, great for print) and **Dark Presentation** (dark backgrounds, great for screen)
- Full component library: cards, tables, badges, metric grids, progress bars, timelines, callouts, and more
- Print-optimized with proper `@page` rules, color preservation, and page breaks
- Works with any browser's "Print to PDF" or "Save as PDF" feature

## Usage

Describe the report you want to create:

```
Create an HTML report showing our Q1 sales performance with a cover page,
three department breakdowns, and a summary page.
```

Or ask for a single-page document:

```
Generate a one-page project status handout with our key metrics and next steps.
```

The skill handles layout, typography, color, and print optimization automatically.

## Requirements

- Claude Code
- A web browser (for viewing and printing to PDF)

## License

MIT
