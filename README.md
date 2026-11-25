# nojs-ui

Interactive UI components with **zero JavaScript**. One stylesheet, no build step.

Modal, drawer, dropdown menu, tooltip, tabs and accordion, built only from native HTML and modern CSS:
Popover API, `<dialog>`, `<details name>`, `:has()`, CSS anchor positioning, `@starting-style`, `light-dark()`.

**Live demo:** https://bzprince.github.io/Nojs-ui/

## Install

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/YOUR_USERNAME/nojs-ui@main/css/nojs-ui.css">
```

Or copy `css/nojs-ui.css` into your project. That's the whole library.

## Components

| Component | Markup | Powered by |
|-----------|--------|-----------|
| Modal | `<dialog class="nj-modal" popover>` | Popover API |
| Drawer | `<div class="nj-drawer" popover>` | Popover API |
| Dropdown menu | `<div class="nj-menu" popover>` | Popover API + anchor positioning |
| Tooltip | `<button data-tip="Text">` | `attr()` in `::after` |
| Tabs | `<div class="nj-tabs">` with radio labels | `:has(:checked)` |
| Accordion | `<div class="nj-accordion"><details name="x">` | exclusive `<details>` |

Open `index.html` for copy-paste snippets of each.

## Theming

Override tokens anywhere:

```css
:root {
  --nj-accent: oklch(60% 0.2 150);
  --nj-radius: 4px;
}
```

Dark mode follows the system setting automatically. All styles live in `@layer nj.*`, so your own CSS wins without `!important`.

## Browser support

Popover, `:has()` and `light-dark()` work in current browsers. Two features are progressive enhancements:

- **Anchor positioning:** without it, the dropdown opens centered on screen.
- **`::details-content`:** without it, accordion panels open without the slide animation.

Motion is disabled under `prefers-reduced-motion`.

## Known limits

- Popover-based modals do not make the rest of the page inert. For flows that must block the page, use `<dialog>` with JavaScript's `showModal()`.
- Tooltip text is generated content. Add `aria-label` on icon-only buttons.

## Roadmap

- [ ] Toast notifications
- [ ] Carousel with `::scroll-button()`
- [ ] Switch, badge and avatar components
- [ ] Combobox using `<datalist>`

## License

MIT
