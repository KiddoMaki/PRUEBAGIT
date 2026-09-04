# Auditoría UX y accesibilidad

Auditoría realizada con apoyo de Qwen (`qwen2.5-coder:1.5b`) y revisión del código de la página.

## Resumen

La página tiene una base sólida para una experiencia sencilla: jerarquía clara, navegación interna, diseño responsive y controles de foco visibles. No se detectan bloqueos críticos en el HTML. La imagen depende de un recurso externo, por lo que conviene contemplar un respaldo local.

## Hallazgos

### Baja: imagen externa

**Evidencia:** la fotografía se carga desde Wikimedia Commons mediante una URL remota.

**Recomendación:** guardar una copia optimizada en el proyecto o añadir un estado alternativo para evitar que la experiencia pierda el contenido visual si falla la red.

### Baja: validación visual pendiente

**Evidencia:** el CSS incluye estados responsive y de foco, pero no se ejecutó una prueba visual automatizada en diferentes tamaños.

**Recomendación:** revisar la página en móvil y escritorio, comprobar el zoom al 200% y verificar que no aparezca scroll horizontal.

### Baja: contenido informativo breve

**Evidencia:** el perfil ofrece datos resumidos y no incluye fuentes o enlaces adicionales.

**Recomendación:** añadir una fuente fiable o una sección de referencias si la página se utiliza fuera de la demostración.

## Puntos positivos

- El documento declara `lang="es"` y una descripción meta.
- Existe un único encabezado principal `h1` y una jerarquía de secciones con `h2` y `h3`.
- La navegación usa enlaces reales y etiquetas `aria-label` descriptivas.
- La imagen tiene texto alternativo específico y dimensiones declaradas.
- Los enlaces muestran foco visible con `:focus-visible`.
- El layout se adapta a pantallas pequeñas mediante una media query.
- Se respeta `prefers-reduced-motion`.
- Los colores mantienen una separación visual clara entre texto, fondos y botón.

## Mejoras recomendadas

1. Descargar y optimizar la imagen en formatos modernos como WebP o AVIF.
2. Ejecutar Lighthouse o axe para comprobar contraste, estructura y navegación con teclado.
3. Probar con lector de pantalla y con zoom del 200%.
4. Añadir una fuente verificable para los datos biográficos.
5. Mantener el contenido textual breve y ampliar la información solo cuando aporte valor al usuario.
