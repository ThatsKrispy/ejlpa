# The Lichter Law Group — Website

Single self-contained `index.html` (all CSS in a `<style>` block, all JS in one `<script>`),
plus `privacy.html` and `accessibility.html` sharing the same inline styling. One flat folder;
images referenced by plain filename. No build step, no framework, no dependencies.

## Deploy to Cloudflare Pages
Workers & Pages → Create → Pages → Upload assets → drag this WHOLE folder in → add ejlpa.com.
(Drag the folder, not just index.html, so the images come along.) Works as a local file too.

## Photos (SEO-friendly filenames)
- erik-lichter-attorney-miami.jpg — Erik before the lion mural (hero + founder)
- erik-lichter-lichter-law-group.jpg — studio headshot, re-cropped to match Genesis (team)
- genesis-williams-paralegal.jpg — Genesis Williams, re-cropped to match Erik (team)
- lichter-law-group-miami-office.jpg — environmental shot (firm intro)
- florida-bar-board-certified-{real-estate,business-litigation,criminal-trial,tax-law}.png — seals
- lichter-law-group-logo.png — wordmark (schema/OG logo)
- favicon.svg — lion crest

## This revision
- Removed the Fidelity / Circle-of-Excellence badge images (they read as mismatched) — the
  credential is now an elegant gold text line under Real Estate & Title.
- Re-cropped both team headshots to matched head-and-shoulders framing (faces same size, eyes aligned).
- Added scroll-reveal section animations, a back-to-top button, practice-row hover states, and
  active-nav highlighting as you scroll. All respect reduced-motion.

## SEO
Front-loaded title + meta description, descriptive alt text on every image, Open Graph + Twitter
cards, geo meta, rich JSON-LD (LegalService + Attorney + WebSite + FAQPage), sitemap + robots.

## Confirm before launch
1. Board certifications — confirm Erik holds all four shown; remove any not current.
2. Address — 5805 Blue Lagoon Dr, Suite 178, Miami, FL 33126.
3. Email — info@ejlpa.com.
