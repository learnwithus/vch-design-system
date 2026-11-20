# Typography

## Typefaces ([guide](../sources/brandfolder/05-brand-fonts.md))

| Font | Role | Notes |
|---|---|---|
| **Proxima Nova** (Mark Simonson) | Brand font: public campaigns, signage, designed collateral, **the website** | Weights Thin → Black, all with italics. Most staff don't have it installed. |
| **Calibri** | General internal use: PowerPoint, memos, email | Light, Regular, Italic, Bold, Bold Italic |
| **BC Sans** | Indigenous-language words and content | Replace the **whole word**, never single characters. Longer documents may set the whole block in BC Sans. |
| **Palatino Linotype** | Body copy in text-heavy documents for low-vision readers | Headings stay in Proxima/Calibri. Not for corporate comms. |

**Never use Proxima Nova and Calibri in the same layout.**

### Loading Proxima Nova on the web
vch.ca serves it from Adobe Fonts (Typekit):
- Site: `https://use.typekit.net/rmz3gak.css`
- CKEditor: `https://use.typekit.net/aze8vvi.css`

These kits are tied to VCH's Adobe licence. New products need their own kit or licence; don't hot-link these from another domain. CSS stack: `'proxima-nova', sans-serif`.

## Web type scale (vch.ca, `_mixins-typos.scss`)

Root font size is `62.5%`, so 1rem = 10px. The breakpoint is **768px**. Values are size / line-height, letter-spacing.

| Style | ≥768px | <768px | Weight |
|---|---|---|---|
| H1 | 60 / 64, −1.8px | 40 / 44, −1.2px | 600 |
| H2 | 40 / 44, −1.2px | 32 / 36, −0.96px | 600 |
| H3 | 32 / 36, −0.96px | 24 / 32, −0.72px | 600 |
| H4 | 24 / 32, −0.72px | 18 / 24, −0.36px | 600 |
| H5 | 18 / 24, −0.36px | 16 / 20, −0.32px | 600 |
| Quote | 32 / 38, −0.96px | 24 / 28, −0.48px | 600 |
| Body 1 (lead) | 24 / 28, −0.72px | same | 400 |
| **Body 2 (default)** | 18 / 24, −0.36px | same | 400 |
| Button | 18 / 24, −0.36px | same | 400 |
| Caption | 16 / 24, −0.32px | same | 400 |
| Media caption | 14 / 16, −0.28px | same | 400 |
| Form label | 13 / 16, −0.26px | same | 400 |
| Table | 14 / 16, −0.28px | same | th 500 |
| Tabs | 16 / 16, −0.32px | same | active 600 |

Letter-spacing is **−3%** of font size for headings, Quote and Body 1, and **−2%** for Body 2, Caption, Media caption and the smaller mobile steps (H4/H5 below 768px). Headings are all **Semibold (600)**. Body text colour is soft-black `#1E2124`. The `body` element itself is Body 2, so anything without its own type style inherits **18/24, −0.36px**.

### Styles that inherit Body 2 (verified live, 2026-11-19)
These elements set only a size (or nothing), so they keep Body 2's **−0.36px** tracking even at other sizes:

| Element | Size / line-height | Letter-spacing | Weight | Notes |
|---|---|---|---|---|
| **Eyebrow / surtitle** (`p.surtitle`) | **18 / 24 at every width** | **−0.36px** | 400 | `text-transform: uppercase`. **16px** below it. It has no type class of its own, so don't give it positive tracking or a smaller mobile size. |
| Footer land acknowledgement | 32 / 40 (≥900px), 24 / 28 below | −0.36px (inherited, not scaled) | 400 | `p.title.col-tb-9`, 9 of 12 columns |
| Footer copyright strip | 12 / 24 | −0.36px | 400 | |
| Paragraph under a section H2 | 18 / 24 | −0.36px | 400 | Soft black, not grey; about 720px wide |

### Component type (from module SCSS)
| Use | Size / line-height, tracking | Weight | Source |
|---|---|---|---|
| Location result type label | 12 / 20, **+0.6px**, uppercase | 400 | `find-location .loc-type`, the only positive tracking in the theme |
| Location result title | 24 / 28, −0.48px | 600 | `find-location h4` |
| Location address / content | 16 / 20, −0.32px | 400 | |
| Location distance | 16 / 18, −0.32px, Ocean Blue | 400 | |
| Quicklink card title | H4 (24/32 → 18/24) | 600 | `quicklink-page .link-title` |
| Card "Learn more" link | 16 / 24, −0.32px (Caption) | 400 | region cards on home |
| Footer menu heads | 21 / 24 | 600 | `_footer.scss` |
| Footer menu links | 16 / 18 | 400 | |
| Theme header intro | Body 1, 24 / 28, −0.72px at every width | 400 | `theme-header` `p.font-body-1` |

The digital guide also has "font sizes and styles" tables, but only as images. Compare them against this scale in the guide.
