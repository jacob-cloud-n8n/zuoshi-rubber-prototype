# 琢石橡塑官網原型

This repository contains a static client-review prototype for 東莞市琢石橡塑製品有限公司.

## Preview

- Entry page: `index.html`
- GitHub Pages: enabled through `.github/workflows/deploy-pages.yml`

## Local Review

Open `index.html` directly in a browser, or run a small local server:

```bash
python3 -m http.server 4173
```

Then visit `http://localhost:4173`.

## Project Notes

- The current version is based on `琢石橡塑_網頁原型建議案_V1_20260524.html`.
- The logo reference was normalized to `assets/zuoshi-logo.jpg` for GitHub Pages.
- The prototype currently uses CDN-hosted React, ReactDOM, Babel, and Google Fonts.

## Files

- `index.html`: single-page prototype
- `assets/zuoshi-logo.jpg`: logo asset used by the page
- `docs/project-cockpit.md`: progress and handoff notes
- `AGENTS.md`: project working rules
