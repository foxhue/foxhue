# Foxhue — Creative Design & Marketing

## Overview
Agency website for Foxhue Ltd, a creative design and marketing studio based in Bicester, Oxfordshire. Built from the Foxhue Studio template.

**GitHub Pages**: https://foxhue.github.io/foxhue/
**Design Hub**: https://foxhue.github.io/foxhue/designs/
**Layout Variants**: https://foxhue.github.io/foxhue/website/variants/

## Repo Structure
```
foxhue/
├── CLAUDE.md
├── project.json              ← all config (names, colors, fonts, emails, pages, designs)
├── .gitignore
├── .claude/commands/
│   ├── scaffold.md           ← /scaffold command
│   ├── seo-report.md        ← /seo-report command
│   └── brand-palette.md     ← /brand-palette command
├── index.html                ← project hub (internal)
├── designs/
│   ├── index.html            ← design direction hub (client-facing)
│   ├── styles.css
│   ├── design-a/             ← Studio Minimal
│   ├── design-b/             ← Editorial Motion
│   └── design-c/             ← Warm Craft
├── website/
│   ├── index.html            ← homepage
│   ├── services.html
│   ├── work.html
│   ├── about.html
│   ├── blog.html
│   ├── contact.html
│   ├── styles.css            ← brand tokens stylesheet
│   ├── images/               ← local images (shared across all pages)
│   └── variants/
│       ├── index.html        ← client review hub (AJAX form + localStorage)
│       ├── home-b.html
│       ├── services-b.html
│       ├── work-b.html
│       ├── about-b.html
│       ├── blog-b.html
│       ├── contact-b.html
│       ├── home-c.html
│       ├── services-c.html
│       ├── work-c.html
│       ├── about-c.html
│       ├── blog-c.html
│       └── contact-c.html
├── landing/
├── docs/
│   ├── client-asset-brief.md
│   └── seo-competitor-report.html
└── inspiration/
    └── references.md         ← design inspiration research
```

## Brand Tokens
| Token | Value | Name |
|-------|-------|------|
| Primary | `#1A1A2E` | deep navy |
| Accent | `#E94560` | coral |
| Accent hover | `#D63851` | dark coral |
| Background | `#F8F8FA` | near-white |
| Surface | `#FFFFFF` | white |
| Heading font | DM Serif Display | serif |
| Body font | Inter | sans-serif |

```css
--foxhue-primary: #1A1A2E;
--foxhue-accent: #E94560;
--foxhue-accent-hover: #D63851;
--foxhue-bg: #F8F8FA;
--foxhue-surface: #FFFFFF;
--foxhue-text: #1A1A2E;
--foxhue-light: #ffffff;
--foxhue-font-heading: 'DM Serif Display', serif;
--foxhue-font-body: 'Inter', sans-serif;
```

### Font Loading
```html
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
```

## Design Directions
| Direction | Name | Mood |
|-----------|------|------|
| A | Studio Minimal | Clean, architectural white space with bold typography — confidence through restraint |
| B | Editorial Motion | Magazine-inspired layouts with cinematic transitions — creative energy meets polish |
| C | Warm Craft | Approachable, textured, and human — boutique studio feel with premium finish |

## Pages (6)
| Page | File | Description |
|------|------|-------------|
| Homepage | index.html | Hero, services overview, recent work, testimonials, CTA |
| Services | services.html | Brand refresh, web design, logo, social media, presentations, documentation |
| Our Work | work.html | Portfolio/case studies (MARR Laser as first case study) |
| About | about.html | Team, values, 30+ years combined experience |
| Blog | blog.html | SEO content hub |
| Contact | contact.html | Form, Bicester location, social links |

## Subdirectory Details

### `website/`
6-page site for Foxhue. `variants/` contains Layout B and Layout C alternatives for each page (12 variant pages). The review hub at `variants/index.html` presents all 3 layouts per page with radio-button selectors, notes fields, and Formsubmit.co AJAX submission (sends to andrew@foxhue.com, CC ashley@foxhue.com). Form submits via AJAX and displays inline confirmation. JavaScript handles localStorage auto-save, live summary panel, and copy-to-clipboard fallback.

### `designs/`
Three design directions for internal review. Hub at `designs/index.html`. Design pages reference `../website/images/` for shared image assets.

### `docs/`
SEO competitor report (`seo-competitor-report.html`), brand palette exploration (`brand-palette.html`), and client asset brief.

## Deployment
- **Branch**: `main` (GitHub Pages source)
- **Pages**: Enabled, serves from root of `main`
- **URL**: https://foxhue.github.io/foxhue/

## Architecture Notes
- All generated files read from `project.json` — CSS prefix is `--foxhue-`
- Review hub uses AJAX form submission via Formsubmit.co (stays on page)
- Contact form submits to Formsubmit.co/hello@foxhue.com
- No external images — all visual placeholders use CSS gradients and decorative elements
- `website/images/` reserved for client-provided assets (currently empty)
- All HTML self-contained with Google Fonts loaded via `<link>`
- Website pages link to shared `styles.css`; variant pages link to `../styles.css`
- Variant pages use inline `<style>` blocks for layout-specific overrides
- Website breakpoints: 992px, 767px, 477px
- CSS-only mobile hamburger (checkbox toggle pattern) — no JavaScript on any page
- JavaScript only in review hub (`variants/index.html`) for form handling and localStorage
