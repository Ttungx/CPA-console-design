# Design Language

This file defines the reference project's stable desktop light-theme design language as executable rules.

The goal is not to copy a screenshot. The goal is to preserve the reference project's control-surface logic so a new page still feels like the same product.

## 1. Design Principles

### Principle 1: Console first, not showcase first

- Start from an application shell, not from isolated cards.
- The page must read like a management console used for configuration, monitoring, or operations.
- Prioritize orientation, status, actions, and dense content over visual spectacle.

### Principle 2: Warm neutral utility, not cold SaaS blue

- Use warm grays, paper-like backgrounds, and a muted taupe primary accent.
- The primary color is an action color, not a decoration color.
- Do not replace the accent with generic enterprise blue or saturated gradients.
- Keep the palette warm but not washed out.
- Active and highlighted states must feel fuller and more deliberate than the neutral resting surfaces.

### Principle 3: Borders carry structure

- Use 1px borders to separate surfaces, define controls, and anchor hierarchy.
- Shadows are secondary and must stay light.
- If a component has both a strong border and a strong shadow, reduce one of them.

### Principle 4: Density with discipline

- Information density should be medium-high.
- Preserve readability with a strict spacing scale and clear title-to-body hierarchy.
- Do not create airy marketing spacing or giant empty hero bands on ordinary admin pages.

### Principle 5: One component language

- Buttons, cards, nav items, inputs, pills, tables, and floating actions must feel related.
- Reuse the same radius, spacing, border treatment, hover treatment, and text hierarchy.
- Do not let one screen mix multiple component dialects.

### Principle 6: Lightweight implementation is part of the design

- The reference project feels handcrafted and direct.
- Favor native HTML and CSS, or a thin React/Vue layer.
- Do not rely on heavy UI frameworks to approximate the look.

## 2. Design Tokens

### Color tokens

Use this desktop light-theme token set as the default:

```css
:root {
  --bg-secondary: #f6f2ea;
  --bg-primary: #ece4d8;
  --bg-tertiary: #ddd1c0;
  --bg-hover: var(--bg-tertiary);
  --bg-quinary: #f3ece2;
  --bg-error-light: rgba(198, 87, 70, 0.1);

  --floating-surface: #fffaf2;
  --floating-border: #cfc0ad;
  --floating-shadow: 0 14px 28px rgba(62, 44, 23, 0.16);

  --text-primary: #2f2923;
  --text-secondary: #665b4f;
  --text-tertiary: #8f8172;
  --text-quaternary: #b4a798;
  --text-muted: var(--text-tertiary);

  --border-color: #d8ccbd;
  --border-secondary: var(--border-color);
  --border-primary: #cab9a4;
  --border-hover: #bfa98f;

  --primary-color: #8f7557;
  --primary-hover: #7d654b;
  --primary-active: #6b573f;
  --primary-contrast: #ffffff;

  --success-color: #10b981;
  --warning-color: #c65746;
  --error-color: #c65746;
  --info-color: var(--primary-color);

  --warning-bg: rgba(198, 87, 70, 0.12);
  --warning-border: rgba(198, 87, 70, 0.35);
  --warning-text: var(--warning-color);

  --success-badge-bg: #d1fae5;
  --success-badge-text: #065f46;
  --success-badge-border: #6ee7b7;

  --failure-badge-bg: rgba(198, 87, 70, 0.14);
  --failure-badge-text: #8a3a30;
  --failure-badge-border: rgba(198, 87, 70, 0.35);

  --shadow: 0 1px 2px 0 rgb(45 31 15 / 0.08);
  --shadow-lg: 0 12px 22px -6px rgb(45 31 15 / 0.14);
}
```

### Color usage rules

- Use `--bg-secondary` for the page background.
- Use `--bg-primary` for cards, panels, headers, and sidebar surfaces.
- Use `--bg-tertiary` only for hover states, compact nested surfaces, segmented controls, and subtle grouping.
- Use `--primary-color` only for primary actions, active selection, focused controls, and compact emphasis.
- Active nav items, segmented controls, and selected pills should use a clearer primary tint than neutral hover surfaces.
- Sidebar icon containers should use a stronger tint-and-border treatment than ordinary text-only nav.
- Use semantic colors only for status, alerts, badges, progress, and exceptional states.
- Do not use warning or success colors as decorative layout accents.

### Spacing system

Use only:

- `4px`
- `8px`
- `16px`
- `24px`
- `32px`
- `48px`

Rules:

- Intra-component spacing: `4px` or `8px`
- Control padding and compact grouping: `8px` or `16px`
- Card padding: `16px` or `24px`
- Page section gaps: `24px` or `32px`
- Do not introduce one-off layout values such as `10px`, `14px`, `18px`, `20px`, `22px`, or `30px` for ordinary structure.

### Radius system

Use only:

- `4px` for tiny internal details
- `8px` for controls and compact containers
- `12px` for cards and major surfaces
- `9999px` for pills, badges, segmented rails, and floating bars

Rules:

- Buttons and inputs must use `8px`.
- Cards and summary panels must use `12px`.
- Do not mix `8px`, `12px`, `16px`, and `24px` randomly across the same component family.

