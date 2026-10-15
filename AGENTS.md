# Frontend Design & Quality Kit

This kit sets up an agent for frontend work where the result must look deliberate, work for
everyone, and load and respond fast. It covers UI and UX direction, accessibility (WCAG 2.2),
web performance (Core Web Vitals, Lighthouse-style audits), animation, and design-system
tokens. Quality is checked, not assumed: measure, change one thing, measure again.

## Working agreement

- Read the existing code and styles first. Match the project's framework, component patterns,
  CSS approach and naming. Do not introduce a second styling system or UI library.
- Ask before adding a dependency. Prefer the platform (CSS, HTML, native elements) over a
  package when it does the job.
- Keep changes small and reviewable. Do not redesign what you were not asked to redesign.
- Do not install global packages, push, or deploy. Run local dev, lint, type-check and test
  commands that the project already defines.
- If a design decision is subjective, state the choice and the reason in one sentence so the
  user can overrule it.

## Design direction

- Start from the content and the user's task, then choose type, spacing, colour and layout to
  serve it. Avoid default-looking output: identical card grids, purple-blue gradients,
  centred hero plus three feature boxes, lorem ipsum, stock placeholder copy.
- Pick one type scale and one spacing scale and stick to them. Limit the palette: a neutral
  ramp, one accent, and semantic colours for success, warning and error.
- Establish hierarchy with size, weight and space before adding borders, shadows or colour.
- Design every state: empty, loading, error, disabled, hover, focus, active and long-content.
- Design mobile first; verify at roughly 360, 768 and 1280 px widths.
- Write real microcopy. Buttons say what they do; errors say what to do next.

## Design system and tokens

- Colour, spacing, radius, type size, shadow and z-index come from tokens (CSS custom
  properties or the project's theme file). Do not hard-code one-off hex values or pixel sizes
  in components.
- Layer tokens: primitive values, then semantic names (`--color-text-muted`), then component
  tokens only where needed.
- Support dark mode through semantic tokens, not duplicated components.
- Build components with a small, consistent prop API; document variants next to the component.

## Accessibility

- Use semantic elements first (`button`, `a`, `nav`, `main`, `label`, `ul`). Add ARIA only
  when no native element fits, and never contradict native semantics.
- Everything operable by mouse is operable by keyboard, in a logical tab order, with a
  visible focus indicator that has at least 3:1 contrast.
- Text contrast is at least 4.5:1 (3:1 for large text and UI boundaries). Do not use colour
  as the only signal.
- Every input has a programmatic label; every image has meaningful `alt` text or empty `alt`
  if decorative; dialogs trap and restore focus; live updates use appropriate live regions.
- Touch targets are at least 24x24 CSS px (aim for 44).
- Respect `prefers-reduced-motion` and zoom/text-resize up to 200% without loss of content.

## Performance

- Targets (75th percentile, field data): LCP at most 2.5 s, INP at most 200 ms, CLS at most
  0.1. Say when you only have lab data.
- Reserve space for images, embeds and late content (width/height or aspect-ratio) to
  prevent layout shift. Lazy-load below-the-fold images; do not lazy-load the LCP image.
- Ship less JavaScript: split by route, defer non-critical scripts, avoid large libraries for
  small jobs, and do not hydrate what is static.
- Optimise fonts (subset, `font-display`, preload only the critical file) and images
  (modern formats, responsive `srcset`, correct dimensions).
- Break up long tasks; keep event handlers cheap; debounce expensive input work.

## Animation

- Animate `transform` and `opacity`; avoid animating layout properties (`width`, `top`,
  `margin`). Use `will-change` sparingly and remove it after use.
- Motion has a purpose: orient, give feedback, or show a relationship. Durations around
  150-300 ms for UI, longer only for deliberate storytelling.
- Always provide a reduced-motion path (disable or replace with a fade).
- With GSAP, clean up on unmount (context or the framework's hook), batch scroll work, and
  kill what you create.

## Verifying in a browser

- Run the app and look at it at the three widths above. Check keyboard-only use, zoom, and
  dark mode if supported.
- Use DevTools or the project's Lighthouse tooling to capture a baseline before performance
  changes and a result after. Record the numbers in your reply.
- Check the console for errors and the network panel for oversized or blocking requests.

## Before you finish

1. Run the project's lint, type-check and tests; report failures honestly.
2. Re-check the three widths, keyboard path and focus states for what you changed.
3. Summarise: what changed, what you measured (before and after), and what remains.

## Skills in this kit

- `design-taste-frontend` — art direction for new pages and apps that avoids generic output.
- `redesign-existing-projects` — upgrade an existing UI without breaking behaviour.
- `frontend-ui-engineering` — build responsive, accessible production components and layouts.
- `design-system` — design tokens, scales and component specifications.
- `accessibility` — WCAG 2.2 audit and fixes.
- `screen-reader-testing` — verify with VoiceOver, NVDA or JAWS.
- `core-web-vitals` — improve LCP, INP and CLS.
- `web-quality-audit` — whole-page quality audit across performance, accessibility, SEO.
- `gsap-core` — GSAP tweens, easing, responsive and reduced-motion handling.
- `gsap-performance` — keep animation smooth and cheap.
- `browser-testing-with-devtools` — inspect and profile pages in a real browser.

## Commands

- `/ui-review` — prioritised design, accessibility and responsive review.
- `/vitals-pass` — measure and fix the biggest Core Web Vitals problems.
- `/a11y-pass` — audit against WCAG 2.2 and fix issues.

## Sub-agents

- `a11y-auditor` — read-only accessibility audit of markup and components.
- `perf-investigator` — finds likely causes of slow load, layout shift or slow interaction.

## Scoped rules

Agents that support scoped rules load these automatically. If yours does not, read the matching file before editing files it covers:

- `.agents/rules/accessible-markup.md` — for `**/*.tsx`, `**/*.jsx`, `**/*.vue`, `**/*.svelte`, `**/*.html`: Semantic HTML, keyboard access, visible focus and labelled controls in UI code.
- `.agents/rules/motion-and-performance.md` — for `**/*.css`, `**/*.scss`, `**/*.tsx`, `**/*.jsx`, `**/*.ts`, `**/*.js`: Animate compositor-friendly properties, honour reduced motion, and protect Core Web Vitals.
- `.agents/rules/design-tokens.md` — for `**/*.css`, `**/*.scss`, `**/*.tsx`, `**/*.jsx`, `**/*.vue`, `**/*.svelte`: Use design tokens for colour, spacing, type and radius instead of one-off values.
