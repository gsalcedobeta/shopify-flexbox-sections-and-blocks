# Shopify Section Flexbox (Dawn-ready)

Composable Flexbox section for Shopify with modular blocks and EN/ES localization. Works out-of-the-box on **Dawn** and can be adapted to other themes with small tweaks.

**Español** → [README.es.md](./README.es.md)

## Features
- Section: `Section Flexbox` (`sections/custom-flexbox.liquid`)
- Blocks: `wrapper`, `container`, `heading`, `richtext`, `image`, `button`, `hr`
- i18n namespaces: `t:sections.section_flexbox.*` and `t:blocks.*` (EN/ES included)
- Color-scheme aware (Dawn) and easily portable to other themes

## Installation
1. Copy files into your theme:
   - `sections/custom-flexbox.liquid`
   - `blocks/*.liquid`
   - `locales/en.default.json` and `locales/es.json` (merge if you already have locales)

2. Global styles  
   - **Dawn**: paste the provided CSS into `assets/base.css` (already included in this repo’s `assets/base.css`).
   - **Other themes**: paste the same CSS into your main stylesheet (e.g., `assets/theme.css`) or add a separate file and include it in `theme.liquid`:
     ```liquid
     {{ 'theme.css' | asset_url | stylesheet_tag }}
     {{ 'global-flexbox.css' | asset_url | stylesheet_tag }} {# if you keep it separate #}
     ```

3. **Dawn** works as is.  
   **Other themes**: if you don’t have color-scheme variables, port Dawn’s color-scheme setup (see the Spanish README for details or copy from Dawn).

4. Open the Theme Editor → add **Section Flexbox** → insert blocks as needed.

## Usage tips
- `Wrapper`: flex direction, gap, alignment (with mobile variant).
- `Container`: width, max-width, paddings, color scheme, custom IDs/classes.
- The section exposes background image, repeat/size/position, gap and paddings.
- All labels/options are localized via `t:blocks.*` and `t:sections.section_flexbox.*`.

## Localization
- English: `locales/en.json`
- Spanish: `locales/es.json`

## Screenshots
<p align="center">
<img width="1617" height="855" alt="image" src="https://github.com/user-attachments/assets/45e307dd-b510-4ee9-889f-3737ccbaf419" />
</p>
<p align="center">
<img width="1908" height="856" alt="image" src="https://github.com/user-attachments/assets/2b5d303c-290b-4bb1-8462-33b1f536399a" />
</p>
<p align="center">
<img width="1905" height="850" alt="image" src="https://github.com/user-attachments/assets/e8596d5c-bcd9-4125-b7f0-46edeab44df9" />
</p>

## License
MIT — see [`LICENSE`](./LICENSE).
