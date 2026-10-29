# El Aleph · Librería y café

Sitio web de El Aleph, una librería clásica con café en Medellín. Vende libros nuevos y usados, ofrece intercambio de libros, la suscripción mensual "El Universo en una Caja", envíos a domicilio, club de lectura, talleres de escritura, lanzamientos con autores y noches de jazz los sábados.

El nombre viene del cuento "El Aleph" de Jorge Luis Borges: un punto que contiene todo el universo, como una librería contiene todos los mundos.

## Páginas
- `index.html`: inicio, presenta la librería y su ambiente.
- `servicios.html`: libros, café, comunidad y agenda semanal.
- `contacto.html`: formulario de contacto con validación nativa, dirección y horario.

## Tecnologías
- HTML5 semántico y accesible.
- CSS con framework (Bootstrap o Tailwind): se agregará más adelante.

## Sitio publicado
https://yulianadurangoh.github.io/el-aleph/


## Comparación: CSS propio vs Bootstrap

Sección migrada: **"Lo que encontrarás"** (inicio), con tres tarjetas: Libros, Café y Comunidad y eventos.

| Criterio | CSS propio | Bootstrap |
| --- | --- | --- |
| Líneas de código escritas | 5 líneas de CSS en la regla `.tarjetas` (Grid con `repeat(auto-fit, minmax(250px, 1fr))` y `gap`). El HTML solo agrega un `div`. | 0 líneas de CSS. En el HTML, 1 fila (`row g-4`) y 3 columnas (`col-12 col-md-6 col-lg-4`) con `h-100` en cada tarjeta: 3 `div` más. |
| Tiempo invertido | Unos 20 minutos (semana 2, día 1), con guía. | Unos minutos, con guía. |
| Facilidad para hacer cambios | Hay que editar `styles.css`; las columnas se calculan solas según el espacio. | Se cambian clases en el HTML (por ejemplo `col-lg-3` para 4 columnas); no hay que tocar el CSS. |
| Legibilidad del HTML | Más limpio: un `div` y los `article`. | Más largo: cada tarjeta va dentro de un `div` con varias clases. |
| Conclusión | Más control y HTML más limpio, pero hay que escribir y mantener el CSS. | Más rápido de armar y de cambiar entre breakpoints, a cambio de un HTML más cargado. |

Conflictos que encontré al agregar Bootstrap:
- Los títulos `h3` de las tarjetas se ven más grandes: Bootstrap les da su propio tamaño.
- La imagen de la portada quedó pegada al título y al texto: el reboot de Bootstrap quita márgenes.
- Los colores y las fuentes de la marca se mantienen porque `styles.css` se carga después de Bootstrap.

**Decisión:** para las tarjetas del sitio, Bootstrap me ahorra tiempo y hace fácil cambiar las columnas por breakpoint. Mantengo `styles.css` para la identidad visual (colores, tipografía, fondo y bordes de las tarjetas).