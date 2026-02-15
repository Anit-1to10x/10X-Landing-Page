# 10x Team Landing Page Skill

A production-grade multi-agent skill for creating high-converting landing pages. Works across **every major AI coding agent, IDE, and CLI**.

## Compatible With

| Platform | Type | Status |
|----------|------|--------|
| **Claude Code** | CLI | Fully supported |
| **Claude Codex** | Cloud agent | Fully supported |
| **OpenCode** | CLI / TUI | Fully supported |
| **Cursor** | IDE | Fully supported |
| **Windsurf** | IDE | Fully supported |
| **VS Code** (Copilot / Cline / Roo Code / Continue) | IDE extensions | Fully supported |
| **Antigravity** | AI agent | Fully supported |
| **Gemini CLI** | CLI | Fully supported |
| **Aider** | CLI | Fully supported |
| **Amazon Q Developer** | CLI / IDE | Fully supported |
| **Any Agent Skills compatible tool** | Any | Fully supported |

> Built on the **Agent Skills open standard** — if your tool reads `SKILL.md` files with YAML frontmatter, this works out of the box.

## Quick Start

```bash
# Clone the repo
git clone https://github.com/Anit-1to10x/10X-Landing-Page.git
cd 10X-Landing-Page

# Use with Claude Code
claude
/landing-page new

# Use with OpenCode
opencode
/landing-page new

# Use with any compatible agent
# Just open this folder — the skill is auto-discovered
```

## What It Does

You answer 12 questions about your business. Six specialist AI agents then build you a complete landing page:

```
You answer questions
       ↓
Discovery Agent      → Strategic brief
       ↓
Copywriting Agent    → Headlines, body copy, CTAs
       ↓
Design Agent         → Colors, typography, layout
       ↓
Build Agent          → Production HTML/CSS/JS (or React/Next/Astro/Vue)
       ↓
QA Agent             → User testing scripts
       ↓
Launch Agent         → SEO, analytics, deployment checklist
```

**Output**: A complete `projects/{name}/` folder with production-ready code, testing kit, and launch checklist.

## Tech Stack Options

| Stack | Description | Run Command |
|-------|-------------|-------------|
| `html` | Static HTML/CSS/JS (default) | Open `build/index.html` or `npx serve build` |
| `react` | React 18 + Vite | `cd build && npm install && npm run dev` |
| `nextjs` | Next.js 14 (App Router) | `cd build && npm install && npm run dev` |
| `astro` | Astro 4 | `cd build && npm install && npm run dev` |
| `vue` | Vue 3 + Vite | `cd build && npm install && npm run dev` |

## Model Adaptation

This skill adapts to your model's capability automatically:

| Tier | Models | Behavior |
|------|--------|----------|
| **Tier 1** | Claude Opus 4.6, GPT-5.3, Claude Sonnet 4.5 | Full 6-phase pipeline, rich outputs, PM review with 2 revision cycles |
| **Tier 2** | Big Pickle, Gemini 2.5 Pro/Flash, Claude Sonnet 4.0 | Sequential phases, on-demand knowledge loading, 1 revision max |
| **Tier 3** | Claude Haiku, smaller open-weight models | Combined 3-phase flow, minimal knowledge loading, no revision cycle |

Models self-assess based on context window and reasoning capability. Every tier produces a complete landing page — higher tiers just do more refinement.

## Commands

```
/landing-page new           # Start new project
/landing-page resume {name} # Continue existing project
/landing-page list          # Show all projects
/landing-page edit {name}   # Modify existing project
/lp                         # Shortcut for /landing-page new
```

## Architecture

### Multi-Agent System

```
USER INPUT (12 questions)
    │
    ▼
┌────────────────────────────────────────────────┐
│               MAIN SKILL                       │
│         (Collects requirements)                │
│   Saves to: user-preferences/{project}.json    │
└────────────────────────────────────────────────┘
    │
    ▼
┌────────────────────────────────────────────────┐
│          PROJECT MANAGER AGENT                 │
│               (Judge)                          │
│                                                │
│  Orchestrates 6 specialists in sequence        │
│  Reviews each output against your requirements │
│  Approves or sends back for revision           │
└────────────────────────────────────────────────┘
    │
    ├──► Discovery Agent      → requirements/brief.json
    ├──► Copywriting Agent    → copy/headlines.md, copy/page-copy.md
    ├──► Design Agent         → design/strategy.md, colors.json, typography.json
    ├──► Build Agent          → build/ (tech-stack specific)
    ├──► QA Agent             → testing/test-kit.md
    └──► Launch Agent         → launch/checklist.md, launch/maintenance.md
```

### Agent → Knowledge Mapping

Each agent loads only the knowledge files it needs (progressive loading saves context):

| Agent | Knowledge Files Loaded | ~Tokens |
|-------|----------------------|---------|
| Discovery | None (uses user input) | 0 |
| Copywriting | `headline-formulas.md`, `copy-principles.md` | ~2k |
| Design | `color-psychology.md`, `typography-pairings.md`, `layout-patterns.md`, `visual-interest.md` | ~6k |
| Build | `accessibility-checklist.md`, `layout-patterns.md`, `visual-interest.md` | ~5k |
| QA | `testing-scripts.md` | ~2k |
| Launch | `seo-checklist.md` | ~2k |

