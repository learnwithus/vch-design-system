# Layout and spacing (vch.ca)

The guide has a "Grids and spacings" section, but its content is image-only. Everything below comes from the vch.ca theme source (`helpers/grid/_rad-grid.scss`, `_variables.scss`, module SCSS) and was **verified against computed styles on the live site** (home, VGH location, Indigenous Health, About) on 2026-11-19.

## Grid
- **12 columns**, container capped at **1262px**.
- The container is `width: calc(100% - var(--margins))`, centred. `--margins` is the **total** horizontal margin (both sides together), not a per-side value.
- Columns (and `.col-padding`) add **half a gutter** of padding on each side.

`--margins` is the **total** horizontal margin, split between the two sides, and each column also has half a gutter of padding. The column-content inset from the viewport edge is therefore `margins/2 + gutter/2`:

| Viewport | `--gutters` | `--margins` (total) | Container side margin | **Content inset from edge** |
|---|---|---|---|---|
| < 768px | 10px | 22px | 11px | **16px** |
| 768 – 1279px | 10px | 62px | 31px | **36px** |
| ≥ 1280px | 16px | 104px | 52px | **60px** |

The container stops growing at 1262px. Verified live: at 1440px the logo sits at x = 60, and on mobile content starts at x = 16.

## Spacing scale (`$sp-*`)
| Token | px |
|---|---|
| `sp-xxs` | 8 |
| `sp-xs` | 16 |
| `sp-s` | 24 |
| `sp-m` | 32 |
| `sp-l` | 40 |
| `sp-xl` | 80 |
| `sp-xxl` | 120 |

## Vertical rhythm (live)
| Gap | Value | Source |
|---|---|---|
| Between page modules | **80px** (`--modules-margins`). On phones, article/news/page/press types use **40px** | `.section-module { margin-top: var(--modules-margins) }` |
| Top of the white content sheet to first content | **32px** | `.page-header { padding-top: 32px }` |
| Page header to first module | 80px | `.page-header { margin-bottom: 80px }` |
| Last module to footer | 80px | `.pre-footer` / feedback block `padding: 80px 0` |
| Eyebrow (`.surtitle`) to heading | 16px | jumbotron, text-image |
| Section title to its content | 32px; lists/tiles follow at 32px (≥1024) or 24px | `featured-tiles.scss` |
| Paragraphs in rich text | 24px below each `<p>`; lists 32px above and below; list items 10px apart | `.wysiwyg-content` |

`--section-margin-v: 100px` is defined in the theme but **never used**. Don't treat it as a rhythm value.

## Page shell (inner pages)
- **Content sheet** (`.page-content`): white, top corners **64px** at ≥768px and **32px** below, overlapping the header by the same amount.
- **Theme header** (Ocean Blue topic header, `modules/theme-header.scss`):
  - The site nav overlays it. Content starts at `--site-nav-height`, and the container adds 28px top and 35px bottom padding at ≥768px.
  - The copy column is **6 of 12 columns** (`col-tb-6`) holding the H1, then a `font-body-1` intro (24/28 at every width). The H1 has **24px** below it (12px on phones).
  - The copy column has 40px bottom padding (52px on phones), and the header's bottom padding equals the sheet overlap (64 / 32).
  - An image fills the right 5 columns. On phones it stacks above the copy with 27px below it.

## Breakpoints
375 · 480 · **600** (`$smedium`) · **768 (`$tablet`, main mobile/desktop switch)** · **900 (`$medium`, footer layout)** · **1024 (`$desktop`, nav layout)** · **1280 (grid)** · 1366 · 1600 · 1920.
Drupal's image breakpoints are different: mobile ≤600, retina ≥769 @2x, large ≥1440.

## Shape
| Radius | Where |
|---|---|
| **64px / 32px** | Content sheet top corners (≥768 / below) |
| 48px | Search panel bottom |
| **24px** | Buttons and tabs (pills) |
| 25px | Inputs |
| **10px** | Images in cards and tiles (most common radius in the theme) |
| **8px** | Bordered link grids (quicklink page), nav dropdowns |
| 50% | Icon buttons (36 / 40 / 45 / 50px) |

- Borders are 1px `#CCCCCC`. Light dividers are `#E8E8E8` (live) or `#CED7DB` (featured tiles on phones).
- The site uses almost no shadows. Shadows appear only in focus rings and the slider arrows.

## Motion
- The default is `0.3s ease-out`. Link colour changes use `0.3s ease`.
- Button hover: a fill slides in from the reading-start side (`translate3d(-100%)` → 0, 0.2s). It is RTL-aware.
- Body text links don't animate their underline; only the colour changes (see [05-components](05-components.md#links)). The collapsing-underline effect belongs to `.button-tertiary`.
