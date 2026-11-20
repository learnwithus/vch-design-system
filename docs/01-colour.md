# Colour

**Source of truth:** the Brandfolder guide, *Brand colours* ([snapshot](../sources/brandfolder/03-brand-colours.md)). Web-only values come from `helpers/_variables.scss` in the vch.ca theme.

Use **CMYK/Pantone** for print and **HEX/RGB** for screens.

## Primary (use first, in everything)

| Name | HEX | RGB | CMYK | Pantone |
|---|---|---|---|---|
| **Ocean Blue** | `#0078AE` | 0 120 174 | 100 16 0 27 | 307 C/U |
| **Cloud White** | `#FFFFFF` | 255 255 255 | 0 0 0 0 | – |

## Secondary (when you need range beyond primary, e.g. a banner series)

| Name | HEX | RGB | CMYK | Pantone |
|---|---|---|---|---|
| Harbour Teal | `#006271` | 0 98 113 | 100 45 45 20 | 3155 |
| Seaside Teal | `#009793` | 0 151 147 | 87 20 48 0 | 7716 |
| Rainforest Green | `#009E4E` | 0 158 78 | 96 8 100 0 | 7482 |
| Cyan Blue | `#D4EFFC` | 212 239 252 | 15 0 0 0 | – |

## Accent (small elements only, never large blocks)

| Name | HEX | RGB | CMYK | Pantone | Notes |
|---|---|---|---|---|---|
| Sunlit Green | `#C1D82F` | 193 216 47 | 29 0 100 0 | 382 | Logo colour |
| Sea Star Purple | `#843275` | 132 50 117 | 55 95 25 5 | 512 | |
| Emergency Red | `#FF1236` | 255 18 54 | 0 93 79 0 | 185 | Not used on vch.ca |
| Cool Grey | `#53585F` | 83 88 95 | 63 52 44 33 | Cool Gray 11 | |
| Sunshine Yellow | `#FFE850` | 255 232 80 | 0 5 80 0 | 113 | Never as text |
| Sunset Orange | `#FF3630` | 255 54 48 | 0 79 81 0 | 171 | **Print only** per the guide |

**Logo colours:** Ocean Blue + Sunlit Green.

## Web-only colours (on vch.ca but not in the guide)

| Token | HEX | Used for |
|---|---|---|
| `soft-black` | `#1E2124` | All body text (`html { color }`). Effectively the site's "black". |
| `copyright-blue` | `#003147` | Dark bands, with `lines.png` texture |
| `sunset-orange` (web) | `#FE5C39` | Form validation errors. **Not the same as** guide `#FF3630` |
| greys | `#CCCCCC` borders · `#F2F2F2` table headers · `#F9FAFB` input fill · `#B1B1B1` disabled · `#707780` inactive tabs | UI chrome |

The theme also defines a `$secondary-colors` map (purple `#8357FF`, yellow `#FEDF46`, red `#E64C25`, etc.). A code comment marks it **"Not used, only kept for legacy code"**. Do not use these colours.

## Recommended combinations (from the guide)

Every combination includes Ocean Blue:

- Ocean Blue · Harbour Teal · Sunlit Green
- Ocean Blue · Cyan Blue · Rainforest Green
- Ocean Blue · Seaside Teal · Sunlit Green · Cloud White
- Ocean Blue · Sunlit Green · Cloud White
- Ocean Blue · Sea Star Purple
- Ocean Blue · Seaside Teal · Sea Star Purple
- Ocean Blue · Cyan Blue · Sunshine Yellow
- Ocean Blue · Cyan Blue · Sunset Orange (print)

## Section backgrounds on vch.ca

Sections take `data-bg-color` with a matching texture image:

| `data-bg-color` | Texture | Text |
|---|---|---|
| `ocean-blue`, `copyright-blue`, `sunlit-green` | `lines.png` | white (except sunlit-green: use black) |
| `harbour-teal`, `rainforest-green`, `seaside-teal`, `sea-star-purple` | `<colour>-wave.png` | white |
| `cyan-blue`, `white` | none | soft-black |

Page theming: `data-theme="harbour-teal"` swaps `--main-color` (buttons, links) from Ocean Blue to Harbour Teal. Ocean Blue and Harbour Teal are the only two themes in code.

## Contrast

These are computed WCAG 2.x ratios. AA requires **4.5:1** for normal text and **3:1** for large text (≥24px, or ≥18.66px bold) and UI elements.

| Colour | HEX | vs white | vs soft-black `#1E2124` |
|---|---|---|---|
| Ocean Blue | `#0078AE` | **4.89** ✅ | 3.31 |
| Harbour Teal | `#006271` | **7.03** ✅ | 2.30 |
| Seaside Teal | `#009793` | 3.59 ⚠️ large only | **4.50** ✅ (just) |
| Rainforest Green | `#009E4E` | 3.50 ⚠️ large only | **4.62** ✅ |
| Cyan Blue | `#D4EFFC` | 1.20 ❌ | **13.52** ✅ |
| Sunlit Green | `#C1D82F` | 1.60 ❌ | **10.11** ✅ |
| Sea Star Purple | `#843275` | **7.79** ✅ | 2.08 |
| Emergency Red | `#FF1236` | 3.89 ⚠️ | 4.15 ⚠️ |
| Cool Grey | `#53585F` | **7.17** ✅ | 2.26 |
| Sunshine Yellow | `#FFE850` | 1.24 ❌ | **13.03** ✅ |
| Sunset Orange (guide) | `#FF3630` | 3.61 ⚠️ | 4.48 ⚠️ |
| Sunset Orange (web) | `#FE5C39` | 3.09 ⚠️ | **5.24** ✅ |
| Copyright Blue | `#003147` | **13.72** ✅ | 1.18 |
| Inactive tab grey | `#707780` | **4.53** ✅ (just) | 3.57 |

**Safe defaults for small text:**
- On white: Ocean Blue, Harbour Teal, Sea Star Purple, Cool Grey, Copyright Blue, Soft Black.
- White text on these backgrounds: Ocean Blue, Harbour Teal, Sea Star Purple, Cool Grey, Copyright Blue.
- Dark text on these backgrounds: Cyan Blue, Sunlit Green, Sunshine Yellow, Seaside Teal, Rainforest Green.

⚠️ The guide says Seaside Teal and Rainforest Green may be used "as text on white" and as backgrounds with "white text in any font size". **Both fail AA for normal-size text.** Treat them as large-text/decorative only. See [09-discrepancies](09-discrepancies.md).