## Project Output

```
projects/{project-name}/
├── requirements/
│   └── brief.json           # Strategic brief
├── copy/
│   ├── headlines.md         # Headlines with rationale + rejected options
│   └── page-copy.md         # Complete page copy by section
├── design/
│   ├── strategy.md          # Visual design strategy
│   ├── colors.json          # Color palette (WCAG AA compliant)
│   └── typography.json      # Font system with responsive scale
├── build/                   # Production code (varies by tech stack)
│   ├── index.html
│   ├── css/styles.css
│   └── js/main.js
├── testing/
│   └── test-kit.md          # 10-second test + full user testing script
├── launch/
│   ├── checklist.md         # Pre/post deployment checklist
│   └── maintenance.md       # Ongoing maintenance guide
├── summary.md               # Project summary
└── status.json              # Build status tracking
```

## Repo Structure

```
.
├── .claude/                          # Claude Code / Codex / Cursor
│   └── skills/landing-page/
│       ├── SKILL.md                  # Skill entry point
│       ├── agents/                   # 7 specialist agent prompts
│       │   ├── project-manager.md
│       │   ├── discovery-agent.md
│       │   ├── copywriting-agent.md
│       │   ├── design-agent.md
│       │   ├── build-agent.md
│       │   ├── qa-agent.md
│       │   └── launch-agent.md
│       ├── knowledge/                # 9 reference knowledge files
│       │   ├── headline-formulas.md
│       │   ├── copy-principles.md
│       │   ├── color-psychology.md
│       │   ├── typography-pairings.md
│       │   ├── layout-patterns.md
│       │   ├── visual-interest.md
│       │   ├── accessibility-checklist.md
│       │   ├── seo-checklist.md
│       │   └── testing-scripts.md
│       └── scripts/                  # 8 Node.js generator scripts
│           ├── init-project.js
│           ├── generate-project.js
│           ├── generate-html.js
│           ├── generate-react.js
│           ├── generate-nextjs.js
│           ├── generate-astro.js
│           ├── generate-vue.js
│           └── list-projects.js
│
├── .opencode/                        # OpenCode CLI / TUI
│   ├── config.json                   # Skill registration
│   └── skills/landing-page/          # Full standalone mirror
│       ├── SKILL.md
│       ├── agents/    (7 files)
│       ├── knowledge/ (9 files)
│       └── scripts/   (8 files)
│
├── projects/                         # Generated project output
├── user-preferences/                 # Saved user inputs
├── CLAUDE.md                         # Project instructions
└── README.md                         # This file
```

Both `.claude/` and `.opencode/` are **full standalone copies** — no cross-references between them. Each works independently with its respective tool.

## Knowledge Base

| File | Used By | Contains |
|------|---------|----------|
| `headline-formulas.md` | Copywriting | 6 headline patterns, validation rules, subhead formulas |
| `copy-principles.md` | Copywriting | 11 copy commandments, CTA guidelines, social proof ranking |
| `color-psychology.md` | Design | Color meanings, brand personality mapping, palette structure |
| `typography-pairings.md` | Design | Font pairings by brand type, responsive type scale |
| `layout-patterns.md` | Design, Build | 10 ATF layouts, 18 section layouts, page structure template |
| `visual-interest.md` | Design, Build | CSS techniques for text effects, depth, backgrounds, animation |
| `accessibility-checklist.md` | Build | WCAG AA requirements, semantic HTML, contrast, keyboard nav |
| `seo-checklist.md` | Launch | Meta tags, Open Graph, Twitter Cards, structured data, sitemap |
| `testing-scripts.md` | QA | 10-second test, full user testing script, analysis templates |

Every knowledge file has a **TL;DR comment** at the top so smaller models can decide whether to load the full file.

## Scripts

| Script | Purpose |
|--------|---------|
| `init-project.js` | Create project folder structure |
| `generate-project.js` | Route to correct tech-stack generator |
| `generate-html.js` | Generate static HTML/CSS/JS |
| `generate-react.js` | Generate React 18 + Vite project |
| `generate-nextjs.js` | Generate Next.js 14 (App Router) project |
| `generate-astro.js` | Generate Astro 4 project |
| `generate-vue.js` | Generate Vue 3 + Vite project |
| `list-projects.js` | List all projects with status |

## How It Works With Different Tools

### Claude Code / Claude Codex
```bash
claude                    # or run via Codex
/landing-page new
```
Discovers skill from `.claude/skills/landing-page/SKILL.md`.

### OpenCode
```bash
opencode
/landing-page new
```
Discovers skill from `.opencode/skills/landing-page/SKILL.md` (or falls back to `.claude/skills/`).

### Cursor / Windsurf / VS Code
Open this folder as your project root. The IDE agent reads `.claude/skills/` automatically. Trigger with `/landing-page` in the AI chat.

### Antigravity / Gemini CLI / Aider / Other Agents
Any tool that supports the Agent Skills open standard will discover and load `SKILL.md` from either `.claude/skills/` or `.opencode/skills/`. Just open this folder and invoke `/landing-page`.

## License

MIT
