Aquí tienes el archivo **README.md** adaptado específicamente para tu proyecto de Control Sanitario en Trucha Arcoíris, siguiendo exactamente la estructura, estilo y nivel de detalle del ejemplo de "Retorno al Diseño Universal" que proporcionaste.

Este archivo está listo para ser subido a tu repositorio de GitHub.

```markdown
# 📊 Infografía Interactiva — Control Sanitario en Trucha Arcoíris

Infografía web construida en un único archivo HTML sin dependencias externas (frameworks). Presenta diez estadísticas críticas sobre la producción de trucha arcoíris, enfermedades y buenas prácticas acuícolas, con micro-interacciones CSS y animaciones de gráficos controladas por JavaScript vanilla.

HTML5CSS3JavaScriptLicencia

📋 Tabla de contenidos
Vista previa | Estructura del archivo | Arquitectura CSS | Sistema de animaciones | Paleta y variables de diseño | Responsive — breakpoints | Accesibilidad | Guía de personalización | Estructura semántica | Créditos

---

## 🖼️ Vista previa

Cada tarjeta de la infografía incluye dos estados de interacción:

**Al pasar el cursor (Hover):**
*   Elevación suave de la tarjeta con sombra ampliada.
*   El borde del ícono cambia de color (gris → verde agua).
*   Micro-escala de la tarjeta (scale 1.02).

**Al hacer clic (Clic/Toque):**
*   Expansión vertical de la tarjeta (efecto acordeón).
*   Revelación progresiva de la cifra estadística principal.
*   Animación de crecimiento de las barras del gráfico SVG/CSS (0% → valor real).
*   Revelación del texto de detalle y fuente.

---

## 📁 Estructura del archivo

`index.html`
├── │
│   ├── Meta tags (charset, viewport)
│   ├── <title>
│   └── <style> ← Todo el CSS (Variables, Reset, Grid, Animaciones)
│
└── ├── <body>
    │
    ├── <header> ← Título principal + subtítulo
    │
    ├── <main>
    │   └── <section.infographic-grid>
    │       ├── ×10 ← Tarjetas interactivas (<article>)
    │       │   ├── .card-header > .card-icon + h3
    │       │   ├── .card-description
    │       │   └── .card-content (Oculto inicialmente)
    │       │       ├── .stat-highlight
    │       │       ├── .stat-detail
    │       │       └── .chart-container > .bar[n]
    │
    └── <footer> ← Fuente bibliográfica y diseñador

**No se utilizan librerías externas:** No Bootstrap, no Tailwind, no React. Todo el diseño y la lógica es autocontenido.

---

## 🏗️ Arquitectura CSS

El archivo `<style>` está organizado en 12 secciones numeradas con comentarios de separación para facilitar el mantenimiento:

| Sección | Contenido |
|:---:|:---|
| 1 | Reset (`box-sizing: border-box`) y declaración de variables `:root` (Paleta acuícola). |
| 2 | Base tipográfica y fondo del `body` (fondo gris claro sutil). |
| 3 | Contenedor principal (`max-width: 1200px`, centrado). |
| 4 | Encabezado: gradiente lineal azul-verde, título y subtítulo. |
| 5 | Grid Layout: `display: grid` con lógica Mobile First (1 col → 2 → 3 → 4). |
| 6 | Tarjeta base: fondo blanco, bordes redondeados, sombra inicial. |
| 7 | Iconos: contenedor circular y estilo de emoji/ícono. |
| 8 | Estado Hover: elevación (`translateY`) y cambio de borde. |
| 9 | Estado Activo (Click): expansión de `max-height` y aparición de bordes. |
| 10 | Gráficos: contenedor flex y estilo de las barras (`.bar`). |
| 11 | Pie de página: fondo oscuro y tipografía pequeña. |
| 12 | Responsive tablet y escritorio (`@media`). |

---

## ✨ Sistema de animaciones

Combinación de transiciones CSS y manipulación del DOM vía JavaScript.

1.  **Expansión de Tarjeta (Click)**
    *   *Técnica:* `max-height: 0` → `max-height: 300px` + `opacity: 0` → `1`.
    *   *Duración:* 0.5s ease-in-out.
2.  **Animación de Barras (Gráficos)**
    *   *Estado inicial:* `height: 0%`.
    *   *Estado activo:* `height: [valor en data-atributo]%`.
    *   *Técnica:* JS inyecta el estilo; CSS aplica `transition: height 1s ease-out`.
3.  **Elevación de Tarjeta (Hover)**
    *   `transform: translateY(-5px) scale(1.02)`.
    *   Sombra: `0 10px 15px rgba(0, 18, 25, 0.1)`.
4.  **Micro-interacción del Ícono**
    *   Fondo cambia de transparente a color secundario (`#0A9396`).
    *   Color del ícono invierte a blanco.

