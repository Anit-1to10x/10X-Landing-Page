# 10x Team Landing Page Skill

A professional Claude Code skill for creating high-converting landing pages using 10x Team's proprietary multi-agent methodology.

## Installation

1. **Download** this folder (or clone the repository)
2. **Open** the folder in your terminal
3. **Run** Claude Code: `claude`
4. **Start** with `/landing-page` or `/lp`

## Features

- **Multi-Agent Architecture**: 6 specialist agents coordinated by a Project Manager
- **5 Tech Stacks**: HTML, React, Next.js, Astro, Vue
- **Phase-wise Development**: Each phase has its own todo list for tracking
- **Knowledge Base**: 9 reference files for copy, design, and best practices
- **Quality Assurance**: Built-in review and revision cycles
- **Worksheets Integration**: Import existing requirements documents

## Tech Stack Options

| Option | Description | Run Command |
|--------|-------------|-------------|
| `html` | Static HTML/CSS/JS (default) | Open in browser or `npx serve build` |
| `react` | React 18 with Vite | `npm install && npm run dev` |
| `nextjs` | Next.js 14 (App Router) | `npm install && npm run dev` |
| `astro` | Astro 4 | `npm install && npm run dev` |
| `vue` | Vue 3 with Vite | `npm install && npm run dev` |

## Usage

### Start a New Project
```
/landing-page new
```
or simply
```
/lp
```

### Resume Existing Project
```
/landing-page resume my-saas-app
```

### List All Projects
```
/landing-page list
```

## Architecture

```
USER INPUT
    │
    ▼
┌─────────────────────────────────────────────────────────┐
│                    MAIN SKILL                           │
│            (Collects All User Requirements)             │
│                                                         │
│  - Tech stack selection (HTML, React, Next, Astro, Vue) │
│  - Optional: Import from Landing Page Worksheets        │
│  Saves to: user-preferences/{project}.json              │
└─────────────────────────────────────────────────────────┘
    │
    ▼
┌─────────────────────────────────────────────────────────┐
│              PROJECT MANAGER AGENT                      │
│                   (Coordinator)                         │
│                                                         │
│  - Manages master todo list for all phases              │
│  - Orchestrates all specialist agents                   │
│  - Reviews output against requirements                  │
│  - Approves or requests revisions                       │
└─────────────────────────────────────────────────────────┘
    │
    ├──► Discovery Agent      → Phase 1: Requirements analysis
    ├──► Copywriting Agent    → Phase 2: Headlines, copy, CTAs
    ├──► Design Agent         → Phase 3: Visual strategy & palette
    ├──► Build Agent          → Phase 4: Code generation (tech-stack aware)
    ├──► QA Agent             → Phase 5: Testing preparation
    └──► Launch Agent         → Phase 6: Deployment & SEO
```

## Specialist Agents

| Agent | Phase | Knowledge Base | Output |
|-------|-------|----------------|--------|
| **Discovery** | 1 | - | `requirements/brief.json` |
| **Copywriting** | 2 | `headline-formulas.md`, `copy-principles.md` | `copy/headlines.md`, `copy/page-copy.md` |
| **Design** | 3 | `color-psychology.md`, `typography-pairings.md`, `layout-patterns.md`, `visual-interest.md` | `design/strategy.md`, `colors.json`, `typography.json` |
| **Build** | 4 | `accessibility-checklist.md`, `layout-patterns.md`, `visual-interest.md` | Tech-stack specific output |
| **QA** | 5 | `testing-scripts.md` | `testing/test-kit.md` |
| **Launch** | 6 | `seo-checklist.md` | `launch/checklist.md`, `launch/maintenance.md` |

## Project Output Structure

```
projects/{project-name}/
├── requirements/
│   └── brief.json           # Strategic brief from Discovery
├── copy/
│   ├── headlines.md         # Headline options with rationale
│   └── page-copy.md         # Complete page copy
├── design/
│   ├── strategy.md          # Visual design strategy
│   ├── colors.json          # Color palette
│   └── typography.json      # Font selections
├── build/                   # Tech-stack specific output
│   ├── index.html           # (HTML) or package.json + src/ (React/Vue/etc)
│   ├── css/styles.css
│   └── js/main.js
├── testing/
│   └── test-kit.md          # User testing materials
├── launch/
│   ├── checklist.md         # Deployment checklist
│   └── maintenance.md       # Maintenance guide
└── status.json              # Project status tracking
```

## Directory Structure

```
10x-Team-Landing-Page-Skill/
├── .claude/
│   ├── settings.json
│   ├── commands/
│   │   ├── landing-page.md
│   │   └── lp.md
│   └── skills/
│       └── landing-page/
│           ├── SKILL.md
│           ├── agents/           (7 agent files)
│           ├── knowledge/        (9 knowledge base files)
│           └── scripts/          (8 generator scripts)
├── .claude-plugin/
│   ├── plugin.json
│   └── marketplace.json
├── projects/                     # Output folder
├── user-preferences/             # Saved preferences
└── README.md
```

## Scripts

| Script | Purpose |
|--------|---------|
| `init-project.js` | Initialize new project with tech stack |
| `generate-project.js` | Unified generator (routes to correct tech) |
| `generate-html.js` | Generate static HTML/CSS/JS |
| `generate-react.js` | Generate React + Vite project |
| `generate-nextjs.js` | Generate Next.js project |
| `generate-astro.js` | Generate Astro project |
| `generate-vue.js` | Generate Vue + Vite project |
| `list-projects.js` | List all projects |

## License

10x Team Proprietary - For use with 10x Team subscription.
