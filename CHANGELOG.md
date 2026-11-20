# Changelog

## 2026-11-19 — Vector SVG logos
- Converted the EPS master to SVG (vector paths only) in three versions: full colour, white, black. CMYK drift was corrected to the official RGB values (#0078AE / #C1D82F).

## 2026-11-19 — Readability and agent pass
- Rewrote README: a 60-second brand summary, an "I want to…" index, trust labels, a repo map, and known gaps.
- Added AGENTS.md (rules, tokens and component defaults for AI agents) and CLAUDE.md (imports AGENTS.md).
- Added preview.html, a visual specimen built from the tokens: palette with live contrast grades, type scale, buttons, tabs, fields, alerts, logos, textures, spacing.
- Added a README to docs/, tokens/, assets/ and sources/.
- **Fixed:** grid margins. `--margins` is the total, not per side. Content inset is 16 / 36 / 60px, verified against the live site.
- **Fixed:** the small eyebrow uses +0.6px tracking (find-location.scss). Added both eyebrow styles to tokens.json.

## 2026-11-19 — Layout and type corrections from a measured audit
Measured home, VGH, Indigenous Health and About us at 1440px and 500px (computed styles) and cross-checked the vch.ca theme source. These corrections came out of building the ROAR onboarding site to match vch.ca.
- **Grid corrected (04, tokens):** `--margins` is the total horizontal margin, not per side. Text sits 16 / 36 / 60+px in (97px at 1440), not ≈22/62/104px.
- **Eyebrow / surtitle (02, 10, tokens):** 18/24 at every width with **−0.36px** tracking inherited from Body 2, 16px below. The card eyebrow is 12/20 with +0.6px.
- **Letter-spacing pattern (02):** −3% for headings and Body 1; −2% for Body 2, captions and the small mobile steps. It was previously stated as −3% everywhere.
- **Links (05, 04):** always underlined with the default underline; hover changes colour only. The collapsing underline belongs to tertiary buttons. Focus ring split out for links / buttons / inputs / whole-row links.
- **Footer (10):** 900px breakpoint, padding values, logo row on Ocean Blue under a full-width white rule (VCH logo 28px, 30px gaps), copyright strip 15/19 padding and its live wording, land acknowledgement wording.
- **New specs:** theme-header and page-shell spacing (04); vertical rhythm table (04); radii table (04); bordered link grid, list rows, contact-method icons and icon-button hover (05); component type sizes (02); site-nav logo 37/34px (10).
- **Tokens:** added `--gutters`, `--margins`, `--container-width`, `--modules-margins`, image/card/sheet radii, and eyebrow, land-acknowledgement and copyright type tokens. `section-v` is marked unused.
- **Discrepancies 18–20:** footer text over pattern, two card radii, the unused 100px section token.

## 2026-11-19 — Official logo files
- Added assets/logos/official/: the 2019 EPS master (from VCH/Assets/NEWVCHlogo.eps) plus full-colour, reversed and black 1462px PNGs (from LT Site).
- Confirmed that the 'vch_logo_2025' PNG is unchanged artwork.

## 2026-11-19 — Live site audit
- Rendered vch.ca in a browser (home, Locations, VGH, Find care) and captured computed styles.
- Added docs/10-website-audit.md (header, footer, page shells, live component specs, extra type sizes) and 3 screenshots.
- Added discrepancies 13–17 (two tab styles, emergency colour, a11y widget, shadows, ad hoc type sizes).

## 2026-11-19 — Initial compilation
- Captured all 11 Brandfolder guide pages as text (`sources/brandfolder/`).
- Snapshotted vch.ca theme SCSS helpers, button/form/tab/alert modules, logos, patterns and icon sprite (repo commit `817c34944`).
- Wrote docs 01–09 and tokens.
- Logged 12 discrepancies between the guide and the website (docs/09).
