# JoorDesignSystem (@joor/design-system@4.2.1)

This design system is the published @joor/design-system React library, bundled as a single
browser global. All 37 components are the real upstream code.

## Where things are

- `_ds_bundle.js` — the whole-DS bundle at the project root; loads every component to `window.JoorDesignSystem`. First line is a `/* @ds-bundle: … */` metadata header.
- `styles.css` — the single stylesheet entry: it `@import`s the tokens, fonts, and component styles (`_ds_bundle.css`). Link this one file.
- `components/<group>/<Name>/<Name>.prompt.md` (example JSX + variants), `<Name>.d.ts` (types), `<Name>.html` (variant grid).
- `tokens/*.css` — CSS custom properties, names verbatim from upstream.
- `fonts/` — `@font-face` files + `fonts.css` (when the package ships fonts).

For a specific component, `read_file("components/<group>/<Name>/<Name>.prompt.md")`.

## Loading

Add these two lines to your page once (React must be on the page first):

```html
<link rel="stylesheet" href="styles.css">
<script src="_ds_bundle.js"></script>
```

Components are then available at `window.JoorDesignSystem.*`. Mount into a dedicated child node (e.g. `<div id="ds-root">`), not the host page's own React root, so the two trees don't collide:

```jsx
const { Breadcrumbs } = window.JoorDesignSystem;
ReactDOM.createRoot(document.getElementById('ds-root')).render(<Breadcrumbs />);
```

## Tokens

112 CSS custom properties from @joor/design-system. Names are
preserved verbatim from upstream. They are declared inside `_ds_bundle.css` (this DS ships one compiled stylesheet rather than separate token files).

- **color** (73): `--color-primary-100`, `--color-primary-200`, `--color-primary-300`, …
- **typography** (32): `--font-family-alpha`, `--font-family-numeric`, `--font-weight-light`, …
- **radius** (3): `--size-border-radius-small`, `--size-border-radius-medium`, `--size-border-radius-large`
- **shadow** (4): `--elevation-2`, `--elevation-4`, `--elevation-8`, …

## Components

### design-system
- `Breadcrumbs`
- `Button`
- `Card`
- `Checkbox`
- `ChickenNuggets`
- `Collapsible`
- `CollapsibleHeader`
- `Divider`
- `Drawer` (compound: `Drawer.Header`, `Drawer.Footer`, `Drawer.Content`, `Drawer.Wrapper`, `Drawer.PageWrapper`)
- `Dropdown`
- `EditableLabel`
- `EmptyPlaceholder`
- `GammaBadge`
- `Icon`
- `IconLabelToggle`
- `ImageCarousel`
- `LegacyModal` (compound: `LegacyModal.Title`, `LegacyModal.Content`, `LegacyModal.Actions`, `LegacyModal.CloseButton`)
- `Menu`
- `Modal` (compound: `Modal.Content`, `Modal.Actions`, `Modal.CloseButton`)
- `MultiValueTextField`
- `Pagination`
- `PrimaryPill`
- `RadioButton`
- `Search`
- `SingleDatePicker`
- `Spinner`
- `SubNavbar`
- `Swatch`
- `Switch`
- `TabularMenu`
- `Text`
- `TextArea`
- `TextField`
- `TextWithLabel`
- `Tooltip`

### data-visualization
- `RadialWheel`

### notification
- `SuccessToast`
