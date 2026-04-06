# Page Recipes

Use these recipes to preserve the reference project's desktop layout behavior.

The key rule is simple: choose a page archetype first, then place components inside it. Do not start from a pile of cards.

## Shared page rules

- Default to desktop light-theme output.
- Keep section gaps at `24px` or `32px`.
- Keep actions close to the surfaces they govern.
- Do not create large empty decorative zones on ordinary tool pages.
- One expressive gesture per page is enough.

## App shell recipe

Use for dashboards, settings, provider management, quota pages, logs, config, and most internal-tool screens.

### Structure

1. Top bar
2. Left sidebar
3. Main content column
4. Optional floating action bar

### Rules

- The shell must be visible and structurally meaningful.
- Sidebar and header must anchor orientation.
- Main content should feel dense but ordered.
- The page should still look functional even if all decorative gradients are removed.

## Standard management page recipe

Use for most CRUD-like or settings-heavy pages.

### Structure

1. Page title and context
2. Compact actions and filters
3. Primary content surface
4. Secondary detail or summary surfaces

### Rules

- Put filters near the data they affect.
- Avoid oversized introductory copy.
- Prefer compact cards, tables, or grouped sections over showcase panels.

## Dashboard recipe

Use when the page summarizes system state or entry actions.

### Structure

1. Restrained hero or summary band
2. Status or stat grid
3. Dense operational sections
4. Secondary summaries or lists

### Rules

- Allow one expressive gesture only: watermark, orb, split layout, or subtle tinted band.
- The hero must support orientation, not dominate the page.
- Lower sections must return to strict utility surfaces.

## Config workspace recipe

Use for code, YAML, advanced settings, or multi-step editing tools.

### Structure

1. Page header
2. Rounded workspace shell
3. Toolbar or search strip
4. Editor or grouped settings body
5. Floating bottom actions

### Rules

- The workspace shell must feel like a tool surface, not a marketing card.
- The editor body should be visually contained.
- Save and reset actions should live in a floating bar when they govern the current workspace.

## Data management recipe

Use for credentials, auth files, archives, logs, item management, or dense records.

### Structure

1. Title plus compact actions
2. Filters, search, or segmented controls
3. Dense rows, cards, or hybrid table surfaces
4. Batch action surface when relevant

### Rules

- Keep metadata compressed with pills, badges, and compact labels.
- Use card grids only when each card contains structured operational data.
- If rows or cards can be selected, selection state must be obvious.

## Analytics recipe

Use for charts, health metrics, and usage reporting.

### Structure

1. Title plus filters
2. Stat grid
3. Chart wrappers
4. Dense detail cards or lists

### Rules

- Stat cards should remain compact and scannable.
- Charts must live inside card wrappers that inherit the shared card system.
- Analytics pages should still feel like admin tooling, not a presentation deck.

## Login recipe

Use only when the page is a true entry point.

### Structure

1. Strong brand wall
2. Quiet form panel

### Rules

- The split layout is intentional.
- The form side must stay calmer and lighter than the brand side.
- Do not import the login split layout into ordinary internal pages.
