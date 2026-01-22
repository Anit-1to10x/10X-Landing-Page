# Visual Design Strategy - 10x Vibe Marketing

Generated: 2026-01-16

## Brand Summary

**Personality**: Modern, Approachable, Innovative, Clear
**Visual Mood**: Fresh and forward-thinking, yet welcoming and accessible. Technology meets humanity—innovative without being intimidating.

---

## Typography

### Fonts
- **Headings**: Inter (600-700) — Clean, modern, highly readable
- **Body**: Inter (400) — Consistent, professional, excellent for digital
- **Source**: https://fonts.google.com/specimen/Inter

### Why Inter
- Modern geometric design that feels innovative
- Highly readable at all sizes (clear)
- Friendly x-height and proportions (approachable)
- Industry standard for tech/education (professional credibility)

### Scale
```
h1: clamp(2.5rem, 5vw, 4rem)    -- Hero headline
h2: clamp(2rem, 4vw, 3rem)      -- Section headers
h3: clamp(1.5rem, 3vw, 2rem)    -- Subsection headers
h4: clamp(1.25rem, 2vw, 1.5rem) -- Feature titles
body: 1rem (16px)               -- Standard text
bodyLarge: 1.125rem (18px)      -- Hero subhead, emphasis
small: 0.875rem (14px)          -- Captions, labels
```

### Line Heights
- Headings: 1.2 (tight, impactful)
- Body: 1.6 (comfortable reading)

### Letter Spacing
- Headings: -0.02em (slightly tighter)
- Body: 0 (default)
- Uppercase labels: 0.05em (slightly spaced)

---

## Color Palette

### Primary Colors
- **Primary**: #6366F1 (Indigo) — Modern, innovative, trustworthy
- **Primary Light**: #818CF8 — Hover states, backgrounds
- **Primary Dark**: #4F46E5 — Active states, emphasis
- **Secondary**: #14B8A6 (Teal) — Fresh, growth-oriented, approachable
- **Accent**: #F59E0B (Amber) — Warmth, attention, friendly energy

### Why This Palette
- **Indigo primary**: Combines the trustworthiness of blue with the innovation of purple. Modern tech feel without being corporate.
- **Teal secondary**: Fresh, growth-oriented (learning), calming yet energetic.
- **Amber accent**: Adds warmth and approachability, great for CTAs and highlights.

### Neutrals
- **White**: #FFFFFF — Clean backgrounds
- **Background**: #FAFBFC — Subtle off-white for depth
- **Surface**: #FFFFFF — Card backgrounds
- **Border**: #E5E7EB — Subtle dividers
- **Text Primary**: #111827 — High contrast headings
- **Text Secondary**: #4B5563 — Body text
- **Text Muted**: #9CA3AF — Captions, placeholders

### Semantic Colors
- **Success**: #10B981 — Confirmations, positive states
- **Warning**: #F59E0B — Caution, attention
- **Error**: #EF4444 — Errors, destructive actions
- **Info**: #3B82F6 — Informational elements

