---
trigger: glob
globs: "**/*.css,**/*.scss,**/*.tsx,**/*.jsx,**/*.vue,**/*.svelte"
description: "Use design tokens for colour, spacing, type and radius instead of one-off values."
---

# Design tokens

When writing styles or component markup:

- Take colour, spacing, radius, font size, shadow and z-index from the project's tokens (CSS custom properties or theme config). Do not add raw hex values or arbitrary pixel sizes in components.
- If a needed value does not exist, add a token in the token file and use it, rather than inlining a one-off.
- Name tokens by role (`--color-text-muted`, `--space-4`), not by appearance (`--light-grey`).
- Build dark mode and theming by redefining semantic tokens, not by duplicating component styles.
- Reuse existing components and variants before creating new ones. Match their prop names and naming style.
- Keep the type scale and spacing scale consistent; do not introduce a new size to fix one layout.
