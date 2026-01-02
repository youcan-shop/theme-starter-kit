# YouCan Theme Starter Kit

<img src="https://s4.ezgif.com/tmp/ezgif-4da1f24eb7673519.gif" alt="theme starter kit" />

## Introduction

This starter kit provides the core building blocks every theme needs, so you can skip the repetitive setup and focus on design, creativity, and new sections. All using native HTML, CSS (SCSS), and JS, while still feeling clean.

## Usage

1. Clone the repository

```bash
git clone https://github.com/youcan-shop/theme-starter-kit
```

2. Initialize the starter theme

> You'll be guided through a few setup questions, like the theme `name`, `author`, `version`, etc.

```bash
youcan theme:init -i
```

3. Install your dependencies

```bash
cd your_theme_name
pnpm run dev
```

4. Start the development server

```bash
pnpm run dev
```

## Templates

| Template (page)  | Section                                                       |
| ---------------- | ------------------------------------------------------------- |
| Index            | N/A                                                           |
| Product          | [single-product.liquid](sections/single-product.liquid)       |
| List Collections | [list-collections.liquid](sections/list-collections.liquid)   |
| Collection       | [single-collection.liquid](sections/single-collection.liquid) |
| Search           | [search.liquid](sections/search.liquid)                       |
| Cart             | [cart.liquid](sections/cart.liquid)                           |
| Thank You        | [thankyou.liquid](sections/thankyou.liquid)                   |
| Upsell           | [upsell.liquid](sections/upsell.liquid)                       |
| Page             | [page.liquid](sections/page.liquid)                           |

## Snippets

> [!IMPORTANT]
> Snippets marked with `\*` are part of the theme core logic and shouldn't be removed (feel free to tweak the visuals). The rest are totally up to you.

### Core

| Snippet          | Type     | File                                                                  |
| ---------------- | -------- | --------------------------------------------------------------------- |
| Quantity         | `CORE`\* | [core.quantity.liquid](snippets/core.quantity.liquid)                 |
| Shop Button      | `CORE`\* | [core.shop-button.liquid](snippets/core.shop-button.liquid)           |
| Variants         | `CORE`\* | [core.variants.liquid](snippets/core.variants.liquid)                 |
| Express Checkout | `CORE`\* | [core.express-checkout.liquid](snippets/core.express-checkout.liquid) |
| Linked Fields    | `CORE`\* | [core.linked-fields.liquid](snippets/core.linked-fields.liquid)       |
| Cart Form        | `CORE`\* | [core.cart-form.liquid](snippets/core.cart-form.liquid)               |
| Cart Item        | `CORE`\* | [core.cart-item.liquid](snippets/core.cart-item.liquid)               |
| Cart Form Item   | `CORE`\* | [core.cart-form-item.liquid](snippets/core.cart-form-item.liquid)     |

### Constants

| Snippet          | Type      | File                                                                    |
| ---------------- | --------- | ----------------------------------------------------------------------- |
| Inventory Status | `CONST`\* | [const.inventory-status.liquid](snippets/const.inventory-status.liquid) |
| Discount Value   | `CONST`\* | [const.discount-value.liquid](snippets/const.discount-value.liquid)     |
| Payment Status   | `CONST`\* | [const.payment-status.liquid](snippets/const.payment-status.liquid)     |
| Payment Gateway  | `CONST`\* | [const.payment-gateway.liquid](snippets/const.payment-gateway.liquid)   |

### Misc

| Snippet        | Type   | File                                                              |
| -------------- | ------ | ----------------------------------------------------------------- |
| Icon           | `MISC` | [misc.icon.liquid](snippets/misc.icon.liquid)                     |
| Search         | `MISC` | [misc.search.liquid](snippets/misc.search.liquid)                 |
| Toast          | `MISC` | [misc.toast.liquid](snippets/misc.toast.liquid)                   |
| Pagination     | `MISC` | [misc.pagination.liquid](snippets/misc.pagination.liquid)         |
| Breadcrumb     | `MISC` | [misc.breadcrumb.liquid](snippets/misc.breadcrumb.liquid)         |
| Empty          | `MISC` | [misc.empty.liquid](snippets/misc.empty.liquid)                   |
| Image Fallback | `MISC` | [misc.image-fallback.liquid](snippets/misc.image-fallback.liquid) |
| Cart Drawer    | `MISC` | [misc.cart-drawer.liquid](snippets/misc.cart-drawer.liquid)       |
| Menu Drawer    | `MISC` | [misc.menu-drawer.liquid](snippets/misc.menu-drawer.liquid)       |

### Block

