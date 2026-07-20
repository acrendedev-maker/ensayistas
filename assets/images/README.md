# Fotos de Ensayistas

Esta carpeta tiene imágenes de ejemplo (los bloques de colores con texto) que debes
reemplazar por las fotos reales del grupo. Cada archivo debe llamarse **exactamente
igual** (mismo nombre, misma extensión `.jpg`) para que el sitio las use automáticamente,
sin tener que tocar el código.

| Archivo a crear/reemplazar | Dónde se usa | Tamaño recomendado |
|---|---|---|
| `hero.jpg` ✅ ya cargada | Foto de portada, fondo de la sección de inicio | Horizontal, mínimo 1600×1000px |
| `about.jpg` ✅ ya cargada | Foto del grupo en la sección "Sobre nosotros" | Vertical u horizontal, mínimo 900×1100px |
| `gallery-1.jpg` ✅ ya cargada | Primera foto de la galería | Cuadrada, mínimo 800×800px |
| `gallery-2.jpg` ✅ ya cargada | Segunda foto de la galería | Cuadrada, mínimo 800×800px |
| `gallery-3.jpg` ✅ ya cargada | Tercera foto de la galería | Cuadrada, mínimo 800×800px |
| `gallery-4.jpg` ✅ ya cargada | Cuarta foto de la galería | Cuadrada, mínimo 800×800px |
| `gallery-5.jpg` ✅ ya cargada | Quinta foto de la galería | Cuadrada, mínimo 800×800px |
| `gallery-6.jpg` ✅ ya cargada | Sexta foto de la galería | Cuadrada, mínimo 800×800px |

## Pasos para reemplazar una foto

1. Elegí la foto real que quieras usar (por ejemplo, para la portada).
2. Renombrala exactamente como el archivo que vas a reemplazar, por ejemplo `hero.jpg`.
3. Copiala en esta carpeta (`assets/images/`), reemplazando el archivo existente.
4. Guardá y recargá la página en el navegador para ver el cambio.

## Agregar más fotos a la galería (carrusel automático)

La galería es una cinta que se mueve sola y repite el mismo set de fotos en loop.
Por eso cada foto aparece **dos veces** en `index.html` (sección `#galeria`, dentro
de `#carouselTrack`... busca `class="gallery-track"`): una vez en el primer bloque
de fotos, y otra vez al final marcada con `aria-hidden="true" tabindex="-1"` (esa
copia es solo para que el loop no se corte, no hace falta que la edites a mano
salvo para agregar la foto nueva ahí también).

Pasos para sumar una foto (por ejemplo `gallery-7.jpg`):

1. Copiá tu foto a esta carpeta como `gallery-7.jpg`.
2. En `index.html`, copiá un bloque `<button class="gallery-item">...</button>`
   del primer grupo (sin `aria-hidden`) y pegalo al final de ese grupo, cambiando
   el nombre del archivo a `gallery-7.jpg`.
3. Copiá también un bloque de los que tienen `aria-hidden="true" tabindex="-1"`
   y pegalo al final del segundo grupo (el duplicado), con el mismo `gallery-7.jpg`.
4. En `css/style.css`, buscá `--set-width` (hay 3 lugares: el general y los dos
   `@media`) y actualizá el múltiplo según la cantidad total de fotos reales.
   Por ejemplo, con 7 fotos: en desktop (4 visibles) sería
   `calc(175cqw + 1.75 * var(--gap))`, y en mobile/tablet (2 visibles) sería
   `calc(350cqw + 3.5 * var(--gap))`. La fórmula general es:
   `(cantidad de fotos / fotos visibles) * (100cqw + gap)`.
