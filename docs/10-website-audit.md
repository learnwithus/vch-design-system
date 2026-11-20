# Live website audit (vch.ca)

Captured **2026-11-19** in a real browser at 1440px and mobile widths. All values are computed styles from the rendered page, so they reflect what users actually see, including anything the SCSS snapshot doesn't explain. Pages sampled: home, Locations (UPCC filter), Vancouver General Hospital, Find care. A second pass the same day measured home, VGH, Indigenous Health (quicklink page) and About us at 1440px and 500px, cross-checked against the theme source in `~/Work/VCH/vch.ca/phsa-imits-vchwebsites/docroot/themes/custom/vch/src/scss`.

Screenshots: [home desktop](../assets/screenshots/home-desktop.png) · [home mobile](../assets/screenshots/home-mobile.png) · [VGH location](../assets/screenshots/location-vgh-desktop.png)

## Colour in use
By element count, the palette in practice is Soft Black `#1E2124` (512), white (355), **Ocean Blue** (44), and `#E8E8E8` dividers (17). The rest barely registers: Copyright Blue (1, copyright bar), web Sunset Orange `#FE5C39` (1, Emergency button), Cyan Blue (one section on topic pages).

**The live site is effectively an Ocean Blue and white site.** No secondary or accent colours appeared on the pages sampled, apart from Cyan Blue as a section background.

## Global header (fixed, 97px desktop / 61px mobile)
- **Utility bar** (white, about 33px): language switcher on the left; *Donate · Volunteer · Media · Staff hub* on the right, at **13px** soft-black.
- **Main bar:** logo on the left, **max-height 37px at ≥1024px** with 13px above and 12px below; **34px below 1024px** with 13px above and below. Mega-menu triggers at **16px / weight 500** (*Services and resources, Locations, Patients and visitors, About us, Careers*), each with a chevron. Dropdowns are plain link lists ending with an "All …" link.
- **Search** opens as a full-width white panel with a 48px bottom radius.
- **Emergency button:** white pill (18px radius, 36px tall), **1px `#FE5C39` border**, 14px soft-black text, and a small orange circle icon with a white cross. This is the only place orange appears.
- **Mobile:** logo, search icon and hamburger only.

