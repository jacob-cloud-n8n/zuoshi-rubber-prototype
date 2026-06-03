# 琢石橡塑官網原型 Cockpit

## Current State

- Date: 2026-06-03
- Status: Latest mobile navigation and product browsing fixes are published to GitHub Pages for phone review.
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

- Verify Antig's final handoff claims against the live prototype and source.
- Collect feedback on the latest 22-product prototype.
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

### 2026-06-03

- Mobile product browsing revision:
  - Converted the phone product catalog from desktop-style list/preview interaction into searchable product result cards.
  - Preserved the approved desktop product list and preview layout.
  - Reworked product detail pages on mobile into a single-column layout so tabs, text, and diagrams no longer squeeze horizontally.
  - Converted product-detail and technical-spec tabs to real button controls for more stable touch behavior.
  - Kept technical tables horizontally scrollable on mobile to protect chemical formulas, model names, and numeric columns.
- Mobile navigation revision:
  - Added a phone-only header menu button.
  - Added menu entries for 首頁, 關於我們, 產品目錄, 技術規格, and 聯絡我們.
  - Current mobile menu item highlights the active page and closes automatically after navigation.
  - Hid the cropped mobile header quote button to avoid horizontal overflow.
- Validation and publish:
  - Local static preview returned HTTP 200.
  - Chrome headless mobile screenshots verified product catalog, product detail, technical spec tabs, and mobile menu display.
  - Published commit `1d01aba` (`Improve mobile product browsing`) to GitHub Pages.
  - Published commit `1cd9860` (`Add mobile navigation menu`) to GitHub Pages.
  - Latest public preview remains `https://jacob-cloud-n8n.github.io/zuoshi-rubber-prototype/`.

### 2026-06-02

- Product catalog list-view revision:
  - Reworked the product catalog from a 22-card grid into a list-style searchable index based on client feedback and competitor reference.
  - Added product grouping: 發泡與膨脹助劑, 功能性助劑, 顏料與色母, and 特殊加工助劑.
  - Added keyword search across Chinese names, English names, model hints, materials, and product descriptors.
  - Preserved the existing product detail pages and linked each list item to the full detail view.

- Applied the latest client PDF revision request:
  - Updated the homepage banner to use the PDF page 3 Corporate Vision / 企業願景 copy.
  - Re-aligned product prose fields against the final PDF text while leaving technical table rows untouched.
  - Removed duplicate `● / X / ○` usage legend text from pigment product overview content; the legend remains in the technical data table area.
  - Hid empty product detail tabs so pigment pages do not show PDF-absent application/storage copy.
- Follow-up language consistency pass:
  - Converted public site copy to Traditional Chinese after the client requested full-site Traditional Chinese.
  - Preserved technical rows, model codes, CAS numbers, English labels, and numeric values.
  - Corrected address wording after conversion so `歡雅里` remains an administrative place name.
- PDF page 7 certification alignment:
  - Added the missing ROHS report image from PDF page 7.
  - Replaced the generated crops with the original report screenshots from `/Users/jacob/Documents/各專案/琢石網站/`.
  - Corrected certification/report cards to match PDF page 7: REACH, 海/陸/空運輸鑑定, 鄰苯 Phthalates, ROHS, 納稅信用 A 級, and 常年法律顧問.
  - Removed the incorrect split between separate 海洋/航空 transport report cards because the PDF shows one combined 海/陸/空運輸鑑定報告.
  - Cropped the in-image blue report labels from the four SGS report screenshots so they do not duplicate or overlap the card titles below.
- Local validation:
  - `python3 -m http.server 4173` served the prototype successfully.
  - `curl -I http://127.0.0.1:4173/` returned HTTP 200.
  - Source checks confirmed homepage vision copy, dynamic product tabs, and retained technical-data legend.
- opencode note: version `1.15.12` is installed, but actual `opencode run` currently fails locally with `Failed to run the query 'PRAGMA wal_checkpoint(PASSIVE)'`; no files were edited by opencode.

- Resumed from Antig handoff and confirmed the latest local and remote commit is `cd1cedd`.
- Latest public preview remains `https://jacob-cloud-n8n.github.io/zuoshi-rubber-prototype/`.
- Verified Antig handoff items before continuing:
  - Product card layout alignment CSS is present using Flexbox height and spacing rules.
  - `fluorescent-pigment-p18` needed follow-up correction for the full instant-fluorescence characteristic text and special storage wording.
  - Page 18 fluorescent pigment rows needed explicit `colorHex` values so the `呈色參考` pill column renders visible colors.
  - Pigment table color badge logic needed fluorescent color checks before generic color checks.
- `jasper-newmater.com` remains parked on the existing website service until client approval for DNS switch.

### 2026-06-01 (22-Product Data Completion)

- Added dynamic product detail rendering for the full 22-product dataset.
- Fixed JavaScript syntax issues introduced during data patching.
- Completed table/data alignment work including expandable microspheres and PDF product content.
- Final pushed commit before this startup: `cd1cedd` (`feat: 修正版面對齊、補齊螢光顏料完整PDF文字與新增顏料類呈色參考`).
- GitHub Pages deployment for `cd1cedd` completed successfully.

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
