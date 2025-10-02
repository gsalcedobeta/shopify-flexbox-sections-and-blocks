# Sección Flexbox para Shopify (compatible con Dawn)

Sección flexible basada en Flexbox con bloques modulares e i18n EN/ES. Funciona de inmediato en **Dawn** y puede adaptarse a otros temas con pequeños ajustes.

## Características
- Sección: `Section Flexbox` (`sections/section-flexbox.liquid`)
- Bloques: `wrapper`, `container`, `heading`, `richtext`, `image`, `button`, `hr`
- Namespaces i18n: `t:sections.section_flexbox.*` y `t:blocks.*` (EN/ES incluidos)
- Soporta esquemas de color (Dawn) y es portable a cualquier tema

## Instalación
1. Copia los archivos en tu tema:
   - `sections/section-flexbox.liquid`
   - `blocks/*.liquid`
   - `locales/en.default.json` y `locales/es.json` (haz merge si ya tienes locales)
2. **Dawn**: funciona tal cual.  
   **Otros temas**: añade variables CSS de esquema de color y el grupo en settings:

   En `theme.liquid` (en `<style>` raíz), inyecta variables CSS por esquema. Puedes usar este snippet (igual al de Dawn):

   ```liquid
   {% for scheme in settings.color_schemes -%}
     {% if forloop.index == 1 %}:root,{% endif %}
     .color-{{ scheme.id }} {
       --color-background: {{ scheme.settings.background.red }},{{ scheme.settings.background.green }},{{ scheme.settings.background.blue }};
       {% if scheme.settings.background_gradient != empty %}
         --gradient-background: {{ scheme.settings.background_gradient }};
       {% else %}
         --gradient-background: {{ scheme.settings.background }};
       {% endif %}

       {% liquid
         assign background_color = scheme.settings.background
         assign background_color_brightness = background_color | color_brightness
         if background_color_brightness <= 26
           assign background_color_contrast = background_color | color_lighten: 50
         elsif background_color_brightness <= 65
           assign background_color_contrast = background_color | color_lighten: 5
         else
           assign background_color_contrast = background_color | color_darken: 25
         endif
       %}

       --color-foreground: {{ scheme.settings.text.red }},{{ scheme.settings.text.green }},{{ scheme.settings.text.blue }};
       --color-background-contrast: {{ background_color_contrast.red }},{{ background_color_contrast.green }},{{ background_color_contrast.blue }};
       --color-shadow: {{ scheme.settings.shadow.red }},{{ scheme.settings.shadow.green }},{{ scheme.settings.shadow.blue }};
       --color-button: {{ scheme.settings.button.red }},{{ scheme.settings.button.green }},{{ scheme.settings.button.blue }};
       --color-button-text: {{ scheme.settings.button_label.red }},{{ scheme.settings.button_label.green }},{{ scheme.settings.button_label.blue }};
       --color-secondary-button: {{ scheme.settings.background.red }},{{ scheme.settings.background.green }},{{ scheme.settings.background.blue }};
       --color-secondary-button-text: {{ scheme.settings.secondary_button_label.red }},{{ scheme.settings.secondary_button_label.green }},{{ scheme.settings.secondary_button_label.blue }};
       --color-link: {{ scheme.settings.secondary_button_label.red }},{{ scheme.settings.secondary_button_label.green }},{{ scheme.settings.secondary_button_label.blue }};
       --color-badge-foreground: {{ scheme.settings.text.red }},{{ scheme.settings.text.green }},{{ scheme.settings.text.blue }};
       --color-badge-background: {{ scheme.settings.background.red }},{{ scheme.settings.background.green }},{{ scheme.settings.background.blue }};
       --color-badge-border: {{ scheme.settings.text.red }},{{ scheme.settings.text.green }},{{ scheme.settings.text.blue }};
       --payment-terms-background-color: rgb({{ scheme.settings.background.rgb }});
     }
   {% endfor %}
