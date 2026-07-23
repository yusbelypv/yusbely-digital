# Arquitectura CSS - Yusbely Digital

## Introducción

El proyecto Yusbely Digital utiliza una arquitectura CSS basada en principios de Design System.

El objetivo de esta estructura no es solamente definir estilos visuales, sino crear un sistema organizado, escalable y mantenible que permita que el proyecto pueda crecer sin perder consistencia.

En lugar de crear estilos aislados para cada elemento de la página, el sistema utiliza variables globales, componentes reutilizables y una organización clara del código.

Esta metodología permite:

- Mantener una identidad visual consistente.
- Facilitar futuras modificaciones.
- Reducir código repetido.
- Mejorar la legibilidad del proyecto.
- Facilitar el trabajo colaborativo con otros desarrolladores.

---

# Estructura general del archivo style.css

El archivo principal de estilos está organizado en nueve secciones:

```
style.css

1. CSS Variables
2. CSS Reset
3. Base Styles
4. Typography
5. Layout
6. Components
7. Sections
8. Utilities
9. Media Queries
```

Cada sección tiene una responsabilidad específica dentro del sistema visual del proyecto.

Esta organización permite que cualquier persona que revise el código pueda comprender rápidamente cómo está construido el diseño.

---

# 1. CSS Variables

## Objetivo

Las variables CSS funcionan como los valores centrales del sistema de diseño.

En esta sección se almacenan elementos importantes como:

- Colores de marca.
- Colores secundarios.
- Tipografía.
- Tamaños de texto.
- Espaciados.
- Sombras.
- Bordes.
- Animaciones.

Ejemplo:

```css
--color-primary: #9065B0;
```

En lugar de repetir directamente un color dentro del código:

```css
color: #9065B0;
```

el proyecto utiliza:

```css
color: var(--color-primary);
```

## Beneficios

Esta metodología permite realizar cambios globales de manera rápida.

Por ejemplo, si en el futuro cambia la identidad visual de la marca, solamente sería necesario actualizar las variables principales sin modificar cientos de líneas de CSS.

---

# 2. CSS Reset

## Objetivo

El CSS Reset elimina los estilos predeterminados que aplican los navegadores.

Cada navegador interpreta algunos elementos de forma diferente, agregando márgenes, tamaños o comportamientos automáticos.

El reset crea una base limpia donde todos los estilos son controlados por el proyecto.

Incluye:

- Eliminación de márgenes predeterminados.
- Control del modelo de cajas.
- Normalización de imágenes.
- Configuración inicial de enlaces y elementos generales.

Esto permite tener mayor control sobre el resultado visual final.

---

# 3. Base Styles

## Objetivo

Esta sección define los estilos generales que afectan todo el sitio.

Aquí se establecen reglas globales como:

- Fuente principal.
- Color general del texto.
- Fondo de la página.
- Espaciado base.
- Comportamiento general de elementos HTML.

Son los estilos fundamentales sobre los cuales se construyen todas las demás secciones.

---

# 4. Typography

## Objetivo

La tipografía establece la jerarquía visual del contenido.

No todos los textos tienen la misma importancia, por eso se crean diferentes niveles:

## Hero Title

Utilizado para el título principal del sitio.

Ejemplo:

"Hola, soy Yusbely Parra"

Este elemento tiene mayor tamaño y peso visual porque representa la primera impresión del usuario.

---

## Section Title

Utilizado para los títulos principales de cada sección:

- Sobre mí.
- Mis proyectos.
- Servicios.
- Contacto.

Mantiene una estructura visual uniforme.

---

## Subtitle

Utilizado para textos secundarios importantes que acompañan los títulos principales.

---

## Highlight

Permite destacar palabras importantes utilizando los colores de la marca.

Ejemplo:

UX

Desarrollo Web

Ecommerce

---

# 5. Layout

## Objetivo

La sección Layout controla la distribución y estructura de los elementos dentro de la página.

Para esto se utilizan tecnologías modernas de CSS:

- Flexbox.
- CSS Grid.

