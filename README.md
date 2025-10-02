# Shopify Section Flexbox (Dawn-ready)

Composable Flexbox section for Shopify with modular blocks and EN/ES localization. Works out-of-the-box on **Dawn** and can be adapted to other themes with small tweaks.

## Features
- Section: `Section Flexbox` (`sections/section-flexbox.liquid`)
- Blocks: `wrapper`, `container`, `heading`, `richtext`, `image`, `button`, `hr`
- i18n namespaces: `t:sections.section_flexbox.*` and `t:blocks.*` (EN/ES included)
- Color scheme aware (Dawn) and easily portable to any theme

## Installation
1. Copy files into your theme:
   - `sections/section-flexbox.liquid`
   - `blocks/*.liquid`
   - `locales/en.default.json` and `locales/es.json` (merge if you already have locales)
2. **Dawn**: works as is.  
   **Other themes**: add color-scheme CSS variables and settings:

   In `theme.liquid` (root `<style>`), inject CSS vars for each scheme (sample provided in this repo under `docs/snippets/color-schemes.liquid` or see README.es.md).

   In `config/settings_schema.json`, add a `color_scheme_group` named `color_schemes` (sample provided under `docs/snippets/settings_schema-colors.json`).

3. Open the Theme Editor → add **Section Flexbox** → insert blocks as needed.

## Usage tips
- Use `Wrapper` to control gaps, alignment and mobile direction.
- Use `Container` for width, max-width, paddings, color scheme, and custom IDs/classes.
- The section exposes background image, repeat/size/position, gap and paddings.
- All labels/options are localized via `t:blocks.*` and `t:sections.section_flexbox.*`.

## Localization
- English strings: `locales/en.default.json`
- Spanish strings: `locales/es.json`

## License
MIT — see `LICENSE`.
