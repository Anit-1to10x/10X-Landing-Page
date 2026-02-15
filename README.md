# 10x Team Marketing Agency Suite

A complete AI-powered marketing agency — **14 specialist skills** for creating, optimizing, and converting landing pages across **12 domain categories**. Works across **every major AI coding agent, IDE, and CLI**.

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
# Just open this folder — skills are auto-discovered
```

## The 14-Skill Suite

### Core Skill
| Command | What it does |
|---------|-------------|
| `/landing-page` or `/lp` | Full multi-agent landing page creation — asks 12 questions, runs 6 specialist agents, produces production-ready code |

### Companion Skills (use directly or auto-invoked)
| Command | What it does |
|---------|-------------|
| `/lp-copy` | Optimize headlines, body copy, CTAs, and microcopy |
| `/lp-seo` | SEO audit — meta tags, schema markup, Open Graph, keywords |
| `/lp-design` | Design system — colors, typography, spacing, CSS variables |
| `/lp-analytics` | Analytics setup — GA4, Meta Pixel, events, UTM strategy |
| `/lp-inject` | JavaScript injection — tracking scripts, chat widgets, custom code |
| `/lp-audit` | 7-point page audit — copy, design, SEO, a11y, speed, CRO, mobile |
| `/lp-optimize` | CRO analysis — LIFT model, friction audit, conversion psychology |
| `/lp-funnel` | Funnel builder — multi-page flows, upsells, email sequences |
| `/lp-leads` | Lead capture — forms, popups, exit-intent, email integration |
| `/lp-abtest` | A/B test setup — variants, tracking, hypothesis, analysis |
| `/lp-competitor` | Competitor teardown — positioning, gaps, counter-strategies |
| `/lp-content` | Content strategy — testimonials, case studies, social proof |
| `/lp-speed` | Performance — Core Web Vitals, images, lazy loading, minification |

## 12 Domain Categories

When you run `/landing-page new`, you choose your page type. Each domain generates a **different page structure** with domain-appropriate sections, CTAs, and data points:

| # | Domain | Primary CTA | Example Sections |
|---|--------|-------------|------------------|
| 1 | **SaaS / Software** | Start Free Trial | Hero, Social Proof Bar, Features, How It Works, Pricing, FAQ |
| 2 | **Ecommerce / Product** | Add to Cart | Product Gallery, Specs, Reviews, Trust Signals, Cross-Sell |
| 3 | **Portfolio / Personal** | Hire Me | Featured Work, Skills, About, Contact |
| 4 | **IT Support / Services** | Get Consultation | Pain Points, Services, Process, Case Studies, Quote Form |
| 5 | **Event / Webinar** | Register Now | Speakers, Agenda, Countdown Timer, Registration Form |
| 6 | **Demo / Product Demo** | Book a Demo | Demo Video, Benefits, Booking Calendar |
| 7 | **Lead Magnet** | Download Free | What's Inside, Author Credibility, Email Capture |
| 8 | **Agency / Services** | Get a Quote | Services, Process, Results, Client Logos, Contact Form |
| 9 | **App Download** | Get the App | App Screenshots, Store Badges, Ratings |
| 10 | **Coming Soon** | Join Waitlist | Teaser, Countdown, Email Capture |
| 11 | **Nonprofit / Cause** | Donate Now | Impact Stats, Stories, Transparency, Donation Tiers |
| 12 | **Real Estate** | Schedule Viewing | Photo Gallery, Property Details, Map, Agent Info |

## Intelligent Skill Routing

The system **automatically decides** which companion skills to invoke based on:

1. **Domain category** — SaaS auto-invokes SEO + Analytics; Ecommerce auto-invokes Speed + SEO
2. **Your prompt** — saying "with SEO" triggers `/lp-seo`; saying "with analytics" triggers `/lp-analytics`
3. **Token efficiency** — simple requests (e.g., "create a portfolio page") skip unnecessary skills

```
"Create a SaaS landing page"
→ Core pipeline + SEO + Analytics (auto-invoked for SaaS)

"Create a portfolio page"
→ Core pipeline only (lightweight domain, minimal skills)

"Create a landing page with everything — SEO, analytics, speed, A/B test"
→ Core pipeline + ALL mentioned skills

"Create an ecommerce product page with lead capture"
→ Core pipeline + SEO + Speed (auto) + Leads (explicit)
```

## How It Works

```
You answer questions (including domain selection)
       ↓
