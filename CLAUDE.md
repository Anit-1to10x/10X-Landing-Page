# 10x Team Marketing Agency Suite

## Quick Start

```
/landing-page new    # Full landing page (asks domain category)
/lp                  # Shortcut
```

## All 14 Skills

| Command | Purpose |
|---------|---------|
| `/landing-page` | Full multi-agent landing page creation |
| `/lp-copy` | Optimize headlines, body copy, CTAs |
| `/lp-seo` | SEO audit + meta tags + schema |
| `/lp-design` | Design system — colors, typography, layout |
| `/lp-analytics` | Analytics — GA4, pixels, events |
| `/lp-inject` | JavaScript injection — tracking, widgets |
| `/lp-audit` | 7-point page audit with scores |
| `/lp-optimize` | CRO — conversion rate optimization |
| `/lp-funnel` | Multi-page funnel + email sequences |
| `/lp-leads` | Lead capture — forms, popups, exit-intent |
| `/lp-abtest` | A/B test setup with variants |
| `/lp-competitor` | Competitor page teardown |
| `/lp-content` | Content strategy + social proof |
| `/lp-speed` | Core Web Vitals + performance |

## 12 Domain Categories

SaaS, Ecommerce, Portfolio, IT Support, Event, Demo, Lead Magnet, Agency, App, Coming Soon, Nonprofit, Real Estate

## Tech Stacks

1. `html` - Static HTML/CSS/JS (default)
2. `react` - React 18 + Vite
3. `nextjs` - Next.js 14 (App Router)
4. `astro` - Astro 4
5. `vue` - Vue 3 + Vite

## File Locations

```
.claude/skills/
├── landing-page/           # Core skill (agents, knowledge, scripts)
├── lp-copy/SKILL.md        # 13 companion skills
├── lp-seo/SKILL.md
├── lp-design/SKILL.md
├── lp-analytics/SKILL.md
├── lp-inject/SKILL.md
├── lp-audit/SKILL.md
├── lp-optimize/SKILL.md
├── lp-funnel/SKILL.md
├── lp-leads/SKILL.md
├── lp-abtest/SKILL.md
├── lp-competitor/SKILL.md
├── lp-content/SKILL.md
└── lp-speed/SKILL.md
```

## Knowledge Base (18 files in `landing-page/knowledge/`)

Core: `headline-formulas.md`, `copy-principles.md`, `color-psychology.md`, `typography-pairings.md`, `layout-patterns.md`, `visual-interest.md`, `accessibility-checklist.md`, `seo-checklist.md`, `testing-scripts.md`

Extended: `domain-templates.md`, `cro-principles.md`, `analytics-setup.md`, `funnel-patterns.md`, `lead-capture.md`, `competitor-analysis.md`, `speed-optimization.md`, `abtest-framework.md`, `js-injection.md`

## Intelligent Routing

Skills auto-invoke based on domain + user prompt. Simple requests skip unnecessary skills to save tokens.

## Branding

This is **10x Team's proprietary methodology**. Never reference external sources.
