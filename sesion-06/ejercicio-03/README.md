# Recuperando los estilos de la barra de navegación

Comencemos por indicarle a la barra de navegación que ocupe todo el ancho de la
pantalla para que no se quede cortado como está en este momento.

Si analizamos los estilos que tiene la etiqueta `nav`, nos daremos cuenta que
tiene un estilo que limita su ancho al 70% del ancho de su contendor:

![Estilos de la barra de navegación](../assets/devtools-navbar.png)

Y como bien indica las herramientas de desarrollo, son estilos que se aplicaron
en el archivo `styles.css` que nosotros creamos.

:::tip

¿Por qué se puede haber originado este error? Resulta que Bootstrap utiliza una
clase llamada `navbar` para ponerle sus propios estilos, y nosotros
coincidentemente usamos el mismo hombre, sin embargo, al momento de nosotros
poner los estilos de Bootstrap antes que el nuestro (al momento que pusimos las
etiquetas `<link />` en el HTML), nuestros estilos terminan predominando sobre
los de Bootstrap a pesar de tener el mismo nombre.

:::

Eliminando el ancho de la clase `.navbar` quedaría así:

```css
.navbar {
  text-align: center;
  color: #025157;
  font-weight: 500;
}
```

Resultando en la barra de navegación tomando el ancho disponible del contenedor:

![Barra de navegación con el ancho habitual](../assets/navbar-width.png)

Lo siguiente que corregiremos será el color, ya que ha tomado un color gris que
la mayoría de componentes de Bootstrap usa por defecto. Para esto, no es
necesario sobreescribir los estilos en la clase `.navbar` ya que en si, el color
de fondo viene dada po una clase utilitaria de Bootstrap que nosotros pegamos
en nuestro código al usar el ejemplo de la documentación oficial de Bootstrap.

Dicha clase es `bg-light` que está añadida a la etiqueta `<nav></nav>`.
Quitándola de la lista de clases que tiene esta etiqueta, recuperaremos el color
original de la barra.

Quedando nuestra etiqueta nav de la siguiente forma:

```html
<nav class="navbar navbar-expand-lg navbar-light">
  <!-- resto del código -->
</nav>
```

:::tip

Si deseas saber que otras clases relacionadas con los colores de fondo existen
en Bootstrap, puedes consultar [esta sección de la documentación](https://getbootstrap.com/docs/4.4/utilities/colors/#background-color).

:::

Ahora procedamos a corregir el alineamiento del menú de navegación, ya que
aparece apegada al logo en la parte izquierda de la pantalla y debería de estar
alineado al centro del espacio disponible del contenedor. Para esto, debemos de
modificar los estilos de la etiqueta `<ul></ul`. Dicha etiqueta en estos
momentos tiene 2 clases (`navbar-nav` y `mr-auto`), la primera clase `navbar-nav`
es importante para poder indicar que los elementos de dicha lista son los que
conformarán el menú de navegación, mientras que la segunda clase `mr-auto` indica
que dicha lista debe tener un margen derecho automático, y dado que los elementos
de la lista Bootstrap les asigna un `display: block;` podemos alinear su
contenido aplicando un margen automático a cada lado, Bootstrap nos permite hacer
dicho comportamiento a través de una clase llamada `mx-auto`. Por lo tanto,
reemplazaremos la clase `mr-auto` por `mx-auto`:

```html
<ul class="navbar-nav mx-auto">
  <!-- lista del menú de navegación -->
</ul>
```

:::tip

Si deseas saber qué otras clases utilitarias relacionas a espaciado que tiene
Bootstrap para ti, puedes revisar [esta sección de la documentación](https://getbootstrap.com/docs/4.4/utilities/spacing/).

:::

Resultando en:

![Menú de navegación centrado](../assets/navbar-centered.png)

Para terminar de cambia la barra de navegación a como estaba originalmente, nos
falta corregir los estilos de la sección de acciones, y si analizamos un poco
los estilos que teníamos anteriormente, nos daremos cuenta que sus estilos
dependían de la clase de su contenedor llamada `actions`. Así que para no
sobreescribir ningún estilo o escribir una clase nueva, podemos tomar la clase
que nosotros habíamos creado y agregársela a las clases que actualmente tiene el
formulario, resultando de la siguiente manera:

```html
<form class="form-inline my-2 my-lg-0 actions">
  <!-- acciones -->
</form>
```

Como último detalle de las acciones, podemos notar que el espacio que existe
hacia el lado derecho entre el botón y el borde del navegador es más grande que
el espacio entre el logo y el borde izquierdo del navegador. Esto sucede debido
a que la clase `form-inline` convierte al formulario en un _flex container_ y le
asigna que debe estar el contenido alineado al centro horizontalmente, mientras
que nosotros necesitaríamos que se alínea hacia el final de su eje horizontal,
normalmente lograríamos esto usando `justify-content: flex-end;`, dado que
usamos Bootstrap, podemos hacer uso de una clase llamada `justify-content-end`:

```html
<form class="form-inline my-2 my-lg-0 actions justify-content-end">
  <!-- acciones -->
</form>
```

:::tip

Si deseas saber qué otras clases relacionadas a Flexbox tiene Bootstrap para ti,
puedes revisar [esta sección de la documentación](https://getbootstrap.com/docs/4.4/utilities/flex/#justify-content).

:::

Con estos cambios la mayoría de estilos debería de volver a verse similar a como
lo teníamos antes:

![Barra de navegación con estilos](../assets/navbar-styled.png)