## Page shells
- **Homepage hero:** a full-bleed photo with the thin white `lines` art over it. White H1 60/64. "Scroll to explore" indicator.
- **"How can we help?" quicklinks card:** Ocean Blue, large radius on the left corners, overlapping the hero on the right. Contains an H3, a white pill search field with a circular Ocean Blue search button, and a list of 18px white links with → arrows.
- **Inner pages:** a hero photo, or an Ocean Blue `theme-header` for topic pages, followed by a **white content sheet with 64px top-left/top-right radius (32px below 768px)** that overlaps the hero by the same amount. Content starts 32px inside the sheet. This rounded "sheet" is a signature pattern of the site. Theme-header specs are in [04-layout-and-spacing](04-layout-and-spacing.md#page-shell-inner-pages).
- **Breadcrumb:** 13/24, "Home / Locations".
- **Location header:** H1 on the left. Contact methods on the right with outline icons (pin, phone) in Ocean Blue, separated by 1px rules. Phone numbers are underlined Ocean Blue links.

## Footer (Ocean Blue, `section--background-color`, `layout/_footer.scss`)
The footer switches layout at **900px** (`$medium`), not 768.

1. **Land acknowledgement band:** `lines.png` texture behind the text. Padding **64px** top and bottom below 900px, **133 / 121px** above. Text is **24/28 → 32/40**, regular, white, in 9 of 12 columns. It inherits Body 2's −0.36px tracking. Wording on the live site: *"Vancouver Coastal Health is committed to delivering exceptional care to 1.25 million people, including the First Nations, Métis and Inuit, within the traditional territories of the Heiltsuk, Kitasoo-Xai’xais, Lil’wat, Musqueam, N’Quatqua, Nuxalk, Samahquam, shíshálh, Skatin, Squamish, Tla’amin, Tsleil-Waututh, Wuikinuxv, and Xa’xtsa."*
2. **Link region:** a **full-width 1px white rule** on top, padding-top 30 / 40px. Column heads are **21/24 weight 600** white (for example "Get involved"), links 16/18.
3. **Logos and social row:** still on Ocean Blue, under another **full-width 1px white rule**, with 23px bottom padding. Logos start 21px below the rule: the white **VCH logo at 28px tall**, then the BC government mark at 46px (Providence at 31px), each **30px apart**, with no dividers. Social icons sit on the right at ≥900px.
4. **Copyright strip:** Copyright Blue `#003147`, padding **15 / 19px**, **12/24** white text reading *"Copyright © {year} Vancouver Coastal Health"*, with utility links (Privacy & terms of use, Sitemap) 10px apart. Centred and stacked below 900px; space-between above.

## Components seen live (beyond [05-components](05-components.md))
| Component | Live spec |
|---|---|
| **Page tabs** (location pages) | Pills, 16px. **Active = solid Ocean Blue fill, white text, weight 500.** Inactive = 1px soft-black outline. This differs from the `button-tab` code default (active = outline). Two tab styles exist. |
| Sort tabs (Nearest / A–Z) | Active: soft-black outline, weight 600. Passive: `#707780` text, no border. |
| Location card / result row | Type label at **12/20, +0.6px, UPPERCASE**; H4 **24/28, −0.48px**; distance 16/18 in Ocean Blue with a pin icon; address 16/20. Rows have no box: a 1px `#CCC` rule between rows, 16px vertical padding, the whole row is the link, and focus shows a 3px black inset outline. |
| Section eyebrow (`surtitle`) | **18/24, −0.36px (inherited Body 2), UPPERCASE**, regular, at every width, with 16px below it. Sits above an H1/H2. |
| Quicklink card grid | 1px `#CCC` box with an **8px** radius, cells with 30px padding, H4 titles, a 36px `button-icon` in each cell. Whole cell clickable. 3 / 2 / 1 columns at 768 / 600 / below. |
| Content-card icon button | `button-icon` S: **36px**, Ocean Blue fill and border, white 12px icon. It inverts to white with a `#CCC` border when the card is hovered. |
| Large statement / quote | `font-h2` 40/44 weight 600 used on a paragraph |
| Feature list title | H3 styled as `font-h4` 24/32 |
| Region / service cards | Image with **10px radius**, H4 24/32, caption 16/24, "Learn more" text link 16/24 Ocean Blue |
| Slider arrows | 50px circles, white with `#CCC` border, **Material-style elevation shadow**. These are the only shadows on the site. Disabled arrow uses a `#B1B1B1` border. |
| Video | Black frame with a circular Ocean Blue play button |
| Text links | Ocean Blue, always underlined (default underline), hover changes colour only to `#00608B`. Focus: 3px white outline + 6px black shadow. |
| Primary button | Confirmed: Ocean Blue pill, 18/24, white. Reversed white version on blue. |
| Form inputs (Locations filters) | Confirmed: `#F9FAFB`, 25px radius, `rgba(0,0,0,.2)` border, 13px labels. Selectize dropdowns share the style. Circular "find me" crosshair button. |

## Third-party elements
- **Accessibility widget** (`astral-accessibility`): a floating button, bottom right, with a **yellow circle (≈`#FFCB00`) on a black tab**. It's not brand yellow (`#FFE850`), and it sits outside the system.
- **Google Maps** embeds on location pages use their default styling.
- **Font Awesome 6.6** is loaded site-wide.

## Typography additions (live, not in the SCSS type mixins)
| Use | Size / line-height | Weight | Case |
|---|---|---|---|
| Main nav | 16/16 | 500 | – |
| Utility nav, language | 13/13 | 400 | – |
| Emergency button | 14/14 | 400 | – |
| Eyebrow (section) | 18/24, −0.36px | 400 | UPPER |
| Eyebrow (card) | 12/20, +0.6px | 400 | UPPER |
| H4 (location card) | 24/28, −0.48px | 600 | – |
| Breadcrumb | 13/24 | 400 | – |
| Footer land acknowledgement | 32/40 (≥900), 24/28 below; −0.36px | 400 | – |
| Footer column heads | 21/24 | 600 | – |
| Footer links | 16/18 | 400 | – |
| Copyright / legal | 12/24 | 400 | – |
| Bold in body | 18/24 | 700 | – |
