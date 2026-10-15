---
name: ui-review
description: "Review a page or component for design quality, accessibility and responsiveness, with prioritised findings."
disable-model-invocation: true
---

# ui-review

When invoked, review the page or component the user names for design quality, accessibility and responsiveness.

1. Identify the target (route, file or component). If none is given, ask.
2. Read the code and styles. If a dev server is already running or the project has a documented dev command, view the result at about 360, 768 and 1280 px widths; check keyboard-only use and zoom.
3. Evaluate: visual hierarchy, type and spacing consistency, token usage, states (empty, loading, error, focus, disabled), copy quality, responsive behaviour, colour contrast, semantics and keyboard access.
4. Report findings as a prioritised list: blocker, should fix, nice to have. For each, give the location (file and line), what is wrong, and a concrete fix.
5. Do not change code unless the user asks. Offer to apply the blocker fixes.
6. End with the three changes that would improve the result the most.
