# Frontend Redesign

The repository does not currently contain a standalone web app. The public frontend is the GitHub README, generated bitmap hero/infographic assets, and SVG support diagrams.

## v5.4.2 Design Goals

- Lead with a real cinematic production-control hero instead of generic abstract graphics.
- Show Seedance's practical range: references, first/last-frame continuity, product reveal, timeline control, audio, and camera direction.
- Use generated cinematic infographics for both the operating-system overview and skill map.
- Keep bitmap assets text-free so GitHub renders all important content as searchable Markdown.
- Keep SVG assets as support diagrams, not the primary emotional surface.
- Validate README completeness and asset presence with `scripts/design_audit.py`.

## v5.2 Design Goals

- Replace collapsed one-line Markdown with readable sections.
- Put the workflow selector near the top.
- Use dark/light hero assets with accessible SVG metadata.
- Show the skill constellation visually, then provide tables for navigation.
- Keep platform status source-aware instead of hardcoding stale claims.
- Validate design quality with `scripts/design_audit.py`.

## Assets

- `assets/hero-cinematic.png`
- `assets/skill-os-infographic.png`
- `assets/skill-map-cinematic.png`
- `assets/hero-dark.svg`
- `assets/hero-light.svg`
- `assets/skill-map.svg`

## Design Rules

- No external fonts or scripts in SVG.
- Every SVG needs `<title>` and `<desc>`.
- README should stay readable on mobile and dark mode.
- Avoid dense badge walls and noisy decorative text.
- Keep generated bitmap hero assets text-free; render all product/project text as real Markdown.
- Keep the infographic text-light; README prose should explain the lanes with accessible Markdown.
