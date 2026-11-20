# Discrepancies and open questions

This page lists places where the official guide, the website code, and accessibility requirements disagree. Each item has a **working recommendation** to use until the brand team decides. Record each resolution in the CHANGELOG.

| # | Topic | Brand guide says | vch.ca does | Recommendation |
|---|---|---|---|---|
| 1 | **Sunset Orange value** | `#FF3630`, print only | `#FE5C39`, used as the form-error colour | Print: `#FF3630`. Web errors: keep `#FE5C39` (5.2:1 on soft-black). Ask the brand team to formally name a web error colour. |
| 2 | **Status colours** | Emergency Red `#FF1236` exists. No status palette is defined. | `alert.scss` uses off-brand `#F55353`, `#FFBB33` and `#53A653`. The alert bar uses Sunlit Green (notice) and Sea Star Purple (alert). | For new work: notice = Sunlit Green with dark text, alert/emergency = Sea Star Purple or Emergency Red with **bold/large** text. Avoid the three off-brand hexes. |
| 3 | **Soft Black `#1E2124`** | Not in the guide. Cool Grey `#53585F` is the only dark neutral. | All body text | Use soft-black for text. It is de facto brand. Get it added to the guide. |
| 4 | **Copyright Blue `#003147`** | Not in the guide | Used for dark bands | Treat as web-only. Don't use in print. |
| 5 | **Seaside Teal / Rainforest Green as text** | "Only use as text on white", and as backgrounds with "white text in any font size" | – | Both are ~3.5:1 on white, which **fails AA** for normal text. Use only at ≥24px (or ≥18.66px bold), or use Harbour Teal for text. |
| 6 | **Secondary button (Rainforest Green + white)** | Recommended | Same, at 18px regular | Fails AA (3.5:1). Make the label ≥18.66px **bold** or ≥24px, or use the hollow/reversed primary button instead. |
| 7 | **Cyan Blue as text** | "Only on dark backgrounds" | Used only as a background | Fine. Never use Cyan Blue text on white (1.2:1). |
| 8 | **Wave pattern on Ocean Blue** | Ocean Blue is an approved pattern background | Ocean Blue sections use `lines.png`, not a wave. Sunlit Green (not approved) also gets `lines.png`. | Treat `lines` as a separate web texture. Ask whether an Ocean Blue wave asset exists. Don't put any pattern on Sunlit Green. |
| 9 | **Text over pattern** | Never | Hero and section text sits on wave/lines backgrounds | Keep text off the pattern area in new layouts, or confirm a web exception with the brand team. |
| 10 | **Button shape** | A sample `.button` CSS on the *Our written brand* page uses a 5px radius, 15×32 padding, 16px text | Pill, 24px radius | Follow the site (pill). The guide's snippet looks like a placeholder. |
| 11 | **Legacy `$secondary-colors` and `.tag`** | – | Defined in SCSS. `_tag.scss` references undefined variables (`--color-yellow`, etc.). | Ignore. These are dead code and shouldn't be used as a source. |
| 12 | **Web font sizes and grid** | Exist only as images in *Digital branding guidelines* | Documented in code ([02](02-typography.md), [04](04-layout-and-spacing.md)) | Compare the guide images against the code values and record any differences here. |
| 13 | **Two tab styles** | – | `button-tab` default: active = soft-black outline (sort tabs). Location page tabs: active = solid Ocean Blue fill. | Pick one. Recommendation: Ocean Blue fill for page-level navigation tabs, outline for filters and sorts. Document both until the brand team decides. |
| 14 | **Emergency colour** | Emergency Red `#FF1236` is the named emergency colour | The header Emergency button uses web Sunset Orange `#FE5C39` | Ask whether the Emergency button should move to Emergency Red. |
| 15 | **Accessibility widget** | – | A third-party floating button in non-brand yellow `#FFCB00` on black | Out of the design system's scope. Note it as a known off-brand element. |
| 16 | **Shadows** | – | The only shadows are Material-style elevation on slider arrows. Everything else is flat. | Treat the system as flat. Don't introduce shadows elsewhere. |
| 17 | **Ad hoc type sizes** | – | Live sizes outside the mixin scale: 12, 13, 14, 21px; H4 24/28 vs 24/32; land acknowledgement 32/40 regular | Use the mixin scale for new work. These are documented in [10-website-audit](10-website-audit.md). |
| 18 | **Text over pattern in the footer** | Never place text over the pattern | The footer land acknowledgement (32/40 white) sits directly on `lines.png` | Same as #9. Ask the brand team to confirm a web exception. The ROAR onboarding site follows vch.ca here (`lines.png` behind the acknowledgement, centred, `cover`) by owner decision, 2026-11-19. |
| 19 | **Two card radii** | – | Bordered link grids use **8px**; images in cards and tiles use **10px** | Use 8px for bordered boxes and 10px for images. Don't introduce other card radii (16px, 12px…). |
| 20 | **Unused section spacing token** | – | `--section-margin-v: 100px` is defined but never used. Modules are spaced by `--modules-margins` (80px; 40px on phones for article types). | Space modules at 80px. Ignore the 100px token. |

## Open questions for brand@vch.ca
1. Is there an official web status/feedback palette (error, warning, success, info)?
2. Can Soft Black and Copyright Blue be added to the official palette?
3. Can developers get the master logo SVGs and the wave pattern assets in an Ocean Blue tint?
4. What are the guide's minimum logo sizes (print mm / digital px)?
5. Should Harbour Teal be the official secondary theme colour for web? Code supports only Ocean Blue and Harbour Teal themes.
6. Will the guide's secondary-colour accessibility rules be updated for WCAG 2.2 AA?
