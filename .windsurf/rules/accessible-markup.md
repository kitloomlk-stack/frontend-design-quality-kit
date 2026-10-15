---
trigger: glob
globs: "**/*.tsx,**/*.jsx,**/*.vue,**/*.svelte,**/*.html"
description: "Semantic HTML, keyboard access, visible focus and labelled controls in UI code."
---

# Accessible markup

When writing or editing UI code:

- Use native elements first: `button` for actions, `a` with a real `href` for navigation, `label` tied to each input, `ul`/`ol` for lists, landmarks (`header`, `nav`, `main`, `footer`).
- Do not put click handlers on `div` or `span`. If unavoidable, add role, tabindex, and key handlers, and explain why.
- Never use `href="#"` or buttons that do nothing.
- Every image has `alt`: descriptive when it carries meaning, empty when decorative.
- Keep a visible focus style. Never `outline: none` without an equivalent replacement.
- Heading levels follow document structure, one `h1` per page.
- Do not rely on colour alone; keep text contrast at 4.5:1 or better.
- Dialogs, menus and popovers manage focus: move in on open, return on close, close on Escape.
- Form errors are linked to their fields (`aria-describedby`) and announced.
- Add ARIA only to fill gaps native HTML cannot; do not override native roles.
