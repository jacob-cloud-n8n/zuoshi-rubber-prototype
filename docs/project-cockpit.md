# 琢石橡塑官網原型 Cockpit

## Current State

- Date: 2026-05-29
- Status: First client revision is published to GitHub Pages and ready for client review.
- Source draft: `/Users/jacob/Downloads/琢石橡塑_網頁原型建議案_V1_20260524.html`
- Local project folder: `/Users/jacob/Documents/zuoshi-rubber-prototype`

## What Was Initialized

- Static prototype entry: `index.html`
- Logo asset copied to `assets/zuoshi-logo.jpg`
- GitHub Pages workflow added for static preview
- Project rules added in `AGENTS.md`
- README and `.gitignore` added

## Adjustments From Draft

- Replaced missing draft logo reference with `assets/zuoshi-logo.jpg`.
- Switched React and ReactDOM CDN URLs from development builds to production builds.

## Next Steps

- Collect feedback on the first client revision.
- Decide whether the next iteration remains a static prototype or becomes a structured Astro site.

## Custom Domain Handoff

- Candidate production domain: `jasper-newmater.com`
- DNS provider observed on 2026-05-25: GoDaddy (`ns37.domaincontrol.com`, `ns38.domaincontrol.com`)
- Existing routing observed on 2026-05-25:
  - Root domain currently resolves to `35.172.94.1` and `100.24.208.97`.
  - `www.jasper-newmater.com` currently points to `s.multiscreensite.com`.
- Impact: attaching the domain to the new site will replace the current website routing for the root domain and `www`.

### Client Confirmation Checklist

- [ ] Confirm the intended production domain spelling is exactly `jasper-newmater.com`.
- [ ] Confirm whether the website currently displayed on that domain is an old site to be replaced.
- [ ] Confirm the approved go-live date and acceptable switching window.
- [ ] Confirm who can provide GoDaddy DNS access or perform the requested DNS edits.
- [ ] Confirm whether both `jasper-newmater.com` and `www.jasper-newmater.com` should open the new website.
- [ ] Confirm whether any company email uses this domain so mail-related DNS records must remain untouched.
- [ ] Confirm final website copy, products, contact details, and legal/privacy content before the domain switch.
- [ ] Confirm whether the inquiry form needs actual message submission before public launch.

### Implementation Checklist After Approval

- [ ] Capture or export the existing DNS records before editing.
- [ ] Finish production-ready site content and required form behavior.
- [ ] Add `jasper-newmater.com` as the GitHub Pages custom domain.
- [ ] Replace root-domain website A records with GitHub Pages A records.
- [ ] Replace the `www` CNAME value with `jacob-cloud-n8n.github.io`.
- [ ] Leave mail and verification records such as MX and unrelated TXT records unchanged.
- [ ] Verify root and `www` DNS propagation.
- [ ] Enable and verify HTTPS after GitHub issues the certificate.
- [ ] Check both public URLs and preserve the previous DNS snapshot for rollback.

## Shutdown Log

### 2026-05-29

- Replaced `index.html` with the first client revision from `/Users/jacob/Downloads/zhuoshi-final-0529.html`.
- Added the image assets referenced by the revised homepage.
- Verified local homepage and referenced images returned HTTP 200.
- Published commit `66e8f45` to GitHub Pages and confirmed the public preview returned HTTP 200.
- Work paused pending client feedback on the first revision.

### 2026-05-25

- Confirmed that `jasper-newmater.com` currently routes to an existing website service.
- Recorded client questions and implementation steps required before a GitHub Pages domain switch.
- No DNS or public-site configuration changes were made; work paused pending client confirmation.

### 2026-05-24

- GitHub Pages preview published and confirmed reachable.
- Preview link provided to the client for first review.
- Work paused pending client feedback.

### 2026-05-31 (Zuo Shi Design Critique & Optimization)

- Synced and committed the latest prototype version from Open Design local repository (May 30 snapshot) including high-fidelity factory assets.
- Conducted design review/critique and created `docs/specs_zuoshi_critique.md` to eliminate generic "AI slop" characteristics.
- Defined and invoked `opencode` execution subagent to rewrite `index.html`:
  - Upgraded styling palette to warm Alabaster, deep Graphite Charcoal, and rich Terracotta.
  - Replaced `"PRODUCT IMAGE"` placeholder text with custom dynamic hex-grid polymer SVG illustrations.
  - Fixed single-page routing refresh bug with custom React Hash Router state tracking.
- Successfully verified and pushed changes to GitHub Pages; verified the live preview returns HTTP 200.

