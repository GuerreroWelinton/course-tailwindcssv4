# Apuntes de Tailwind CSS

Este archivo contiene notas y conceptos importantes sobre Tailwind CSS que se han ido recopilando durante el aprendizaje.

---

## Estilos Base

Al importar Tailwind con `@import 'tailwindcss'`, se aplica un reseteo de estilos (similar a `normalize.css`) para asegurar consistencia entre navegadores.

---

## Colores y Fondos

- `bg-[#fff]`: Color hexadecimal.
- `bg-slate-50`: Usando la paleta de colores de Tailwind.

### Opacidad

- `bg-[#989898]/40`: Usando la sintaxis de color con canal alfa.
- `bg-[rgba(45,12,62,0.5)]`: Usando `rgba`.
- `text-black/50`: Opacidad aplicada al color del texto.

---

## Direcciones (Padding, Margin, etc.)

- `t`: `top`
- `r`: `right`
- `b`: `bottom`
- `l`: `left`
- `x`: Eje horizontal (`left` y `right`).
- `y`: Eje vertical (`top` y `bottom`).

---

## Gradientes

- `bg-gradient-to-r from-yellow-500 to-green-500`: Gradiente lineal a la derecha.
- `bg-gradient-to-tl`: Gradiente a la esquina superior izquierda (`top-left`).
- `bg-radial from-yellow-500 to-green-500`: Gradiente radial.
- `bg-[linear-gradient(to_right,#3b82f6,#ffffff)]`: Gradiente personalizado.

**Nota:** `bg-gradient-to-r` es un atajo para `bg-linear-gradient-to-r`.

---

## Ancho y Alto (Width and Height)

La escala de Tailwind se basa en múltiplos de `0.25rem` (4px).

- `w-1` / `h-1` = `0.25rem` (4px)
- `w-2` / `h-2` = `0.5rem` (8px)
- `w-64` / `h-64` = `16rem` (256px)

### Valores Personalizados

- `w-[2px]`
- `h-[4rem]`

---

## Padding y Margin

Siguen la misma escala de espaciado que `width` y `height`.

- `p-1`, `p-2`, etc.
- `m-1`, `m-2`, etc.

---

## Tipografía

### Font Family

- `font-sans`
- `font-serif`
- `font-mono`
- `font-[Georgia]`

### Text Align

- `text-left`
- `text-center`
- `text-right`

### Font Size

- `text-xs`
- `text-sm`
- `text-base`
- `text-lg`
- `text-xl`, `text-2xl`, etc.

---

## Clases Personalizadas

Para clases que en CSS usan espacios, en Tailwind se deben reemplazar con guiones bajos `_`.
Ejemplo: `font-[Times_New_Roman]`

---

## Flexbox

- `flex`: `display: flex;`
- `justify-center`: `justify-content: center;`
- `items-center`: `align-items: center;`
- `flex-row`: `flex-direction: row;`
- `flex-col`: `flex-direction: column;`

---

## Grid

- `grid`: `display: grid;`
- `grid-cols-2`: `grid-template-columns: repeat(2, minmax(0, 1fr));`
- `col-span-2`: `grid-column: span 2 / span 2;`

## Breakpoints

El diseño debe ser **mobile-first**, y luego escalar a pantallas más grandes.

- `sm`: `>= 640px` (40rem)
- `md`: `>= 768px` (48rem)
- `lg`: `>= 1024px` (64rem)
- `xl`: `>= 1280px` (80rem)
- `2xl`: `>= 1536px` (96rem)

Se pueden aplicar estilos a un rango específico, por ejemplo, solo en `md` hasta `lg`:
`md:max-lg:text-center`

---

## Posicionamiento y z-index

- `relative` -> `position: relative;`
- `absolute` -> `position: absolute;`
- `bottom-0` -> `bottom: 0px;`
- `top-5` -> `top: 1.25rem; /* 20px */`
- `bottom-[-40px]` -> `bottom: -40px;`
- `-top-5` -> `top: -1.25rem; /* -20px */`
- `-bottom-[-40px]` -> `bottom: 40px; /* doble negación: signo invertido */`

- `z-1` -> `z-index: 1;`
- `z-5` -> `z-index: 5;`
- `-z-1` -> `z-index: -1;`
- `-z-5` -> `z-index: -5;`

> Nota: Algunas utilidades como `z-1`/`z-5` pueden no estar disponibles por defecto en la configuración estándar de Tailwind; se pueden añadir en `tailwind.config.js` si las necesitas.

---

## Bordes y border-radius

- `rounded-xs` -> `border-radius: 2px;`
- `rounded-full` -> crea un círculo si el elemento es cuadrado (`border-radius: 9999px;`)
- `rounded-[5px]` -> `border-radius: 5px;`
- `rounded-tr-4xl` -> `border-top-right-radius: 2.5rem; /* 4xl en la escala de Tailwind */`

Consejos:

- Para radios personalizados usa la sintaxis `rounded-[<valor>]` con la unidad deseada.
- Para radios en esquinas específicas usa `rounded-tr-*`, `rounded-bl-*`, etc.

---

## Hover y Transiciones

### Hover

- `hover:bg-slate-600` -> Aplica `background-color: rgb(71 85 105);` al hacer hover sobre el elemento.
- Puedes usar el modificador `hover:` con cualquier clase de Tailwind para aplicar estilos al pasar el cursor.

### Transiciones

- `transition-all` -> Aplica `transition-property: all;` con una duración predeterminada de 150ms.
- `duration-300` -> `transition-duration: 300ms;`
- `ease-linear` -> `transition-timing-function: linear;`
- `ease-in`, `ease-out`, `ease-in-out` -> Otras funciones de temporización disponibles.

Ejemplo completo:

```html
<div class="transition-all duration-300 ease-linear hover:bg-slate-600">
  Elemento con transición
</div>
```

---

## Sombras (Box Shadow)

- `shadow-2xl` -> Aplica un `box-shadow` extra grande predefinido.
- `shadow-md`, `shadow-lg`, `shadow-sm` -> Diferentes tamaños de sombra disponibles.
- `shadow-sky-200` -> Cambia el color de la sombra usando la paleta de colores de Tailwind (ej: `sky-200`).
- `shadow-[<valor>]` -> Sombra personalizada usando sintaxis CSS estándar.

Ejemplos:

- `shadow-md shadow-black` -> Sombra mediana de color negro.
- `shadow-lg shadow-blue-500/50` -> Sombra grande azul con 50% de opacidad.
- `shadow-[0_10px_20px_rgba(0,0,0,0.3)]` -> Sombra completamente personalizada.
