# TestBootstrap

A small, local‑asset Bootstrap site scaffold with a unified design system, multiple pages, a searchable docs section, and consistent components (navbar, hero, CTA, footer).

## Highlights

- Local assets: `css/bootstrap.css`, `js/bootstrap.bundle.js`, `css/theme.css` (no CDN for core UI)
- Shared UI: navbar, hero, global CTA, and full footer across all pages
- Pages: Home, About, Services, Pricing, Docs, Contact
- Searchable Docs: client‑side search (Fuse.js) with sidebar, tags, and markdown rendering
- Design system: custom tokens/utilities in `theme.css` + timeline and docs styles
- Accessible defaults: semantic markup, buttons/links with clear labels, responsive layout

## Pages

- `index.html` — Landing page with hero, 3 feature cards linking to key pages
- `about.html` — Team page with values, team grid, ways of working, milestones
- `services.html` — Rich services layout (highlights, deliverables, process timeline, tech stack, FAQs)
- `pricing.html` — Four plans (Starter/Pro/Business/Enterprise), comparison table, FAQs
- `docs.html` — Searchable docs browser (left sidebar + right content)
- `contact.html` — Contact form with Bootstrap client‑side validation

All pages include:
- Navbar: brand “TestBootstrap” + links (Home, About, Services, Pricing, Docs)
- Hero: `.hero-custom-bg` gradient, centered `display-3 fw-bold` heading, subtitle, and two CTAs
- Global CTA: consistent block inviting users to start or contact
- Footer: dark, multi‑column footer with links and a bottom copyright bar

## Design System (`css/theme.css`)

- Tokens
  - `--brand-primary: #0d6efd`
  - `--brand-dark: #0f172a`
- Utilities
  - `.section-pad` — vertical padding helper
  - `.card-soft` — soft rounded card shadow
  - Natural section rhythm: `section + section { margin-top: ... }`
- Hero
  - `.hero-custom-bg` — radial/linear gradient background used on all heroes
- Timeline
  - `.timeline`, `.timeline-steps`, `.timeline-step`, `.circle` — lightweight horizontal process line with numbered points
- Docs styling
  - Sticky sidebar/search, list hover, monospace code blocks

## Docs System

- Data: `data/docs.json` (15 entries across HTML/CSS/JavaScript)
- Search: Fuse.js v6+ (local first `js/vendor/fuse.min.js`, with CDN fallback if not present)
- Fields indexed: `title`, `tags`, `summary`, `body`
- Deep links: preserves `?q=` (query) and `#slug` (article)
- Markdown: minimal renderer for headings, code blocks, paragraphs, and inline code

## Local Development

This is a static site. Any static HTTP server works, e.g.:

```bash
# Python
python -m http.server 15501
# Node (serve)
npx serve . -l 15501
```

Then open `http://localhost:15501/TestBootstrap/index.html`.

## Structure

```
TestBootstrap/
├── about.html
├── contact.html
├── css/
│   ├── bootstrap.css
│   └── theme.css
├── data/
│   └── docs.json
├── docs.html
├── index.html
├── js/
│   ├── bootstrap.bundle.js
│   └── vendor/
│       └── fuse.min.js   # optional (CDN fallback in docs.html)
├── pricing.html
└── services.html
```

## Customization

- Change brand and menu in the shared navbar on each page
- Tune gradients, spacing, or colors in `css/theme.css`
- Extend docs by appending entries to `data/docs.json`
- Replace placeholder team avatars (About) and add real links in the footer columns

## Notes

- If you want fully offline docs search, download Fuse v6 and place it at `js/vendor/fuse.min.js`.
- Buttons/links are intentionally consistent across pages for a cohesive experience.

Enjoy building with TestBootstrap!

