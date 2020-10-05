# Agregando scripts de Bootstrap para interactividad

En la sección de inicio de la documentación de Bootstrap, nosotros encontramos
los links para el código fuente del CSS de este framework y los agregamos a
nuestro HTML. Lo mismo sucede con JavaScript. En esta ocasión, nosotros no
queremos agregar el CSS de Bootstrap, ahora queremos agregar el JS que este
framework nos provee. Para esto, podemos ir a [esta sección de la documentación](https://getbootstrap.com/docs/4.4/getting-started/introduction/#js)
y copiar los 3 scripts que se listan.

Ahora la pregunta, es dónde lo insertamos en el HTML, ¿en la etiqueta HEAD puesto
que es algo que no se ve? Si bien el razonamiento es completamente válido y
lógico 🤓, existen otras implicaciones relacionadas al rendimiento de una página
web que hace que insertarlo en otra ubicación nos pueda ayudar a tener una mejor
experiencia de usuario.

Donde lo vamos a posicionar es antes de cerrar la etiqueta `</body>` y después de
la última etiqueta que se encuentre dentro de esta.

```html
<body>
  <!-- Todo el código de nuestro HTML viene aquí -->
  <script
    src="https://code.jquery.com/jquery-3.4.1.slim.min.js"
    integrity="sha384-J6qa4849blE2+poT4WnyKhv5vZF5SrPo0iEjwBvKU7imGFAV0wwj1yYfoRSJoZ+n"
    crossorigin="anonymous"
  ></script>
  <script
    src="https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js"
    integrity="sha384-Q6E9RHvbIyZFJoft+2mJbHaEWldlvI9IOYy5n3zV9zzTtmI3UksdQRVvoxMfooAo"
    crossorigin="anonymous"
  ></script>
  <script
    src="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.min.js"
    integrity="sha384-wfSDF2E50Y2D1uUdj0O3uMBJnjuUD4Ih7YwaYd1iqfktj0Uod8GCExl3Og8ifwB6"
    crossorigin="anonymous"
  ></script>
</body>
```

:::tip

Si quieres conocer los fundamentos de porqué es mejor ingresar la etiqueta
`<script></script>` antes de cerrar el body del HTML, puedes leer esta
[pregunta y respuesta de Stack Overflow](https://es.stackoverflow.com/questions/25088/cu%C3%A1l-es-el-mejor-lugar-para-colocar-los-tag-scripts-src-en-html).

:::

Si recargas ahora la página, al darle click al menú hamburguesa desde la vista
de un móvil, ¡verás que funciona! 😉.
