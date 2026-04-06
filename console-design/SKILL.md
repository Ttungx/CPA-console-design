---
name: console-design
description: "Extract and reproduce the CLI Proxy API Management Center design language as a lightweight desktop light-theme console. Use whenever generating or restyling a dashboard, admin panel, control center, settings UI, analytics page, data console, or internal tool that should inherit this repository's warm neutral management-console language instead of a generic SaaS template. Apply this skill even when the user only says build a dashboard, redesign this admin page, make a console, or create a management UI."
---

# Console Design

## Purpose

Use this skill to recreate the reference project's design language at the system level.

The target is:

- desktop first
- light theme only
- warm neutral management console
- lightweight implementation

This skill is not for:

- dark mode reproduction
- mobile-first redesign
- generic marketing pages
- heavy UI-library admin clones

## Scope lock

Treat these constraints as part of the design language, not as optional implementation choices:

- Reproduce only the desktop light-theme output.
- Do not spend effort on dark mode parity.
- Do not spend effort on mobile parity unless the user explicitly asks for it.
- Prefer native HTML/CSS plus a small amount of JavaScript.
- If a framework is needed, prefer lightweight React or Vue without a component library.
- Keep dependencies minimal and explainable.

## Required reading order

Before writing UI code, read these files in order:

1. [references/design-language.md](./references/design-language.md)
2. [references/page-recipes.md](./references/page-recipes.md)
3. [references/component-recipes.md](./references/component-recipes.md)

Reuse [assets/console-base.css](./assets/console-base.css) when building a standalone implementation.

## Working method

1. Identify the page archetype first.
   Choose the closest desktop page pattern from `page-recipes.md`.
2. Establish the token layer before component CSS.
   Define colors, spacing, radii, borders, and shadows before styling any feature.
3. Build the shell before the content cards.
   The reference project is shell-driven, not card-driven.
4. Apply one shared component language.
   Buttons, cards, nav, tables, badges, and inputs must share the same structural rules.
5. Add explicit interaction states.
   Hover, focus, active, disabled, loading, and selection states must be deliberate.
6. Keep implementation light.
   Avoid heavy frameworks, large UI kits, and decorative dependency chains.

## Hard constraints

- Use the warm neutral light-theme token set from `design-language.md`.
- Keep the app shell explicit: top bar, sidebar, content column, optional floating action bar.
- Use borders as the primary structure signal.
- Use `4px`, `8px`, `12px`, and pill radii only.
- Use the spacing scale `4px`, `8px`, `16px`, `24px`, `32px`, `48px`.
- Keep animations under `200ms` for ordinary state changes.
- Use dense, operational layouts suitable for a management console.
- Prefer CSS variables or one small token file instead of scattered literal values.

## What to avoid

Reject these outcomes immediately:

- generic Tailwind or Bootstrap dashboard styling
- oversized hero-first SaaS landing layouts
- shallow color copying without shell structure
- random spacing and radius values
- inconsistent button patterns across one screen
- decorative glassmorphism as the dominant visual language
- deep dependency trees for simple UI work
- Ant Design, Element Plus, MUI, Chakra, shadcn bundles, or similar heavy component stacks

## Output expectation

When using this skill, generate code that already contains:

- the desktop light-theme token system
- the shell and layout rules
- the component state rules
- the interaction rules
- the lightweight implementation discipline
- the anti-pattern avoidance baked into the markup and CSS
