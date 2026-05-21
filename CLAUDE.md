# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

ERK Consult marketing website — a static HTML site for an IT recruitment firm. No frameworks, no build tools, no package manager.

## Development

```bash
# Local dev server
python3 -m http.server 8765

# No build, lint, or test commands — pure static HTML/CSS/JS
```

## Architecture

- **index.html** — Single-page marketing site with scroll-to-section navigation (sections: #home, #about, #stats, #services, #why, #tech, #contact)
- **privacy.html** — GDPR privacy policy page with identical styling
- **robots.txt / sitemap.xml** — SEO configuration (production domain: www.erkconsult.com)

All CSS is embedded in `<style>` within each HTML file's `<head>`. All JS is a small inline `<script>` block at the end of `<body>`.

## Design System (CSS Variables)

Key tokens defined in `:root`:
- Colors: `--navy` (#0a1f3d), `--gold` (#c9a961), `--cream` (#f5f1ea)
- Fonts: `--font-sans` (Inter Tight), `--font-serif` (Source Serif 4), `--font-mono` (JetBrains Mono) — loaded from Google Fonts
- Layout: `--max-width` (1200px), `--section-pad` (112px, responsive)
- Breakpoints: 1024px, 768px, 480px

## Key Conventions

- Styles are duplicated between index.html and privacy.html — changes to shared styles (header, footer, CSS variables) must be applied to both files
- Responsive design uses CSS Grid with media queries at the three breakpoints above
- Semantic HTML with ARIA labels for accessibility
- No external CSS or JS files — everything is inline