### Shadow system

Use only:

- `--shadow` for ordinary cards and shells
- `--shadow-lg` for elevated hero or modal surfaces
- `--floating-shadow` for menus and floating bottom bars

Rules:

- Keep shadows soft and subordinate to borders.
- Do not use strong blur-heavy shadows as the main depth model.
- Do not combine heavy shadows with saturated gradients on ordinary admin components.

### Typography rules

- Use a system sans stack for all UI text.
- Use monospace only for technical identifiers, file names, endpoints, IDs, YAML, logs, and code-like data.
- Eyebrows must be uppercase, `12px`, bold, and positively tracked.
- Desktop body text should default closer to `14px` or `15px`, not `12px` or `13px`.
- Sidebar nav labels should default to `14px` with medium or semibold weight.
- Card titles and section titles should stay in the `17px` to `18px` range.
- Desktop page titles should stay in the `24px` to `28px` range on normal pages.
- Hero titles may grow larger, but only on pages that genuinely need a hero.

## 3. Layout System

### Core shell

Default desktop shell:

- top bar
- left sidebar
- scrollable content column
- optional floating bottom action bar

Rules:

- Header height target: `64px`
- Sidebar width target: `240px`
- Content padding: `24px`
- Content width should remain readable; do not stretch everything edge to edge unless the data density requires it.
- The shell must exist before internal cards are designed.

### Layout discipline

- Use grid for structured stats, card groups, detail grids, and dashboard summaries.
- Use flex for nav rows, toolbars, button rows, metadata rows, and compact action groups.
- Use `gap`, not ad hoc sibling margins, as the default spacing tool.
- Add `min-width: 0` to flexible children that can overflow.
- Keep sections visually grouped by shell and spacing, not by arbitrary background changes.

### Page archetypes

#### Standard management page

- Page title and context at the top
- Controls close to the controlled data
- Dense content surfaces below

#### Dashboard page

- One restrained hero or summary band first
- Stat or status layer second
- Dense operational content after that

#### Config or editor page

- Header and workspace shell first
- Editor or grouped settings body second
- Floating action bar for save and reset actions when needed

#### Data page

- Compact filters and actions near the top
- Dense rows, tables, or compact cards below
- Batch actions must feel attached to the selection state

## 4. Interaction Rules

- Every clickable control must have a hover state.
- Every focusable control must have a visible focus treatment.
- Every async primary action must expose a loading state.
- Every stateful row, card, or nav item must distinguish default, hover, and active states.
- Ordinary transitions must stay at `150ms` to `180ms`.
- Longer animation is reserved for page transition or one hero entrance only.
- Motion must clarify state change, not decorate otherwise flat hierarchy.

## 5. Failure Modes To Avoid

These patterns are the main reasons a reproduction drifts away from the reference project:

### Failure mode 1: Copying color, missing structure

- Warm neutrals alone do not recreate the design language.
- If the shell is weak, the result will look like a themed mockup instead of a console.
- If the palette is too pale and every surface sits in the same value range, the interface loses operational confidence.

### Failure mode 2: Copying cards, missing page archetype

- Repeating 12px cards is not enough.
- The original project changes composition by page type while staying inside one system.

### Failure mode 3: Copying components, missing state logic

- A page without clear hover, focus, active, loading, and selected states will feel unfinished even if it uses the right colors.
- The sidebar especially fails if active state, icon container, and text hierarchy are too weak.

### Failure mode 4: Over-designing the hero

- The original project allows a restrained expressive gesture.
- If the hero becomes dominant, the page stops reading like a management tool.

### Failure mode 5: Adding heavy framework defaults

- UI libraries pull in spacing, radii, shadows, and interaction patterns that conflict with the reference system.
- The result often becomes visually inconsistent even after token overrides.

## 6. Anti-Patterns

Avoid these directly:

- random paddings and radii inside one page
- generic blue buttons replacing the taupe primary
- over-pale beige surfaces with insufficient contrast between page, sidebar, and card
- large empty marketing-style hero sections
- card-only layouts with no recognizable shell
- tables replaced by oversized cards without a density reason
- undersized desktop typography that makes the console feel toy-like
- lack of hover and active states on nav and action controls
- text-only sidebar items with no icon container or weak active marker
- repeated decorative gradients on many surfaces
- mixed button heights in one toolbar
- mixing borderless ghost controls with fully filled controls without hierarchy
- bringing in Ant Design, Element Plus, MUI, Chakra, shadcn bundles, or similar heavy stacks for simple internal-tool screens

## 7. Implementation Guide

- Preferred stack: HTML + CSS + minimal JavaScript.
- Acceptable stack: lightweight React or Vue with local components.
- Keep dependencies minimal, auditable, and easy to remove.
- Do not introduce a UI library just to get buttons, cards, forms, tables, or modals.
- Abstract tokens first with CSS variables or one small token file.
- Build primitives locally: button, input, card, table, sidebar, top bar, modal, badge.
- Reuse the same primitives across the screen instead of styling each feature independently.
