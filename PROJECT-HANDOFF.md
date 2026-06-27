# The Lichter Law Group — Website Project Handoff

**Purpose of this file:** paste this into a new conversation to resume work with full context.
Everything needed to continue is here, plus the complete site is in this same folder.

---

## 1. Quick start for the next conversation

> I'm continuing work on a website for **The Lichter Law Group** (ejlpa.com), a Miami law firm.
> The complete current build is attached (a single self-contained `index.html` plus `privacy.html`,
> `accessibility.html`, all images, and Cloudflare config). Read `PROJECT-HANDOFF.md` first — it has
> the full design system, firm facts, file inventory, and open items. Don't rebuild from scratch;
> edit the existing files. Here's what I want to change next: …

Attach the whole folder (or the ZIP) so the assistant has the real source to edit.

---

## 2. What this site is

A fast, framework-free static website for a Miami law firm, deployed to **Cloudflare Pages** by
drag-and-drop. No build step, no dependencies.

**Architecture (current, decided):**
- **One self-contained `index.html`** — all CSS in a single `<style>` block, all JS in one
  `<script>` block. The whole homepage is one long single-page scroll with anchor nav
  (`#practice`, `#about`, `#faq`, `#contact`).
- **`privacy.html`** and **`accessibility.html`** — separate pages sharing the same inline styling.
- **One flat folder.** Every image is referenced by **plain filename** (e.g. `erik.jpg`, not
  `/assets/erik.jpg`). This is deliberate — absolute paths (`/styles.css`) were the recurring
  "site looks black-and-white / broken" bug, because they only resolve at a server root and break
  when you open the file locally. Plain relative filenames work both locally (file://) and on Cloudflare.

**Known cosmetic note:** opened as a local file, the display font falls back to a system serif
because Google Fonts needs a connection. It loads correctly once hosted. Not a bug.

---

## 3. Firm facts (verbatim — use for copy, schema, SEO)

- **Firm:** The Lichter Law Group. Tagline: "Your Trusted Ally in South Florida."
- **Founder:** Erik J. Lichter, Esq. — born-and-bred Miamian from Coconut Grove, played football
  for the University of Miami Hurricanes; brings that passion/energy to each case.
- **Paralegal:** Genesis Williams (interested in real estate; strong client-satisfaction focus).
- **Phone:** 305.894.6750  →  `tel:+13058946750`
- **Email:** info@ejlpa.com
- **Address:** 5805 Blue Lagoon Dr, Suite 178, Miami, FL 33126  *(CONFIRM — see open items)*
- **Geo:** 25.7836, -80.2925
- **Google rating:** 5.0
- **Four practice areas:**
  1. **Real Estate & Title** — purchase/sale, title agent & insurance, title/lien searches, escrow,
     opinion of title, 1031 guidance, power of attorney, issuing title policies. *Credential:
     Authorized Policy-Issuing Agent for Fidelity National Title; 2022 FNF Circle of Excellence.*
  2. **Business Law** — incorporation/entity formation, joint ventures, management agreements,
     legal compliance, business consulting.
  3. **Criminal Defense** — felonies, misdemeanors, expungement & record sealing.
  4. **Intellectual Property** — trademark registration, trademark guidance & strategy.
- **Board certifications shown:** Florida Bar Board Certified in Real Estate, Business Litigation,
  Criminal Trial, Tax Law. *(CONFIRM all four are current.)*
- **Socials:** facebook.com/TheLichterLawGroup · linkedin.com/company/the-lichter-law-group ·
  instagram.com/thelichterlawgroup · yelp.com/biz/the-lichter-law-group-miami

---

## 4. Design system — "The Guardian"

Grounded in the firm's own world: a **geometric faceted lion mural** on Erik's office wall. That
lion is the signature motif — recreated as an inline SVG crest (header, footer, watermarks, favicon)
and echoed by the hero photo of Erik in front of the actual mural.

**Palette (pulled from the mural):**
- `--ink:#0f1722` (midnight) · `--ink-2:#16202e` · `--slate:#1d2c3f`
- `--gold:#c9a25e` (lion bronze) · `--gold-deep:#a8823f`
- `--bone:#f0ece3` (parchment) · `--paper:#fbfaf7` · `--grey:#8a9099` · `--line:#26313f`

**Type:** Fraunces (display serif, Google Fonts) + Inter (body). Editorial, asymmetric layouts.

**Signature layouts (don't revert these):**
- Lion-mural full-bleed hero, headline "Strength when it *counts.*" (italic gold accent on "counts").
- **Indexed editorial practice list (01–04)** with hairline rules + diamond-bulleted services.
  The user explicitly REJECTED the templated card-grid look — do not bring it back.
- Asymmetric thesis split, stat band (4 / 5.0 / 1:1 / FL), "A guardian's approach" values,
  founder feature (Erik vs. lion mural), team, testimonials, FAQ accordion, mailto contact form.

**Sections alternate** midnight / parchment / slate — not evenly-stacked centered blocks.

---

## 5. Features wired in

- **Accessibility panel** (lower-left button, self-contained — NOT a third-party overlay): text
  size, readable font, high contrast, highlight links, big cursor, stop animations, hide images.
  Persists to `localStorage` key `llg-a11y`. WCAG 2.1 AA. Keyboard accessible.
- **Consent banner** gates non-essential scripts; `localStorage` key `llg-consent`. A
  `#google-reviews` mount point on the home page is ready for a future consent-gated reviews plugin.
- **Contact form** = `mailto:` to info@ejlpa.com composed in JS (no backend). Honeypot anti-spam.
- **Polish:** scroll-reveal section animations, back-to-top button (lower-right), practice-row
  hover (index turns gold), active-nav highlight on scroll. All respect `prefers-reduced-motion`.

---

## 6. SEO already done

- Front-loaded `<title>` (~39 chars) + meta description (~142 chars), within Google display limits.
- Descriptive, keyword-aware **alt text on every image**.
- Open Graph + Twitter Card tags (hero image = `erik-lichter-attorney-miami.jpg`).
- Geo meta (Miami, FL coords), `robots: index, follow, max-image-preview:large`, hreflang en-us.
- **Rich JSON-LD `@graph`** (validated): LegalService + Attorney (address, geo, areaServed,
  opening hours Mon–Fri 09:00–17:00, aggregateRating 5.0, hasOfferCatalog of the 4 services,
  sameAs socials) · Person (Erik, alumniOf University of Miami) · WebSite · FAQPage (7 Q&As).
- `sitemap.xml` (with image sitemap entry) + `robots.txt`. privacy/accessibility set to `noindex, follow`.

---

## 7. File inventory (this folder)

**Pages:** `index.html` (the whole site, ~576 lines, CSS+JS inline) · `privacy.html` ·
`accessibility.html`

**Images (plain filenames, SEO-named):**
- `erik-lichter-attorney-miami.jpg` — Erik before the lion mural → hero + founder feature
- `erik-lichter-lichter-law-group.jpg` — studio headshot → team (re-cropped to match Genesis)
- `genesis-williams-paralegal.jpg` — Genesis → team (re-cropped to match Erik; faces sized to match)
- `lichter-law-group-miami-office.jpg` — environmental/Blue Lagoon shot → "one firm" intro
- `florida-bar-board-certified-{real-estate,business-litigation,criminal-trial,tax-law}.png` —
  white-on-transparent seals; CSS inverts them on the dark Recognitions section
- `lichter-law-group-logo.png` — wordmark for schema/OG logo
- `favicon.svg` — lion crest

**Config:** `_headers` (security + caching) · `_redirects` (old WordPress `/service/*`, `/about`,
etc. → single-page anchors, 301) · `sitemap.xml` · `robots.txt`

> Note: earlier revisions had Fidelity National Title / FNF Circle-of-Excellence badge IMAGES under
> Real Estate. They were **removed** (looked mismatched) and replaced with a gold text credential
> line. Don't re-add the badge images unless asked.

---

## 8. Deploy

Cloudflare Pages → Workers & Pages → Create → Pages → **Upload assets** → drag the **whole folder**
in (not just index.html, or images won't come along) → add `ejlpa.com` as a custom domain.
No build command, no env vars.

---

## 9. OPEN ITEMS — confirm before launch

1. **Board certifications** — confirm Erik currently holds all four shown (Real Estate, Business
   Litigation, Criminal Trial, Tax Law). Remove any not active — these are regulated representations
   under The Florida Bar.
2. **Address** — verify 5805 Blue Lagoon Dr, Suite 178, Miami, FL 33126 (an older WP site
   contradicted itself on this).
3. **Email** — confirm info@ejlpa.com is correct and monitored.
4. **Florida Bar advertising compliance** — have the firm/attorney review the marketing copy; the
   site already carries an attorney-advertising disclaimer in the footer.
5. **Google reviews** — add a consent-gated reviews plugin later (mount point `#google-reviews`
   already on the home page).

---

## 10. Brand assets source (if originals are needed again)

- Client Google Drive folder ID: `1ZdRxQ8BDvIP86NPN0cy5nWzdA3XYuQ8I`
- The original photo uploads used this session include: `_TKR2260.jpg` (lion mural, = hero),
  `e1.jpg` (studio headshot), `g1.jpg` / `genesis_headshot.jpg` (Genesis), `_TKR1603.jpg`
  (environmental), the four `Board-Certified-Logo-2022-*-BW.png` seals, and
  `lichterlawgroup_logo_final-2.png` (wordmark).
- All photos here are already EXIF-rotated, resized, and progressive-JPEG optimized.
