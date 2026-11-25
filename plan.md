# Plan de implementación — Nyuk Hub

## Alcance
Construir una landing profesional mobile-first que replique la referencia adjunta: fondo oscuro tecnológico, brillos neón cian/azul/violeta, tarjetas con glassmorphism, líneas de luz y una navegación clara. La página mantiene el orden de la referencia: hero, confianza, servicios, portafolio/demos, ecommerce, restaurante, CRM, dashboard, SEO/performance, resultados, contacto y footer.

Las demos no serán imágenes: estarán construidas con componentes funcionales y datos locales persistidos en `localStorage` cuando corresponda.

## Arquitectura
- `src/main.tsx`: entrada React.
- `src/App.tsx`: composición de la landing y estado global de navegación.
- `src/data.ts`: datos de productos, menú, clientes, métricas y contenido.
- `src/components/`: Header, SectionHeading, Demo tabs, EcommerceDemo, RestaurantDemo, CrmDemo, DashboardDemo, ContactForm, Footer y primitives visuales.
- `src/styles.css`: sistema visual, responsive mobile-first, efectos de glow, grids y accesibilidad.
- `public/manus-routes.json`: manifiesto de rutas.
- `app.config.ts`: metadatos de logo del proyecto.

## Sistema visual
- **Movimiento**: cyber-editorial / digital growth con influencia de interfaces SaaS premium.
- **Principios**: contraste dramático; contenido agrupado en módulos luminosos; profundidad mediante transparencias y halos; ritmo vertical compacto en móvil.
- **Color**: `#050818` como base; cian `#08d9ff` para acción y confianza; violeta `#7437ff` y magenta `#d63cff` para energía y diferenciación; blanco frío para legibilidad.
- **Layout**: composición por bandas, diagonales y bloques asimétricos; cards que pasan de columnas a carrusel horizontal controlado en móvil.
- **Firma**: líneas orbitantes, bordes con gradiente, píldoras de categoría y CTA con degradado cian-violeta.
- **Interacción**: cada CTA navega o ejecuta una acción real; demos con filtros, búsqueda, edición y confirmación; feedback visible mediante toasts/estados.
- **Animación**: entrada suave, halos flotantes y hover reducido en touch; `prefers-reduced-motion` desactiva desplazamientos no esenciales.
- **Tipografía**: `Inter`/system sans para lectura; pesos 500–800 y headlines compactos con tracking negativo.
- **Esencia**: socio tecnológico que convierte estrategia, datos y ejecución en crecimiento medible. Directo, preciso, ambicioso.
- **Voz**: clara, orientada a resultados, sin relleno. Ejemplos: “Tu siguiente salto empieza con datos.” / “Convierte atención en crecimiento.”
- **Marca**: wordmark “Nyuk Hub” acompañado por un monograma N compuesto por dos barras luminosas.
- **Color propio**: cian eléctrico `#08d9ff`.

## Funcionalidad
- Header sticky con menú hamburguesa móvil y scroll suave.
- Ecommerce: catálogo, búsqueda, categorías, selección de variante, cantidad, carrito lateral, totales y compra simulada.
- Restaurante: categorías, búsqueda, favoritos, agregar al pedido, cantidades, método de pago y confirmación.
- CRM: alta, edición, eliminación, búsqueda, filtro de estado, seguimiento y estadísticas; persistencia local.
- Dashboard: filtro temporal, KPIs, gráfico de líneas SVG, donut SVG, tabla filtrable y métricas dinámicas.
- Formulario de contacto validado con mensaje de envío simulado.
- Footer con enlaces internos, newsletter y privacidad.

## Rendimiento y SEO
HTML semántico, `meta` description, `aria` labels, botones táctiles de mínimo 44px, SVG sin dependencias pesadas, CSS responsive desde 320px, `loading=lazy` para recursos no críticos, manifiesto de rutas y build Vite autocontenido.

## Entrega
Servidor Vite en puerto 3000, verificación de build, endpoint `/manus-routes.json`, revisión visual en 375px y 1280px mediante Preview, corrección de overflow y estados de interacción antes del checkpoint.
