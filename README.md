# Risograph UI

A risograph print aesthetic as a real, drop-in **UI design system** — tokens, components, and hard numeric rules. Not a one-off filter. Free, MIT, framework-agnostic.

**▶ [Live demo](https://sanchezalvarez.github.io/risograph-design-system/demo.html)** · or open [`demo.html`](./demo.html) locally (no build needed).

## What's in here

| File | What it is |
|------|------------|
| **`riso.css`** | Drop-in tokens + component classes. Light + dark, self-contained CSS — no build, no images, no deps. |
| **`DESIGN_RULES.md`** | The hard numeric rules: control heights, dropdown widths, spacing, typography, anti-patterns. |
| **`SKILL.md`** | A [Claude Code](https://claude.com/claude-code) skill — drop into `.claude/skills/` and Claude audits/applies the look. |
| **`demo.html`** | The full component set on one page. |

## Quick start

```css
@import "./riso.css";   /* import once at the app root */
```
```html
<html class="dark">     <!-- optional: dark palette -->
<button class="btn-tactile btn-tactile-orange">Ship it</button>
<div class="card-riso card-riso-teal">…</div>
```

Then follow [`DESIGN_RULES.md`](./DESIGN_RULES.md) for dimensions. The essentials:

- Control heights bucket to **22 / 26 / 32px** — never mix two in one row.
- Dropdowns with names: **`min-width: 200px`**, never `w-auto`.
- One spacing scale (`2/4/8 → 12/16 → 20/24 → 32/40`) and one easing curve (`cubic-bezier(0.22, 1, 0.36, 1)`).
- Colours via tokens only — never raw hex.

## Palette

Four "inks" over warm paper, each with a role: 🟠 `--accent-orange` (primary / selection) · 🟢 `--accent-teal` (toggle-on / dates) · 🟣 `--accent-violet` (info) · 🟡 `--accent-gold` (warning).

## Notes

Plain CSS — works anywhere. Examples reference React + Tailwind v4 + Radix for the tricky bits; nothing depends on a framework (Tailwind v4: map tokens via `@theme inline`).

## Fonts

Three free fonts (all degrade to `system-ui` if absent):

| Font | Used for | `riso.css` family | Download |
|------|----------|-------------------|----------|
| **Syne** | titles / display | `Syne Variable` (`.font-display`) | [Google Fonts](https://fonts.google.com/specimen/Syne) · [@fontsource](https://www.npmjs.com/package/@fontsource-variable/syne) |
| **IBM Plex Mono** | labels, buttons, chips, tables | `IBM Plex Mono` (`.font-mono-ui`) | [Google Fonts](https://fonts.google.com/specimen/IBM+Plex+Mono) · [@fontsource](https://www.npmjs.com/package/@fontsource/ibm-plex-mono) |
| **Noto Sans** | body text | `Noto Sans Variable` | [Google Fonts](https://fonts.google.com/specimen/Noto+Sans) · [@fontsource](https://www.npmjs.com/package/@fontsource-variable/noto-sans) |

Fastest drop-in (exactly what `demo.html` uses) — paste into `<head>`:

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@fontsource-variable/syne@5/index.css" />
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@fontsource-variable/noto-sans@5/index.css" />
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@fontsource/ibm-plex-mono@5/400.css" />
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@fontsource/ibm-plex-mono@5/500.css" />
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@fontsource/ibm-plex-mono@5/700.css" />
```

## License

[MIT](./LICENSE) — by [sanchez.sk](https://www.sanchez.sk). A star is appreciated ⭐.
