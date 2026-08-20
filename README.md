# DripDrop — Township Streetwear, Limited Drops

> Local heat. Limited runs. Built for the streets.

**Live Store:** [dripdrop-9979.myshopify.com](https://dripdrop-9979.myshopify.com)

DripDrop is a South African limited-drop streetwear store built on Shopify's Horizon theme. It celebrates township culture through exclusive and limited sneaker and apparel drops — where every release is an event, inventory moves fast, and the experience has to match the hype.

---

## What This Project Is

This is the capstone project for the Bitcube Software Development Trainee Programme. The brief called for a production-ready Shopify storefront on the Horizon theme that demonstrates:

- Deep understanding of Horizon's block-as-file-type architecture
- Custom Liquid section and block development
- Clean, performant image handling using Shopify's `image_url` filter with responsive `srcset`
- Correct currency formatting using the `money` filter
- Zero Theme Check CLI errors
- A polished, brand-led customer experience

---

## Tech Stack

| Layer | Technology |
|---|---|
| Platform | Shopify |
| Theme base | Horizon (block-as-file-type architecture) |
| Templating | Liquid |
| Styling | CSS custom properties + Horizon's design token system |
| Templates | JSON |
| CI/CD | Shopify CLI + GitHub |

---

## Custom Features Built

### 1. Drop Spotlight Section
A full-width editorial section that puts the hero product front and centre. Built from scratch using Horizon's block architecture with three configurable block types exposed in the theme editor:

- **Story block** — headline, subheading, and brand narrative copy
- **FAQ block** — collapsible product details and sizing info
- **Picker block** — connects directly to the variant picker

All blocks are flat-structured and fully configurable without touching code.

### 2. Variant Picker with Size Swatches
A custom size swatch picker replacing Shopify's default dropdown. Swatches render as radio tile inputs driven by `product.options_by_name['Size']`. Sold-out variants are visually crossed out and disabled. One tap to select — no dropdowns, no friction.

### 3. Lookbook Masonry Section
An editorial product grid on the homepage inspired by SA premium streetwear stores. Features:

- Two configurable layouts: **Editorial** (asymmetric 12-column) and **Classic** (3-column)
- Product tiles using `image_url` with full responsive `srcset` (400w / 600w / 900w / 1200w)
- Price overlays using the `money` filter
- Editorial text cards for brand copy between product tiles
- Drop badges (NEW, LIMITED, COLLAB) configurable per tile in the theme editor
- Subtle hover zoom on product images
- Fully mobile responsive

### 4. Cart Drawer with Free Shipping Progress
The cart drawer includes a live free shipping progress indicator. When a customer adds items, the bar updates via Shopify's **Section Rendering API** — no page reload. The threshold and messaging are configurable from the theme editor.

---

## Project Structure

dripdrop/
├── sections/
│ ├── drop-spotlight.liquid # Custom hero section
│ ├── lookbook-masonry.liquid # Editorial product grid
│ ├── cart-drawer-section.liquid # Cart with shipping progress
│ └── ... # Horizon base sections
├── blocks/
│ ├── spotlight-story.liquid
│ ├── spotlight-faq.liquid
│ └── spotlight-picker.liquid
├── snippets/
│ ├── variant-main-picker.liquid
│ └── cart-drawer.liquid
├── templates/
│ ├── index.json # Homepage
│ ├── product.json # Product page
│ └── collection.json # Collection page
└── config/
├── settings_schema.json
└── settings_data.json


---

## Running Locally

You'll need [Shopify CLI](https://shopify.dev/docs/themes/tools/cli) installed.

```bash
# Clone the repo
git clone https://github.com/Kavin-Maziya/DripDrop.git
cd DripDrop

# Authenticate with Shopify
shopify auth login --store dripdrop-9979.myshopify.com

# Start local development
shopify theme dev --store dripdrop-9979.myshopify.com
```

---

## Theme Check

This theme passes Shopify's Theme Check CLI with zero errors.

```bash
shopify theme check
```

---

## Capstone Brief Compliance

| Requirement | Status |
|---|---|
| Horizon block-as-file-type architecture | ✅ |
| Custom section with 3+ configurable block types | ✅ |
| Custom variant picker with size swatches | ✅ |
| JSON templates throughout | ✅ |
| Zero Theme Check CLI errors | ✅ |
| Cart drawer free shipping progress (Section Rendering API) | ✅ |
| Masonry lookbook with `image_url` + `money` filters | ✅ |

---

## Author

**Kavin Ozzie Maziya** — Bitcube Software Development Trainee Programme, 2026