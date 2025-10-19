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