Discovery Agent      → Strategic brief (domain-specific structure)
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
       ↓
[Conditional Skills] → SEO, Analytics, Speed, Leads, etc. (if triggered)
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

| Tier | Models | Behavior |
|------|--------|----------|
| **Tier 1** | Claude Opus 4.6, GPT-5.3, Claude Sonnet 4.5 | Full 6-phase pipeline, rich outputs, PM review with 2 revision cycles |
| **Tier 2** | Big Pickle, Gemini 2.5 Pro/Flash, Claude Sonnet 4.0 | Sequential phases, on-demand knowledge loading, 1 revision max |
| **Tier 3** | Claude Haiku, smaller open-weight models | Combined 3-phase flow, minimal knowledge loading, no revision cycle |

## Knowledge Base (18 files)

| File | Used By | Contains |
|------|---------|----------|
| `domain-templates.md` | Discovery | 12 domain categories with section structures and routing rules |
| `headline-formulas.md` | Copywriting | 6 headline patterns, validation rules, subhead formulas |
| `copy-principles.md` | Copywriting | 11 copy commandments, CTA guidelines, social proof ranking |
| `color-psychology.md` | Design | Color meanings, brand personality mapping, palette structure |
| `typography-pairings.md` | Design | Font pairings by brand type, responsive type scale |
| `layout-patterns.md` | Design, Build | 10 ATF layouts, 18 section layouts, page structure template |
| `visual-interest.md` | Design, Build | CSS techniques for text effects, depth, backgrounds, animation |
| `accessibility-checklist.md` | Build, Audit | WCAG AA requirements, semantic HTML, contrast, keyboard nav |
| `seo-checklist.md` | Launch, SEO | Meta tags, Open Graph, Twitter Cards, structured data, sitemap |
| `testing-scripts.md` | QA | 10-second test, full user testing script, analysis templates |
| `cro-principles.md` | Optimize, Audit | LIFT model, friction audit, conversion psychology |
| `analytics-setup.md` | Analytics, Inject | GA4, Meta Pixel, Google Ads, events, data layer, UTM |
| `funnel-patterns.md` | Funnel | 6 funnel types, page sequences, email frameworks |
| `lead-capture.md` | Leads, Optimize | 8 capture mechanisms, form optimization, GDPR |
| `competitor-analysis.md` | Competitor | 5-step teardown, SWOT, positioning matrix |
| `speed-optimization.md` | Speed, Audit | Core Web Vitals, image optimization, lazy loading |
| `abtest-framework.md` | A/B Test | Hypothesis template, sample size, significance |
| `js-injection.md` | Inject, Analytics | Script loading patterns, CSP, debug mode |

## Repo Structure

```
.
├── .claude/                          # Claude Code / Codex / Cursor
│   └── skills/
│       ├── landing-page/             # Core multi-agent skill
│       │   ├── SKILL.md
│       │   ├── agents/    (7 files)
│       │   ├── knowledge/ (18 files)
│       │   └── scripts/   (8 files)
│       ├── lp-copy/SKILL.md          # Copy optimizer
│       ├── lp-seo/SKILL.md           # SEO optimizer
│       ├── lp-design/SKILL.md        # Design system
│       ├── lp-analytics/SKILL.md     # Analytics setup
│       ├── lp-inject/SKILL.md        # JS injection
│       ├── lp-audit/SKILL.md         # Page audit
│       ├── lp-optimize/SKILL.md      # CRO optimizer
│       ├── lp-funnel/SKILL.md        # Funnel builder
│       ├── lp-leads/SKILL.md         # Lead capture
│       ├── lp-abtest/SKILL.md        # A/B testing
│       ├── lp-competitor/SKILL.md    # Competitor analysis
│       ├── lp-content/SKILL.md       # Content strategy
│       └── lp-speed/SKILL.md         # Speed optimizer
│
├── .opencode/                        # OpenCode CLI / TUI
│   ├── config.json
│   └── skills/                       # Full standalone mirror (14 skills)
│       ├── landing-page/
│       ├── lp-copy/ ... lp-speed/
│
├── projects/                         # Generated project output
├── user-preferences/                 # Saved user inputs
├── CLAUDE.md                         # Project instructions
└── README.md                         # This file
```

Both `.claude/` and `.opencode/` are **full standalone copies** — no cross-references between them.

## License

10x Team Proprietary - For use with [10x.in](https://10x.in) subscription.