**Diagrama de secuenciamiento al Click:**

```text
0.00s ─── Añadir clase .active a tarjeta
0.00s ─── Inicio expansión altura del contenedor (dura 0.5s)
0.30s ─── Inicio aparición opacidad del texto (espera a que el contenedor abra)
0.30s ─── JS asigna altura a las barras (animación CSS dura 1s)
```

---

## 🎨 Paleta y variables de diseño

```css
:root {
    --color-main:      #005F73;   /* Principal: Encabezados, íconos activos */
    --color-secondary: #0A9396;   /* Secundario: Fondo hover, bordes, bloques */
    --color-accent:    #94D2BD;   /* Acento: Detalles, estadísticas, barras */
    --color-dark:      #001219;   /* Texto oscuro / Footer */
    --color-light:     #e0fbfc;   /* Fondos suaves */
    --color-white:     #ffffff;   /* Fondo de tarjetas */
}
```

El diseño transmite **ciencia y agua** mediante el uso de verdes azulados y tonos oscuros profesionales.

---

## 📱 Responsive — breakpoints

Diseño **Mobile First**. Los estilos base son para móvil; los media queries escalan hacia arriba.

| Breakpoint | Columnas Grid | Tamaño Tarjeta |
|:---:|:---:|:---|
| **Base (< 640px)** | 1 columna | Ancho completo |
| **≥ 600px (Tablet)** | 2 columnas | Padding aumentado |
| **≥ 1024px (Desktop)** | 3 columnas | Espaciado amplio |
| **≥ 1400px (Large)** | 4 columnas | Máximo aprovechamiento |

---

## ♿ Accesibilidad

| Técnica | Implementación |
|:---|:---|
| HTML semántico | `<main>`, `<header>`, `<article>`, `<footer>` |
| Navegación por teclado | `tabindex="0"` en cada tarjeta |
| Focus visible | `:focus-within` con outline verde oscuro y offset |
| Contraste | Texto `#001219` sobre fondo `#ffffff` (Contraste alto) |
| Texto alternativo | Uso de emojis/texto en lugar de imágenes raster sin `alt` |

---

## 🔧 Guía de personalización

Todos los puntos de ajuste están señalados con **COMENTARIOS** en el código.

### Cambiar colores
Modifica las variables en `:root` para alterar todo el tema instantáneamente:
```css
:root {
    --color-main:  #nuevo-primario;
    --color-secondary: #nuevo-secundario;
}
```

### Ajustar velocidad de las animaciones
Busca las transiciones en `.card` y `.bar`:
```css
.card { transition: all 0.4s cubic-bezier(0.25, 0.8, 0.25, 1); }
.bar  { transition: height 1s ease-out; }
```

### Agregar o eliminar tarjetas
Copia o elimina bloques `<article class="card">` dentro de `<section class="infographic-grid">`.
*   **Importante:** Asegúrate de actualizar los atributos `data-height` en las barras `<div class="bar">` para que la animación funcione correctamente.
    *   Ejemplo: `<div class="bar" data-height="80%" data-value="80%"></div>`

### Modificar datos estadísticos
Simplemente edita el texto dentro de los spans `.stat-highlight` y párrafos `.stat-detail` en el HTML.

---

## 🏛️ Estructura semántica

```text
<body>
  <main>
    <header>                      ← Título H1 y subtítulo
    <section class="infographic-grid">  ← Contenedor Grid
      <article class="card" tabindex="0">  ← Ítem interactivo
        <div class="card-header">  ← Ícono + Título
        <p class="card-description">  ← Texto resumen
        <div class="card-content">  ← Contenido oculto (Stats + Gráfico)
          <span class="stat-highlight">
          <div class="chart-container"> ...barras... </div>
    <footer>                      ← Citas y autor
```

---

## 📄 Créditos

**Fuente:**
> Mendoza Bojorquez, R. J., & Palomino Ramos, A. R. (2004). Manual de cultivo de trucha arco iris en jaulas flotantes. Fondo Nacional de Desarrollo Pesquero (FONDEPES) & Agencia Española de Cooperación Internacional (AECI).

**Diseño y Desarrollo:**
> Ronald Fabrizio Aguirre Paricahua

**Tecnologías:**
> HTML5 puro + CSS3 puro + Vanilla JS — cero dependencias de frameworks.

---

## 📝 Licencia

MIT — Puedes usar, modificar y distribuir este archivo libremente con atribución al diseñador original.
```
