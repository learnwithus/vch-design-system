# AGENTS.md — VCH brand rules for AI agents

You are producing work that must comply with the **Vancouver Coastal Health (VCH)** brand. This file is the short version. Follow the links when you need detail.

## How to use this repo

1. **Read this file first.** It covers most tasks.
2. When you need more detail, open the topic doc in `docs/`. When you need exact values, use `tokens/tokens.json` (each value has a `status`) or `tokens/vch.css`.
3. **Before you add a value that isn't here, measure it**, from the vch.ca SCSS (`sources/website-scss/`, or the full theme at `~/Work/VCH/vch.ca/phsa-imits-vchwebsites/docroot/themes/custom/vch/src/scss`) or from the live site's computed styles. Never invent a spec to fill a gap. Say it's unknown.
4. If sources conflict, the priority is: **WCAG 2.2 AA → official guide → live site → website code.** Known conflicts and their resolutions are in `docs/09-discrepancies.md`. Check there before deciding anything yourself.
5. Status labels: **Official** (brand guide), **Web** (vch.ca only), **Legacy** (don't use), **Unverified** (confirm first).

## Hard rules (never break)

- Ocean Blue `#0078AE` appears in every piece. At least one primary colour is required.
- Use the **existing logo files only**: `assets/logos/official/` (print, hi-res) or `assets/logos/header-logo.svg` (web). Never recolour, redraw, stretch, add effects or rearrange the logo, and never create a new logo for a team, app or program.
- Logo clear space on every side = the height of the "C" in "Coastal". The logo is horizontal only.
- Use the mountain symbol alone only with brand@vch.ca approval.
- **Never combine Proxima Nova and Calibri** in one layout.
- Indigenous-language words are set in **BC Sans**, and the whole word is replaced, not individual characters.
- Text must meet **4.5:1 contrast** (3:1 for text ≥24px, or ≥18.66px bold). See the contrast table below.
- Never use **Sunset Orange `#FF3630`** for digital text. Never use **Sunshine Yellow** as text. Never put **Cyan Blue** text on white.
- Wave pattern: only on Ocean Blue, Harbour Teal, Seaside Teal, Rainforest Green or Sea Star Purple. Don't recolour it, and don't put text or images on it.
- Don't use the legacy `$secondary-colors` palette (`#8357FF`, `#FEDF46`, `#E64C25`…) or the alert colours `#F55353`, `#FFBB33`, `#53A653`.
- Use photography before illustration. Don't use AI-generated images for clinical, instructional or trust-critical content.
- Use Canadian spelling (colour, centre).

## Colour

| Token | HEX | Role | Status |
|---|---|---|---|
| ocean-blue | `#0078AE` | Primary: buttons, links, brand surfaces | Official |
| cloud-white | `#FFFFFF` | Primary | Official |
| harbour-teal | `#006271` | Secondary. Alternate web theme colour | Official |
| seaside-teal | `#009793` | Secondary. Large text or backgrounds only | Official |
| rainforest-green | `#009E4E` | Secondary. Secondary button | Official |
| cyan-blue | `#D4EFFC` | Secondary. Light section background | Official |
| sunlit-green | `#C1D82F` | Accent. Logo; notice bar | Official |
| sea-star-purple | `#843275` | Accent. Alert bar | Official |
| emergency-red | `#FF1236` | Accent | Official |
| cool-grey | `#53585F` | Accent. Placeholder text | Official |
| sunshine-yellow | `#FFE850` | Accent. Background only | Official |
| sunset-orange | `#FF3630` | Accent. **Print only** | Official |
| soft-black | `#1E2124` | Body and heading text | Web |
| copyright-blue | `#003147` | Footer copyright bar | Web |
| sunset-orange-web | `#FE5C39` | Form errors; Emergency button border | Web |
| greys | `#CCCCCC` border · `#E8E8E8` divider · `#F2F2F2` table · `#F9FAFB` input · `#B1B1B1` disabled · `#707780` inactive | UI | Web |

**Contrast quick check** (ratio vs white / vs soft-black):
Ocean Blue 4.89 / 3.31 · Harbour Teal 7.03 / 2.30 · Seaside Teal **3.59** / 4.50 · Rainforest Green **3.50** / 4.62 · Cyan Blue 1.20 / 13.5 · Sunlit Green 1.60 / 10.1 · Sea Star Purple 7.79 / 2.08 · Cool Grey 7.17 / 2.26 · Sunshine Yellow 1.24 / 13.0 · Copyright Blue 13.7 / 1.18.

- White text on: Ocean Blue, Harbour Teal, Sea Star Purple, Cool Grey, Copyright Blue.
- Dark text on: Cyan Blue, Sunlit Green, Sunshine Yellow (Seaside Teal and Rainforest Green pass too, but only just).

## Typography (web: Proxima Nova via Adobe Fonts, `'proxima-nova', sans-serif`)

Root is `62.5%` (1rem = 10px). Breakpoint at 768px. Letter-spacing ≈ −3% of size.

| Style | ≥768px | <768px | Weight |
|---|---|---|---|
| H1 | 60/64 −1.8px | 40/44 −1.2px | 600 |
| H2 | 40/44 −1.2px | 32/36 −0.96px | 600 |
| H3 | 32/36 −0.96px | 24/32 −0.72px | 600 |
| H4 | 24/32 −0.72px | 18/24 −0.36px | 600 |
| H5 | 18/24 −0.36px | 16/20 −0.32px | 600 |
| Body (default) | 18/24 −0.36px | same | 400 |
| Lead | 24/28 −0.72px | same | 400 |
| Caption | 16/24 −0.32px | same | 400 |
| Label | 13/16 −0.26px | same | 400 |
| Eyebrow | 18/24 UPPERCASE · small: 12/20 +0.6px UPPERCASE | | 400 |

## Layout

- 12 columns, max width 1262px.
- Content inset from the viewport edge: **16px** (<768), **36px** (768–1279), **60px** (≥1280).
- Gutters: 10px, or 16px at ≥1280.
- Spacing scale: 8 · 16 · 24 · 32 · 40 · 80 · 120. Section vertical spacing: 100px.
- Breakpoints: 375 · 480 · 600 · **768** · 900 · 1024 · **1280** · 1366 · 1600 · 1920.
- Radius: buttons and tabs 24px (pill), inputs 25px, icon buttons 50%, card images 10px. Inner-page content sheet: 64px top corners.
- Motion: `0.3s ease-out`. Shadows: none, except slider arrows.

## Components (defaults)

- **Primary button:** Ocean Blue pill, white 18/24 text, padding 12×24. On hover, white fill slides in from the start side. On coloured backgrounds, use the reversed version (white fill, blue text).
- **Secondary button:** Rainforest Green with white text. Fails AA at 18px regular; use bold or ≥24px, or a hollow primary instead.
- **Focus ring:** `outline: 3px solid #fff; box-shadow: 0 0 0 3px #000`. Always keep it.
- **Input:** `#F9FAFB` fill, 1px `rgba(0,0,0,.2)` border, 25px radius, min-height 51px, 16px text. Error: `#FE5C39` border plus inset ring.
- **Tabs:** pills. Page tabs: active = Ocean Blue fill. Filter/sort tabs: active = soft-black outline.
- **Alert bar:** notice = Sunlit Green with dark text; alert = Sea Star Purple with white text.
- **Header:** white; logo at left; 16px/500 mega-menu; Emergency pill with a `#FE5C39` border. **Footer:** Ocean Blue; land acknowledgement on the `lines` texture; Copyright Blue legal bar.

Full specs: `docs/05-components.md` and `docs/10-website-audit.md`.

## Voice

Plain-language, warm and service-first, in Canadian English.

- Vision: "Healthy lives in healthy communities."
- Values: We Care for Everyone · We are Always Learning · We Strive for Better Results.

## When you're unsure

Say so, cite the doc, and suggest asking **brand@vch.ca**. Add the open question to `docs/09-discrepancies.md`. Don't guess.

## Maintaining this repo

If you change a value: update the doc, `tokens/tokens.json`, `tokens/vch.css`, this file if the value appears here, and `CHANGELOG.md`. Keep the status labels accurate.
