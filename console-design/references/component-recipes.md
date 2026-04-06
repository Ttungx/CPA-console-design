# Component Recipes

Use these recipes to keep the desktop light-theme console coherent.

Each component definition includes structure, required states, and forbidden behavior. Treat the forbidden items as hard constraints.

## Button

### Structure

- `inline-flex`
- center aligned
- min height `40px`
- horizontal padding around `14px`
- radius `8px`
- explicit 1px border on every variant
- font weight `600`

### Variants

- Primary: `--primary-color` background and border, white text
- Secondary: `--bg-tertiary` background, `--border-color` border, primary text
- Ghost: transparent background, transparent border, secondary text
- Danger: `--error-color` background and border, white text

### States

- Hover required
- Focus required
- Active optional but recommended for primary and segmented contexts
- Disabled required
- Loading required for async actions

### Forbidden

- no gradient primary buttons
- no borderless primary actions
- no multiple button heights in one toolbar
- no icon-only buttons without a visible hover and focus state

## Card

### Structure

- background `--bg-primary`
- 1px border `--border-color`
- radius `12px`
- shadow `--shadow`
- padding `16px` or `24px`
- optional header row with title and actions

### States

- Static cards do not need hover
- Interactive cards may shift by `1px` to `2px` on hover
- Interactive cards may brighten border slightly on hover

### Forbidden

- no heavy shadow as primary depth cue
- no 16px or 20px decorative radii on ordinary cards
- no mixing tinted, outlined, and flat card idioms without hierarchy

## Table

### Structure

- wrapped in a card or card-like panel
- compact header row
- dense rows with clear vertical rhythm
- 1px separators or clear row boundaries
- technical fields may use monospace

### States

- Row hover required when rows are interactive
- Selected row state required when selection exists
- Empty state required
- Loading state required when async data is being fetched

### Forbidden

- no giant card grids used as fake tables unless density remains equivalent
- no weak-contrast rows where hover cannot be seen
- no inconsistent column alignment

## Sidebar

### Structure

- fixed or sticky left rail
- width around `240px`
- surface uses `--bg-primary`
- right border required
- top section should include product or page-context block, not only menu items
- nav items arranged in a vertical stack
- each nav item includes text plus a compact icon container
- icon container target: about `28px` square, bordered, slightly tinted, visually centered
- nav item text target: `14px`, medium or semibold
- bottom section should usually include one compact environment, version, or status cue

### States

- Default state must be quiet
- Hover must add subtle fill or border tint
- Active must use primary-tinted emphasis
- Active item should strengthen both the row and the icon container, not only the text color
- Current location must be scannable without reading every label

### Forbidden

- no decorative gradient sidebar
- no oversized iconography competing with content
- no flat text list with no active-state treatment
- no tiny monochrome icons floating without their own container

## Navbar / Top Bar

### Structure

- top-aligned control strip
- height around `64px`
- bottom border required
- used for page context, mode switches, connection state, or global actions
- controls must share the same button language as the rest of the UI
- page title should usually feel one step larger and firmer than card titles

### States

- Interactive controls require hover and focus
- Sticky behavior is preferred on desktop shell pages
- Action groups must preserve consistent heights and spacing

### Forbidden

- no promotional hero copy inside the navbar
- no decorative chrome that competes with page content
- no mixture of unrelated control styles

## Input

### Structure

- background `--bg-secondary`
- 1px border `--border-color`
- radius `8px`
- padding about `10px 12px`
- text color `--text-primary`
- desktop input text should not drop below `14px`

### States

- Focus required with primary border plus soft ring
- Disabled required
- Error required when validation fails
- Hover optional

### Forbidden

- no underlined-only input treatment
- no floating-label pattern unless the whole form uses it consistently
- no mismatched input heights in one form block

## Pill / Badge

### Structure

- radius full pill
- min height around `28px`
- horizontal padding `8px` to `10px`
- weight `600`
- border visible

### Usage

- neutral pills for metadata
- primary-tinted pills for selection or active compact state
- semantic pills for success, failure, or warning
- primary-tinted pills should feel more saturated than passive neutral metadata pills

### Forbidden

- no large decorative chips that behave like cards
- no saturated semantic colors used everywhere

## Floating Action Bar

### Structure

- fixed bottom center
- full-pill radius
- translucent light surface
- visible border
- compact internal spacing
- uses `--floating-shadow`

### States

- primary and ghost actions must preserve shared button language
- hover required on each child action
- disabled required when actions are unavailable

### Forbidden

- no full-width sticky footer bar unless the layout explicitly demands it
- no dense text blocks inside the floating bar
- no heavy glassmorphism effect dominating the page
