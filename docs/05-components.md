# Components

The guide's *Web components* section ([snapshot](../sources/brandfolder/10-digital-branding-guidelines.md)) gives only minimum rules in text. The visual specs are images. The vch.ca implementation is the most detailed spec available, and it is summarised below. Source SCSS is in [`sources/website-scss/`](../sources/website-scss/).

## Minimum rules for any platform (from the guide)
- **Primary button:** Ocean Blue `#0078AE` with white text.
- **Secondary button:** Rainforest Green `#009E4E` with white text. ⚠️ This is 3.5:1 contrast, which passes AA only at ≥24px or ≥18.66px bold.
- **Search button:** Ocean Blue with white.
- **Forms:** use VCH fonts and colours, meet WCAG 2.2 AA, and involve the privacy and security teams.
- **Alerts:** use an *alert banner* for site-wide emergencies and a *notification bar* for service or process changes. Use pop-ups sparingly.
- **Accordions:** use sparingly, for FAQs, steps, or long lists where users need only one item.
- **Logos and favicon:** VCH logo only.

## Buttons (vch.ca `_buttons.scss`)
Every button is a **pill**: 12px × 24px padding, 18/24 text, with a 10px gap before any icon (icons are 12px).

| Variant | Default | Hover |
|---|---|---|
| `.button-primary` | `--main-color` fill, white text | White fill slides in, main-colour text, `#CCC` border |
| `.button-primary[data-variant=reversed]` (auto-applied on coloured sections) | White fill, main-colour text | Main-colour fill, white text |
| `.button-primary[data-variant=hollow]` | Transparent, soft-black text, `#CCC` border | Main-colour fill, white text |
| `.button-secondary` | Rainforest Green fill, white text | White fill, green text |
| `.button-icon` | Circle, sizes S/M/SL/L = 36/40/45/50 | Same as primary |
| `.button-tab` (filters/sorts; page tabs on location pages use a solid Ocean Blue active state, see [10](10-website-audit.md)) | Pill, 10×16 padding, 16px text. Active: soft-black border and text, weight 600. Passive: `#707780` text | Main-colour text |
| `.button-tertiary` | Text link with a 2px underline | Underline collapses |
| Disabled | `#B1B1B1` fill, soft-black text | – |

**Focus:** `outline: 3px solid #fff` plus a black `box-shadow` ring. This double ring stays visible on any background. Keep it.
- **Links** (`.link`, rich-text links, footer links): `box-shadow: 0 0 0 6px #000`, `outline-offset: 3px` on `.link`.
- **Buttons and icon buttons:** `box-shadow: 0 0 0 3px #000`.
- **Inputs:** 6px shadow.
- **Whole-row and whole-card links** (location results, quicklink cells) use an **inset** ring instead: `outline: 3px solid #000; outline-offset: -3px`.

**Icon button (`.button-icon`)** sizes are S/M/SL/L = 36/40/45/50px. The default is an Ocean Blue fill with a white 12px icon and a 1px Ocean Blue border. On hover (or when its parent card is hovered), it flips to a white fill with a main-colour icon and a `#CCC` border. The small 36px size is the one used in content cards ("Learn more about this location").

## Links
Measured live (`.link`, `.wysiwyg-content a`):
- Colour `var(--link-color)` (Ocean Blue), **always underlined** with the browser's default underline (no custom thickness or offset).
- On hover, only the colour changes, to `#00608B` (0.3s ease). The underline doesn't animate. The collapsing 2px underline belongs to `.button-tertiary`, not body links.
- On coloured sections (`.section--background-color`, `.has-background`), link colours switch to white.
- External links in rich text get an 18px external icon with 5px side margins.

## Forms (`_forms.scss`)
- Inputs: full width, minimum height 51px, padding 12×24, radius 25px, fill `#F9FAFB`, border `rgba(0,0,0,.2)`, text 16/19.
- Placeholder colour is `#53585F` (Cool Grey).
- Labels are 13/16, block, with 10px below.
- Error state: Sunset Orange (web) `#FE5C39` border plus a 2px inset ring.
- Checkboxes and radios are 24px with `accent-color: var(--main-color)`.
- Selects use a custom 5px grey caret.

## Alerts
- **Alert bar** (`alert-bar.scss`), site-wide, 14/20 text, 16×24 padding:
  - `data-type="notice"` uses a **Sunlit Green** background with dark text.
  - `data-type="alert"` uses a **Sea Star Purple** background with white text.
- **Inline alert/message** (`alert.scss`) uses **off-brand** status colours: error `#F55353`, warning `#FFBB33`, success `#53A653`, error tint `#FDEAE5`. See discrepancies.

## Accordion
- Items are separated by a 1px `#CCCCCC` top border.
- A circular plus/minus icon button sits on the right. When open, it inverts to white with a grey border.
- There is a "large" variant with 24px titles. A numbered variant exists in the guide.

## Tables
- Text 14/16, cell padding 16px.
- Header cells use a `#F2F2F2` fill. Cells are divided by 1px `#F2F2F2` lines.

## Cards and lists
| Pattern | Spec | Source |
|---|---|---|
| **Bordered link grid** (quicklink page) | One box with a 1px `#CCC` border and **8px** radius, cells divided by 1px `#CCC`. Each cell has **30px** padding, an H4 title with 32px below it, and a `button-icon` at the bottom. The whole cell is the link (inset focus ring); hovering the cell flips the icon button. Columns: 1 below 600px, 2 from 600, 3 from 768. | `modules/quicklink-page.scss` |
| **List rows** (location results) | No box. Rows are separated by a 1px `#CCC` top border with 16px vertical padding. The whole row is the link, and `:focus-within` shows a 3px black inset outline. | `modules/find-location.scss` |
| **Image cards** (regions, tiles) | Image with a **10px** radius, H4 24/32, Caption 16/24, then a 16/24 "Learn more" link. | home, `tile.scss` |
| **Contact-method icons** | Bare Ocean Blue outline icons, max **25×28px**, in a 60px-wide slot before the text. No circle and no background. | `contact-methods.scss`, `find-location.scss` |

No card on vch.ca uses a tinted hover background. Hover feedback comes only from the link colour and the icon button.

## Lists (WYSIWYG)
- Ordered lists use numbered circular badges: 24px, 14px number, `#CCCCCC` border.
- Unordered lists use standard discs with 10px item spacing.

## Page-level modules on vch.ca
81 module stylesheets exist, including: hero, homepage-header, campaign-header, theme-header, service-header, article-header, page-header, tile, featured-tiles, quicklinks-widget, alert-bar, important-advisory, accordion, faq, step-by-step, table-of-content, anchor-nav, page-tabs, breadcrumb, quote, text-image, image-gallery, images-slider, video, infographic, contact-methods, hours-of-operation, location-info, find-location, service-finder, search-page, team-members, staff-spotlights, sponsor-logos, signup, modal, and footer (land acknowledgement band on `lines.png`, white top rules).

## Icons (`assets/icons/svg-symbols.svg`)
arrow-right, scroll, thumb-up, pin, phone, fax, envelop, plus, minus, triangle-right, download, external, bus, clock, leaflet, chevron-down, play, pause, magnifier, crosshair, menu, cross, globe. The sprite also contains logo symbols and fallback article/tile illustrations. The site additionally loads **Font Awesome 6.6** and a tiny custom `vchicons` webfont.
