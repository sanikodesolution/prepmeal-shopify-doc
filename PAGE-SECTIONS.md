# Page sections map

**Rule:** one content job per theme section. Do not nest How-it-works / FAQ / Reviews / Forms inside a single mega-section. In the theme editor, each content area should appear as its own section in the template sidebar.

Always keep this file (and related docs in `prepmeal-shopify-doc`) in sync when page structure changes.

---

## Split pages (content-wise)

### Gift cards — `page.gift-cards.json`

| Order | Section file | Editor name | Job |
| --- | --- | --- | --- |
| 1 | `cm-gift-card` | CM gift card | Card visual + buy form + ticker strip |
| 2 | `cm-gift-card-how` | GC how it works | Steps |
| 3 | `cm-gift-card-faq` | GC FAQ | FAQ accordion |
| 4 | `cm-gift-card-reviews` | GC reviews | Reviews + write form |

Related: `page.gift-card-editor.json` → `cm-gift-card-editor` (single interactive editor; intentionally one section).

### Private chef — `page.private-chef-experience.json`

| Order | Section file | Editor name | Job |
| --- | --- | --- | --- |
| 1 | `cm-private-chef` | PC hero | Hero + perk strip |
| 2 | `cm-private-chef-occasions` | PC occasions | Occasion chips |
| 3 | `cm-private-chef-expect` | PC expect | Expect list + quote |
| 4 | `cm-private-chef-steps` | PC steps | How it works (`#pc-how`) |
| 5 | `cm-private-chef-quote` | PC quote form | Enquiry form (`#pc-quote`) |

### Meal plan pages — `page.meal-plans.json`, `page.5/6/7/10/15-meal-plan.json`

Shipped templates use **separate** `cm-mp-*` sections (not one mega `cm-meal-plan-page`):

| Typical order | Section | Job |
| --- | --- | --- |
| 1 | `cm-mp-order` | Order / this week’s menu box |
| 2 | `cm-mp-hero` | Hero + hero buttons |
| 3 | `cm-mp-benefits` | Benefits / chips |
| 4 | `cm-mp-menu-grid` | Menu grid |
| 5 | `cm-mp-thali` | Thali / plate visual |
| 6 | `cm-mp-explore` | Explore band |
| 7 | `cm-mp-chef` | Chef story |
| 8 | `cm-mp-steps` | Steps |
| 9 | `cm-mp-delivery` | Delivery |
| 10 | `cm-mp-reviews` | Reviews |
| 11 | `cm-mp-faq` | FAQ |
| 12 | `cm-mp-related` | Related plans |
| 13 | `cm-mp-cta` | Closing CTA |

`cm-meal-plan-page` may still exist in the theme as a legacy/combined option, but **current page templates** use the split `cm-mp-*` stack.

### Other pages already split

| Template | Sections |
| --- | --- |
| `page.about` | story → usp → cta |
| `page.how-it-works` | hero → steps → good_to_know → cta |
| `page.contact` | main → contact_page |
| `page.custom-meal-plans` | main → intro → form |
| `page.faqs` | main + multiple collapsible content sections |

## Intentionally single-section

| Template | Why |
| --- | --- |
| `page.gift-card-editor` | One interactive editor UI |
| `page.json` | Default Shopify page body |
| System (`404`, `search`, …) | Not marketing pages |

## Gift card editor notes

- Live preview + customization panel (card size, colors, tilt, logo, PNG/SVG export)
- Typography: font family / weight / per-line sizes (minimum **14px**)
- Do **not** load fonts from a local Downloads folder; use theme fonts or Google fonts via the editor JS

## Text typography & background (theme-wide)

Meal-prep and core content sections share per-text controls (via `pm-block-type-style`). For each text role in the theme editor:

| Group | Controls |
| --- | --- |
| Typography | Text color, font size (0 = theme default; custom ≥ **14px**), weight, letter spacing, line height |
| Spacing | Padding / margin (default 0 = look unchanged) |
| Background | Background **color** and/or **image**, image size (cover / contain / auto), image position |
| Image mask | None, Fade bottom, Fade edges, Circle, Soft vignette, Rounded box, Custom mask image |
| Clip to letters | Optional knockout: fill letter shapes with the background color/image |

Clear a color swatch to reset that color. Leave image/mask empty when unused.

Applies across CM sections, gift card, private chef, `cm-mp-*` meal-plan stack, SS Feature #1, Image banner, Image with text, rich text, newsletter, and related blocks. See **Sections Reference** in `index.html`.

### Footer (`cm-footer`)

| Block | Job |
| --- | --- |
| `cta` | Orange call-to-action band (limit 1) — content + button + typography |
| `links` / `menu` | Link columns |
| `contact` | Phone / email / area / hours |

CTA content is **not** section settings; use Add block → Call to action.

## Workflow

1. Prefer **Add section** over stuffing unrelated blocks into another section.
2. Keep editor names short and content-scoped (`GC FAQ`, `PC steps`, `MP reviews`).
3. After theme changes: push live theme, sync GitHub `prepmeal-shopify`, then update **this doc repo** (`prepmeal-shopify-doc`).
