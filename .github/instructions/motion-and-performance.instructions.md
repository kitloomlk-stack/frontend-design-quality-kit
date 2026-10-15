---
applyTo: "**/*.css,**/*.scss,**/*.tsx,**/*.jsx,**/*.ts,**/*.js"
description: "Animate compositor-friendly properties, honour reduced motion, and protect Core Web Vitals."
---

# Motion and performance

When adding animation or touching load-critical code:

- Animate `transform` and `opacity`. Do not animate `width`, `height`, `top`, `left` or `margin`.
- Wrap non-essential motion in `prefers-reduced-motion` handling; provide a static or fade-only fallback.
- Use `will-change` only on elements about to animate and remove it afterwards.
- Clean up timelines, observers and listeners on unmount; never leave them running off-screen.
- Give images, video and embeds explicit dimensions or an `aspect-ratio` to prevent layout shift.
- Do not lazy-load the above-the-fold or LCP image. Lazy-load the rest.
- Keep event handlers short; move heavy work off the interaction path (defer, chunk, or use a worker).
- Do not add a large dependency for a small feature; check bundle impact before importing.
- Load fonts with `font-display` and preload only the file needed for first paint.
