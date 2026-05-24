# Project Working Rules

## Project

- Name: 琢石橡塑官網原型
- Folder: `/Users/jacob/Documents/zuoshi-rubber-prototype`
- Type: Static HTML prototype
- Primary preview target: GitHub Pages
- Project cockpit: `docs/project-cockpit.md`

## Commands

- Local preview: open `index.html` directly in a browser
- Optional local server: `python3 -m http.server 4173`

## Content And Assets

- Main prototype file: `index.html`
- Logo asset: `assets/zuoshi-logo.jpg`
- Keep customer-facing copy in Traditional Chinese unless the client requests otherwise.
- Do not replace source copy blindly; document major content changes in the cockpit note.

## Deployment Notes

- GitHub Pages is configured by `.github/workflows/deploy-pages.yml`.
- The workflow publishes the repository root as a static artifact.
- No build step or package install is required for the current prototype.

## Git Hygiene

- Preserve existing Git history.
- Before edits, inspect current status and relevant files.
- Keep changes scoped to this prototype.
- Do not commit or push unless the user asks.

## Privacy

- Do not commit private customer data, tokens, credentials, or internal-only material.
- Treat the current prototype as client-review material suitable for GitHub preview.
