# Frontend Design System

This repository has no application frontend. The user-facing frontend is the GitHub README, generated bitmap assets, and SVG support assets.

## Design goals

- Clean, cinematic, high-contrast presentation.
- No collapsed Markdown.
- No overloaded neon copy.
- Usable on GitHub mobile and dark mode.
- Clear start-here decision path.
- Validation commands visible above the fold after the skill map.

## Asset rules

- Use SVG for simple structural support diagrams.
- Use generated bitmap images for the README hero, operating-system infographic, and skill-map infographic when the asset needs cinematic texture, real scene depth, or visual storytelling.
- Bitmap hero/infographic/map assets should be text-free or nearly text-free, logo-free, and readable at GitHub README width.
- SVG assets must include `<title>` and `<desc>`.
- No external scripts, images, fonts, or tracking in SVG assets.
- Avoid generic lens dashboards, dense decorative noise, and unreadable micro labels.

## README rules

- No line longer than 500 characters.
- Tables should have real newlines.
- Every major section should answer a user decision: what is it, where do I start, what skills exist, how do I validate, what changed.
- Bitmap hero art should contain no embedded text, logos, or watermarks; keep real project text in Markdown for accessibility.
