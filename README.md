# El Aleph · Librería y café

Sitio web de El Aleph, una librería clásica con café en Medellín. Vende libros nuevos y usados, ofrece intercambio de libros, la suscripción mensual "El Universo en una Caja", envíos a domicilio, club de lectura, talleres de escritura, lanzamientos con autores y noches de jazz los sábados.

El nombre viene del cuento "El Aleph" de Jorge Luis Borges: un punto que contiene todo el universo, como una librería contiene todos los mundos.

## Páginas
- `index.html`: inicio, presenta la librería y su ambiente.
- `servicios.html`: libros, café, comunidad y agenda semanal.
- `contacto.html`: formulario de contacto con validación nativa, dirección y horario.

## Tecnologías
- HTML5 semántico y accesible.
- CSS propio con variables (`css/styles.css`).
- Bootstrap 5.3.8 y Bootstrap Icons 1.13.1 por CDN, personalizados con la paleta de El Aleph.

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
## Landing page con Bootstrap

En el inicio (`index.html`) usé estos componentes de Bootstrap:
- Navbar que se vuelve menú ☰ en celular.
- Cards en "Lo que encontrarás", con íconos de Bootstrap Icons.
- Formulario para reservar mesa en la noche de jazz, con la validación de Bootstrap.
- Modal con las políticas de reserva y una alerta con el horario del jazz.

Para ponerle los colores de El Aleph:
- Cambié las variables `--bs-*` en `:root` (color principal Madera, fondo Crema y letra Lora).
- Los botones tienen sus propias variables (`--bs-btn-*`), por eso los cambié aparte.
- Hice clases propias: `.encabezado-bootstrap`, `.card-aleph` y `.titulo-seccion`.

Problemas que tuve con mi CSS anterior:
- La regla `header` tenía Flexbox y desacomodaba la navbar. Lo arreglé con la clase `.encabezado-bootstrap`.
- La regla `button` ponía oscuro el botón ☰ y la X al pasar el mouse. Los dejé con fondo transparente.
- Los bordes de los campos casi no se veían sobre el fondo crema. Los puse Gris Piedra.
