# 10x Team Landing Page Skill

## Quick Start

```
/landing-page new    # Start new project
/lp                  # Shortcut
```

## Tech Stacks

1. `html` - Static HTML/CSS/JS (default)
2. `react` - React 18 + Vite
3. `nextjs` - Next.js 14 (App Router)
4. `astro` - Astro 4
5. `vue` - Vue 3 + Vite

## File Locations

```
.claude/skills/landing-page/
├── SKILL.md                    # Main skill entry point
├── agents/                     # 7 agent definitions
│   ├── project-manager.md
│   ├── discovery-agent.md
│   ├── copywriting-agent.md
│   ├── design-agent.md
│   ├── build-agent.md
│   ├── qa-agent.md
│   └── launch-agent.md
├── knowledge/                  # 9 reference files
│   ├── headline-formulas.md
│   ├── copy-principles.md
│   ├── color-psychology.md
│   ├── typography-pairings.md
│   ├── layout-patterns.md
│   ├── visual-interest.md
│   ├── accessibility-checklist.md
│   ├── seo-checklist.md
│   └── testing-scripts.md
└── scripts/                    # 8 generator scripts
    ├── init-project.js
    ├── generate-project.js
    ├── generate-html.js
    ├── generate-react.js
    ├── generate-nextjs.js
    ├── generate-astro.js
    ├── generate-vue.js
    └── list-projects.js
```

## Agent → Knowledge Mapping

| Agent | Loads |
|-------|-------|
| Copywriting | `headline-formulas.md`, `copy-principles.md` |
| Design | `color-psychology.md`, `typography-pairings.md`, `layout-patterns.md`, `visual-interest.md` |
| Build | `accessibility-checklist.md`, `layout-patterns.md`, `visual-interest.md` |
| QA | `testing-scripts.md` |
| Launch | `seo-checklist.md` |

## 6 Phases

1. **Discovery** → `requirements/brief.json`
2. **Copywriting** → `copy/headlines.md`, `copy/page-copy.md`
3. **Design** → `design/strategy.md`, `colors.json`, `typography.json`
4. **Build** → `build/` (tech-stack specific)
5. **QA** → `testing/test-kit.md`
6. **Launch** → `launch/checklist.md`, `launch/maintenance.md`

## Branding

This is **10x Team's proprietary methodology**. Never reference external sources.
