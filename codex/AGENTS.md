# Risograph UI — agent instructions

This project uses the **Risograph UI design system**: layered offset "ink"
shadows, grain texture, a tight 4-ink palette, bold mono labels, registration
marks, and tactile micro-animations. The drop-in system lives in `riso.css`; the
hard numeric rules live in `DESIGN_RULES.md`.

## Before any visual change — read the rules

Before editing any `.tsx` / `.jsx` / `.vue` / `.css` that touches layout,
className/styling, colours, or spacing, **read `DESIGN_RULES.md` first** and
follow its numbers. Do not improvise sizes from "what looks balanced."

## Hard rules — non-negotiable

- Import `riso.css` once at the app root; build from its classes (`btn-tactile`,
  `card-riso`, `surface-noise`, `riso-section-label`, …), not raw utilities.
- Control heights bucket to **22 / 26 / 32 px** — never mix two in one row.
- Dropdowns with user-facing names: **`min-width: 200px`**, never `w-auto`.
- Colours via tokens only (`var(--accent-orange)`, `var(--riso-teal)`, …) —
  never raw hex, never a framework palette class (`bg-red-500`).
- One spacing scale (`2/4/8 → 12/16 → 20/24 → 32/40`) and one easing curve
  (`cubic-bezier(0.22, 1, 0.36, 1)`).
- All new animations must respect `prefers-reduced-motion` (the bundled ones do).

## The four inks

🟠 `--accent-orange` (primary / selection) · 🟢 `--accent-teal` (toggle-on / dates) ·
🟣 `--accent-violet` (info) · 🟡 `--accent-gold` (warning).

## Dark mode

Add the class `dark` to `<html>` / `<body>` — the dark palette is the same tokens
re-mapped. Verify both light and dark read coherently after a change.

## Auditing

For a full sweep aligning an app to the look, the audit workflow is in
`risograph-audit.md` — copy it to `~/.codex/prompts/risograph-audit.md` to expose
it as the `/risograph-audit` slash command.
