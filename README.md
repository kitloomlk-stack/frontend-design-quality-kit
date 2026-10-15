# Frontend Design & Quality Kit

Build frontends with real design taste and measurable quality: UI/UX direction, accessibility, Core Web Vitals, purposeful animation and design-system tokens, checked in a real browser.

A setup for AI coding agents, made by [Kitloom](https://kitloom.site). One source, generated for every major agent: Claude Code, OpenAI Codex, Cursor, Google Antigravity, Gemini CLI, GitHub Copilot, Windsurf (Devin), opencode and Aider.

## Install

1. Download this repository as a ZIP, or use the **Check and download** button on its Kitloom page, which checks it first.
2. Read the files. Nothing here runs on its own: the kit has no hooks and no install scripts.
3. Copy the folders and files you want into the root of your project. `AGENTS.md` is the shared instructions file; edit it to fit your project.

## What is inside

### Skills

- `design-taste-frontend` — Art direction for a new page or app so the result does not look like generic AI output.
- `redesign-existing-projects` — Upgrading an existing site or app while keeping its behaviour intact.
- `frontend-ui-engineering` — Building production-quality, responsive, accessible components, layouts and state.
- `design-system` — Defining or refactoring design tokens, spacing and type scales, and component specs.
- `accessibility` — Auditing or fixing WCAG 2.2 issues: semantics, keyboard use, contrast, focus, labels.
- `screen-reader-testing` — Verifying behaviour with VoiceOver, NVDA or JAWS after accessibility changes.
- `core-web-vitals` — Improving LCP, INP and CLS using field and lab evidence.
- `web-quality-audit` — A full Lighthouse-style audit of performance, accessibility, SEO and best practices.
- `gsap-core` — Writing GSAP tweens, easing and responsive or reduced-motion animation.
- `gsap-performance` — Keeping animations smooth: transforms, layout thrash, will-change, batching.
- `browser-testing-with-devtools` — Inspecting the DOM, console and network or profiling a page in a real browser.

### Commands

Invoke by name (for example `/ui-review`).

- `ui-review` — Review a page or component for design quality, accessibility and responsiveness, with prioritised findings.
- `vitals-pass` — Find and fix the biggest Core Web Vitals problems on a page, measuring before and after.
- `a11y-pass` — Audit a page or component against WCAG 2.2 and fix the issues found.

### Sub-agents

- `a11y-auditor` — Delegate to audit markup and components for accessibility problems and return a prioritised report.
- `perf-investigator` — Delegate to find the likely causes of slow loading, layout shift or sluggish interaction in the code.

### Scoped rules

- `accessible-markup` — Semantic HTML, keyboard access, visible focus and labelled controls in UI code.
- `motion-and-performance` — Animate compositor-friendly properties, honour reduced motion, and protect Core Web Vitals.
- `design-tokens` — Use design tokens for colour, spacing, type and radius instead of one-off values.

## Where each agent finds it

| Agent | Instructions | Skills and commands | Rules | Sub-agents |
|---|---|---|---|---|
| Claude Code | `CLAUDE.md` (imports `AGENTS.md`) | `.claude/skills/` | `.claude/rules/` | `.claude/agents/` |
| OpenAI Codex | `AGENTS.md` | `.agents/skills/` | listed in `AGENTS.md` | `.codex/agents/` |
| Cursor | `AGENTS.md` | `.agents/skills/`, `.claude/skills/` | `.cursor/rules/` | `.claude/agents/` |
| Google Antigravity | `AGENTS.md` | `.agents/skills/` | `.agents/rules/` | `.agents/agents/` |
| Gemini CLI | `AGENTS.md` via `.gemini/settings.json` | `.agents/skills/`, `.gemini/commands/` | listed in `AGENTS.md` | `.gemini/agents/` |
| GitHub Copilot | `AGENTS.md` | `.agents/skills/`, `.github/prompts/` | `.github/instructions/` | `.claude/agents/` |
| Windsurf (Devin) | `AGENTS.md` | `.agents/skills/`, `.windsurf/workflows/` | `.windsurf/rules/` | — |
| opencode | `AGENTS.md` | `.agents/skills/`, `.opencode/commands/` | listed in `AGENTS.md` | `.opencode/agents/` |
| Aider | `AGENTS.md` via `.aider.conf.yml` | — | — | — |

Skills are stored twice (`.agents/skills/` and `.claude/skills/`) because Claude Code reads only its own folder. Agents that read both may list a skill twice; delete the copy you do not need.

## Credits

The skills come from these open-source repositories, each under its own licence. Their licence and a notice are kept beside every copied skill.

| Skill | Source | Licence |
|---|---|---|
| `design-taste-frontend` | [Leonxlnx/taste-skill](https://github.com/Leonxlnx/taste-skill) at `a60a36d` | MIT |
| `redesign-existing-projects` | [Leonxlnx/taste-skill](https://github.com/Leonxlnx/taste-skill) at `a60a36d` | MIT |
| `frontend-ui-engineering` | [addyosmani/agent-skills](https://github.com/addyosmani/agent-skills) at `aeac41d` | MIT |
| `design-system` | [nextlevelbuilder/ui-ux-pro-max-skill](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill) at `7246805` | MIT |
| `accessibility` | [addyosmani/web-quality-skills](https://github.com/addyosmani/web-quality-skills) at `afa8da9` | MIT |
| `screen-reader-testing` | [wshobson/agents](https://github.com/wshobson/agents) at `46891e7` | MIT |
| `core-web-vitals` | [addyosmani/web-quality-skills](https://github.com/addyosmani/web-quality-skills) at `afa8da9` | MIT |
| `web-quality-audit` | [addyosmani/web-quality-skills](https://github.com/addyosmani/web-quality-skills) at `afa8da9` | MIT |
| `gsap-core` | [greensock/gsap-skills](https://github.com/greensock/gsap-skills) at `aed9cfd` | MIT |
| `gsap-performance` | [greensock/gsap-skills](https://github.com/greensock/gsap-skills) at `aed9cfd` | MIT |
| `browser-testing-with-devtools` | [addyosmani/agent-skills](https://github.com/addyosmani/agent-skills) at `aeac41d` | MIT |

Everything else in this repository (instructions, rules, commands, sub-agents) is by Kitloom under the MIT licence.

## Use at your own risk

Read every file before you use it. Agent instructions can make an agent run commands on your machine. This kit was checked with Kitloom's pre-download check, which looks for warning signs but cannot prove anything is safe.