Esta sección define:

- Distribución del Hero.
- Organización de columnas.
- Alineación de contenido.
- Estructura de proyectos.
- Estructura de servicios.

---

## Sistema Container

El proyecto utiliza un sistema de contenedores para controlar el ancho máximo del contenido.

La estructura visual sigue este modelo:

```
SECTION

    CONTAINER

        CONTENIDO
```

La sección controla espacios generales y fondos.

El contenedor controla el ancho y alineación del contenido.

Esto permite que el diseño sea más limpio y profesional.

---

# 6. Components

## Objetivo

Los componentes son elementos reutilizables dentro del sistema.

La idea principal es evitar repetir estilos y crear patrones consistentes.

---

## Botones

El sistema utiliza una clase base:

```css
.btn
```

con diferentes variantes:

```css
.btn-primary

.btn-outline
```

Esto permite crear botones con la misma estructura pero diferentes estilos visuales.

Ejemplo:

- Botón principal para contacto.
- Botón secundario para visualizar proyectos.

---

## Cards

Las tarjetas son utilizadas para mostrar:

- Proyectos.
- Servicios.

Incluyen características como:

- Fondo.
- Espaciado interno.
- Bordes redondeados.
- Sombras.
- Animaciones al pasar el cursor.

Esto mejora la experiencia visual del usuario.

---

## Action Links

Son enlaces utilizados para acciones secundarias.

Ejemplo:

"Ver caso de estudio →"

Mantienen una apariencia consistente en todo el sitio.

---

# 7. Sections

## Objetivo

Esta sección contiene estilos específicos para cada parte única del sitio.

Incluye:

- Hero.
- About.
- Projects.
- Services.
- Contact.
- Footer.

A diferencia de los componentes, las secciones representan áreas únicas de la página.

Ejemplo:

```css
#hero
```

solamente existe una vez dentro del proyecto.

---

# 8. Utilities

## Objetivo

Las clases Utilities son pequeñas herramientas reutilizables que permiten aplicar ajustes rápidos.

Ejemplos:

```css
.text-center
```

Permite centrar contenido.

```css
.text-primary
```

Aplica el color principal de la marca.

```css
.hidden
```

Permite ocultar elementos.

Estas clases ayudan a evitar repetir código innecesariamente.

---

# 9. Media Queries

## Objetivo

Las Media Queries permiten que el sitio sea responsive.

El diseño debe adaptarse correctamente a diferentes dispositivos:

- Computadoras.
- Tablets.
- Teléfonos móviles.

---

## Adaptación Tablet

Breakpoint:

```css
max-width:900px
```

Cambios principales:

- El Hero pasa de dos columnas a una sola.
- Los proyectos reducen columnas.
- Los servicios se reorganizan.

---

## Adaptación Mobile

Breakpoint:

```css
max-width:600px
```

Cambios principales:

- Reducción de tamaños tipográficos.
- Elementos organizados en una sola columna.
- Ajustes de espacios para pantallas pequeñas.

---

# Principios del sistema CSS

La arquitectura creada sigue cuatro principios fundamentales:

## 1. Reutilización

Evitar duplicación de código mediante variables y componentes.

---

## 2. Consistencia

Mantener una identidad visual uniforme en todo el proyecto.

---

## 3. Escalabilidad

Permitir agregar nuevas secciones o funcionalidades sin reconstruir el sistema.

---

## 4. Mantenibilidad

Crear un código organizado y fácil de comprender para cualquier desarrollador.

---

# Conclusión

El archivo style.css de Yusbely Digital no funciona solamente como una hoja de estilos.

Funciona como un pequeño Design System personalizado que define:

- La identidad visual.
- La estructura.
- Los componentes.
- La experiencia responsive.

Esta arquitectura permite que el proyecto pueda evolucionar hacia nuevas páginas, productos digitales y futuros desarrollos manteniendo una base profesional y organizada.

El objetivo no es únicamente construir una página web, sino aplicar una metodología de desarrollo utilizada en proyectos reales.
