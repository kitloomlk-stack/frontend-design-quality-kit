---
description: "Audit a page or component against WCAG 2.2 and fix the issues found."
---

# a11y-pass

When invoked, audit the page or component the user names against WCAG 2.2 (level AA) and fix the issues found.

1. Identify the target. Read its markup, styles and scripts.
2. Check: semantic structure and headings, landmarks, names and labels for every control, keyboard access and tab order, visible focus, colour contrast, alt text, form errors and instructions, dialog and menu focus handling, motion and reduced-motion, and target size.
3. If the project already has an accessibility linter or test command, run it and include the results. If a browser is available, also test with keyboard only.
4. Fix issues that are clear and local, in the smallest change. For anything that needs a design decision, list it instead of guessing.
5. Recommend screen reader testing for dialogs, menus, live regions and complex widgets, and say which to test.
6. Report: issues fixed (with file and line), issues left for the user, and how you verified each.
