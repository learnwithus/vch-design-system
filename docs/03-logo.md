# Logo

Source: [logo guide](../sources/brandfolder/01-logo-use-guidelines.md) and [program and facility logos](../sources/brandfolder/02-program-and-facility-logos.md).

## The VCH logo
- The logo reflects the region "from the coast to the mountains". It was refreshed in **2019**: the old tagline was removed and the font was made consistent. Always use the current version.
- There is **one horizontal logo** only. No stacked or vertical versions exist.
- It is made up of the **mountain-and-wave graphic symbol** plus the wordmark "Vancouver Coastal Health".
- Colours: **Ocean Blue `#0078AE`** and **Sunlit Green `#C1D82F`**. A white (reversed) version also exists.
- **Clear space (X)** on all sides equals the height of the **"C" in "Coastal"**. This applies to every version.
- A **minimum size** is defined, but only as an image in the guide. Check it there before using the logo very small.

## Backgrounds
- Use the full-colour logo only on white or near-white areas, including bright white parts of photos.
- On colour or busy photography, use the **white** (or black) logo. If no clean area exists, add a solid colour bar at the top or bottom of the image and place the logo in it.
- The guide's "how not to use the logo" examples are images only. Standard rules apply: no recolouring, stretching, effects, rotating or rearranging.

## The mountain symbol on its own
The symbol is not used alone externally, because people won't recognise it without the name. Exceptions are internal use between health authorities and social media avatars, and then "Vancouver Coastal Health" must appear nearby. Ask brand@vch.ca first.

## Partner logos
- Keep plenty of space between logos and **don't add divider lines**.
- Give logos equal visual weight.
- Group logos on one line. Any corner of the layout is fine.

## Program and facility lockups
- A lockup is only for **patient-facing clinics, programs and centres**, as a wayfinding aid. It is **not for teams or departments**.
- Creating any logo without approval from VCH Communications, Equity & Partnerships is **against policy**, and older custom logos must be retired.
- This applies to digital products too: **no unique logos for apps, teams or programs**.
- In signage lockups, the facility name is set in Ocean Blue next to the full-colour logo. The clinic name comes before the facility type, at the same size and weight, on the same baseline as the VCH logo.

## Official master files (`assets/logos/official/`)
These were found elsewhere in `~/Work/VCH`. Copies under different names in other projects are the same artwork.
| File | What it is | Original location |
|---|---|---|
| `VCH_logo_master_2019.eps` | **Vector master.** Illustrator 23 EPS created 2019-04-08 (the 2019 refresh), 248×62pt, full colour. Use it for print or for exporting SVG/PDF in Illustrator. | `VCH/Assets/NEWVCHlogo.eps` |
| `VCH_logo_full-colour.svg` | **Vector SVG** converted from the EPS master. Brand RGB `#0078AE` / `#C1D82F`. Use it for web and screens at any size. | Generated 2026-11-19 |
| `VCH_logo_white.svg` | Vector, all white, for colour or photo backgrounds | Generated |
| `VCH_logo_black.svg` | Vector, all black | Generated |
| `VCH_logo_RGB_1462w.png` | Full colour, transparent, 1462×382 | `LT Site/vchdesign-craft/web/assets/VCH_logo_RGB_transparent.png` |
| `VCH_logo_reversed-white_RGB_1462w.png` | White (reversed), transparent, 1462×382 | `…/VCH_logo_rev_RGB_transparent.png` |
| `VCH_logo_black_K_1462w.png` | Black (K), transparent, 1462×382 | `…/VCH_logo_K_RGB_transparent.png` |

`vch_logo_2025.png` (in `Act AP`) is the **same artwork** as `VCH_logo_RGB_transparent.png`. Only the filename says 2025; the logo hasn't changed.

The SVGs were converted from the EPS with Ghostscript (EPS → PDF) and Poppler `pdftocairo` (PDF → SVG). They are pure vector paths with no embedded bitmaps, and they matched the official PNG when compared side by side. The EPS is CMYK, so the conversion shifted the colours (blue came out as about `#3276B5`); the fills were reset to the official RGB values. Prefer these SVGs over the vch.ca web SVGs below.

## Web files in this repo (`assets/logos/`)
| File | What it is |
|---|---|
| `header-logo.svg` / `theme-logo.svg` | Full-colour horizontal logo (Ocean Blue + Sunlit Green), 145×38.8 |
| `header-logo-bw.svg`, `vch.svg` | White single-colour logo, for dark backgrounds |
| `britishcolumbia.svg` | BC government mark, white (footer co-brand) |
| `ProvidenceHealthCare.svg` | Partner mark used on vch.ca |
| `../icons/svg-symbols.svg` | Contains `logo-color--full` and `logo-white--full` symbols |

These are web-optimised copies taken from the site. For print, or any official use, get the master files from the Brandfolder "brand collection".
