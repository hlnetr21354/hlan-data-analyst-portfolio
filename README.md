# Nguyen Quoc Hoang Lan — Data Portfolio

Single-page personal portfolio site for **Nguyen Quoc Hoang Lan**, an entry-level data professional
with ~9 months of experience in Data Analytics & BI and hands-on exposure to data engineering
(PySpark, Databricks, CDC pipelines). Currently open to **Data Analyst**, **Data Engineer**,
**Analytical Engineer**, and **BI Analyst** roles.

Live site: https://hlnetr21354.github.io/hlan-data-analyst-portfolio/

## Structure

```
hlan-data-analyst-portfolio/
├── index.html      # entire site — markup, CSS, and JS in one file
├── image/          # profile photo and company logos
└── README.md
```

The site is intentionally a single static HTML file (no build step, no framework) — all styles are
in a `<style>` block and all behavior in a `<script>` block at the bottom of `index.html`. It's
deployed as-is via GitHub Pages.

## Sections

- **Hero** — name, target roles, short pitch
- **About** — background summary and quick facts
- **Skills** — grouped by Data Engineering, BI Tools, Languages, Python Libraries, Dev Tools, Data
  Analysis, Machine Learning, and AI usage
- **Experience** — timeline of internships (NAB Innovation Centre Vietnam, GeoComply, C98/NinetyEight)
- **Projects** — featured data engineering, analytics, and BI projects
- **Education** — degree and coursework
- **Certificates** — data-related and other certifications

## Features

- Scroll-triggered fade-in animations via `IntersectionObserver`
- Active nav-link highlighting on scroll
- Dark/light mode toggle (top-right of the nav bar), persisted in `localStorage` and defaulting to
  the visitor's OS color-scheme preference on first visit. A small inline script in `<head>` applies
  the saved theme before first paint so the page never flashes the wrong colors on load.

## Updating content

Everything lives in `index.html`:
- Theme colors are defined once as CSS custom properties under `:root` (dark) and
  `html[data-theme="light"]` (light) — update a color there and it propagates everywhere. The rest
  of the stylesheet references only those tokens (never a raw hex or `rgba`), which is what keeps
  both themes readable; add new colors as tokens in *both* blocks rather than inline.
- Each section (`#about`, `#skills`, `#experience`, `#projects`, `#education`, `#certificates`) is a
  self-contained block of cards/items — copy an existing card and edit its text to add new content.

## Running locally

No build tools required — just open `index.html` in a browser, or serve the folder:

```bash
npx serve .
```
