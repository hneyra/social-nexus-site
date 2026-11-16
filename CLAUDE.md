# CLAUDE.md

## Project overview

Static website for Social Nexus E.I.R.L. (Peruvian company offering integrated services for the mining
exploration phase, with a social-management focus). Content is in Spanish. Published with GitHub Pages.

## Layout

- `site/` — everything that is published. `index.html` + `style.css` is the production design
  (proposal A); `v2/` (B, editorial) and `v3/` (C, dark technical) are full alternative proposals;
  `comparar/` compares A/B/C; `v1/` archives the first version of A. All but the root are noindex.
- `site/assets/fonts/` — self-hosted Archivo + Public Sans (woff2, latin subset).
- `site/assets/icons.svg` — shared SVG sprite; `site/assets/img/` — images (webp).
- `.github/workflows/pages.yml` — uploads `site/` and deploys to GitHub Pages on push to `main`.

## Rules

- No build step, bundler, npm or JS framework in `site/` — plain static files only.
- Scripts stay vanilla and inline at the bottom of each `index.html`.
- Theme colors are CSS custom properties at the top of each `style.css`
  (brand: blue `#36538A`; logo accents red `#E2231A`, orange `#F39200`, yellow `#FFC20E`, green `#4BA82E`).
  In the main design the logo accents are only a brand signature; gold `--gold` is the action color.
- Do not invent business facts (clients, figures, certifications, years) in site copy.
- Use relative paths only (the site is served under `/social-nexus-site/`).
- The contact forms have no backend: they open WhatsApp (`wa.me/51943250843`) with the message pre-filled.
