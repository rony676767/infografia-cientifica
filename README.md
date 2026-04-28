Aquí tienes el archivo `README.md` profesional, estructurado y listo para acompañar a tu proyecto.

```markdown
# 📊 Infografía Interactiva: Control Sanitario en Trucha Arcoíris

Infografía web interactiva minimalista enfocada en la visualización de datos estadísticos sobre la producción de trucha arcoíris, control sanitario y buenas prácticas acuícolas. Diseñada con un enfoque científico, limpio y responsivo.

![Licencia](https://img.shields.io/badge/Licencia-MIT-blue.svg)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)

---

## 📝 Descripción

Este proyecto presenta una serie de tarjetas estadísticas que revelan información detallada (cifras, porcentajes y gráficos de barras) únicamente mediante la interacción del usuario (clic o hover). El objetivo es mantener una interfaz visualmente limpia al inicio, evitando la saturación de datos, mientras se provee información profunda bajo demanda.

El diseño se centra en transmitir conceptos de biología marina, tecnología ambiental y ciencia, utilizando una paleta de colores acuícola profesional.

---

## 🚀 Características

-   **Diseño Minimalista:** Interfaz limpia que oculta la complejidad de los datos.
-   **Interactividad Fluida:** Animaciones suaves de entrada, revelado de contenido y gráficos animados sin librerías pesadas.
-   **Totalmente Responsivo (Mobile First):** Adaptado perfectamente a teléfonos, tablets y escritorios mediante CSS Grid y Flexbox.
-   **Gráficos CSS/SVG Ligeros:** Visualización de datos mediante barras generadas dinámicamente sin Canvas ni D3.js.
-   **Accesibilidad:** Navegación por teclado y contrastes de color adecuados.
-   **Sin Dependencias:** HTML5, CSS3 y Vanilla JavaScript puro.

---

## 🛠️ Tecnologías Utilizadas

El proyecto ha sido desarrollado utilizando tecnologías web estándar, sin frameworks ni librerías externas (Bootstrap, Tailwind, React, etc., están prohibidos en este proyecto).

-   **HTML5 Semántico:** Estructura del documento (`<article>`, `<section>`, `<header>`, etc.).
-   **CSS3 Moderno:**
    -   Variables CSS (`:root`) para gestión de paleta de colores.
    -   CSS Grid y Flexbox para el layout.
    -   Transiciones y transformaciones para micro-interacciones.
-   **Vanilla JavaScript (ES6+):** Manipulación del DOM y lógica de eventos.
-   **Tipografía:** Montserrat (Títulos) y Open Sans (Cuerpo) vía Google Fonts.

---

## 📂 Estructura del Proyecto

El código está contenido en su mayoría en un solo archivo para facilitar el despliegue rápido, pero se recomienda separarlo para mantenimiento a largo plazo.

```text
/mi-proyecto-trucha
│
├── README.md              # (Este archivo)
├── index.html             # Estructura HTML principal + Estilos CSS embebidos + Script JS embebido
├── style.css              # (Opcional) Archivo de estilos si se decide separar
├── script.js              # (Opcional) Archivo de lógica si se decide separar
└── data/                  # (Futuro) Carpeta para JSON o CSV externos
    └── datos_trucha.json  # Archivo de datos simulados para conectar vía fetch()
```

---

## 💻 Cómo visualizar localmente

Dado que es un proyecto estático basado únicamente en el navegador, no requiere instalación de Node.js, Python ni servidores de base de datos.

### Opción 1: Abrir directamente (Método más rápido)

1.  Descarga o copia el código proporcionado en un archivo llamado `index.html`.
2.  Haz doble clic en el archivo `index.html`.
3.  La infografía se abrirá automáticamente en tu navegador predeterminado (Chrome, Firefox, Edge, Safari).

### Opción 2: Usar un servidor local (Live Server)

Si estás usando Visual Studio Code o similar, se recomienda usar una extensión como "Live Server" para una experiencia de desarrollo más fluida:

1.  Abre la carpeta del proyecto en tu editor de código.
2.  Instala la extensión **Live Server**.
3.  Haz clic derecho en `index.html` y selecciona **"Open with Live Server"**.

---

## 🎨 Guía de Uso e Interacción

1.  **Estado Inicial:** Verás una cuadrícula de tarjetas con iconos, títulos y descripciones breves. Los datos numéricos están ocultos.
2.  **Hover (Escritorio):** Al pasar el mouse sobre una tarjeta, esta se elevará ligeramente y mostrará una sombra suave.
3.  **Click / Tap:** Haz clic en cualquier tarjeta (o presiona Enter si navegas con teclado) para:
    -   Expandir la tarjeta (efecto focus).
    -   Revelar las estadísticas principales (números destacados).
    -   Animar las barras del gráfico inferior mostrando tendencias o comparaciones.

---

## 🔌 Conexión de Datos Externos (JSON/CSV)

El código JavaScript está preparado para recibir datos dinámicos en lugar de estar "hardcoded" (escritos directamente en el HTML). Para implementar esto:

1.  Crea un archivo JSON en la carpeta `data/`.
2.  En la sección `<script>` de `index.html`, busca la función comentada `loadData()`.
3.  Descomenta el bloque y asegúrate de que tu JSON tenga la siguiente estructura por objeto:

```json
[
  {
    "id": 1,
    "icon": "🐟",
    "title": "Densidad de Población",
    "description": "Texto descriptivo corto...",
    "statHighlight": "15 - 20 kg/m³",
    "statDetail": "Explicación técnica...",
    "chartValues": [60, 80, 40],
    "chartLabels": ["15kg", "20kg", "Min"]
  }
]
```

---

## 📚 Créditos y Fuentes

Este proyecto se ha basado en información técnica y científica reconocida:

**Fuente Bibliográfica:**
> Mendoza Bojorquez, R. J., & Palomino Ramos, A. R. (2004). Manual de cultivo de trucha arco iris en jaulas flotantes. Fondo Nacional de Desarrollo Pesquero (FONDEPES) & Agencia Española de Cooperación Internacional (AECI).

**Diseño y Desarrollo:**
> Diseñado por: Ronald Fabrizio Aguirre Paricahua

---

## 📄 Licencia

Este proyecto es de código abierto y está disponible para fines educativos y científicos.
```
## 📝 Licencia

MIT — Puedes usar, modificar y distribuir este archivo libremente con atribución al diseñador original.
```