### Gradients
- **Primary Gradient**: linear-gradient(135deg, #6366F1 0%, #8B5CF6 100%)
- **Hero Background**: linear-gradient(180deg, #FAFBFC 0%, #F3F4F6 100%)
- **CTA Gradient**: linear-gradient(135deg, #6366F1 0%, #4F46E5 100%)

### Usage Guidelines
- **Backgrounds**: White (#FFFFFF) for main, Background (#FAFBFC) for alternating sections
- **Text**: Primary (#111827) for headings, Secondary (#4B5563) for body
- **CTAs**: Primary (#6366F1) with white text, hover to Primary Dark (#4F46E5)
- **Accents**: Use Amber sparingly for highlights, badges, important elements

---

## Imagery

### Style
Modern tech with human warmth. Clean UI screenshots, professional photography, subtle abstract elements.

### Hero
**Recommendation**: Half-and-Half layout
- Left: Headline, subhead, CTA
- Right: Product screenshot in styled frame or abstract tech illustration
- Background: Subtle gradient or light pattern

**Alternative**: Device mockup showing course interface with subtle floating elements

### Section Imagery
| Section | Imagery Approach |
|---------|-----------------|
| Problem | Abstract frustrated illustration OR icons |
| Solution | Clean UI screenshot of course platform |
| Benefits | Icons for each benefit (custom, matching style) |
| How It Works | Step icons or simple illustrations |
| Features | Feature icons with subtle backgrounds |
| Social Proof | Certification badge, minimal graphics |
| FAQ | Expand/collapse icons |
| Final CTA | Background gradient, no heavy imagery |

### Assets Required
- Logo (SVG format, light and dark versions)
- Hero image/illustration (min 1200px wide)
- Course UI screenshot (for credibility)
- Certification badge/seal graphic
- Icon set (12-16 icons, matching style)
- Favicon (32x32 SVG)

---

## Layout

### Above the Fold
**Pattern**: Half-and-Half

```
┌─────────────────────────────────────────────────────┐
│  NAV: Logo                    Links    [CTA Button] │
├─────────────────────────────────────────────────────┤
│                                                     │
│  ┌──────────────────┐   ┌──────────────────────┐   │
│  │                  │   │                      │   │
│  │  HEADLINE        │   │   HERO VISUAL        │   │
│  │                  │   │   (Screenshot or     │   │
│  │  Subhead text    │   │    Illustration)     │   │
│  │                  │   │                      │   │
│  │  [Primary CTA]   │   │                      │   │
│  │  [Secondary]     │   │                      │   │
│  │                  │   │                      │   │
│  │  Micro-proof     │   │                      │   │
│  │                  │   │                      │   │
│  └──────────────────┘   └──────────────────────┘   │
│                                                     │
└─────────────────────────────────────────────────────┘
```

### Section Layouts
| Section | Layout Pattern | Notes |
|---------|---------------|-------|
| Problem | Centered text with icon list | Emotional connection, scannable |
| Solution | Half-and-half (text + visual) | Introduce the product |
| Benefits | 3-column card grid | Equal visual weight, icons |
| How It Works | 3-step horizontal timeline | Clear progression |
| Features | 2x2 or 4-column grid | Feature cards with icons |
| Social Proof | Centered, minimal | Certification focus |
| FAQ | Accordion style | Clean, expandable |
| Final CTA | Centered on gradient background | Strong close |

### Grid System
- Max width: 1200px
- Gutter: 32px (desktop), 24px (tablet), 16px (mobile)
- Columns: 12-column grid

---

## Visual Interest Techniques

### Selected Techniques (5)

1. **Gradient Text (Hero)**
   - Apply primary gradient to key words in headline
   - Draws attention, modern feel
   ```css
   .gradient-text {
     background: linear-gradient(135deg, #6366F1, #8B5CF6);
     -webkit-background-clip: text;
     -webkit-text-fill-color: transparent;
   }
   ```

2. **Card Shadows (Feature Cards)**
   - Subtle layered shadows for depth
   - Creates visual hierarchy
   ```css
   .card {
     box-shadow: 0 1px 3px rgba(0,0,0,0.05),
                 0 4px 6px rgba(0,0,0,0.05);
   }
   .card:hover {
     box-shadow: 0 4px 6px rgba(0,0,0,0.05),
                 0 10px 20px rgba(0,0,0,0.1);
     transform: translateY(-2px);
   }
   ```

3. **Subtle Background Gradient**
   - Light gradient between sections for depth
   - Keeps the page from feeling flat
   ```css
   .section-alt {
     background: linear-gradient(180deg, #FAFBFC 0%, #F3F4F6 100%);
   }
   ```

4. **Scroll Animations**
   - Elements fade in and slide up on scroll
   - Modern, polished feel
   - Keep timing subtle (0.5s ease)

5. **Icon Backgrounds**
   - Light colored circle/rounded square behind feature icons
   - Adds visual weight without clutter
   ```css
   .icon-wrapper {
     background: rgba(99, 102, 241, 0.1);
     border-radius: 12px;
     padding: 12px;
   }
   ```

---

## Design System Summary

### For Build Agent Reference

**Border Radius**
- Small (buttons, inputs): 8px
- Medium (cards): 12px
- Large (modals, hero images): 16px
- Full (pills, avatars): 9999px

**Shadow Levels**
- sm: 0 1px 2px rgba(0,0,0,0.05)
- md: 0 4px 6px rgba(0,0,0,0.1)
- lg: 0 10px 25px rgba(0,0,0,0.15)
- xl: 0 20px 40px rgba(0,0,0,0.2)

**Spacing Scale**
- xs: 0.5rem (8px)
- sm: 1rem (16px)
- md: 1.5rem (24px)
- lg: 2rem (32px)
- xl: 3rem (48px)
- 2xl: 5rem (80px)
- 3xl: 8rem (128px)

**Animation Timing**
- Fast: 150ms ease
- Base: 300ms ease
- Slow: 500ms ease

**Button Styles**
- Primary: Background primary, white text, 8px radius
- Secondary: Transparent background, primary border, primary text
- Hover: Darken background, slight lift (translateY -2px)

**Navigation**
- Height: 72px
- Sticky on scroll
- Transparent to white on scroll (optional)
