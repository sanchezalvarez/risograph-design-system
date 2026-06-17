# Risograph UI — Codex bundle

Everything needed to use the Risograph design system with [OpenAI Codex](https://github.com/openai/codex).

Codex has no "skill" or "subagent" abstraction — instead it reads an `AGENTS.md`
for always-on project instructions, and exposes markdown files in
`~/.codex/prompts/` as slash commands. This bundle maps the system onto both.

| File | Where it goes |
|------|---------------|
| `riso.css` | into your project; `@import` once at the app root |
| `DESIGN_RULES.md` | next to `riso.css` — the hard numeric ruleset |
| `AGENTS.md` | your project root — always-on trigger ("read the rules before any visual change") |
| `risograph-audit.md` | `~/.codex/prompts/risograph-audit.md` — exposes the `/risograph-audit` slash command |

## Install

```bash
# 1. drop the CSS + rules into your project
cp riso.css DESIGN_RULES.md  /path/to/your-app/

# 2. always-on instructions (merge into an existing AGENTS.md if you have one)
cp AGENTS.md  /path/to/your-app/AGENTS.md

# 3. the on-demand audit command  →  run /risograph-audit in Codex
mkdir -p ~/.codex/prompts
cp risograph-audit.md  ~/.codex/prompts/risograph-audit.md
```

Then `@import "./riso.css";` at your app root, add `class="dark"` to `<html>` for
the dark palette, and build from the bundled classes. With `AGENTS.md` in place,
Codex reads `DESIGN_RULES.md` before any visual change; run `/risograph-audit` for
a full alignment sweep.

**Note vs. Claude Code:** the Codex prompt runs inline in the main conversation
(no isolated subagent context), and you invoke it manually (`/risograph-audit`)
rather than relying on auto-trigger. The `riso.css` + `DESIGN_RULES.md` are
identical across both bundles.

Using Claude Code instead? See [`../claude-code/`](../claude-code/).
