# Sección Flexbox para Shopify (compatible con Dawn)

Sección flexible basada en Flexbox con bloques modulares e i18n EN/ES. Funciona de inmediato en **Dawn** y puede adaptarse a otros temas con ajustes mínimos.

**English** → [README.md](./README.md)

## Características
- Sección: `Section Flexbox` (`sections/section-flexbox.liquid`)
- Bloques: `wrapper`, `container`, `heading`, `richtext`, `image`, `button`, `hr`
- Namespaces i18n: `t:sections.section_flexbox.*` y `t:blocks.*` (EN/ES incluidos)
- Compatible con esquemas de color (Dawn) y portable a otros temas

## Instalación
1. Copia los archivos en tu tema:
   - `sections/section-flexbox.liquid`
   - `blocks/*.liquid`
   - `locales/en.default.json` y `locales/es.json` (haz merge si ya tienes locales)

2. **Dawn**: funciona tal cual.  
   **Otros temas**: añade variables CSS y settings para esquemas de color:
   - Agrega el loop de variables CSS de **[docs/snippets/color-schemes.liquid](./docs/snippets/color-schemes.liquid)** dentro del `<style>` raíz de `theme.liquid`.
   - Agrega el grupo de colores de **[docs/snippets/settings_schema-colors.json](./docs/snippets/settings_schema-colors.json)** en `config/settings_schema.json`.

3. Abre el Editor de temas → agrega **Section Flexbox** → inserta los bloques que necesites.

## Consejos
- `Wrapper`: dirección de flex, gap y alineación (con variante móvil).
- `Container`: ancho, `max-width`, paddings, esquema de color e IDs/clases.
- La sección controla imagen de fondo, tamaño/repetición/posición, gap y paddings.
- Todo el texto/opciones salen de `t:blocks.*` y `t:sections.section_flexbox.*`.

## Localización
- Inglés: `locales/en.json`
- Español: `locales/es.json`

## Capturas
<p align="center">
<img width="1617" height="855" alt="image" src="https://github.com/user-attachments/assets/45e307dd-b510-4ee9-889f-3737ccbaf419" />
</p>
<p align="center">
<img width="1908" height="856" alt="image" src="https://github.com/user-attachments/assets/2b5d303c-290b-4bb1-8462-33b1f536399a" />
</p>
<p align="center">
<img width="1905" height="850" alt="image" src="https://github.com/user-attachments/assets/e8596d5c-bcd9-4125-b7f0-46edeab44df9" />
</p>

## Licencia
MIT — ver [`LICENSE`](./LICENSE).
