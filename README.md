# VCH Design System

**Everything we know about the Vancouver Coastal Health brand, in one place.**

This repo records the VCH brand as it really exists today. It pulls together three sources that don't always agree:

1. 📘 **The official brand guide**: [brandguides.brandfolder.com/vch](https://brandguides.brandfolder.com/vch)
2. 💻 **The vch.ca website code**: the Drupal theme's SCSS
3. 🌐 **The live vch.ca site**: what actually renders in a browser

Where they disagree, we say so plainly and recommend what to do. Use this repo whenever you make something that needs to look and sound like VCH.

> **Open [`preview.html`](preview.html) in a browser** to see the palette, type scale and buttons rendered from the real tokens.

---

## The brand in 60 seconds

| | |
|---|---|
| **Main colour** | **Ocean Blue `#0078AE`** on white. Every piece should include it. |
| **Logo** | One horizontal logo in Ocean Blue and Sunlit Green `#C1D82F`. No stacked version, and no custom team or app logos. |
| **Font** | **Proxima Nova** for anything designed or public, including the website. **Calibri** for internal Office docs. Never use both together. |
| **Text colour** | Soft Black `#1E2124`. Headings are Semibold (600) with slightly tight letter-spacing. |
| **Shapes** | Pill buttons (24px radius), rounded inputs, mostly flat with almost no shadows. |
| **Accessibility** | Digital work must meet **WCAG 2.2 AA**. Some brand colours fail as small text; [see the contrast table](docs/01-colour.md#contrast). |
| **Vision** | *Healthy lives in healthy communities.* |
| **Questions** | brand@vch.ca |

---

## Find what you need

| I want to… | Read |
|---|---|
| Pick colours, or check contrast | [Colour](docs/01-colour.md) |
| Set type: fonts, sizes, weights | [Typography](docs/02-typography.md) |
| Use the logo correctly | [Logo](docs/03-logo.md) |
| Lay out a page: grid, spacing, breakpoints | [Layout & spacing](docs/04-layout-and-spacing.md) |
| Build buttons, forms, tabs, alerts | [Components](docs/05-components.md) |
| Use the wave pattern, photos, icons | [Graphics & imagery](docs/06-graphics-and-imagery.md) |
| Write in the VCH voice | [Voice & messaging](docs/07-voice-and-messaging.md) |
| Make signage, posters, slides | [Print, signage & templates](docs/08-print-signage-templates.md) |
| Match vch.ca exactly (header, footer, page layout) | [Live website audit](docs/10-website-audit.md) |
| Know where the sources disagree | [Discrepancies & open questions](docs/09-discrepancies.md) |
| Drop tokens into code | [`tokens/`](tokens/) |
| Get logo files | [`assets/logos/official/`](assets/logos/official/) |

🤖 **Using an AI agent?** Point it at [`AGENTS.md`](AGENTS.md), a compact rulebook written for that purpose.

---

## How much to trust each fact

Facts in the docs and tokens carry one of these labels:

| Label | Meaning | Trust |
|---|---|---|
| **Official** | Stated in the Brandfolder guide | Follow it, unless it fails accessibility |
| **Web** | Used on vch.ca, but not in the guide | Safe for web work. Avoid in print. |
| **Legacy** | Still in the code, but marked unused or broken | Don't use |
| **Unverified** | Exists only as an image in the guide, or wasn't checked | Confirm before relying on it |

If sources conflict, use this order: **accessibility (WCAG 2.2 AA) → official guide → live site → website code.** Any exception to that order is spelled out in [Discrepancies](docs/09-discrepancies.md).

---

## What's in the repo

```
VCH Design System/
├── README.md            ← you are here
├── AGENTS.md            ← rules and quick reference for AI agents
├── preview.html         ← visual specimen (open in a browser)
├── CHANGELOG.md         ← what changed, and when
│
├── docs/                ← the guidance, one topic per file
├── tokens/              ← colours, type, spacing as CSS variables and JSON
├── assets/
│   ├── logos/official/  ← master EPS + hi-res PNGs (use these)
│   ├── logos/           ← web SVGs taken from vch.ca
│   ├── patterns/        ← wave and line textures
│   ├── icons/           ← vch.ca SVG icon sprite
│   └── screenshots/     ← live-site reference captures
└── sources/             ← raw evidence: the guide's text and the site's SCSS
```

Each folder has its own short README.

---

## What's *not* here (yet)

- **Image-only guide content:** minimum logo size, logo misuse examples, the guide's digital font tables, grid diagrams, and header/footer specs. View these on Brandfolder.
- **Wave-pattern `.ai` files, Office templates, and the Writing Style Guide PDF:** download them from Brandfolder.
- **An official SVG logo:** only the EPS master and PNGs exist locally.
- **Proxima Nova font files:** the font is licensed. Use the Adobe Fonts kit or VCH's licence.
- **Page types not yet audited:** news articles, careers, forms.

---

## Keeping it current

Snapshot date: **2026-11-19**. Sources: guide pages last edited 2025-12-16; vch.ca theme commit `817c34944`.

When something changes:
1. Update the affected doc and its label.
2. If a value changed, update [`tokens/`](tokens/) too.
3. Add an entry to [`CHANGELOG.md`](CHANGELOG.md).
4. Resolved a discrepancy? Mark it resolved in [09](docs/09-discrepancies.md); don't delete it.

To check a web value, measure it, don't guess. Use the theme source at `~/Work/VCH/vch.ca/phsa-imits-vchwebsites/docroot/themes/custom/vch/src/scss` and the computed styles on the live site.