| Snippet | Type    | File                                                        |
| ------- | ------- | ----------------------------------------------------------- |
| Icon    | `BLOCK` | [block.product.liquid](snippets/block.product.liquid)       |
| Search  | `BLOCK` | [block.collection.liquid](snippets/block.collection.liquid) |

## Color System

To simplify theming, we include a CSS only color palette generated from a single primary (brand) color. This approach guarantees all generated colors respect [accessibility](https://webaim.org/resources/contrastchecker/) standards, regardless of the chosen base color. It also improves DX by using semantic color tokens (e.g. `primary`, `on-primary`, `primary-container`, `on-primary-container`) instead of numeric shade levels that are rarely all needed. For a better understanding of the system, we recommend checking [Alwan Generator](https://github.com/ibrilBadreddine/alwan-generator).

### Tokens vs Shades

| Tokens                       | Shades (50 - 900)   |
| ---------------------------- | ------------------- |
| --color-primary              | --color-primary-500 |
| --color-on-primary           | --color-primary-50  |
| --color-primary-container    | --color-primary-100 |
| --color-on-primary-container | --color-primary-900 |

```css
// With Shades
[ui-slot="button"] {
  color: var(--color-primary-50);
  background-color: var(--color-primary-500);
}
```

```css
// With Tokens
[ui-slot="button"] {
  color: var(--color-on-primary);
  background-color: var(--color-primary);
}
```

### Usage

```css
:root {
  --brand-hue: 333;
  --brand-saturation: 86%;
}
```

### Dark Mode

```html
<html data-theme="dark"></html>
```

### Tokens

| Name        | Tokens                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Primary     | <ul><li><code>--color-primary</code></li><li><code>--color-on-primary</code></li><li><code>--color-primary-container</code></li><li><code>--color-on-primary-container</code></li></ul>                                                                                                                                                                                                                                                                |
| Secondary   | <ul><li><code>--color-secondary</code></li><li><code>--color-on-secondary</code></li><li><code>--color-secondary-container</code></li><li><code>--color-on-secondary-container</code></li></ul>                                                                                                                                                                                                                                                        |
| Tertiary    | <ul><li><code>--color-tertiary</code></li><li><code>--color-on-tertiary</code></li><li><code>--color-tertiary-container</code></li><li><code>--color-on-tertiary-container</code></li></ul>                                                                                                                                                                                                                                                            |
| Error       | <ul><li><code>--color-error</code></li><li><code>--color-on-error</code></li><li><code>--color-error-container</code></li><li><code>--color-on-error-container</code></li></ul>                                                                                                                                                                                                                                                                        |
| Success     | <ul><li><code>--color-success</code></li><li><code>--color-on-success</code></li><li><code>--color-success-container</code></li><li><code>--color-on-success-container</code></li></ul>                                                                                                                                                                                                                                                                |
| Warning     | <ul><li><code>--color-warning</code></li><li><code>--color-on-warning</code></li><li><code>--color-warning-container</code></li><li><code>--color-on-warning-container</code></li></ul>                                                                                                                                                                                                                                                                |
| Information | <ul><li><code>--color-info</code></li><li><code>--color-on-info</code></li><li><code>--color-info-container</code></li><li><code>--color-on-info-container</code></li></ul>                                                                                                                                                                                                                                                                            |
| Outline     | <ul><li><code>--color-outline</code></li><li><code>--color-outline-variant</code></li></ul>                                                                                                                                                                                                                                                                                                                                                            |
| Surface     | <ul><li><code>--color-surface</code></li><li><code>--color-on-surface</code></li><li><code>--color-surface-variant</code></li><li><code>--color-on-surface-variant</code></li><li><code>--color-surface-container</code></li><li><code>--color-surface-container-lowest</code></li><li><code>--color-surface-container-low</code></li><li><code>--color-surface-container-high</code></li><li><code>--color-surface-container-highest</code></li></ul> |

## Components

This project includes a UI component library ([Celeste](https://github.com/youcan-shop/celeste) DS) with over 30 reusable components. The components are built primarily with CSS + minimal JavaScript used only when required for accessibility. Each component is documented, no dependencies, and full control to style things your way.

> [!NOTE]
> Don't need a component? Just remove it. You own the code.

### Core

| Name           | File                                                              |
| -------------- | ----------------------------------------------------------------- |
| Avatar         | [avatar.scss](styles/components/core/avatar.scss)                 |
| Badge          | [badge.scss](styles/components/core/badge.scss)                   |
| Button         | [button.scss](styles/components/core/button.scss)                 |
| Button Group   | [button-group.scss](styles/components/core/button-group.scss)     |
| Compact Button | [compact-button.scss](styles/components/core/compact-button.scss) |
| Link Button    | [link-button.scss](styles/components/core/link-button.scss)       |
| Divider        | [divider.scss](styles/components/core/divider.scss)               |
| Status Badge   | [status-badge.scss](styles/components/core/status-badge.scss)     |

### Data Display

| Name          | File                                                                    |
| ------------- | ----------------------------------------------------------------------- |
| Banner        | [banner.scss](styles/components/data-display/banner.scss)               |
| Kbd           | [kbd.scss](styles/components/data-display/kbd.scss)                     |
| Progress Bar  | [progress-bar.scss](styles/components/data-display/progress-bar.scss)   |
| Rating Bar    | [rating-bar.scss](styles/components/data-display/rating-bar.scss)       |
| Rating Review | [rating-review.scss](styles/components/data-display/rating-review.scss) |

### Disclosure

| Name      | File                                                          |
| --------- | ------------------------------------------------------------- |
| Accordion | [accordion.scss](styles/components/disclosure/accordion.scss) |
| Drawer    | [drawer.scss](styles/components/disclosure/drawer.scss)       |
| Dropdown  | [dropdown.scss](styles/components/disclosure/dropdown.scss)   |
| Popover   | [popover.scss](styles/components/disclosure/popover.scss)     |
| Sheet     | [sheet.scss](styles/components/disclosure/sheet.scss)         |

### Feedback

| Name    | File                                                    |
| ------- | ------------------------------------------------------- |
| Alert   | [alert.scss](styles/components/feedback/alert.scss)     |
| Modal   | [modal.scss](styles/components/feedback/modal.scss)     |
| Tooltip | [tooltip.scss](styles/components/feedback/tooltip.scss) |

### Form

| Name         | File                                                        |
| ------------ | ----------------------------------------------------------- |
| Checkbox     | [checkbox.scss](styles/components/form/checkbox.scss)       |
| Filed Upload | [file-upload.scss](styles/components/form/file-upload.scss) |
| Hint         | [hint.scss](styles/components/form/hint.scss)               |
| Input        | [input.scss](styles/components/form/input.scss)             |
| Label        | [label.scss](styles/components/form/label.scss)             |
| Radio        | [radio.scss](styles/components/form/radio.scss)             |
| Select       | [select.scss](styles/components/form/select.scss)           |
| Slider       | [slider.scss](styles/components/form/slider.scss)           |
| Switch       | [switch.scss](styles/components/form/switch.scss)           |
| Textarea     | [textarea.scss](styles/components/form/textarea.scss)       |

### Layout

| Name              | File                                                                      |
| ----------------- | ------------------------------------------------------------------------- |
| Carousel          | [carousel.scss](styles/components/layout/carousel.scss)                   |
| Segmented Control | [segmented-control.scss](styles/components/layout/segmented-control.scss) |
| Skeleton          | [skeleton.scss](styles/components/layout/skeleton.scss)                   |

### Navigation

| Name       | File                                                            |
| ---------- | --------------------------------------------------------------- |
| Breadcrumb | [breadcrumb.scss](styles/components/navigation/breadcrumb.scss) |
| Pagination | [pagination.scss](styles/components/navigation/pagination.scss) |

## Common Way

Not strict rules, just small guidelines to keep things organized and make the code easier to read for everyone.

### Add Section

1. Section files naming

```
cart.liquid
section.cart.scss
section.cart.js
```

2. Liquid section

```html
<div ui-section="cart">My Section</div>
```

3. Styling (CSS or SCSS)

```css
[ui-section="cart"] {
}
```

### Add Block

1. Block files naming

```
block.product.liquid
block.product.scss
block.product.js
```

2. Liquid section

```html
<div ui-block="product">My Bock</div>
```

3. Styling (CSS or SCSS)

```css
[ui-block="product"] {
}
```

### Add Snippet

1. Snippet files naming

```
misc.promotion.liquid
misc.promotion.scss
misc.promotion.js
```

2. Liquid section

```html
<ui-promotion>My Snippet</ui-promotion>
```

3. Styling (CSS or SCSS)

```css
ui-promotion {
}
```

### Web Component

```js
if (!customElements.get("ui-select")) {
  class Select extends HTMLElement {
    static observedAttributes = ["variant", "size"];

    constructor() {
      super();

      this.trigger = this.querySelector('[ui-select="trigger"]');
    }

    connectedCallback() {
      this._render();
    }

    _render() {
      // Your logic
    }
  }

  customElements.define("ui-select", Select);
}
```
