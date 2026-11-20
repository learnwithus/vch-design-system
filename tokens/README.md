# Tokens

| File | Use it for |
|---|---|
| [`vch.css`](vch.css) | Drop-in CSS custom properties. Brand colour names match vch.ca (`--primary-color-ocean-blue`…), so snippets move between the two. |
| [`tokens.json`](tokens.json) | The full set: colours (with RGB/CMYK/Pantone and a `status`), type scale, spacing, radius, breakpoints, layout, motion. Feed it to scripts, Figma plugins or agents. |

```html
<link rel="stylesheet" href="https://use.typekit.net/<your-kit>.css"> <!-- Proxima Nova; needs a VCH-licensed kit -->
<link rel="stylesheet" href="tokens/vch.css">
<style>
  body   { font: 1.8rem/2.4rem var(--vch-font); color: var(--text-color); }
  .btn   { background: var(--main-color); color: #fff; border-radius: var(--radius-pill); padding: 12px 24px; }
</style>
```

`vch.css` assumes `html { font-size: 62.5% }`, as on vch.ca. If you don't use that, use px values.

`status` values in the JSON: `official` (brand guide) · `web-only` (vch.ca, not in the guide). Legacy colours are deliberately left out.
