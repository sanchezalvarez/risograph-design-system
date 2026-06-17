# Risograph UI — Claude Code bundle

Everything needed to use the Risograph design system with [Claude Code](https://claude.com/claude-code).

| File | Where it goes |
|------|---------------|
| `riso.css` | into your project; `@import` once at the app root |
| `DESIGN_RULES.md` | next to `riso.css` — the hard numeric ruleset |
| `SKILL.md` | `.claude/skills/risograph-ui/SKILL.md` — inline skill (applies/audits the look on request) |
| `risograph-ui-auditor.md` | `.claude/agents/risograph-ui-auditor.md` — subagent for a dedicated full-app audit pass |

## Install

```bash
# 1. drop the CSS + rules into your project
cp riso.css DESIGN_RULES.md  /path/to/your-app/

# 2. the skill (inline, auto-triggers by description)
mkdir -p /path/to/your-app/.claude/skills/risograph-ui
cp SKILL.md riso.css DESIGN_RULES.md  /path/to/your-app/.claude/skills/risograph-ui/

# 3. (optional) the auditor subagent — for big cross-file audits in its own context
cp risograph-ui-auditor.md  /path/to/your-app/.claude/agents/
```

Then `@import "./riso.css";` at your app root, add `class="dark"` to `<html>` for
the dark palette, and build from the bundled classes. Claude reads `DESIGN_RULES.md`
before any visual change.

**Skill vs. agent:** the skill runs inline in the main conversation and
auto-triggers from its description; the agent is an isolated subagent you delegate
to for a comprehensive, whole-app audit with its own context budget. Ship either or
both.

Using Codex instead? See [`../codex/`](../codex/).
