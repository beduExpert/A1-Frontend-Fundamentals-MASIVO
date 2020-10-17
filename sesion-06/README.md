# Sesión: Bootstrap

Sigue el contenido a continuación durante clase para que no te pierdas ningún
detalle de lo que estás a punto de aprender.

## Objetivos

En esta sesión aprenderás:

- Usar componentes de Bootstrap para nuestra página.

- Reutilizar clases de Bootstrap.

- Desplegar los cambios a nuestra página web hosteada en Netlify.

## Contenido

### Agregando Bootstrap

#### Concepto: Framework CSS

Antes de continuar con el desarrollo de nuestro proyecto, hemos decidido hacer
una pausa con las demás secciones de la página y darnos el tiempo de refactorizar
ciertas partes haciendo uso de un framework de CSS, ¿pero qué es este último
término?

Hasta ahora, nosotros hemos escrito todo el código CSS para tener nuestro
proyecto como se ve ahora, lo cual está genial porque hemos puesto en práctica
varios conceptos y aprendido un montón de cosas en el camino, pero, ¿te has puesto
a pensar qué tan factible es hacer esto a una empresa en cada proyecto que
desarrolle?

Definitivamente es demasiado tiempo que la mayoría de empresas no está dispuesta
a invertir, o no al menos en cada proyecto, ante esto, muchas empresas y personas
de la comunidad (personas que hacen código CSS como tú) han optado por crear
código que pueda ser reutilizable en más de un proyecto además de una colección
de componentes interactivos que suelen estar presentes en una amplia variedad de
páginas, a dicha colección reutilizable se le denomina **Framework CSS\***.

Usar un framework de CSS puede tener una curva de aprendizaje al inicio que tal
vez te de la sensación que te toma más tiempo que hacer tu proyecto con CSS, sin
embargo, una vez que _le agarres el truco_ verás que tu velocidad de desarrollo
irá incrementando poco a poco. Algo a tener en cuenta es que como la apariencia
de los componentes de cara a las necesidades de los proyectos pueden ser muy
variadas, existen varios frameworks de CSS, que dependiendo de tu proyecto puedes
utilizar, aquí te listamos algunos de los más usados a la fecha:

- [Bootstrap](https://getbootstrap.com/)
- [Materialize](https://materializecss.com/)
- [Foundation](https://get.foundation/)
- [Bulma](https://bulma.io/)
- [Semantic UI](https://semantic-ui.com/)
- [Tailwind CSS](https://tailwindcss.com/)

Como verás, existen más opciones a las que listamos aquí, pero estas suelen ser
de las más usadas, cuando revises cada una de ellas, verás algunas similitudes
en la galería de componentes que tienen disponibles, pero a su vez notarás
diferencias en la apariencia de las mismas. Para nuestro proyecto, usaremos
Bootstrap y a continuación estas son las razones:

- Es un framework muy usado al día de hoy.
- La base de componentes con las que cuenta hace que migrar a otro Framework sea
  un proceso más sencillo.
- Tiene aun buena demanda en el mercado.

Adicionalmente, Bootstrap es un framework desarrollado por Twitter que tiene una
comunidad grande debido al gran uso que tiene en muchos proyectos de diversa
índole, dado esto, hace que las dudas que puedan surgir para lograr ciertos
objetivos sea más sencillo debido al soporte de la comunidad.

#### Guía: Agregando estilos de Bootstrap al proyecto

Ahora que ya sabemos que vamos a usar un framework de CSS y que será Bootstrap,
necesitamos agregarlo a nuestro proyecto para empezar a usarlo.

La forma de agregar Boostrap es a través de links externos que hacen referencia
a un archivo de CSS y algunos archivos de **JavaScript**. Este término puede que
sea nuevo o tal vez lo recuerdes desde el prework de la primera sesión. En
cualquier caso, JavaScript es el único lenguaje de programación que el navegador
soporta nativamente, y es el lenguaje que nos permite agregar interacción y
funcionalidad a nuestra web. En este curso, no estaremos programando en
JavaScript, pero dado que Bootstrap lo usa para ciertos componentes, lo usaremos
a través del framework sin que nosotros necesariamente tengamos que programar.

Empecemos agregando solo el CSS, para esto, debemos ingresar a la sección de
[empezar con Bootstrap](https://getbootstrap.com/docs/4.4/getting-started/introduction/#css),
en el apartado de `CSS` encontraremos una etiqueta `<link />` con una sintaxis
similar a la que nosotros usamos para indicarle a nuestro HTML dónde encontrar
los estilos de nuestra web. Vamos a copiar toda esa línea de código y la vamos
a pegar en nuestro `index.html`. La ubicación en la cual lo peguemos es
importante, dado que `CSS` al ser un lenguaje en cascada, si coincide algún
nombre de clase que usa Boostrap con alguna que nosotros estamos, podríamos
terminar sobreescribiendo los nombres y el que prevalezca dependerá del orden en
el que encuentre nuestras hojas de estilo.

Por lo tanto, nosotros queremos agarrar la mayoría de estilos que Bootstrap nos
trae consigo, pero en caso algo no esté alineado con nuestro diseño, debemos de
personalizarlo, por ello pondremos primero el `<link />` de Bootstrap seguido
por el nuestro, quedando algo como:

```html
<head>
  <!-- Aquí van las otras etiquetas del head -->
  <link
    rel="stylesheet"
    href="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css"
    integrity="sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh"
    crossorigin="anonymous"
  />
  <link rel="stylesheet" type="text/css" href="./styles.css" />
</head>
```

#### Concepto: Etiqueta `<link />`

En las primeras sesiones habíamos revisado la etiqueta `<link />` y alguno de
sus atributos como `rel`, `type` y `href`. Sin embargo, en la nueva etiqueta que
acabamos de añadir, usa un par de atributos más (`integrity` y `crossorigin`).

Ambos atributos son usados para implementar una funcionalidad de seguridad
llamada [integridad de subrecurso](https://developer.mozilla.org/en-US/docs/Web/Security/Subresource_Integrity)
que permiten asegurar que el recurso (CSS) pueda ser obtenido correctamente y no
sufra ningún problema de seguridad cuando el navegador lo descargue en nuestra
página web. Para mayor detalle, puedes revisar [esta respuesta en Stackoverflow](https://stackoverflow.com/questions/32039568/what-are-the-integrity-and-crossorigin-attributes).

---

Con esta etiqueta añadida, ya tenemos los estilos de Bootstrap a nuestra
disposición. Ahora practiquemos el concepto de [refactorización](https://es.wikipedia.org/wiki/Refactorizaci%C3%B3n).

### Refactorizando la barra de navegación

Bootstrap viene con un conjunto de componentes, entre los cuales encontramos la
[barra de navegación](https://getbootstrap.com/docs/4.4/components/navbar/) que
tiene la particularidad de funcionar responsivamente, volviendo el menú de
navegación en una hamburguesa cuando se encuentra en un dispositivo pequeño.

#### Guía: Agregando el navbar

Comencemos por comentar la barra de navegación que actualmente tenemos para
evitar que se mezcle con la barra de navegación de Bootstrap.

```html
<body>
  <!-- Esto es lo que se verá en el navegador web -->
  <!-- <section class="fixed-header">
    <header class="header">
      <a href="/" class="logo">
        <img
          src="https://getmatcha.com/wp-content/themes/getmatcha/img/footer_logo.svg"
          alt="Matcha"
        />
      </a>
      <nav class="navbar">
        <ul class="menu">
          <li class="menu-item">Platform</li>
          <li class="menu-item">Pricing</li>
          <li class="menu-item">Customers</li>
          <li class="menu-item">Resources</li>
          <li class="menu-item">About</li>
        </ul>
      </nav>
      <div class="actions">
        <a>Sign In</a>
        <button>Start free trial</button>
      </div>
    </header>
  </section> -->
</body>
```

De tal forma podemos agregar la [barra de navegación de ejemplo](https://getbootstrap.com/docs/4.4/components/navbar/#supported-content)
que nos da Bootstrap y adaptarla a lo que nosotros necesitamos:

```html
<body>
  <!-- Nuestra barra de navegación comentada va aquí -->
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <a class="navbar-brand" href="#">Navbar</a>
    <button
      class="navbar-toggler"
      type="button"
      data-toggle="collapse"
      data-target="#navbarSupportedContent"
      aria-controls="navbarSupportedContent"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <span class="navbar-toggler-icon"></span>
    </button>

    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav mr-auto">
        <li class="nav-item active">
          <a class="nav-link" href="#"
            >Home <span class="sr-only">(current)</span></a
          >
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Link</a>
        </li>
        <li class="nav-item dropdown">
          <a
            class="nav-link dropdown-toggle"
            href="#"
            id="navbarDropdown"
            role="button"
            data-toggle="dropdown"
            aria-haspopup="true"
            aria-expanded="false"
          >
            Dropdown
          </a>
          <div class="dropdown-menu" aria-labelledby="navbarDropdown">
            <a class="dropdown-item" href="#">Action</a>
            <a class="dropdown-item" href="#">Another action</a>
            <div class="dropdown-divider"></div>
            <a class="dropdown-item" href="#">Something else here</a>
          </div>
        </li>
        <li class="nav-item">
          <a
            class="nav-link disabled"
            href="#"
            tabindex="-1"
            aria-disabled="true"
            >Disabled</a
          >
        </li>
      </ul>
      <form class="form-inline my-2 my-lg-0">
        <input
          class="form-control mr-sm-2"
          type="search"
          placeholder="Search"
          aria-label="Search"
        />
        <button class="btn btn-outline-success my-2 my-sm-0" type="submit">
          Search
        </button>
      </form>
    </div>
  </nav>
</body>
```

Debería verse algo similar a:

![Barra de navegación de ejemplo de Bootstrap agregada](./assets/bootstrap-default-navbar.png)

¡Vamos a adaptarla a lo que necesitamos!

#### Challenge: Personaliza el contenido de tu navbar

Cambia el texto usado en el navbar por defecto al contenido que actualmente
tenemos en nuestra página.

<details>
  <summary>Posible solución</summary>

```html
<body>
  <!-- Nuestra barra de navegación comentada va aquí -->
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <a class="navbar-brand" href="#">
      <img
        src="https://getmatcha.com/wp-content/themes/getmatcha/img/footer_logo.svg"
        alt="Matcha"
      />
    </a>
    <button
      class="navbar-toggler"
      type="button"
      data-toggle="collapse"
      data-target="#navbarSupportedContent"
      aria-controls="navbarSupportedContent"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <span class="navbar-toggler-icon"></span>
    </button>

    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav mr-auto">
        <li class="nav-item active">
          <a class="nav-link" href="#">Platform</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Pricing</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Customers</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Resources</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">About</a>
        </li>
      </ul>
      <form class="form-inline my-2 my-lg-0">
        <a>Sign In</a>
        <button>Start free trial</button>
      </form>
    </div>
  </nav>
</body>
```

Viéndose algo como:

![Barra de navegación de Bootstrap con contenido](./assets/bootstrap-default-navbar-with-content.png)

</details>

Si bien ya tenemos el contenido correspondiente a nuestra barra de navegación,
hay detalles notorios en la apariencia que se perdieron con la introducción de
Bootstrap, así que ahora procederemos a corregirlo para que recupere la
apariencia que tenía antes que usemos Bootstrap.

#### Guía: Recuperando los estilos de la barra de navegación

Comencemos por indicarle a la barra de navegación que ocupe todo el ancho de la
pantalla para que no se quede cortado como está en este momento.

Si analizamos los estilos que tiene la etiqueta `nav`, nos daremos cuenta que
tiene un estilo que limita su ancho al 70% del ancho de su contendor:

![Estilos de la barra de navegación](./assets/devtools-navbar.png)

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

![Barra de navegación con el ancho habitual](./assets/navbar-width.png)

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

![Menú de navegación centrado](./assets/navbar-centered.png)

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

![Barra de navegación con estilos](./assets/navbar-styled.png)

#### Challenge: Revisando el responsive de las acciones del navbar

Si comenzamos por cambiar el tamaño del navegador a uno más pequeño, llegaremos
a un punto en el que nuestra barra de navegación se rompe:

![Estilos de acciones en el navbar rotos](./assets/broken-navbar-actions.png)

<details>
  <summary>Posible solución</summary>

En este caso, el problema viene dado por que la clase `actions` tiene una
propiedad `width` asignándola al 15% del tamaño de su contenedor, y dado que
Bootstrap está usando Flexbox para manejar el ancho de sus elementos, no es
necesaria dicha propiedad. Así que una solución es eliminar dicha propiedad,
quedando la clase `actions` de la siguiente manera:

```css
.actions {
  text-align: right;
  font-weight: 600;
  font-size: 14px;
}
```

</details>

#### Guía: Revisando el responsive del navbar

Si activamos el emulador de responsive para nuestra web veremos que un
comportamiento diferente sucede en nuestra barra de navegación:

![Responsive navbar](./assets/responsive-navbar.png)

¡La barra de navegación no aparece 😱!

Si revisamos los estilos en el devtools, nos daremos cuenta que hay un media
query que se está aplicando a las clases `navbar` y `actions` indicando que
tenga un `display: none;`, así que para solucionar este problema, procederemos
a borrar ese estilo de nuestro media query.

![Responsive navbar mostrándose otra vez](./assets/responsive-navbar-2.png)

Notaremos que ahora tenemos una especie de ícono (comunmente llamado
_menú hamburguesa_) que al darle click debería de mostrarnos el menú, pero dicha
característica aun no funciona. ¿A qué se puede deber?

#### Concepto: Interactividad con JavaScript

Es en este punto donde nos toca hablar de JavaScript. Recordando lo visto en la
primera sesión, habíamos indicado que principalmente existen 3 lenguajes
utilizados en el lado del Front-end: HTML, CSS y JavaScript. Hasta el momento,
nosotros hemos implementado HTML y CSS. Sin embargo, JavaScript, es el que tiene
el poder de agrega dinamismo a una página web. Esto quiere decir que con este
lenguaje de programación nosotros podemos agregar reacción a eventos (por ejemplo,
cuando damos clic a un botón y queremos que mande un mensaje o muestre una
sección oculta), entre muchas otras funcionalidades.

Dado que ahora nosotros queremos que un menú que no está visible se muestre al
darle click a un ícono de menú hamburguesa, esto solo es posible a través de
JavaScript, sin embargo, Bootstrap ha intentado abstraer toda esa funcionalidad
que es común en páginas webs para que nosotros con solo importar su código fuente
podemos obtener toda esa funcionalidad sin escribir una sola línea de JavaScript.

#### Guía: Agregando scripts de Bootstrap para interactividad

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

#### Challenge: Corrige el menú desplegado en un móvil

Ahora con el menú funcionando en dispositivos pequeños, notaremos que la
alineación de las opciones y tal vez el color del texto no se logra a percibir
muy bien, para esto puedes usar algunos estilos en el media query para adaptarlo
como tu prefieras.

![Menú responsive desplegado](./assets/responsive-menu.png)

<details>
  <summary>Posible solución</summary>

Este reto es libre, por ejemplo, en nuestro caso cambiamos el color de fuente de
cada uno de los items del menú para un mejor contraste y cambiamos el color del
menú hamburguesa.

```css
.navbar-light .nav-item .nav-link {
  color: #025157;
}

.navbar-light .navbar-toggler {
  border-color: #025157;
}

.navbar-light .navbar-toggler-icon {
  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' width='30' height='30' viewBox='0 0 30 30'%3e%3cpath stroke='rgb(3, 81, 77)' stroke-linecap='round' stroke-miterlimit='10' stroke-width='2' d='M4 7h22M4 15h22M4 23h22'/%3e%3c/svg%3e");
}
```

</details>

#### Challenge: Volviendo la barra de navegación fija

Recuerdas que la barra de navegación tenía un posicionamiento fijo para que esta
nos acompañe cuando hagamos scroll dentro de la página. ¿Has notado que este
comportamiento ya no está presente? ¿Puedes solucionarlo?

:::tip

Al ser este un caso común, Bootstrap tiene clases utilitarias que pueden ayudar
a lograr este comportamiento. Revisa [esta sección de navbar de la documentación](https://getbootstrap.com/docs/4.4/components/navbar/#placement)
para que te des una idea de qué podrías usar.

:::

<details>
  <summary>Posible solución</summary>

La clase `fixed-top` de Bootstrap nos ayuda a solucionar este problema:

```html
<nav class="navbar navbar-expand-lg navbar-light fixed-top">
  <!-- Contenido de la barra de navegación -->
</nav>
```

Si bien nuestra barra se posiciona como queremos, al momento de hacer scroll nos
damos cuenta que no tiene un color de fondo porque el texto se mezcla con el
resto del contenido de la página. Para esto, podemos agregale un color de fondo
en la clase `.navbar` que tenemos sobreescrita en nuestros estilos:

```css
.navbar {
  background-color: #fffbf7;
  text-align: center;
  color: #025157;
  font-weight: 500;
```

</details>

Ya con esto, podemos proceder a limpiar nuestro HTML y CSS eliminando los
elementos que comentamos en un inicio y los estilos que hemos dejado de usar.

Eso significa que debemos de borrar en el HTML:

```html
<!-- <section class="fixed-header">
  <header class="header">
    <a href="/" class="logo">
      <img
        src="https://getmatcha.com/wp-content/themes/getmatcha/img/footer_logo.svg"
        alt="Matcha"
      />
    </a>
    <nav class="navbar">
      <ul class="menu">
        <li class="menu-item">Platform</li>
        <li class="menu-item">Pricing</li>
        <li class="menu-item">Customers</li>
        <li class="menu-item">Resources</li>
        <li class="menu-item">About</li>
      </ul>
    </nav>
    <div class="actions">
      <a>Sign In</a>
      <button>Start free trial</button>
    </div>
  </header>
</section> -->
```

Y los siguientes estilos:

```css
.fixed-header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  background-color: #fffbf7;
  z-index: 1;
}

.header {
  margin-top: 40px;
  margin-left: 20px;
  margin-right: 20px;
  font-size: 0;
  height: 45px;
  font-family: sans-serif;
}

.header > * {
  display: inline-block;
  font-size: 16px;
  height: 100%;
  vertical-align: middle;
  line-height: 45px;
}

.logo {
  width: 15%;
}

.menu-item {
  display: inline;
  margin-right: 25px;
  margin-left: 25px;
}
```

### Agregando carousel de casos de éxito

En un postwork anterior, habíamos indicado que se realice la estructura de la
sección de casos de éxito usando Flexbox, sin embago, hicimos la acotación de que
la parte del slider no se haga aun, esto debido a que en esta sesión veríamos
cómo realizarlo con Bootstrap.

#### Guía: Agregando carousel de Bootstrap

Al igual que con el navbar, Bootstrap cuenta con un [componente de Carousel](https://getbootstrap.com/docs/4.4/components/carousel/)
que nos permitirá cambiar automáticamente los casos de éxito. Para esto,
comencemos por comentar nuestro código actual del carousel de casos de éxito:

```html
<article class="stories-carousel">
  <!-- <div class="card">
    <div class="card-media">
      <figure>
        <img
          src="https://getmatcha.com/wp-content/uploads/2019/05/profile-headshot-square.png"
          alt="Everly worker"
        />
      </figure>
      <div class="company">
        <img
          src="https://getmatcha.com/wp-content/uploads/2019/05/everly_logo_blue_v3_x60@2x.png"
          alt="Everly"
        />
      </div>
    </div>
    <div class="card-body">
      <h4>Everly</h4>
      <h3>
        Early-Stage CPG Brand Increases Lead Conversion 20x, Ecommerce
        Revenue 20%
      </h3>
      <div class="results">
        <img
          src="https://getmatcha.com/wp-content/themes/getmatcha/img/icon_cart.png"
          alt="Cart icon"
        />
        <p>22% of monthly revenue influenced by content</p>
      </div>
    </div>
    <div class="card-footer">
      <button>See Case Study</button>
    </div>
  </div> -->
</article>
```

Y agreguemos el [código de ejemplo de Bootstrap](https://getbootstrap.com/docs/4.4/components/carousel/#with-indicators),
agregaremos ese ejemplo en particular porque tiene los indicadores que
permitirán manipular el slide que se quiere ver a través de un click:

```html
<article class="stories-carousel">
  <!-- Aquí debería estar el código que acabamos de comentar -->
  <div
    id="carouselExampleIndicators"
    class="carousel slide"
    data-ride="carousel"
  >
    <ol class="carousel-indicators">
      <li
        data-target="#carouselExampleIndicators"
        data-slide-to="0"
        class="active"
      ></li>
      <li data-target="#carouselExampleIndicators" data-slide-to="1"></li>
      <li data-target="#carouselExampleIndicators" data-slide-to="2"></li>
    </ol>
    <div class="carousel-inner">
      <div class="carousel-item active">
        <img src="..." class="d-block w-100" alt="..." />
      </div>
      <div class="carousel-item">
        <img src="..." class="d-block w-100" alt="..." />
      </div>
      <div class="carousel-item">
        <img src="..." class="d-block w-100" alt="..." />
      </div>
    </div>
    <a
      class="carousel-control-prev"
      href="#carouselExampleIndicators"
      role="button"
      data-slide="prev"
    >
      <span class="carousel-control-prev-icon" aria-hidden="true"></span>
      <span class="sr-only">Previous</span>
    </a>
    <a
      class="carousel-control-next"
      href="#carouselExampleIndicators"
      role="button"
      data-slide="next"
    >
      <span class="carousel-control-next-icon" aria-hidden="true"></span>
      <span class="sr-only">Next</span>
    </a>
  </div>
</article>
```

Buscando entender el contenido del HTML del ejemplo de Bootstrap, podemos ver
que primero tenemos una lista ordenada (`<ol></ol>`), dicha lista son los
indicadores que se ven como líneas sobre la imagen para indicar cuál es la que
se está mostrando y cuántos elementos hay dentro del carousel. Seguido
encontramos el `div.carousel-inner` que contiene 3 divs con clase `carousel-item`
que contiene cada uno de los elementos del carousel dentro (en este caso las
etiquetas `<img />`). Por último están 2 enlaces que representan las flechas que
se sobreponen sobre los elementos del carousel para controlar manualmente si
queremos avanzar o retroceder en el carousel.

#### Challenge: Cambiando el contenido del carousel

Una vez revisado la estructura del ejemplo de Bootstrap, debemos de cambiar el
contenido del carousel para que contenga lo que nosotros teníamos. No te
preocupes si los estilos no quedan perfecto, de momento solo nos enfocaremos en
que en vez de imágenes rotas girando en el carousel, debe de ser el contenido que
nosotros estamos esperando ver al final.

:::tip

Recuerda en qué sección del código del ejemplo se ponen los elementos del
carousel para que pongas el código que hemos comentado previamente. Por último,
recuerda que nosotros solo teníamos las imágenes y texto de uno de los elementos
del carousel, usa tus habilidades del manejo de las herramientas de desarrollo
del desarrollo para obtener las imágenes.

:::

<details>
  <summary>Posible solución</summary>

Se debe de reemplazar las imágenes dentro de cada contenedor con clase
`carousel-item` por el contenido que tenemos comentado.

```html
<div class="carousel-inner">
  <div class="carousel-item active">
    <div class="card">
      <div class="card-media">
        <figure>
          <img
            src="https://getmatcha.com/wp-content/uploads/2019/05/profile-headshot-square.png"
            alt="Everly worker"
          />
        </figure>
        <div class="company">
          <img
            src="https://getmatcha.com/wp-content/uploads/2019/05/everly_logo_blue_v3_x60@2x.png"
            alt="Everly"
          />
        </div>
      </div>
      <div class="card-body">
        <h4>Everly</h4>
        <h3>
          Early-Stage CPG Brand Increases Lead Conversion 20x, Ecommerce Revenue
          20%
        </h3>
        <div class="results">
          <img
            src="https://getmatcha.com/wp-content/themes/getmatcha/img/icon_cart.png"
            alt="Cart icon"
          />
          <p>22% of monthly revenue influenced by content</p>
        </div>
      </div>
      <div class="card-footer">
        <button>See Case Study</button>
      </div>
    </div>
  </div>
  <div class="carousel-item">
    <div class="card">
      <div class="card-media">
        <figure>
          <img
            src="https://getmatcha.com/wp-content/uploads/2019/05/profile-headshot-square.png"
            alt="Everly worker"
          />
        </figure>
        <div class="company">
          <img
            src="https://getmatcha.com/wp-content/uploads/2019/05/everly_logo_blue_v3_x60@2x.png"
            alt="Everly"
          />
        </div>
      </div>
      <div class="card-body">
        <h4>Everly</h4>
        <h3>
          Early-Stage CPG Brand Increases Lead Conversion 20x, Ecommerce Revenue
          20%
        </h3>
        <div class="results">
          <img
            src="https://getmatcha.com/wp-content/themes/getmatcha/img/icon_cart.png"
            alt="Cart icon"
          />
          <p>22% of monthly revenue influenced by content</p>
        </div>
      </div>
      <div class="card-footer">
        <button>See Case Study</button>
      </div>
    </div>
  </div>
  <div class="carousel-item">
    <div class="card">
      <div class="card-media">
        <figure>
          <img
            src="https://getmatcha.com/wp-content/uploads/2019/05/profile-headshot-square.png"
            alt="Everly worker"
          />
        </figure>
        <div class="company">
          <img
            src="https://getmatcha.com/wp-content/uploads/2019/05/everly_logo_blue_v3_x60@2x.png"
            alt="Everly"
          />
        </div>
      </div>
      <div class="card-body">
        <h4>Everly</h4>
        <h3>
          Early-Stage CPG Brand Increases Lead Conversion 20x, Ecommerce Revenue
          20%
        </h3>
        <div class="results">
          <img
            src="https://getmatcha.com/wp-content/themes/getmatcha/img/icon_cart.png"
            alt="Cart icon"
          />
          <p>22% of monthly revenue influenced by content</p>
        </div>
      </div>
      <div class="card-footer">
        <button>See Case Study</button>
      </div>
    </div>
  </div>
</div>
```

Y luego cambiar el texto e imágenes de los siguientes elementos en el carousel:

```html
<div class="carousel-inner">
  <div class="carousel-item active">
    <div class="card">
      <div class="card-media">
        <figure>
          <img
            src="https://getmatcha.com/wp-content/uploads/2019/05/profile-headshot-square.png"
            alt="Everly worker"
          />
        </figure>
        <div class="company">
          <img
            src="https://getmatcha.com/wp-content/uploads/2019/05/everly_logo_blue_v3_x60@2x.png"
            alt="Everly"
          />
        </div>
      </div>
      <div class="card-body">
        <h4>Everly</h4>
        <h3>
          Early-Stage CPG Brand Increases Lead Conversion 20x, Ecommerce Revenue
          20%
        </h3>
        <div class="results">
          <img
            src="https://getmatcha.com/wp-content/themes/getmatcha/img/icon_cart.png"
            alt="Cart icon"
          />
          <p>22% of monthly revenue influenced by content</p>
        </div>
      </div>
      <div class="card-footer">
        <button>See Case Study</button>
      </div>
    </div>
  </div>
  <div class="carousel-item">
    <div class="card">
      <div class="card-media">
        <figure>
          <img
            src="https://getmatcha.com/wp-content/uploads/2019/08/0.jpg"
            alt="Seato Summit worker"
          />
        </figure>
        <div class="company">
          <img
            src="https://getmatcha.com/wp-content/uploads/2019/08/SeatoSummitLogo.png"
            alt="Seato Summit Logo"
          />
        </div>
      </div>
      <div class="card-body">
        <h4>Sea to Summit</h4>
        <h3>
          Sea to Summit’s Ecommerce Site Traffic Climbs 189%, New Subscribers
          820%
        </h3>
        <div class="results">
          <img
            src="https://getmatcha.com/wp-content/themes/getmatcha/img/icon_audiences.png"
            alt="Audience icon"
          />
          <p>500% increase in traffic from social media</p>
        </div>
      </div>
      <div class="card-footer">
        <button>See Case Study</button>
      </div>
    </div>
  </div>
  <div class="carousel-item">
    <div class="card">
      <div class="card-media">
        <figure>
          <img
            src="https://getmatcha.com/wp-content/uploads/2019/06/matt-and-margaret_headshot.png"
            alt="Mambe workers"
          />
        </figure>
        <div class="company">
          <img
            src="https://getmatcha.com/wp-content/uploads/2019/06/mambe-logo-1.png"
            alt="Mambe"
          />
        </div>
      </div>
      <div class="card-body">
        <h4>Mambe Waterproof Blankets</h4>
        <h3>
          How Mambe Increased Conversions by 327%, Reduced CPL by 60%
        </h3>
        <div class="results">
          <img
            src="https://getmatcha.com/wp-content/themes/getmatcha/img/icon_target.png"
            alt="Target icon"
          />
          <p>+327% more popup conversions at a 60% lower cost</p>
        </div>
      </div>
      <div class="card-footer">
        <button>See Case Study</button>
      </div>
    </div>
  </div>
</div>
```

</details>

Luego de aplicado los cambios debería quedarr algo similar a:

![Carousel de casos de éxito](./assets/carousel-with-content.png)

Con esto, podemos detectar ciertos detalles que debemos corregir en la
apariencia:

- La flecha de siguiente se sale de la tarjeta y probablemente no la necesitamos.
- Los indicadores no se logran ver aunque no los hemos borrado del código.
- La tarjeta tiene espacios en blanco en la parte superior e inferior.
- El color del botón para ver el caso de estudio tiene un color de fondo que
  antes no tenía.

Procedamos a corregir estos detalles 😎.

#### Guía: Eliminando flechas de control de carousel

Las flechas no las necesitamos y no están encajando bien en el comportamiento
por defecto de nuestro carousel, así que podemos eliminarlos. Como lo habíamos
analizado previamente, las flechas son los elementos `<a></a>` que estaban al
final del carousel, asegúrate de eliminarlos del código:

```html
<a
  class="carousel-control-prev"
  href="#carouselExampleIndicators"
  role="button"
  data-slide="prev"
>
  <span class="carousel-control-prev-icon" aria-hidden="true"></span>
  <span class="sr-only">Previous</span>
</a>
<a
  class="carousel-control-next"
  href="#carouselExampleIndicators"
  role="button"
  data-slide="next"
>
  <span class="carousel-control-next-icon" aria-hidden="true"></span>
  <span class="sr-only">Next</span>
</a>
```

#### Guía: Cambiando de posición a los indicadores del carousel

El siguiente problema a solucionar son los indicadores, ya que estos en realidad
están en la interface, pero dado que por defecto son de color blanco y se
posicionan sobre los elementos del carousel, estos no se logran ver. Podemos
analizar sus estilos por defecto en el devtools:

![Estilos de los indicadores del carousel](./assets/carousel-indicators.png)

Lo que se puede notar de acá es que el valor de la propiedad `position` es
`absolute`, lo cual hace que salga del flujo original del documento, y a través
de la propiedad `bottom: 0` logra ubicarlo en la parte inferior de la tarjeta que
tiene una posición diferente a `static`.

Para poder ubicar los indicadores debajo de los elementos de carousel debemos de
sobreescribir la propiedad `position`:

```css
.success-stories .stories-carousel .carousel-indicators {
  position: initial; /** ó: position: static; */
}
```

:::tip

El valor `initial` hace que la propiedad asignada tome el valor inicial que esta
propiedad fue asignada. Para mayor información puedes consultar la
[documentación oficial de MDN](https://developer.mozilla.org/es/docs/Web/CSS/initial).

:::

Con esto, deberíamos lograr tener un resultado simila a:

![Indicadores de carousel con position static](./assets/carousel-indicators-position.png)

Si bien los indicadores ahora ya no se encuentran sobre la imagen, aparecen en
la parte superior del carousel, esto debido a que respeta el flujo del documento
y en el HTML la lista ordenada de indicadores viene escrita antes de los
elementos del carousel, por lo que tendremos que invertir el orden resultando en
algo como:

```html
<article class="stories-carousel">
  <div
    id="carouselExampleIndicators"
    class="carousel slide"
    data-ride="carousel"
  >
    <div class="carousel-inner">
      <!-- Elementos del carousel van aquí -->
    </div>
    <ol class="carousel-indicators">
      <li
        data-target="#carouselExampleIndicators"
        data-slide-to="0"
        class="active"
      ></li>
      <li data-target="#carouselExampleIndicators" data-slide-to="1"></li>
      <li data-target="#carouselExampleIndicators" data-slide-to="2"></li>
    </ol>
  </div>
</article>
```

Después de este cambio, la posición de los indicadores estará correcta pero aun
veremos que aparenta no estar centrada. Este problema puede deberse a que el
contenedor de los indicadores está tomando un ancho diferente al de las tarjetas.
Y si revisamos los estilos de la clase `.card` encontraremos lo siguiente:

```css
.success-stories .stories-carousel .card {
  max-width: 370px;
  width: 100%;
  background-color: #fff;
  border-radius: 10px;
}
```

Hay un ancho máximo definido, que dependiendo del tamaño de la pantalla que lo
estemos viendo, nos podremos topar con este detalle. Dado que esta propiedad
está indicando que si el ancho del contenedor supera los 370px, se deberá
aplicar esta medida. Si bien es algo que permite una buena apariencia, está
definida en un lugar erróneo, dado que al aplicarse solo a las tarjetas, los
indicadores no toman la misma medida. Podríamos optar por aplicarle la misma
propiedad a los indicadores, pero mejor aun podríamos establer dicha propiedad
a un elemento que contenga tanto a los elementos del carousel como a los
indicadores. Este elemento puede ser el div con clase `carousel` dado que
contiene a todos los elementos que forman parte del carousel y eliminar la
propiedad del elemento `div.card`:

```css
.success-stories .stories-carousel .carousel {
  max-width: 370px;
}

.success-stories .stories-carousel .card {
  width: 100%;
  background-color: #fff;
  border-radius: 10px;
}
```

#### Challenge: Cambiando los estilos de los elementos del carousel

¡Yay! Ya tenemos casi listo nuestro carousel y con interactividad gracias a
Bootstrap. Ahora es tu turno de darle los toques finales. Elimina los espacios
en blanco dentro de las tarjetas y cambia el color y el borde que engloca al
botón de ver los casos de éxito.

<details>
  <summary>Posible solución</summary>

Para eliminar el espacio superior entre la imagen y el borde de la tarjeta,
debemos de eliminar el `margin-top` que todos los elementos `<figure></figure>`
tienen.

```css
.success-stories .stories-carousel figure {
  margin-top: 0;
}
```

Y para elimianr el borde y color de fondo del botón en la parte inferior,
debemos de sobreescribir las propiedads de `background-color` y `border-color`
que Bootstrap le puso por coincidir en el nombre de clase que usan. Para lograr
esto, podemos agregar las propiedades a los estilos que tenemos de la clase
`card-footer`:

```css
.success-stories .stories-carousel .card .card-footer {
  margin-bottom: 20px;
  background-color: transparent;
  border-color: transparent;
}
```

</details>

Listo, con esto nuestro carousel quedó funcionando y viéndose como lo teníamos
previamente. No te olvides de eliminar el código comentado y dado que utilizamos
todos los estilos que declaramos en la primera versión de este código, no es
necesario eliminar ninguna clase o selector de estilos en el CSS.

### Agregando nueva página de precios

En este apartado vamos a agregar una nueva página, que al darle click en el
menú de navegación a la opción de **Pricing** nos redirija a otra página. El
motivo por el que la vamos a usar es porque en dicha página encontramos otros
componentes de Bootstrap que podemos aprender a usar.

#### Guía: Agregando una nueva página

Hasta este momento, todo nuestro código a estado dentro del `index.html` que por
defecto es el archivo que todo navegador busca al acceder a un sitio web, ahora
vamos a crear un nuevo archivo en el que vamos a ir agregando código y también
vamos a reutilizar estilos que hemos venido desarrollando hasta el momento.

Empecemos por crear un nuevo archivo para el HTML y otro parar sus estilos en la
carpeta principal del proyecto:

```sh
$ pwd # asegúrate que sea la carpeta del proyecto
/ruta/al/proyecto
$ touch pricing.html
$ ls
index.html   pricing.html   style.css
$ touch pricing.css
index.html   pricing.html   style.css   pricing.css
```

Ahora, enlacemos la estructura principal de la nueva página (html, head, body):

```html
<!-- pricing.html -->
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta
      name="viewport"
      content="width=device-width,initial-scale=1.0,user-scalable=no"
    />
    <title>Matcha - Pricing</title>
    <link
      rel="stylesheet"
      href="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css"
      integrity="sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh"
      crossorigin="anonymous"
    />
    <link rel="stylesheet" type="text/css" href="./pricing.css" />
  </head>
  <body>
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
</html>
```

En este caso, hemos aprovechado en incluir el enlace al nuevo archivo de CSS que
hemos creado así como a los archivos de estilos y scripts de Bootstrap.

Ahora, dado que la barra de navegación será la misma, agreguemos la estructura
y CSS necesaria de entrada para tener lo mismo que en el `index.html`:

```html{20-62}
<!-- pricing.html -->
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta
      name="viewport"
      content="width=device-width,initial-scale=1.0,user-scalable=no"
    />
    <title>Matcha - Pricing</title>
    <link
      rel="stylesheet"
      href="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css"
      integrity="sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh"
      crossorigin="anonymous"
    />
    <link rel="stylesheet" type="text/css" href="./pricing.css" />
  </head>
  <body>
    <nav class="navbar navbar-expand-lg fixed-top navbar-light">
      <a class="navbar-brand" href="#">
        <img
          src="https://getmatcha.com/wp-content/themes/getmatcha/img/footer_logo.svg"
          alt="Matcha"
        />
      </a>
      <button
        class="navbar-toggler"
        type="button"
        data-toggle="collapse"
        data-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav mx-auto">
          <li class="nav-item active">
            <a class="nav-link" href="#">Platform</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="pricing.html">Pricing</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Customers</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Resources</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">About</a>
          </li>
        </ul>
        <form class="form-inline my-2 my-lg-0 actions">
          <a>Sign In</a>
          <button>Start free trial</button>
        </form>
      </div>
    </nav>
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
</html>
```

```css
/** pricing.css */
@import url("https://fonts.googleapis.com/css?family=Alegreya:900|Open+Sans|Slabo+27px&display=swap");

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background-color: #fffbf7;
  font-family: "Open Sans", sans-serif;
}

.navbar {
  background-color: #fffbf7;
}

.navbar-light .nav-item .nav-link {
  color: #025157;
}

.navbar-light .navbar-toggler {
  border-color: #025157;
}

.navbar-light .navbar-toggler-icon {
  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' width='30' height='30' viewBox='0 0 30 30'%3e%3cpath stroke='rgb(3, 81, 77)' stroke-linecap='round' stroke-miterlimit='10' stroke-width='2' d='M4 7h22M4 15h22M4 23h22'/%3e%3c/svg%3e");
}

.actions {
  text-align: right;
  font-weight: 600;
  font-size: 14px;
}

.actions > * {
  margin-right: 10px;
  margin-left: 10px;
}

.actions a {
  color: #67b54b;
}

.actions button {
  color: white;
  background-color: #67b54b;
  padding-left: 14px;
  padding-right: 14px;
  padding-top: 12px;
  padding-bottom: 12px;
  border: 0;
  border-radius: 5px;
}
```

Con estos estilos y estructura extraídas de nuestro `index.html` obtenemos la
misma barra de navegación.

#### Challenge: Agregando la sección principal

La sección principal de la página es un título y una descripción, parece ser
algo similar a la del `index.html`. ¿Cómo lo harías en esta página?

<details>
  <summary>Posible solución</summary>

```html
<body>
  <!-- Aquí viene la barra de navegación -->
  <main class="container">
    <header class="header">
      <h1>Free During COVID-19</h1>
      <p>
        Matcha is on a mission to make your blog the biggest asset for your
        business’ growth, especially in today’s context. That’s why we’re
        making the Matcha Platform free forever to all new users who sign up
        during COVID-19.
      </p>
  </main>
</body>
```

```css
/** Aquí vienen los estilos definido previamente */
main {
  margin-top: 184px;
  text-align: center;
}

h1 {
  color: #025157;
  font-family: "Alegreya", serif;
  font-size: 60px;
  margin-bottom: 24px;
}

.header {
  padding-bottom: 184px;
}

.header p {
  color: #46484c;
  max-width: 680px;
  margin: 0 auto;
  margin-bottom: 72px;
}
```

</details>

#### Guía: Agregando un grupo de botones

La siguiente parte de la sección principal, tenemos una especie de menú de
opciones que cambian el contenido de la siguiente sección, en este caso, nosotros
no nos vamos a enfocar en cambiar el texto, sino en darle la apariencia.

Para esto, vamos a usar el componente [Button group](https://getbootstrap.com/docs/4.4/components/button-group/#basic-example)
de Bootstrap que tiene una apariencia similar, comencemos por agregar el
subtítulo y pegar el código de ejemplo:

```html{12-19}
<body>
  <!-- Aquí viene la barra de navegación -->
  <main class="container">
    <header class="header">
      <h1>Free During COVID-19</h1>
      <p>
        Matcha is on a mission to make your blog the biggest asset for your
        business’ growth, especially in today’s context. That’s why we’re
        making the Matcha Platform free forever to all new users who sign up
        during COVID-19.
      </p>
      <div class="platforms">
        <h5>MY BLOG IS POWERED BY</h5>
        <div class="btn-group" role="group" aria-label="Basic example">
          <button type="button" class="btn btn-secondary">Left</button>
          <button type="button" class="btn btn-secondary">Middle</button>
          <button type="button" class="btn btn-secondary">Right</button>
        </div>
      </div>
  </main>
</body>
```

Ahora, procedamos a cambiar su contenido. Si te das cuenta los 2 primeros botones
tienen íconos (los cuales cambian de color debido a que son SVGs), para lograrlo
usemos los siguientes:

```html
<!-- Ícono de Shopify -->
<svg width="20" height="21" fill="none" xmlns="http://www.w3.org/2000/svg">
  <path
    fill-rule="evenodd"
    clip-rule="evenodd"
    d="M8.571.038c0 .02-.073.038-.163.038-.09 0-.163.017-.163.037 0 .021-.055.038-.123.038C8.055.151 8 .168 8 .19c0 .02-.037.038-.082.038-.045 0-.081.017-.081.037 0 .021-.033.038-.073.038-.04 0-.099.034-.131.076-.033.041-.088.075-.123.075s-.09.034-.122.076c-.033.041-.083.075-.112.075-.064 0-.99.851-.99.91 0 .023-.055.09-.123.148-.067.058-.122.13-.122.158 0 .028-.037.076-.082.106-.045.03-.081.085-.081.122 0 .037-.019.067-.041.067-.023 0-.041.03-.041.067 0 .037-.037.092-.082.122-.045.03-.081.085-.081.122 0 .037-.019.067-.041.067-.023 0-.041.034-.041.075 0 .042-.018.076-.04.076-.023 0-.042.034-.042.075 0 .042-.018.076-.04.076-.023 0-.041.034-.041.075 0 .042-.019.076-.041.076-.023 0-.04.034-.04.076 0 .041-.02.075-.042.075-.022 0-.04.051-.04.113 0 .063-.019.114-.041.114-.023 0-.041.034-.041.075 0 .042-.019.076-.041.076-.022 0-.04.05-.04.113 0 .062-.02.113-.042.113-.022 0-.04.051-.04.114 0 .062-.019.113-.041.113-.023 0-.041.051-.041.113 0 .063-.018.114-.04.114-.023 0-.042.05-.042.113 0 .062-.018.113-.04.113-.023 0-.041.068-.041.151 0 .083-.019.151-.041.151-.023 0-.04.085-.04.19 0 .184-.004.188-.123.188-.068 0-.123.017-.123.038 0 .02-.055.038-.122.038-.068 0-.123.017-.123.037 0 .021-.055.038-.122.038-.068 0-.123.017-.123.038 0 .02-.073.038-.163.038-.09 0-.163.017-.163.038 0 .02-.055.037-.123.037-.067 0-.122.017-.122.038 0 .02-.055.038-.123.038-.067 0-.122.017-.122.038 0 .02-.055.037-.122.037-.068 0-.123.017-.123.038 0 .02-.055.038-.122.038-.068 0-.123.017-.123.038 0 .02-.073.037-.163.037-.09 0-.163.017-.163.038 0 .021-.037.038-.082.038-.045 0-.082.017-.082.038 0 .02-.028.038-.063.038-.099 0-.263.175-.263.281 0 .053-.018.096-.04.096-.024 0-.042.114-.042.265 0 .15-.017.264-.04.264-.024 0-.041.126-.041.302s-.017.302-.041.302-.041.126-.041.303c0 .176-.017.302-.04.302-.024 0-.042.113-.042.264 0 .151-.017.264-.04.264-.024 0-.041.126-.041.303 0 .176-.017.302-.041.302s-.04.126-.04.302-.018.302-.042.302c-.023 0-.04.126-.04.302 0 .177-.018.302-.041.302-.024 0-.041.114-.041.265 0 .15-.018.264-.041.264-.024 0-.04.126-.04.302 0 .177-.018.303-.042.303-.023 0-.04.125-.04.302 0 .176-.017.302-.041.302s-.041.113-.041.264c0 .151-.018.265-.04.265-.025 0-.042.126-.042.302s-.017.302-.04.302c-.024 0-.041.126-.041.302s-.017.302-.041.302-.04.126-.04.302c0 .177-.018.302-.042.302-.023 0-.04.114-.04.265 0 .151-.018.264-.041.264-.024 0-.041.126-.041.303 0 .176-.017.302-.041.302s-.04.125-.04.302c0 .176-.018.302-.042.302-.023 0-.04.126-.04.302s-.017.302-.041.302-.041.114-.041.265c0 .15-.018.264-.04.264-.025 0-.042.126-.042.302 0 .177-.017.302-.04.302-.024 0-.041.126-.041.302 0 .177-.017.303-.041.303-.023 0-.041.085-.041.189v.188h.204c.112 0 .204.017.204.038 0 .02.092.038.204.038.112 0 .204.017.204.038 0 .02.11.037.245.037.136 0 .245.017.245.038 0 .021.109.038.245.038s.245.017.245.038c0 .02.109.037.245.037s.245.017.245.038c0 .021.092.038.204.038.112 0 .204.017.204.038 0 .02.109.038.245.038s.245.016.245.037c0 .021.109.038.245.038s.244.017.244.038c0 .02.11.038.245.038.136 0 .245.016.245.037 0 .021.11.038.245.038.136 0 .245.017.245.038 0 .02.092.038.204.038.112 0 .204.017.204.037 0 .021.11.038.245.038.136 0 .245.017.245.038 0 .021.109.038.245.038s.245.017.245.038c0 .02.109.037.245.037s.245.017.245.038c0 .021.108.038.245.038.136 0 .244.017.244.038 0 .02.092.037.204.037.113 0 .205.017.205.038 0 .021.108.038.244.038.137 0 .245.017.245.038 0 .02.11.037.245.037.136 0 .245.017.245.038 0 .021.109.038.245.038s.245.017.245.038c0 .02.092.038.204.038.112 0 .204.017.204.037 0 .021.109.038.245.038s.245.017.245.038c0 .02.109.038.245.038s.245.017.245.037c0 .021.109.038.245.038s.244.017.244.038c0 .021.11.038.245.038.136 0 .245.017.245.037 0 .021.092.038.204.038.113 0 .205.017.205.038 0 .021.108.038.244.038s.245.017.245.038c0 .02.11.037.245.037.136 0 .245.017.245.038 0 .021.109.038.245.038s.245.017.245.038c0 .02.092.037.204.037.112 0 .204.018.204.038 0 .021.073.038.163.038h.164v-9.237c0-7.956-.008-9.245-.059-9.292-.067-.062-.186-.072-.186-.016 0 .02-.055.038-.123.038-.067 0-.122.017-.122.038 0 .02-.055.037-.123.037-.067 0-.122.017-.122.038 0 .02-.037.038-.082.038-.054 0-.081-.025-.081-.076 0-.041-.019-.075-.041-.075-.023 0-.041-.051-.041-.113 0-.063-.018-.114-.04-.114-.023 0-.042-.034-.042-.075 0-.042-.018-.076-.04-.076-.023 0-.041-.034-.041-.075 0-.042-.019-.076-.041-.076-.023 0-.04-.034-.04-.076 0-.041-.02-.075-.042-.075-.022 0-.04-.03-.04-.067 0-.037-.037-.092-.082-.122-.045-.03-.082-.076-.082-.103 0-.069-.597-.615-.673-.615-.034 0-.061-.017-.061-.037 0-.021-.037-.038-.082-.038-.045 0-.082-.017-.082-.038 0-.02-.037-.038-.081-.038-.045 0-.082-.017-.082-.037 0-.021-.073-.038-.163-.038-.09 0-.164-.017-.164-.038 0-.021-.117-.038-.269-.038-.247 0-.279-.01-.384-.113-.063-.062-.14-.113-.17-.113-.031 0-.083-.034-.115-.076C10.049.261 9.99.227 9.95.227c-.04 0-.072-.017-.072-.038 0-.02-.037-.038-.082-.038-.045 0-.082-.017-.082-.038 0-.02-.055-.037-.122-.037-.068 0-.123-.017-.123-.038C9.47.015 9.293 0 9.02 0c-.272 0-.449.015-.449.038zm.572.68c0 .02.065.037.146.037.08 0 .173.026.207.057.054.05.054.063 0 .113a.213.213 0 01-.117.057c-.03 0-.081.034-.114.076-.032.041-.082.075-.112.075-.064 0-.5.397-.5.456 0 .024-.055.09-.122.148-.068.059-.123.13-.123.158 0 .029-.037.077-.081.107-.045.03-.082.08-.082.113 0 .032-.037.083-.082.113-.045.03-.081.085-.081.122 0 .037-.019.067-.041.067-.023 0-.041.034-.041.076 0 .041-.018.075-.04.075-.023 0-.042.034-.042.076 0 .041-.018.075-.04.075-.023 0-.041.034-.041.076 0 .042-.019.075-.041.075-.023 0-.04.034-.04.076 0 .042-.02.076-.042.076-.022 0-.04.05-.04.113 0 .062-.019.113-.041.113-.023 0-.041.051-.041.114 0 .062-.019.113-.041.113-.022 0-.04.05-.04.113 0 .062-.02.113-.042.113-.022 0-.04.068-.04.152 0 .083-.019.15-.041.15-.023 0-.041.044-.041.098 0 .124-.088.205-.222.205-.057 0-.105.017-.105.038 0 .02-.055.037-.122.037s-.122.017-.122.038c0 .02-.056.038-.123.038s-.122.017-.122.038c0 .02-.055.037-.123.037-.067 0-.122.017-.122.038 0 .02-.055.038-.123.038-.067 0-.122.017-.122.038 0 .02-.074.037-.163.037-.09 0-.164.017-.164.038 0 .021-.055.038-.122.038-.109 0-.123-.013-.123-.113 0-.063.019-.114.041-.114.023 0 .041-.05.041-.113 0-.062.018-.113.04-.113.023 0 .042-.051.042-.114 0-.062.018-.113.04-.113.023 0 .041-.05.041-.113 0-.062.019-.113.041-.113.023 0 .04-.034.04-.076 0-.042.02-.076.042-.076.022 0 .04-.05.04-.113 0-.062.019-.113.041-.113.023 0 .041-.034.041-.076 0-.041.019-.075.041-.075.022 0 .04-.034.04-.076 0-.041.02-.075.042-.075.022 0 .04-.034.04-.076 0-.041.019-.075.041-.075.023 0 .041-.034.041-.076 0-.042.018-.076.04-.076.023 0 .042-.03.042-.067 0-.037.036-.091.081-.121.045-.03.082-.085.082-.122 0-.037.018-.067.04-.067.023 0 .042-.027.042-.06 0-.034.055-.109.122-.167.067-.058.123-.126.123-.15 0-.026.055-.094.122-.152.067-.058.122-.125.122-.148 0-.059.6-.607.664-.607.03 0 .08-.034.112-.076.032-.041.087-.075.122-.075s.09-.034.123-.076c.032-.042.091-.076.131-.076.04 0 .073-.017.073-.037 0-.021.055-.038.122-.038.068 0 .123-.017.123-.038 0-.02.092-.038.204-.038.112 0 .204-.017.204-.037 0-.021.055-.038.122-.038.068 0 .123.017.123.038zm1.959.68c0 .02.037.037.082.037.045 0 .081.017.081.038 0 .02.028.038.063.038.076 0 .427.318.427.387 0 .027.037.074.082.104.045.03.081.084.081.121 0 .037.019.068.041.068.023 0 .041.034.041.075 0 .042.018.076.04.076.023 0 .042.034.042.075 0 .042.018.076.04.076.023 0 .041.034.041.075 0 .042.019.076.041.076.022 0 .04.05.04.113 0 .088-.017.113-.08.113-.046 0-.082.018-.082.038 0 .021-.056.038-.123.038s-.122.017-.122.038c0 .02-.074.038-.163.038-.09 0-.164.017-.164.037 0 .021-.073.038-.163.038h-.163v-.415c0-.252-.016-.416-.041-.416-.023 0-.041-.1-.041-.226s-.018-.227-.04-.227c-.023 0-.042-.051-.042-.113 0-.063-.018-.114-.04-.114-.023 0-.041-.05-.041-.113 0-.088.018-.113.081-.113.045 0 .082.017.082.037zm-.956.091c.032.03.058.098.058.151 0 .054.018.097.04.097.023 0 .042.068.042.151 0 .084.018.152.04.152.023 0 .041.1.041.226s.018.227.041.227c.025 0 .041.176.041.453v.453h-.123c-.067 0-.122.017-.122.038 0 .02-.055.038-.122.038-.068 0-.123.017-.123.038 0 .02-.055.037-.122.037-.068 0-.123.017-.123.038 0 .02-.055.038-.122.038-.068 0-.123.017-.123.038 0 .02-.073.037-.163.037-.09 0-.163.017-.163.038 0 .021-.055.038-.123.038-.067 0-.122.017-.122.038 0 .02-.055.038-.122.038-.068 0-.123.017-.123.037 0 .021-.055.038-.122.038-.068 0-.123.017-.123.038 0 .02-.055.038-.122.038-.068 0-.123-.017-.123-.038 0-.021.019-.038.041-.038.023 0 .04-.068.04-.151 0-.083.02-.151.042-.151.022 0 .04-.034.04-.076 0-.041.019-.075.041-.075.023 0 .041-.051.041-.113 0-.063.019-.114.041-.114.022 0 .04-.034.04-.075 0-.042.02-.076.042-.076.022 0 .04-.034.04-.075 0-.042.019-.076.041-.076.023 0 .041-.034.041-.076 0-.041.018-.075.04-.075.023 0 .042-.034.042-.076 0-.041.018-.075.04-.075.023 0 .041-.03.041-.067 0-.037.037-.092.082-.122.045-.03.082-.077.082-.106 0-.028.073-.116.163-.196.09-.08.163-.165.163-.189 0-.056.103-.151.164-.151.025 0 .117-.068.203-.151.087-.083.186-.151.222-.151.035 0 .064-.017.064-.038 0-.056.12-.046.187.016zm4.14 10.295v9.14h.122c.068 0 .123-.017.123-.037 0-.021.073-.038.163-.038.09 0 .163-.017.163-.038 0-.02.074-.038.163-.038.09 0 .164-.017.164-.037 0-.021.091-.038.204-.038.112 0 .204-.017.204-.038 0-.02.073-.038.163-.038.09 0 .163-.017.163-.038 0-.02.074-.037.164-.037.09 0 .163-.017.163-.038 0-.02.073-.038.163-.038.09 0 .163-.017.163-.038 0-.02.074-.037.164-.037.09 0 .163-.017.163-.038 0-.02.073-.038.163-.038.09 0 .163-.017.163-.038 0-.02.074-.037.164-.037.09 0 .163-.017.163-.038 0-.02.074-.038.163-.038.09 0 .164-.017.164-.038 0-.02.073-.038.163-.038.09 0 .163-.017.163-.037 0-.021.074-.038.163-.038.09 0 .164-.017.164-.038 0-.02.073-.038.163-.038.09 0 .163-.017.163-.037 0-.021.074-.038.163-.038.09 0 .164-.017.164-.038 0-.02.073-.038.163-.038.09 0 .163-.017.163-.037 0-.021.074-.038.163-.038.09 0 .164-.017.164-.038 0-.02.037-.038.081-.038.075 0 .082-.025.082-.302 0-.176-.017-.302-.04-.302-.024 0-.042-.1-.042-.227 0-.126-.018-.226-.04-.226-.024 0-.041-.114-.041-.265 0-.15-.018-.264-.041-.264-.023 0-.04-.113-.04-.264 0-.151-.018-.265-.042-.265-.023 0-.04-.113-.04-.264 0-.151-.018-.265-.041-.265-.023 0-.041-.1-.041-.226s-.018-.227-.041-.227c-.023 0-.04-.113-.04-.264 0-.151-.018-.265-.042-.265-.023 0-.04-.113-.04-.264 0-.151-.018-.264-.041-.264-.024 0-.041-.114-.041-.265 0-.15-.018-.264-.04-.264-.024 0-.042-.1-.042-.227 0-.126-.018-.226-.04-.226-.024 0-.041-.114-.041-.265 0-.15-.018-.264-.041-.264-.023 0-.041-.114-.041-.265 0-.15-.018-.264-.04-.264-.024 0-.042-.113-.042-.264 0-.151-.017-.265-.04-.265s-.041-.1-.041-.226-.018-.227-.041-.227c-.023 0-.04-.113-.04-.264 0-.151-.018-.265-.042-.265-.023 0-.04-.113-.04-.264 0-.151-.018-.264-.041-.264-.024 0-.041-.114-.041-.265 0-.151-.018-.264-.04-.264-.024 0-.042-.114-.042-.265 0-.15-.017-.264-.04-.264s-.041-.1-.041-.227c0-.126-.018-.226-.041-.226-.023 0-.041-.114-.041-.265 0-.15-.018-.264-.04-.264-.024 0-.042-.113-.042-.264 0-.152-.017-.265-.04-.265-.024 0-.041-.113-.041-.264 0-.151-.018-.265-.041-.265-.023 0-.04-.1-.04-.226s-.019-.227-.042-.227c-.023 0-.04-.113-.04-.264 0-.151-.018-.265-.041-.265-.024 0-.041-.113-.041-.264 0-.151-.018-.264-.041-.264-.023 0-.04-.114-.04-.265 0-.15-.018-.264-.042-.264-.022 0-.04-.1-.04-.227 0-.126-.019-.226-.041-.226-.024 0-.041-.114-.041-.265 0-.15-.018-.264-.04-.264-.024 0-.042-.114-.042-.265 0-.15-.017-.264-.04-.264-.024 0-.041-.113-.041-.264 0-.151-.018-.265-.041-.265-.023 0-.041-.068-.041-.15 0-.127-.014-.152-.082-.152-.045 0-.081-.017-.081-.038 0-.024-.32-.037-.879-.037h-.878l-.651-.605c-.359-.332-.661-.604-.673-.604-.012 0-.021 4.113-.021 9.14zM9.959 6.61c0 .02.074.037.163.037.09 0 .164.017.164.038 0 .021.047.038.105.038.119 0 .274.116.19.142-.029.009-.05.08-.05.163 0 .082-.019.148-.041.148-.023 0-.041.068-.041.151 0 .083-.018.151-.04.151-.023 0-.042.051-.042.114 0 .062-.018.113-.04.113-.023 0-.041.068-.041.151 0 .083-.019.151-.041.151-.023 0-.04.068-.04.151 0 .083-.02.151-.042.151-.022 0-.04.068-.04.151 0 .084-.019.152-.041.152-.023 0-.041.05-.041.113 0 .062-.019.113-.041.113-.022 0-.04.068-.04.151v.151h-.164c-.09 0-.163-.017-.163-.037 0-.021-.055-.038-.123-.038-.067 0-.122-.017-.122-.038 0-.02-.074-.038-.164-.038-.09 0-.163-.017-.163-.038 0-.023-.231-.037-.612-.037s-.612.014-.612.037c0 .021-.055.038-.123.038-.067 0-.122.017-.122.038 0 .02-.051.038-.114.038a.23.23 0 00-.172.075c-.032.042-.084.076-.114.076-.075 0-.172.094-.172.167 0 .033-.018.06-.04.06-.023 0-.041.033-.041.075 0 .042-.019.076-.041.076-.024 0-.04.135-.04.331 0 .288.01.339.08.386.046.03.082.077.082.105 0 .061.183.235.247.235.026 0 .099.051.162.113.062.063.14.114.17.114.031 0 .083.034.115.075.033.042.088.076.123.076s.09.034.122.075c.033.042.092.076.132.076.04 0 .072.017.072.038 0 .02.03.037.066.037.035 0 .116.051.18.114.062.062.136.113.162.113.027 0 .1.051.164.113.063.063.135.114.16.114.063 0 .656.554.656.614 0 .027.037.073.082.103.045.03.081.085.081.122 0 .037.019.067.041.067.023 0 .04.034.04.076 0 .041.02.075.042.075.022 0 .04.034.04.076 0 .041.019.075.041.075.023 0 .041.034.041.076 0 .041.019.075.041.075.022 0 .04.068.04.151 0 .084.02.152.042.152.023 0 .04.113.04.264 0 .151.018.264.041.264.024 0 .041.114.041.265 0 .15-.017.264-.04.264-.024 0-.042.126-.042.302s-.017.302-.04.302-.041.068-.041.152c0 .083-.019.15-.041.15-.022 0-.04.034-.04.076 0 .042-.02.076-.042.076-.022 0-.04.05-.04.113 0 .062-.019.113-.041.113-.023 0-.041.034-.041.076 0 .041-.018.075-.04.075-.023 0-.042.03-.042.068 0 .037-.036.091-.081.121-.045.03-.082.077-.082.104 0 .063-.595.614-.664.614-.029 0-.08.034-.111.075-.033.042-.088.076-.123.076s-.09.034-.122.075a.23.23 0 01-.173.076c-.062 0-.113.017-.113.038 0 .02-.037.038-.082.038-.045 0-.081.017-.081.037 0 .021-.055.038-.123.038-.067 0-.122.017-.122.038 0 .021-.123.038-.286.038-.163 0-.286.016-.286.037 0 .023-.177.038-.449.038s-.449-.015-.449-.038c0-.021-.122-.037-.285-.037-.164 0-.286-.017-.286-.038 0-.021-.074-.038-.163-.038-.09 0-.164-.017-.164-.038 0-.02-.055-.037-.122-.037s-.123-.017-.123-.038c0-.021-.036-.038-.081-.038-.045 0-.082-.017-.082-.038 0-.02-.055-.038-.122-.038-.068 0-.123-.017-.123-.037 0-.021-.032-.038-.072-.038-.04 0-.1-.034-.132-.076-.032-.041-.091-.075-.131-.075-.04 0-.073-.017-.073-.038 0-.02-.033-.038-.072-.038-.04 0-.1-.034-.132-.075-.032-.042-.083-.076-.112-.076-.096 0-.337-.256-.337-.357 0-.053.018-.096.04-.096.023 0 .042-.068.042-.151 0-.083.018-.151.04-.151.023 0 .041-.085.041-.19 0-.103.019-.188.041-.188.023 0 .041-.068.041-.151 0-.083.018-.151.04-.151.023 0 .042-.068.042-.151 0-.083.018-.151.04-.151.023 0 .041-.068.041-.151 0-.126.014-.151.082-.151.045 0 .082.017.082.037 0 .021.032.038.072.038.04 0 .1.034.132.076.032.041.091.075.131.075.04 0 .073.017.073.038 0 .02.036.038.081.038.045 0 .082.017.082.038 0 .02.037.037.082.037.044 0 .081.017.081.038 0 .02.037.038.082.038.045 0 .081.017.081.038 0 .02.056.037.123.037s.122.017.122.038c0 .02.055.038.123.038.067 0 .122.017.122.038 0 .02.074.037.164.037.09 0 .163.018.163.038 0 .022.122.038.286.038.163 0 .285-.016.285-.038 0-.02.047-.037.103-.037.116 0 .469-.299.469-.396 0-.032.018-.058.04-.058.025 0 .041-.138.041-.34 0-.201-.016-.34-.04-.34-.023 0-.041-.034-.041-.075 0-.042-.019-.076-.041-.076-.023 0-.041-.025-.041-.057 0-.07-.671-.698-.745-.698-.03 0-.08-.034-.112-.076-.032-.041-.084-.075-.115-.075s-.108-.051-.17-.114c-.064-.062-.136-.113-.16-.113-.064 0-.82-.706-.82-.765 0-.027-.037-.074-.082-.103-.045-.03-.082-.085-.082-.122 0-.037-.018-.067-.04-.067-.023 0-.041-.051-.041-.114 0-.062-.019-.113-.041-.113-.023 0-.04-.051-.04-.113 0-.063-.02-.114-.042-.114-.022 0-.04-.085-.04-.189 0-.103-.019-.188-.041-.188-.025 0-.041-.177-.041-.454 0-.276.016-.453.04-.453.023 0 .041-.1.041-.226s.019-.227.041-.227c.023 0 .041-.068.041-.151 0-.083.018-.151.04-.151.023 0 .042-.034.042-.076 0-.041.018-.075.04-.075.023 0 .041-.051.041-.114 0-.062.019-.113.041-.113.023 0 .041-.034.041-.075 0-.042.018-.076.04-.076.023 0 .042-.03.042-.067 0-.037.036-.092.081-.122.045-.03.082-.08.082-.113 0-.032.037-.083.081-.113.045-.03.082-.077.082-.104 0-.063.759-.765.827-.765.03 0 .08-.034.112-.076.032-.041.091-.075.131-.075.04 0 .073-.017.073-.038 0-.02.037-.038.082-.038.045 0 .081-.017.081-.038 0-.02.037-.037.082-.037.045 0 .082-.017.082-.038 0-.02.036-.038.081-.038.045 0 .082-.017.082-.038 0-.02.037-.037.081-.037.045 0 .082-.017.082-.038 0-.02.055-.038.122-.038.068 0 .123-.017.123-.038 0-.02.055-.037.122-.037.068 0 .123-.017.123-.038 0-.021.073-.038.163-.038.09 0 .163-.017.163-.038 0-.02.11-.038.245-.038.136 0 .245-.016.245-.037 0-.024.286-.038.776-.038.49 0 .775.014.775.038z"
    fill="currentColor"
  />
</svg>
```

```html
<!-- Ícono de Wordpress -->
<svg width="22" height="22" fill="none" xmlns="http://www.w3.org/2000/svg">
  <path
    fill-rule="evenodd"
    clip-rule="evenodd"
    d="M9.828.033c0 .019-.108.032-.26.032-.152 0-.26.014-.26.033 0 .018-.074.032-.163.032-.09 0-.163.015-.163.033 0 .018-.073.032-.162.032-.09 0-.163.015-.163.033 0 .018-.073.032-.163.032-.09 0-.163.015-.163.033 0 .018-.058.032-.13.032-.071 0-.13.015-.13.033 0 .018-.044.033-.098.033-.053 0-.097.014-.097.032 0 .018-.044.033-.098.033-.054 0-.098.014-.098.032 0 .018-.043.033-.097.033-.054 0-.098.014-.098.032 0 .018-.044.033-.097.033-.054 0-.098.014-.098.032 0 .018-.044.033-.098.033-.053 0-.097.015-.097.032 0 .018-.044.033-.098.033-.054 0-.098.015-.098.033 0 .017-.029.032-.065.032-.035 0-.065.015-.065.033 0 .018-.03.032-.065.032-.036 0-.065.015-.065.033 0 .018-.044.032-.098.032-.053 0-.097.015-.097.033 0 .018-.03.032-.065.032-.036 0-.065.015-.065.033 0 .018-.03.032-.065.032-.036 0-.066.015-.066.033 0 .018-.029.033-.065.033-.035 0-.065.014-.065.032 0 .018-.029.033-.065.033-.036 0-.065.014-.065.032 0 .018-.03.033-.065.033-.036 0-.065.014-.065.032 0 .018-.026.033-.058.033s-.079.03-.105.065c-.026.036-.073.065-.105.065-.031 0-.058.015-.058.032 0 .018-.029.033-.065.033-.035 0-.065.015-.065.033 0 .017-.026.032-.058.032-.031 0-.079.03-.104.065-.026.036-.07.065-.098.065-.028 0-.072.03-.098.065-.026.036-.07.065-.097.065-.028 0-.072.03-.098.066-.026.035-.067.065-.092.065-.024 0-.086.044-.136.097-.05.054-.109.098-.13.098-.021 0-.08.044-.13.098-.05.053-.108.097-.13.097-.02 0-.108.073-.196.163-.087.09-.174.163-.193.163-.046 0-1.108 1.062-1.108 1.108 0 .02-.074.106-.163.193-.09.088-.163.176-.163.197 0 .02-.044.079-.097.129-.054.05-.098.109-.098.13 0 .021-.044.08-.098.13-.053.05-.097.112-.097.136 0 .025-.03.066-.065.092-.036.026-.066.07-.066.098 0 .028-.029.071-.065.097-.035.026-.065.07-.065.098 0 .028-.029.072-.065.098-.036.025-.065.073-.065.104 0 .032-.015.058-.032.058-.018 0-.033.03-.033.065 0 .036-.015.065-.033.065-.017 0-.032.027-.032.058 0 .032-.03.08-.065.105-.036.026-.065.073-.065.105s-.015.058-.033.058c-.018 0-.032.03-.032.065 0 .036-.015.065-.033.065-.018 0-.032.03-.032.065 0 .036-.015.065-.033.065-.018 0-.032.03-.032.065 0 .036-.015.065-.033.065-.018 0-.033.03-.033.066 0 .035-.014.065-.032.065-.018 0-.033.029-.033.065 0 .036-.014.065-.032.065-.018 0-.033.03-.033.065 0 .036-.014.065-.032.065-.018 0-.033.044-.033.098 0 .053-.014.097-.032.097-.018 0-.033.03-.033.065 0 .036-.015.065-.032.065-.018 0-.033.044-.033.098 0 .054-.015.098-.033.098-.017 0-.032.044-.032.097 0 .054-.015.098-.033.098-.018 0-.032.03-.032.065 0 .036-.015.065-.033.065-.018 0-.032.044-.032.098 0 .053-.015.097-.033.097-.018 0-.032.059-.032.13 0 .072-.015.13-.033.13-.018 0-.032.045-.032.098 0 .054-.015.098-.033.098-.018 0-.033.059-.033.13 0 .072-.014.13-.032.13-.018 0-.033.059-.033.13 0 .072-.014.13-.032.13-.018 0-.033.074-.033.163 0 .09-.014.163-.032.163-.018 0-.033.087-.033.195 0 .109-.014.196-.032.196-.02 0-.033.108-.033.26 0 .152-.013.26-.032.26C.01 9.828 0 10.241 0 11c0 .76.011 1.172.033 1.172.019 0 .032.108.032.26 0 .152.014.26.033.26.018 0 .032.087.032.196 0 .108.015.195.033.195.018 0 .032.073.032.163 0 .09.015.162.033.162.018 0 .032.059.032.13 0 .072.015.13.033.13.018 0 .032.06.032.13 0 .072.015.131.033.131.018 0 .033.044.033.098 0 .053.014.097.032.097.018 0 .033.059.033.13 0 .072.014.13.032.13.018 0 .033.03.033.066 0 .036.014.065.032.065.018 0 .033.044.033.097 0 .054.014.098.032.098.018 0 .033.044.033.098 0 .053.015.097.032.097.018 0 .033.044.033.098 0 .054.015.098.033.098.017 0 .032.029.032.065 0 .035.015.065.033.065.018 0 .032.03.032.065 0 .036.015.065.033.065.018 0 .032.044.032.098 0 .053.015.097.033.097.018 0 .032.03.032.065 0 .036.015.065.033.065.018 0 .032.03.032.066 0 .035.015.065.033.065.018 0 .033.029.033.065 0 .036.014.065.032.065.018 0 .033.029.033.065 0 .036.014.065.032.065.018 0 .033.03.033.065 0 .036.014.065.032.065.018 0 .033.026.033.058s.03.079.065.105c.036.026.065.073.065.105 0 .031.015.057.032.057.018 0 .033.03.033.066 0 .035.015.065.033.065.017 0 .032.026.032.058s.03.079.065.104c.036.026.065.07.065.098 0 .028.03.072.065.098.036.026.065.07.065.097 0 .028.03.072.066.098.035.026.065.067.065.092 0 .024.044.086.097.136.054.05.098.108.098.13 0 .021.044.08.098.13.053.05.097.108.097.13 0 .02.073.108.163.196.09.087.163.174.163.193 0 .046 1.062 1.108 1.108 1.108.02 0 .106.074.193.163.088.09.176.163.197.163.02 0 .079.044.129.097.05.054.109.098.13.098.021 0 .08.044.13.098.05.053.112.097.136.097.025 0 .066.03.092.065.026.036.07.066.098.066.028 0 .071.029.097.065.026.035.07.065.098.065.028 0 .072.029.098.065.025.036.073.065.104.065.032 0 .058.015.058.032 0 .018.03.033.065.033.036 0 .065.015.065.032 0 .018.027.033.058.033.032 0 .08.03.105.065.026.036.073.065.105.065s.058.015.058.033c0 .018.03.032.065.032.036 0 .065.015.065.033 0 .018.03.032.065.032.036 0 .065.015.065.033 0 .018.03.032.065.032.036 0 .065.015.065.033 0 .018.03.033.066.033.035 0 .065.014.065.032 0 .018.029.033.065.033.036 0 .065.014.065.032 0 .018.044.033.097.033.054 0 .098.014.098.032 0 .018.03.033.065.033.036 0 .065.015.065.032 0 .018.044.033.098.033.054 0 .098.015.098.032 0 .018.029.033.065.033.035 0 .065.015.065.033 0 .017.044.032.097.032.054 0 .098.015.098.033 0 .018.044.032.098.032.053 0 .097.015.097.033 0 .018.044.032.098.032.054 0 .097.015.097.033 0 .018.044.032.098.032.054 0 .098.015.098.033 0 .018.058.032.13.032.072 0 .13.015.13.033 0 .018.044.033.098.033.053 0 .097.014.097.032 0 .018.074.033.163.033.09 0 .163.014.163.032 0 .018.073.033.163.033.089 0 .162.014.162.032 0 .018.073.033.163.033.09 0 .163.014.163.032 0 .02.108.033.26.033.152 0 .26.014.26.033 0 .02.413.032 1.172.032.76 0 1.172-.012 1.172-.032s.097-.033.227-.033.228-.014.228-.033c0-.018.087-.032.195-.032.109 0 .196-.015.196-.033 0-.018.073-.032.162-.032.09 0 .163-.015.163-.033 0-.018.059-.032.13-.032.072 0 .13-.015.13-.033 0-.018.06-.032.13-.032.072 0 .13-.015.13-.033 0-.018.06-.032.131-.032.072 0 .13-.015.13-.033 0-.018.044-.033.098-.033.054 0 .098-.014.098-.032 0-.018.043-.033.097-.033.054 0 .098-.014.098-.032 0-.018.044-.033.097-.033.054 0 .098-.014.098-.032 0-.018.044-.033.098-.033.053 0 .097-.015.097-.032 0-.018.03-.033.065-.033.036 0 .066-.015.066-.032 0-.018.043-.033.097-.033.054 0 .098-.015.098-.033 0-.017.03-.032.065-.032.036 0 .065-.015.065-.033 0-.018.03-.032.065-.032.036 0 .065-.015.065-.033 0-.018.044-.032.098-.032.053 0 .097-.015.097-.033 0-.018.03-.032.066-.032.035 0 .065-.015.065-.033 0-.018.029-.032.065-.032.036 0 .065-.015.065-.033 0-.018.029-.033.065-.033.036 0 .065-.014.065-.032 0-.018.026-.033.058-.033s.079-.029.105-.065c.026-.036.073-.065.105-.065.031 0 .057-.014.057-.032 0-.018.03-.033.066-.033.035 0 .064-.015.064-.033 0-.017.027-.032.058-.032.032 0 .08-.03.105-.065.026-.036.073-.065.105-.065s.058-.015.058-.033c0-.018.026-.032.058-.032s.079-.03.105-.065c.026-.036.067-.066.091-.066.025 0 .086-.043.137-.097.05-.054.11-.098.136-.098.024 0 .066-.029.091-.065.026-.036.067-.065.091-.065.025 0 .1-.058.17-.13.069-.072.142-.13.162-.13.02 0 .108-.073.196-.163.087-.09.174-.163.193-.163.046 0 .978-.932.978-.978 0-.02.074-.106.163-.193.09-.087.163-.176.163-.196 0-.02.058-.094.13-.162.072-.07.13-.145.13-.17 0-.024.03-.065.065-.09.036-.026.065-.068.065-.092 0-.025.044-.086.098-.137.054-.05.098-.114.098-.143 0-.028.014-.052.032-.052.018 0 .033-.026.033-.058s.029-.079.065-.105c.035-.025.065-.07.065-.097 0-.028.03-.072.065-.098.036-.026.065-.073.065-.105 0-.031.015-.058.032-.058.018 0 .033-.029.033-.064 0-.036.015-.066.033-.066.018 0 .032-.026.032-.058 0-.031.03-.079.065-.104.036-.026.065-.073.065-.105s.015-.058.033-.058c.018 0 .032-.03.032-.065 0-.036.015-.065.033-.065.018 0 .032-.03.032-.065 0-.036.015-.065.033-.065.018 0 .033-.03.033-.066 0-.035.014-.065.032-.065.018 0 .033-.043.033-.097 0-.054.014-.098.032-.098.018 0 .033-.03.033-.065 0-.036.014-.065.032-.065.018 0 .033-.03.033-.065 0-.036.015-.065.032-.065.018 0 .033-.044.033-.098 0-.054.015-.097.032-.097.018 0 .033-.03.033-.066 0-.035.015-.065.033-.065.017 0 .032-.044.032-.097 0-.054.015-.098.033-.098.018 0 .032-.044.032-.098 0-.053.015-.097.033-.097.018 0 .032-.044.032-.098 0-.053.015-.098.033-.098.018 0 .032-.043.032-.097 0-.054.015-.098.033-.098.018 0 .032-.058.032-.13 0-.072.015-.13.033-.13.018 0 .033-.059.033-.13 0-.072.014-.13.032-.13.018 0 .033-.059.033-.13 0-.072.014-.13.032-.13.018 0 .033-.074.033-.163 0-.09.014-.163.032-.163.018 0 .033-.087.033-.196 0-.108.014-.195.032-.195.02 0 .033-.108.033-.26 0-.152.014-.26.033-.26.02 0 .032-.391.032-1.107s-.012-1.107-.032-1.107-.033-.108-.033-.26c0-.152-.014-.26-.033-.26-.018 0-.032-.087-.032-.195 0-.109-.015-.196-.033-.196-.018 0-.032-.073-.032-.162 0-.09-.015-.163-.033-.163-.018 0-.032-.059-.032-.13 0-.072-.015-.13-.033-.13-.018 0-.032-.06-.032-.13 0-.072-.015-.13-.033-.13-.018 0-.032-.06-.032-.131 0-.072-.015-.13-.033-.13-.018 0-.033-.044-.033-.098 0-.054-.014-.098-.032-.098-.018 0-.033-.043-.033-.097 0-.054-.014-.098-.032-.098-.018 0-.033-.044-.033-.097 0-.054-.014-.098-.032-.098-.018 0-.033-.044-.033-.098 0-.053-.015-.097-.032-.097-.018 0-.033-.03-.033-.065 0-.036-.015-.066-.032-.066-.018 0-.033-.043-.033-.097 0-.054-.015-.098-.033-.098-.017 0-.032-.03-.032-.065 0-.036-.015-.065-.033-.065-.018 0-.032-.03-.032-.065 0-.036-.015-.065-.033-.065-.018 0-.032-.044-.032-.098 0-.053-.015-.097-.033-.097-.018 0-.032-.03-.032-.065 0-.036-.015-.066-.033-.066-.018 0-.032-.029-.032-.065 0-.035-.015-.065-.033-.065-.018 0-.033-.029-.033-.065 0-.036-.014-.065-.032-.065-.018 0-.033-.026-.033-.058s-.029-.079-.065-.105c-.036-.025-.065-.073-.065-.104 0-.032-.014-.058-.032-.058-.018 0-.033-.03-.033-.065 0-.036-.015-.066-.033-.066-.017 0-.032-.026-.032-.057 0-.032-.03-.08-.065-.105-.036-.026-.065-.073-.065-.105s-.015-.058-.033-.058c-.018 0-.032-.026-.032-.058s-.03-.079-.065-.105c-.036-.026-.066-.067-.066-.091 0-.025-.043-.086-.097-.137-.054-.05-.098-.11-.098-.136 0-.024-.029-.066-.065-.091-.036-.026-.065-.067-.065-.091 0-.025-.058-.1-.13-.17-.072-.068-.13-.142-.13-.162 0-.02-.073-.108-.163-.196-.09-.087-.163-.174-.163-.193 0-.046-.932-.978-.978-.978-.02 0-.106-.074-.193-.163-.087-.09-.176-.163-.196-.163-.02 0-.094-.058-.162-.13-.07-.071-.145-.13-.17-.13-.024 0-.065-.03-.09-.065-.026-.036-.068-.065-.092-.065-.025 0-.086-.044-.137-.098-.05-.054-.11-.098-.136-.098-.024 0-.065-.029-.091-.065-.026-.035-.073-.065-.105-.065s-.058-.014-.058-.032c0-.018-.026-.033-.058-.033s-.079-.03-.105-.065c-.026-.036-.073-.065-.105-.065-.031 0-.058-.015-.058-.033 0-.017-.026-.032-.057-.032-.032 0-.08-.03-.105-.065-.026-.036-.073-.065-.105-.065s-.058-.015-.058-.033c0-.018-.03-.032-.065-.032-.036 0-.065-.015-.065-.033 0-.018-.03-.032-.065-.032-.036 0-.065-.015-.065-.033 0-.018-.03-.032-.065-.032-.036 0-.065-.015-.065-.033 0-.018-.03-.033-.066-.033-.035 0-.065-.014-.065-.032 0-.018-.043-.033-.097-.033-.054 0-.098-.014-.098-.032 0-.018-.03-.033-.065-.033-.036 0-.065-.014-.065-.032 0-.018-.03-.033-.065-.033-.036 0-.065-.014-.065-.032 0-.018-.044-.033-.098-.033-.054 0-.097-.015-.097-.032 0-.018-.03-.033-.066-.033-.035 0-.065-.015-.065-.033 0-.017-.044-.032-.097-.032-.054 0-.098-.015-.098-.033 0-.018-.044-.032-.098-.032-.053 0-.097-.015-.097-.033 0-.018-.044-.032-.098-.032-.053 0-.098-.015-.098-.033 0-.018-.043-.032-.097-.032-.054 0-.098-.015-.098-.033 0-.018-.058-.032-.13-.032-.072 0-.13-.015-.13-.033 0-.018-.044-.033-.098-.033-.053 0-.097-.014-.097-.032 0-.018-.074-.033-.163-.033-.09 0-.163-.014-.163-.032 0-.018-.073-.033-.162-.033-.09 0-.163-.014-.163-.032 0-.018-.074-.033-.163-.033-.09 0-.163-.014-.163-.032 0-.02-.108-.033-.26-.033-.152 0-.26-.013-.26-.032C12.172.01 11.759 0 11 0c-.76 0-1.172.011-1.172.033zm2.279.65c0 .02.108.033.26.033.152 0 .26.014.26.033 0 .017.073.032.163.032.09 0 .163.015.163.033 0 .018.073.032.162.032.09 0 .163.015.163.033 0 .018.059.032.13.032.072 0 .13.015.13.033 0 .018.059.032.13.032.072 0 .13.015.13.033 0 .018.045.032.098.032.054 0 .098.015.098.033 0 .018.059.033.13.033.072 0 .13.014.13.032 0 .018.03.033.066.033.035 0 .065.014.065.032 0 .018.044.033.097.033.054 0 .098.014.098.032 0 .018.044.033.098.033.053 0 .097.014.097.032 0 .018.03.033.065.033.036 0 .065.015.065.032 0 .018.044.033.098.033.054 0 .098.015.098.032 0 .018.029.033.065.033.035 0 .065.015.065.033 0 .017.03.032.065.032.036 0 .065.015.065.033 0 .018.03.032.065.032.036 0 .065.015.065.033 0 .018.03.032.065.032.036 0 .065.015.065.033 0 .018.03.032.065.032.036 0 .066.015.066.033 0 .018.029.032.065.032.035 0 .065.015.065.033 0 .018.029.033.065.033.036 0 .065.014.065.032 0 .018.03.033.065.033.036 0 .065.014.065.032 0 .018.026.033.058.033s.079.029.105.065c.026.036.07.065.097.065.028 0 .072.03.098.065.026.036.073.065.105.065s.058.015.058.033c0 .018.023.032.052.032.028 0 .093.044.143.098.05.054.111.097.136.097.025 0 .066.03.092.066.026.035.067.065.09.065.025 0 .101.058.17.13.069.071.142.13.162.13.02 0 .123.088.229.195.105.108.207.196.226.196.045 0 .717.672.717.717 0 .019.088.12.196.226.107.106.195.209.195.229 0 .02.059.093.13.162.072.069.13.145.13.17 0 .023.03.064.065.09.036.026.066.07.066.098 0 .028.029.072.065.097.035.026.065.07.065.098 0 .028.029.072.065.098.036.026.065.07.065.097 0 .028.03.072.065.098.036.026.065.073.065.105s.015.058.033.058c.017 0 .032.026.032.058 0 .031.03.079.065.104.036.026.065.073.065.105s.015.058.033.058c.018 0 .032.03.032.065 0 .036.015.065.033.065.018 0 .032.03.032.065 0 .036.015.066.033.066.018 0 .033.029.033.065 0 .035.014.065.032.065.018 0 .033.029.033.065 0 .036.014.065.032.065.018 0 .033.03.033.065 0 .036.014.065.032.065.018 0 .033.03.033.065 0 .036.015.065.032.065.018 0 .033.03.033.065 0 .036.015.065.032.065.018 0 .033.044.033.098 0 .054.015.098.033.098.018 0 .032.029.032.065 0 .036.015.065.033.065.018 0 .032.044.032.097 0 .054.015.098.033.098.018 0 .032.044.032.098 0 .053.015.097.033.097.018 0 .032.044.032.098 0 .054.015.098.033.098.018 0 .032.044.032.097 0 .054.015.098.033.098.018 0 .033.044.033.098 0 .053.014.097.032.097.018 0 .033.059.033.13 0 .072.014.13.032.13.018 0 .033.06.033.13 0 .072.014.13.032.13.018 0 .033.074.033.164 0 .09.015.162.032.162.018 0 .033.087.033.196 0 .108.014.195.032.195.02 0 .033.108.033.26 0 .152.014.26.033.26.02 0 .032.37.032 1.042 0 .673-.011 1.041-.032 1.041-.02 0-.033.109-.033.26 0 .153-.014.261-.032.261-.019 0-.033.087-.033.195 0 .109-.015.196-.033.196-.017 0-.032.073-.032.162 0 .09-.015.163-.033.163-.018 0-.032.059-.032.13 0 .072-.015.13-.033.13-.018 0-.032.059-.032.13 0 .072-.015.13-.033.13-.018 0-.032.045-.032.098 0 .054-.015.098-.033.098-.018 0-.032.044-.032.098 0 .053-.015.097-.033.097-.018 0-.033.044-.033.098 0 .054-.014.098-.032.098-.018 0-.033.044-.033.097 0 .054-.014.098-.032.098-.018 0-.033.044-.033.098 0 .053-.014.097-.032.097-.018 0-.033.03-.033.065 0 .036-.014.065-.032.065-.018 0-.033.044-.033.098 0 .054-.015.098-.033.098-.017 0-.032.029-.032.065 0 .035-.015.065-.033.065-.017 0-.032.03-.032.065 0 .036-.015.065-.033.065-.018 0-.032.03-.032.065 0 .036-.015.065-.033.065-.018 0-.032.03-.032.065 0 .036-.015.065-.033.065-.018 0-.032.03-.032.065 0 .036-.015.066-.033.066-.018 0-.033.029-.033.065 0 .035-.014.065-.032.065-.018 0-.033.029-.033.065 0 .036-.014.065-.032.065-.018 0-.033.026-.033.058s-.029.079-.065.105c-.036.025-.065.072-.065.104s-.015.058-.032.058c-.018 0-.033.026-.033.058s-.03.08-.065.105c-.036.026-.065.07-.065.098 0 .027-.03.072-.065.097-.036.026-.065.07-.065.098 0 .028-.03.072-.065.098-.036.025-.066.07-.066.097 0 .028-.029.072-.065.098-.035.026-.065.067-.065.09 0 .025-.058.101-.13.17-.071.069-.13.142-.13.162 0 .02-.088.123-.195.229-.108.105-.196.207-.196.226 0 .045-.672.717-.717.717-.019 0-.12.088-.226.196-.106.107-.209.195-.229.195-.02 0-.093.059-.162.13-.069.072-.145.13-.17.13-.023 0-.064.03-.09.066-.026.035-.07.065-.098.065-.028 0-.072.029-.098.065-.025.035-.07.065-.097.065-.028 0-.072.029-.098.065-.026.036-.07.065-.097.065-.028 0-.072.03-.098.065-.026.036-.073.065-.105.065s-.058.015-.058.033c0 .017-.026.032-.058.032s-.079.03-.104.065c-.026.036-.073.065-.105.065s-.058.015-.058.033c0 .018-.03.032-.065.032-.036 0-.065.015-.065.033 0 .018-.03.032-.065.032-.036 0-.066.015-.066.033 0 .018-.029.033-.065.033-.035 0-.065.014-.065.032 0 .018-.029.033-.065.033-.036 0-.065.014-.065.032 0 .018-.03.033-.065.033-.036 0-.065.014-.065.032 0 .018-.03.033-.065.033-.036 0-.065.015-.065.032 0 .018-.03.033-.065.033-.036 0-.065.015-.065.032 0 .018-.044.033-.098.033-.054 0-.098.015-.098.033 0 .018-.029.032-.065.032-.036 0-.065.015-.065.033 0 .018-.044.032-.098.032-.053 0-.097.015-.097.033 0 .018-.044.032-.098.032-.053 0-.097.015-.097.033 0 .018-.044.032-.098.032-.054 0-.098.015-.098.033 0 .018-.044.032-.097.032-.054 0-.098.015-.098.033 0 .018-.044.033-.098.033-.053 0-.097.014-.097.032 0 .018-.059.033-.13.033-.072 0-.13.014-.13.032 0 .018-.06.033-.13.033-.072 0-.13.014-.13.032 0 .018-.074.033-.164.033-.09 0-.162.015-.162.032 0 .018-.087.033-.196.033-.108 0-.195.014-.195.032 0 .02-.098.033-.228.033s-.227.014-.227.033c0 .02-.391.032-1.107.032s-1.107-.011-1.107-.032c0-.02-.108-.033-.26-.033-.152 0-.26-.014-.26-.032 0-.018-.073-.033-.163-.033-.09 0-.163-.015-.163-.033 0-.017-.073-.032-.162-.032-.09 0-.163-.015-.163-.033 0-.018-.059-.032-.13-.032-.072 0-.13-.015-.13-.033 0-.018-.059-.032-.13-.032-.072 0-.13-.015-.13-.033 0-.018-.045-.032-.098-.032-.054 0-.098-.015-.098-.033 0-.018-.059-.032-.13-.032-.072 0-.13-.015-.13-.033 0-.018-.044-.033-.098-.033-.054 0-.098-.014-.098-.032 0-.018-.029-.033-.065-.033-.036 0-.065-.014-.065-.032 0-.018-.044-.033-.098-.033-.053 0-.097-.014-.097-.032 0-.018-.03-.033-.065-.033-.036 0-.065-.014-.065-.032 0-.018-.044-.033-.098-.033-.054 0-.098-.015-.098-.033 0-.017-.029-.032-.065-.032-.035 0-.065-.015-.065-.033 0-.017-.03-.032-.065-.032-.036 0-.065-.015-.065-.033 0-.018-.03-.032-.065-.032-.036 0-.065-.015-.065-.033 0-.018-.03-.032-.065-.032-.036 0-.065-.015-.065-.033 0-.018-.03-.032-.065-.032-.036 0-.065-.015-.065-.033 0-.018-.03-.033-.066-.033-.035 0-.065-.014-.065-.032 0-.018-.029-.033-.065-.033-.036 0-.065-.014-.065-.032 0-.018-.03-.033-.065-.033-.036 0-.065-.014-.065-.032 0-.018-.026-.033-.058-.033s-.079-.029-.105-.065c-.026-.036-.073-.065-.105-.065-.031 0-.057-.015-.057-.032 0-.018-.027-.033-.058-.033-.032 0-.08-.03-.105-.065-.026-.036-.067-.065-.092-.065-.025 0-.086-.044-.136-.098-.05-.053-.111-.098-.136-.098-.025 0-.066-.029-.092-.064-.026-.036-.067-.066-.09-.066-.025 0-.101-.058-.17-.13-.069-.071-.142-.13-.162-.13-.02 0-.109-.073-.196-.163-.087-.09-.174-.162-.194-.162-.045 0-.848-.803-.848-.848 0-.02-.087-.121-.195-.226-.107-.106-.195-.209-.195-.23 0-.02-.044-.078-.098-.128-.053-.05-.097-.11-.097-.13 0-.022-.044-.08-.098-.13-.054-.05-.098-.112-.098-.137 0-.024-.029-.066-.065-.092-.036-.025-.065-.07-.065-.097 0-.028-.03-.072-.065-.098-.036-.026-.065-.073-.065-.105 0-.031-.015-.057-.033-.057-.017 0-.032-.027-.032-.058 0-.032-.03-.08-.065-.105-.036-.026-.065-.073-.065-.105s-.015-.058-.033-.058c-.018 0-.032-.03-.032-.065 0-.036-.015-.065-.033-.065-.018 0-.032-.03-.032-.065 0-.036-.015-.065-.033-.065-.018 0-.033-.026-.033-.058s-.029-.08-.065-.105c-.035-.026-.065-.073-.065-.105s-.014-.058-.032-.058c-.018 0-.033-.044-.033-.097 0-.054-.014-.098-.032-.098-.018 0-.033-.03-.033-.065 0-.036-.015-.065-.032-.065-.018 0-.033-.03-.033-.065 0-.036-.015-.065-.033-.065-.017 0-.032-.03-.032-.066 0-.035-.015-.065-.033-.065-.017 0-.032-.043-.032-.097 0-.054-.015-.098-.033-.098-.018 0-.032-.03-.032-.065 0-.036-.015-.065-.033-.065-.018 0-.032-.044-.032-.098 0-.053-.015-.097-.033-.097-.018 0-.032-.044-.032-.098 0-.054-.015-.098-.033-.098-.018 0-.032-.043-.032-.097 0-.054-.015-.098-.033-.098-.018 0-.033-.058-.033-.13 0-.072-.014-.13-.032-.13-.018 0-.033-.044-.033-.098 0-.053-.014-.097-.032-.097-.018 0-.033-.074-.033-.163 0-.09-.014-.163-.032-.163-.018 0-.033-.059-.033-.13 0-.072-.014-.13-.032-.13-.018 0-.033-.087-.033-.196 0-.108-.014-.195-.032-.195-.02 0-.033-.108-.033-.26 0-.152-.014-.26-.033-.26-.02 0-.032-.391-.032-1.107s.011-1.107.032-1.107c.02 0 .033-.108.033-.26 0-.152.014-.26.033-.26.018 0 .032-.087.032-.195 0-.109.015-.196.033-.196.018 0 .032-.058.032-.13 0-.072.015-.13.033-.13.018 0 .032-.073.032-.163 0-.09.015-.163.033-.163.018 0 .032-.043.032-.097 0-.054.015-.098.033-.098.018 0 .032-.058.032-.13 0-.072.015-.13.033-.13.018 0 .033-.044.033-.098 0-.053.014-.097.032-.097.018 0 .033-.044.033-.098 0-.054.014-.098.032-.098.018 0 .033-.044.033-.097 0-.054.014-.098.032-.098.018 0 .033-.03.033-.065 0-.036.014-.065.032-.065.018 0 .033-.044.033-.098 0-.053.015-.097.032-.097.018 0 .033-.03.033-.066 0-.035.015-.065.032-.065.018 0 .033-.029.033-.065 0-.035.015-.065.033-.065.017 0 .032-.03.032-.065 0-.036.015-.065.033-.065.018 0 .032-.044.032-.098 0-.053.015-.097.033-.097.018 0 .032-.026.032-.058s.03-.08.065-.105c.036-.026.065-.073.065-.105s.015-.058.033-.058c.018 0 .033-.029.033-.065 0-.036.014-.065.032-.065.018 0 .033-.03.033-.065 0-.036.014-.065.032-.065.018 0 .033-.026.033-.058s.029-.079.065-.105c.036-.026.065-.073.065-.105 0-.031.015-.057.032-.057.018 0 .033-.027.033-.058 0-.032.03-.08.065-.105.036-.026.065-.07.065-.098 0-.028.03-.072.065-.097.036-.026.065-.068.065-.092 0-.025.044-.086.098-.136.054-.05.098-.109.098-.13 0-.022.044-.08.097-.13.054-.05.098-.109.098-.13 0-.02.088-.123.195-.229.108-.105.195-.207.195-.226 0-.045.803-.848.848-.848.02 0 .121-.087.226-.195.106-.107.209-.195.23-.195.02 0 .078-.044.128-.098.05-.053.11-.097.13-.097.022 0 .08-.044.13-.098.05-.054.112-.098.137-.098.024 0 .066-.029.092-.065.025-.036.07-.065.097-.065.028 0 .072-.03.098-.065.026-.036.073-.065.105-.065.031 0 .058-.015.058-.033 0-.017.026-.032.057-.032.032 0 .08-.03.105-.065.026-.036.073-.065.105-.065s.058-.015.058-.033c0-.018.03-.032.065-.032.036 0 .065-.015.065-.033 0-.018.03-.032.065-.032.036 0 .065-.015.065-.033 0-.018.03-.033.065-.033.036 0 .066-.014.066-.032 0-.018.026-.033.057-.033.032 0 .08-.029.105-.065a.178.178 0 01.138-.065c.05 0 .09-.014.09-.032 0-.018.03-.033.065-.033.036 0 .065-.015.065-.032 0-.018.03-.033.065-.033.036 0 .065-.015.065-.033 0-.017.03-.032.066-.032.035 0 .065-.015.065-.033 0-.017.044-.032.097-.032.054 0 .098-.015.098-.033 0-.018.044-.032.097-.032.054 0 .098-.015.098-.033 0-.018.03-.032.065-.032.036 0 .065-.015.065-.033 0-.018.044-.032.098-.032.054 0 .098-.015.098-.033 0-.018.043-.032.097-.032.054 0 .098-.015.098-.033 0-.018.058-.033.13-.033.072 0 .13-.014.13-.032 0-.018.059-.033.13-.033.072 0 .13-.014.13-.032 0-.018.06-.033.13-.033.072 0 .13-.014.13-.032 0-.018.074-.033.164-.033.09 0 .162-.014.162-.032 0-.018.074-.033.163-.033.09 0 .163-.015.163-.032 0-.02.108-.033.26-.033.152 0 .26-.014.26-.033 0-.02.391-.032 1.107-.032s1.107.011 1.107.032zm-1.953 1.172c0 .02-.12.033-.293.033-.174 0-.293.013-.293.032 0 .018-.087.033-.195.033-.109 0-.195.014-.195.032 0 .018-.06.033-.13.033-.072 0-.13.014-.13.032 0 .018-.06.033-.131.033-.072 0-.13.014-.13.032 0 .018-.059.033-.13.033-.072 0-.13.015-.13.032 0 .018-.044.033-.098.033-.054 0-.098.015-.098.033 0 .017-.044.032-.097.032-.054 0-.098.015-.098.033 0 .018-.044.032-.098.032-.053 0-.097.015-.097.033 0 .018-.044.032-.098.032-.054 0-.098.015-.098.033 0 .018-.029.032-.065.032-.035 0-.065.015-.065.033 0 .018-.03.032-.065.032-.036 0-.065.015-.065.033 0 .018-.044.033-.098.033-.053 0-.097.014-.097.032 0 .018-.03.033-.065.033-.036 0-.065.014-.065.032 0 .018-.03.033-.066.033-.035 0-.065.014-.065.032 0 .018-.029.033-.065.033-.035 0-.065.014-.065.032 0 .018-.03.033-.065.033-.036 0-.065.015-.065.032 0 .018-.026.033-.058.033s-.079.03-.105.065c-.025.036-.073.065-.104.065-.032 0-.058.015-.058.033 0 .018-.026.032-.058.032s-.08.03-.105.065c-.026.036-.07.065-.098.065-.028 0-.072.03-.097.066-.026.035-.07.065-.098.065-.028 0-.072.029-.098.065-.025.035-.067.065-.091.065-.025 0-.086.044-.136.097-.05.054-.109.098-.13.098-.021 0-.095.059-.163.13-.07.072-.141.13-.16.13-.047 0-1.11 1.063-1.11 1.11 0 .019-.058.09-.13.16-.071.068-.13.142-.13.163 0 .021-.044.08-.098.13-.053.05-.097.11-.097.136 0 .024-.03.066-.065.091-.036.026-.065.073-.065.105 0 .055.067.058 1.106.058.716 0 1.107-.011 1.107-.032 0-.02.18-.033.473-.033.46 0 .476.002.553.08.044.044.08.102.08.13 0 .028.015.05.033.05.018 0 .032.052.032.115 0 .143-.179.341-.308.341-.045 0-.082.015-.082.033 0 .02-.141.032-.358.032s-.358.013-.358.033c0 .018-.059.032-.13.032-.123 0-.13.006-.13.098 0 .053.014.097.032.097.018 0 .032.044.032.098 0 .054.015.098.033.098.018 0 .033.044.033.097 0 .054.014.098.032.098.018 0 .033.044.033.098 0 .053.014.097.032.097.018 0 .033.044.033.098 0 .054.014.097.032.097.018 0 .033.044.033.098 0 .054.014.098.032.098.018 0 .033.044.033.097 0 .054.015.098.032.098.018 0 .033.044.033.098 0 .053.015.097.033.097.017 0 .032.044.032.098 0 .054.015.098.033.098.018 0 .032.043.032.097 0 .054.015.098.033.098.018 0 .032.044.032.097 0 .054.015.098.033.098.018 0 .032.044.032.098 0 .053.015.097.033.097.018 0 .032.03.032.065 0 .036.015.066.033.066.018 0 .033.043.033.097 0 .054.014.098.032.098.018 0 .033.044.033.097 0 .054.014.098.032.098.018 0 .033.044.033.098 0 .053.014.097.032.097.018 0 .033.044.033.098 0 .054.014.098.032.098.018 0 .033.043.033.097 0 .054.015.098.032.098.018 0 .033.044.033.098 0 .053.015.097.033.097.017 0 .032.044.032.098 0 .053.015.097.033.097.018 0 .032.044.032.098 0 .054.015.098.033.098.018 0 .032.044.032.097 0 .054.015.098.033.098.018 0 .032.044.032.098 0 .053.015.097.033.097.018 0 .032.044.032.098 0 .053.015.097.033.097.018 0 .032.044.032.098 0 .054.015.098.033.098.018 0 .033.044.033.097 0 .054.014.098.032.098.018 0 .033.044.033.098 0 .053.014.097.032.097.018 0 .033.044.033.098 0 .054.014.098.032.098.018 0 .033.043.033.097 0 .054.014.098.032.098.018 0 .033.044.033.097 0 .054.015.098.032.098.018 0 .033.044.033.098 0 .053.015.097.033.097.017 0 .032.044.032.098 0 .054.015.098.033.098.018 0 .032.043.032.097 0 .054.015.098.033.098.018 0 .032.044.032.098 0 .053.015.097.033.097.018 0 .032.044.032.098 0 .053.015.097.033.097.018 0 .032.044.032.098 0 .054.015.098.033.098.018 0 .033.044.033.097 0 .054.014.098.032.098.018 0 .033.044.033.097 0 .054.014.098.032.098.018 0 .033.044.033.098 0 .053.014.097.032.097.018 0 .033.044.033.098 0 .054.014.098.032.098.018 0 .033.044.033.097 0 .054.015.098.032.098.018 0 .033.044.033.098 0 .053.015.097.033.097.017 0 .032.044.032.098 0 .054.015.098.033.098.018 0 .032.043.032.097 0 .054.015.098.033.098.018 0 .032.044.032.097 0 .054.015.098.033.098.018 0 .032.044.032.098 0 .053.015.097.033.097.018 0 .032.044.032.098 0 .054.015.098.033.098.018 0 .033.043.033.097 0 .054.014.098.032.098.018 0 .033.044.033.098 0 .053.014.097.032.097.018 0 .033.044.033.098 0 .053.014.097.032.097.018 0 .033.044.033.098 0 .054.014.098.032.098.018 0 .033-.03.033-.066 0-.035.015-.064.032-.064.018 0 .033-.044.033-.098 0-.054.015-.098.033-.098.017 0 .032-.044.032-.097 0-.054.015-.098.033-.098.018 0 .032-.044.032-.098 0-.053.015-.097.033-.097.018 0 .032-.044.032-.098 0-.054.015-.098.033-.098.018 0 .032-.043.032-.097 0-.054.015-.098.033-.098.018 0 .032-.044.032-.098 0-.053.015-.097.033-.097.018 0 .033-.044.033-.098 0-.053.014-.097.032-.097.018 0 .033-.044.033-.098 0-.054.014-.098.032-.098.018 0 .033-.044.033-.097 0-.054.014-.098.032-.098.018 0 .033-.044.033-.098 0-.053.014-.097.032-.097.018 0 .033-.044.033-.098 0-.053.015-.098.032-.098.018 0 .033-.043.033-.097 0-.054.015-.098.033-.098.017 0 .032-.044.032-.097 0-.054.015-.098.033-.098.017 0 .032-.044.032-.098 0-.053.015-.097.033-.097.018 0 .032-.044.032-.098 0-.054.015-.097.033-.097.018 0 .032-.044.032-.098 0-.054.015-.098.033-.098.018 0 .032-.044.032-.097 0-.054.015-.098.033-.098.018 0 .032-.044.032-.098 0-.053.015-.097.033-.097.018 0 .033-.044.033-.098 0-.054.014-.098.032-.098.018 0 .033-.043.033-.097 0-.054.014-.098.032-.098.018 0 .033-.044.033-.098 0-.053.014-.097.032-.097.018 0 .033-.044.033-.098 0-.053.014-.097.032-.097.018 0 .033-.044.033-.098 0-.054.015-.098.033-.098.017 0 .032-.044.032-.097 0-.054.015-.098.033-.098.018 0 .032-.044.032-.098 0-.053.015-.097.033-.097.018 0 .032-.044.032-.098 0-.053.015-.098.033-.098.018 0 .032-.043.032-.097 0-.054.015-.098.033-.098.018 0 .032-.044.032-.097 0-.054.015-.098.033-.098.018 0 .033-.044.033-.098 0-.053.014-.097.032-.097.018 0 .033-.087.033-.195 0-.109-.015-.196-.033-.196-.018 0-.032-.044-.032-.097 0-.054-.015-.098-.033-.098-.018 0-.033-.044-.033-.098 0-.053-.014-.097-.032-.097-.018 0-.033-.03-.033-.065 0-.036-.014-.066-.032-.066-.018 0-.033-.043-.033-.097 0-.054-.014-.098-.032-.098-.018 0-.033-.044-.033-.097 0-.054-.014-.098-.032-.098-.018 0-.033-.044-.033-.098 0-.053-.015-.097-.033-.097-.017 0-.032-.03-.032-.065 0-.036-.015-.065-.033-.065-.018 0-.032-.044-.032-.098 0-.054-.015-.098-.033-.098-.018 0-.032-.044-.032-.097 0-.054-.015-.098-.033-.098-.018 0-.032-.044-.032-.098 0-.053-.015-.097-.033-.097-.018 0-.032-.03-.032-.065 0-.036-.015-.065-.033-.065-.018 0-.033-.044-.033-.098 0-.054-.014-.098-.032-.098-.018 0-.033-.044-.033-.097 0-.054-.014-.098-.032-.098-.018 0-.033-.044-.033-.098 0-.053-.014-.097-.032-.097-.018 0-.033-.03-.033-.065 0-.036-.014-.065-.032-.065-.018 0-.033-.044-.033-.098 0-.054-.015-.098-.032-.098-.018 0-.033-.044-.033-.097 0-.054-.015-.098-.032-.098-.018 0-.033-.03-.033-.065 0-.036-.015-.065-.033-.065-.017 0-.032-.044-.032-.098 0-.053-.015-.097-.033-.097-.018 0-.032-.044-.032-.098 0-.054-.015-.098-.033-.098-.018 0-.032-.029-.032-.065 0-.056-.022-.065-.163-.065-.09 0-.163-.014-.163-.032 0-.02-.13-.033-.325-.033s-.326-.013-.326-.032c0-.018-.037-.033-.082-.033a.279.279 0 01-.163-.08c-.066-.066-.08-.112-.08-.26 0-.1.015-.18.032-.18.018 0 .033-.03.033-.066 0-.043.022-.065.065-.065.036 0 .065-.015.065-.032 0-.02.174-.033.456-.033.282 0 .455.012.455.033 0 .02.586.032 1.693.032 1.106 0 1.692-.011 1.692-.032 0-.02.18-.033.473-.033.46 0 .476.002.554.08.044.044.08.102.08.13 0 .028.014.05.032.05.018 0 .033.052.033.115 0 .143-.18.341-.309.341-.045 0-.082.015-.082.033 0 .02-.14.032-.358.032-.217 0-.358.013-.358.033 0 .018-.058.032-.13.032-.123 0-.13.006-.13.098 0 .053.014.097.032.097.018 0 .033.044.033.098 0 .054.014.098.032.098.018 0 .033.044.033.097 0 .054.015.098.032.098.018 0 .033.044.033.098 0 .053.015.097.033.097.018 0 .032.044.032.098 0 .054.015.097.033.097.018 0 .032.044.032.098 0 .054.015.098.033.098.018 0 .032.044.032.097 0 .054.015.098.033.098.018 0 .032.044.032.098 0 .053.015.097.033.097.018 0 .033.044.033.098 0 .054.014.098.032.098.018 0 .033.043.033.097 0 .054.014.098.032.098.018 0 .033.044.033.097 0 .054.014.098.032.098.018 0 .033.044.033.098 0 .053.014.097.032.097.018 0 .033.044.033.098 0 .054.014.098.032.098.018 0 .033.044.033.097 0 .054.015.098.033.098.017 0 .032.03.032.065 0 .036.015.065.033.065.018 0 .032.044.032.098 0 .053.015.097.033.097.018 0 .032.044.032.098 0 .054.015.098.033.098.018 0 .032.043.032.097 0 .054.015.098.033.098.018 0 .032.044.032.098 0 .053.015.097.033.097.018 0 .033.044.033.098 0 .053.014.097.032.097.018 0 .033.044.033.098 0 .054.014.098.032.098.018 0 .033.044.033.097 0 .054.014.098.032.098.018 0 .033.044.033.098 0 .053.014.097.032.097.018 0 .033.044.033.098 0 .053.014.097.032.097.018 0 .033.044.033.098 0 .054.015.098.032.098.018 0 .033.044.033.097 0 .054.015.098.032.098.018 0 .033.044.033.098 0 .053.015.097.033.097.018 0 .032.044.032.098 0 .054.015.098.033.098.018 0 .032.043.032.097 0 .054.015.098.033.098.018 0 .032.044.032.097 0 .054.015.098.033.098.018 0 .032.044.032.098 0 .053.015.097.033.097.018 0 .032.044.032.098 0 .054.015.098.033.098.018 0 .033.043.033.097 0 .054.014.098.032.098.018 0 .033.044.033.098 0 .053.014.097.032.097.018 0 .033.044.033.098 0 .053.014.097.032.097.018 0 .033.044.033.098 0 .054.014.098.032.098.018 0 .033.044.033.097 0 .054.015.098.033.098.017 0 .032.044.032.097 0 .054.015.098.033.098.018 0 .032.044.032.098 0 .053.015.097.033.097.018 0 .032.044.032.098 0 .054.015.098.033.098.018 0 .032.044.032.097 0 .054.015.098.033.098.018 0 .032.044.032.098 0 .053.015.097.033.097.018 0 .033.044.033.098 0 .054.014.098.032.098.018 0 .033.043.033.097 0 .054.014.098.032.098.018 0 .033.044.033.097 0 .054.014.098.032.098.018 0 .033.044.033.098 0 .053.014.097.032.097.018 0 .033.044.033.098 0 .054.014.098.032.098.018 0 .033.043.033.097 0 .054.015.098.032.098.018 0 .033.044.033.098 0 .053.015.097.033.097.018 0 .032.044.032.098 0 .053.015.097.033.097.018 0 .032.03.032.066 0 .035.015.064.033.064.018 0 .032-.043.032-.097 0-.054.015-.098.033-.098.018 0 .032-.044.032-.097 0-.054.015-.098.033-.098.018 0 .033-.044.033-.098 0-.053.014-.097.032-.097.018 0 .033-.059.033-.13 0-.072.014-.13.032-.13.018 0 .033-.044.033-.098 0-.054.014-.098.032-.098.018 0 .033-.044.033-.098 0-.053.014-.097.032-.097.018 0 .033-.044.033-.098 0-.053.014-.097.032-.097.018 0 .033-.044.033-.098 0-.054.015-.098.032-.098.018 0 .033-.044.033-.097 0-.054.015-.098.033-.098.017 0 .032-.059.032-.13 0-.072.015-.13.033-.13.018 0 .032-.044.032-.098 0-.054.015-.098.033-.098.018 0 .032-.043.032-.097 0-.054.015-.098.033-.098.018 0 .032-.044.032-.098 0-.053.015-.097.033-.097.018 0 .033-.044.033-.098 0-.053.014-.097.032-.097.018 0 .032-.044.032-.098 0-.054.015-.098.033-.098.018 0 .033-.058.033-.13 0-.071.014-.13.032-.13.018 0 .033-.044.033-.098 0-.053.014-.097.032-.097.018 0 .033-.044.033-.098 0-.054.014-.098.032-.098.018 0 .033-.043.033-.097 0-.054.015-.098.032-.098.018 0 .033-.058.033-.13 0-.072.015-.13.032-.13.018 0 .033-.059.033-.13 0-.072.015-.13.033-.13.018 0 .032-.06.032-.13 0-.072.015-.13.033-.13.018 0 .032-.074.032-.164 0-.09.015-.162.033-.162.018 0 .032-.087.032-.196 0-.108.015-.195.033-.195.02 0 .032-.228.032-.618s-.011-.619-.032-.619c-.018 0-.033-.073-.033-.162 0-.09-.014-.163-.032-.163-.018 0-.033-.059-.033-.13 0-.072-.014-.13-.032-.13-.018 0-.033-.044-.033-.098 0-.054-.014-.098-.032-.098-.018 0-.033-.044-.033-.097 0-.054-.015-.098-.032-.098-.018 0-.033-.03-.033-.065 0-.036-.015-.065-.033-.065-.017 0-.032-.044-.032-.098 0-.053-.015-.097-.033-.097-.018 0-.032-.03-.032-.065 0-.036-.015-.065-.033-.065-.018 0-.032-.03-.032-.066 0-.035-.015-.065-.033-.065-.018 0-.032-.026-.032-.058 0-.031-.03-.079-.066-.104-.035-.026-.064-.073-.064-.105s-.015-.058-.033-.058c-.018 0-.033-.026-.033-.058s-.029-.079-.065-.105c-.035-.026-.065-.073-.065-.105 0-.031-.014-.058-.032-.058-.018 0-.033-.026-.033-.057 0-.032-.03-.08-.065-.105-.036-.026-.065-.073-.065-.105s-.015-.058-.033-.058c-.018 0-.032-.03-.032-.065 0-.036-.015-.065-.033-.065-.018 0-.032-.03-.032-.065 0-.036-.015-.065-.033-.065-.018 0-.032-.03-.032-.065 0-.036-.015-.066-.033-.066-.018 0-.032-.029-.032-.065 0-.035-.015-.065-.033-.065-.018 0-.033-.029-.033-.065 0-.036-.014-.065-.032-.065-.018 0-.033-.044-.033-.097 0-.054-.014-.098-.032-.098-.018 0-.033-.044-.033-.098 0-.053-.014-.097-.032-.097-.02 0-.033-.163-.033-.423s.013-.424.033-.424c.018 0 .032-.058.032-.13 0-.071.015-.13.033-.13.018 0 .032-.03.032-.065 0-.036.015-.065.033-.065.018 0 .033-.023.033-.052 0-.029.043-.093.097-.143.054-.05.098-.108.098-.128 0-.055.218-.263.275-.263.028 0 .05-.015.05-.032 0-.018.026-.033.058-.033s.08-.03.105-.065a.178.178 0 01.137-.065c.05 0 .09-.015.09-.033 0-.019.11-.032.261-.032.143 0 .26-.009.26-.019 0-.033-.091-.111-.13-.111-.02 0-.108-.074-.195-.163-.087-.09-.176-.163-.196-.163-.021 0-.08-.044-.13-.097-.05-.054-.11-.098-.136-.098-.024 0-.066-.03-.091-.065-.026-.036-.067-.065-.092-.065-.025 0-.086-.044-.136-.098-.05-.054-.115-.098-.143-.098-.029 0-.052-.014-.052-.032 0-.018-.026-.033-.058-.033s-.08-.029-.105-.065c-.026-.036-.073-.065-.105-.065s-.058-.014-.058-.032c0-.018-.03-.033-.065-.033-.036 0-.065-.015-.065-.032 0-.018-.026-.033-.058-.033s-.079-.03-.105-.065c-.025-.036-.073-.065-.104-.065-.032 0-.058-.015-.058-.033 0-.018-.03-.032-.066-.032-.035 0-.065-.015-.065-.033 0-.018-.043-.032-.097-.032-.054 0-.098-.015-.098-.033 0-.018-.03-.032-.065-.032-.036 0-.065-.015-.065-.033 0-.018-.03-.033-.065-.033-.036 0-.065-.014-.065-.032 0-.018-.044-.033-.098-.033-.053 0-.098-.014-.098-.032 0-.018-.029-.033-.065-.033-.035 0-.065-.014-.065-.032 0-.018-.044-.033-.097-.033-.054 0-.098-.014-.098-.032 0-.018-.044-.033-.098-.033-.053 0-.097-.015-.097-.032 0-.018-.044-.033-.098-.033-.053 0-.097-.015-.097-.033 0-.017-.059-.032-.13-.032-.072 0-.13-.015-.13-.033 0-.018-.06-.032-.131-.032-.072 0-.13-.015-.13-.033 0-.018-.073-.032-.163-.032-.09 0-.163-.015-.163-.033 0-.018-.073-.032-.162-.032-.09 0-.163-.015-.163-.033 0-.019-.109-.032-.26-.032-.152 0-.26-.014-.26-.033 0-.02-.315-.033-.88-.033-.563 0-.878.012-.878.033zm8.917 4.98c0 .07.015.13.033.13.02 0 .032.216.032.585 0 .37-.012.586-.032.586s-.033.109-.033.26c0 .152-.014.26-.033.26-.018 0-.032.088-.032.196 0 .109-.015.195-.033.195-.017 0-.032.059-.032.13 0 .072-.015.13-.033.13-.018 0-.032.06-.032.13 0 .072-.015.131-.033.131-.018 0-.032.059-.032.13 0 .072-.015.13-.033.13-.018 0-.032.044-.032.098 0 .054-.015.098-.033.098-.018 0-.033.044-.033.097 0 .054-.014.098-.032.098-.018 0-.033.044-.033.098 0 .053-.014.097-.032.097-.018 0-.033.044-.033.098 0 .053-.014.098-.032.098-.018 0-.033.029-.033.065 0 .035-.014.065-.032.065-.018 0-.033.044-.033.097 0 .054-.015.098-.032.098-.018 0-.033.044-.033.098 0 .053-.015.097-.032.097-.018 0-.033.044-.033.098 0 .053-.015.097-.033.097-.018 0-.032.044-.032.098 0 .054-.015.098-.033.098-.018 0-.032.044-.032.097 0 .054-.015.098-.033.098-.018 0-.032.044-.032.098 0 .053-.015.097-.033.097-.018 0-.032.03-.032.065 0 .036-.015.065-.033.065-.018 0-.032.044-.032.098 0 .054-.015.098-.033.098-.018 0-.033.044-.033.097 0 .054-.014.098-.032.098-.018 0-.033.044-.033.098 0 .053-.014.097-.032.097-.018 0-.033.044-.033.098 0 .054-.014.098-.032.098-.018 0-.033.043-.033.097 0 .054-.015.098-.032.098-.018 0-.033.044-.033.097 0 .054-.015.098-.032.098-.018 0-.033.044-.033.098 0 .053-.015.097-.033.097-.018 0-.032.044-.032.098 0 .054-.015.098-.033.098-.018 0-.032.044-.032.097 0 .054-.015.098-.033.098-.018 0-.032.03-.032.065 0 .036-.015.065-.033.065-.018 0-.032.044-.032.098 0 .053-.015.097-.033.097-.018 0-.032.044-.032.098 0 .054-.015.098-.033.098-.018 0-.033.043-.033.097 0 .054-.014.098-.032.098-.018 0-.033.044-.033.097 0 .054-.014.098-.032.098-.018 0-.033.044-.033.098 0 .053-.014.097-.032.097-.018 0-.033.044-.033.098 0 .054-.014.098-.032.098-.018 0-.033.043-.033.097 0 .054-.015.098-.032.098-.018 0-.033.044-.033.098 0 .053-.015.097-.033.097-.017 0-.032.03-.032.065 0 .036-.015.065-.033.065-.018 0-.032.044-.032.098 0 .054-.015.098-.033.098-.018 0-.032.043-.032.097 0 .054-.015.098-.033.098-.018 0-.032.044-.032.098 0 .053-.015.097-.033.097-.018 0-.033.044-.033.098 0 .053-.014.097-.032.097-.018 0-.032.044-.032.098 0 .054-.015.098-.033.098-.018 0-.033.044-.033.097 0 .054-.014.098-.032.098-.018 0-.033.044-.033.098 0 .053-.014.097-.032.097-.018 0-.033.044-.033.098 0 .054-.014.097-.032.097-.018 0-.033.03-.033.066 0 .035-.015.065-.032.065-.018 0-.033.044-.033.097 0 .054-.015.098-.032.098-.018 0-.033.044-.033.098 0 .053-.015.097-.033.097-.018 0-.032.044-.032.098 0 .053-.015.097-.033.097-.018 0-.032.044-.032.098 0 .054-.015.098-.033.098-.018 0-.032.044-.032.097 0 .054-.015.098-.033.098-.018 0-.032.044-.032.098 0 .053-.015.097-.033.097-.018 0-.033.044-.033.098 0 .054-.014.098-.032.098-.018 0-.033.042-.033.094 0 .053-.018.102-.04.11-.023.008-.03.026-.017.04.014.015.052-.005.085-.044.034-.039.085-.07.114-.07.03 0 .054-.015.054-.033 0-.018.026-.032.058-.032.031 0 .079-.03.104-.066.026-.035.067-.065.092-.065.025 0 .086-.043.136-.097.05-.054.109-.098.13-.098.022 0 .08-.044.13-.098.05-.053.109-.097.13-.097.021 0 .095-.059.163-.13.07-.072.141-.13.16-.13.047 0 .98-.933.98-.98 0-.019.058-.09.13-.16.071-.068.13-.142.13-.163 0-.021.044-.08.098-.13.053-.05.097-.108.097-.13 0-.021.044-.08.098-.13.053-.05.097-.114.097-.143 0-.029.015-.052.033-.052.018 0 .032-.026.032-.058s.03-.079.066-.105c.035-.026.065-.07.065-.097 0-.028.029-.072.065-.098.035-.026.065-.073.065-.105s.015-.058.032-.058c.018 0 .033-.03.033-.065 0-.036.015-.065.032-.065.018 0 .033-.03.033-.065 0-.036.015-.065.033-.065.017 0 .032-.03.032-.065 0-.036.015-.065.033-.065.017 0 .032-.03.032-.065 0-.036.015-.066.033-.066.018 0 .032-.029.032-.065 0-.035.015-.065.033-.065.018 0 .032-.029.032-.065 0-.036.015-.065.033-.065.018 0 .032-.03.032-.065 0-.036.015-.065.033-.065.018 0 .033-.03.033-.065 0-.036.014-.065.032-.065.018 0 .033-.044.033-.098 0-.053.014-.098.032-.098.018 0 .033-.043.033-.097 0-.054.014-.098.032-.098.018 0 .033-.029.033-.065 0-.036.014-.065.032-.065.018 0 .033-.044.033-.098 0-.053.014-.097.032-.097.018 0 .033-.059.033-.13 0-.072.015-.13.033-.13.017 0 .032-.044.032-.098 0-.054.015-.098.033-.098.017 0 .032-.073.032-.162 0-.09.015-.163.033-.163.018 0 .032-.059.032-.13 0-.072.015-.13.033-.13.018 0 .032-.087.032-.196 0-.108.015-.195.033-.195.02 0 .032-.12.032-.293 0-.174.014-.293.033-.293.02 0 .032-.282.032-.781 0-.499-.011-.781-.032-.781-.02 0-.033-.12-.033-.293 0-.174-.013-.293-.032-.293-.018 0-.033-.087-.033-.195 0-.109-.014-.195-.032-.195-.018 0-.033-.074-.033-.163 0-.09-.014-.163-.032-.163-.018 0-.033-.058-.033-.13 0-.072-.015-.13-.032-.13-.018 0-.033-.044-.033-.098 0-.054-.015-.097-.032-.097-.018 0-.033-.059-.033-.13 0-.072-.015-.13-.033-.13-.018 0-.032-.045-.032-.098 0-.054-.015-.098-.033-.098-.018 0-.032-.03-.032-.065 0-.036-.015-.065-.033-.065-.018 0-.032-.044-.032-.098 0-.054-.015-.098-.033-.098-.018 0-.032-.043-.032-.097 0-.054-.015-.098-.033-.098-.018 0-.032-.03-.032-.065 0-.036-.015-.065-.033-.065-.018 0-.033-.03-.033-.065 0-.036-.014-.065-.032-.065-.018 0-.033-.04-.033-.09a.178.178 0 00-.065-.138c-.035-.026-.065-.073-.065-.105s-.015-.058-.032-.058c-.018 0-.033-.029-.033-.065 0-.036-.015-.065-.032-.065-.018 0-.033.059-.033.13zM2.538 7.42c0 .036-.014.065-.032.065-.018 0-.033.03-.033.065 0 .036-.014.065-.032.065-.018 0-.033.044-.033.098 0 .054-.014.098-.032.098-.018 0-.033.044-.033.097 0 .054-.014.098-.032.098-.018 0-.033.044-.033.098 0 .053-.015.097-.032.097-.018 0-.033.044-.033.098 0 .054-.015.097-.033.097-.017 0-.032.059-.032.13 0 .072-.015.13-.033.13-.018 0-.032.06-.032.131 0 .072-.015.13-.033.13-.018 0-.032.059-.032.13 0 .072-.015.13-.033.13-.018 0-.032.087-.032.196 0 .108-.015.195-.033.195-.019 0-.032.109-.032.26 0 .152-.014.26-.033.26-.02 0-.033.326-.033.912 0 .586.012.911.033.911.019 0 .033.109.033.26 0 .152.013.261.032.261.018 0 .033.073.033.163 0 .09.014.162.032.162.018 0 .033.074.033.163 0 .09.014.163.032.163.018 0 .033.058.033.13 0 .072.014.13.032.13.018 0 .033.059.033.13 0 .072.015.13.032.13.018 0 .033.045.033.098 0 .054.015.098.033.098.017 0 .032.044.032.098 0 .053.015.097.033.097.018 0 .032.044.032.098 0 .053.015.097.033.097.018 0 .032.03.032.065 0 .036.015.066.033.066.018 0 .032.043.032.097 0 .054.015.098.033.098.018 0 .032.03.032.065 0 .036.015.065.033.065.018 0 .033.044.033.098 0 .053.014.097.032.097.018 0 .033.03.033.065 0 .036.014.065.032.065.018 0 .033.03.033.066 0 .035.014.065.032.065.018 0 .033.029.033.065 0 .035.014.065.032.065.018 0 .033.03.033.065 0 .036.015.065.032.065.018 0 .033.026.033.058s.03.079.065.105c.036.026.065.073.065.105 0 .031.015.057.033.057.018 0 .032.027.032.058 0 .032.03.08.065.105.036.026.065.07.065.098 0 .028.03.072.066.097.035.026.065.07.065.098 0 .028.029.072.065.098.035.026.065.067.065.091 0 .025.044.086.097.137.054.05.098.108.098.129 0 .021.059.095.13.163.072.07.13.141.13.16 0 .047.998 1.044 1.044 1.044.019 0 .106.074.193.163.087.09.176.163.196.163.021 0 .08.044.13.098.05.053.11.097.136.097.024 0 .066.03.091.065.026.036.07.065.098.065.028 0 .072.03.098.066.025.035.073.065.104.065.032 0 .058.014.058.032 0 .018.026.033.058.033s.08.029.105.065c.026.035.073.065.105.065s.058.015.058.032c0 .018.03.033.065.033.036 0 .065.015.065.032 0 .018.026.033.058.033s.079.03.105.065c.025.036.073.065.105.065.031 0 .057.015.057.033 0 .018.015.032.033.032.018 0 .032-.029.032-.065 0-.036-.014-.065-.032-.065-.018 0-.033-.044-.033-.098 0-.053-.014-.097-.032-.097-.018 0-.033-.03-.033-.065 0-.036-.014-.065-.032-.065-.018 0-.033-.044-.033-.098 0-.054-.014-.098-.032-.098-.018 0-.033-.043-.033-.097 0-.054-.014-.098-.032-.098-.018 0-.033-.044-.033-.098 0-.053-.015-.097-.032-.097-.018 0-.033-.03-.033-.065 0-.036-.015-.065-.033-.065-.017 0-.032-.044-.032-.098 0-.054-.015-.098-.033-.098-.018 0-.032-.044-.032-.097 0-.054-.015-.098-.033-.098-.018 0-.032-.044-.032-.098 0-.053-.015-.097-.033-.097-.018 0-.032-.03-.032-.065 0-.036-.015-.065-.033-.065-.018 0-.032-.044-.032-.098 0-.054-.015-.098-.033-.098-.018 0-.033-.043-.033-.097 0-.054-.014-.098-.032-.098-.018 0-.033-.044-.033-.098 0-.053-.014-.097-.032-.097-.018 0-.033-.03-.033-.065 0-.036-.014-.065-.032-.065-.018 0-.033-.044-.033-.098 0-.054-.014-.098-.032-.098-.018 0-.033-.043-.033-.097 0-.054-.015-.098-.032-.098-.018 0-.033-.03-.033-.065 0-.036-.015-.065-.033-.065-.017 0-.032-.044-.032-.098 0-.053-.015-.097-.033-.097-.018 0-.032-.044-.032-.098 0-.054-.015-.098-.033-.098-.018 0-.032-.043-.032-.097 0-.054-.015-.098-.033-.098-.018 0-.032-.03-.032-.065 0-.036-.015-.065-.033-.065-.018 0-.032-.044-.032-.098 0-.053-.015-.097-.033-.097-.018 0-.033-.044-.033-.098 0-.054-.014-.097-.032-.097-.018 0-.033-.044-.033-.098 0-.054-.014-.098-.032-.098-.018 0-.033-.03-.033-.065 0-.036-.014-.065-.032-.065-.018 0-.033-.044-.033-.098 0-.053-.014-.097-.032-.097-.018 0-.033-.044-.033-.098 0-.053-.015-.098-.032-.098-.018 0-.033-.043-.033-.097 0-.054-.015-.098-.033-.098-.017 0-.032-.029-.032-.065 0-.036-.015-.065-.033-.065-.018 0-.032-.044-.032-.098 0-.053-.015-.097-.033-.097-.018 0-.032-.044-.032-.098 0-.053-.015-.097-.033-.097-.018 0-.032-.044-.032-.098 0-.054-.015-.098-.033-.098-.018 0-.032-.029-.032-.065 0-.036-.015-.065-.033-.065-.018 0-.033-.044-.033-.098 0-.053-.014-.097-.032-.097-.018 0-.033-.044-.033-.098 0-.053-.014-.097-.032-.097-.018 0-.033-.044-.033-.098 0-.054-.014-.098-.032-.098-.018 0-.033-.029-.033-.065 0-.036-.014-.065-.032-.065-.018 0-.033-.044-.033-.098 0-.053-.015-.097-.032-.097-.018 0-.033-.044-.033-.098 0-.053-.015-.097-.033-.097-.017 0-.032-.03-.032-.066 0-.035-.015-.065-.033-.065-.018 0-.032-.043-.032-.097 0-.054-.015-.098-.033-.098-.018 0-.032-.044-.032-.098 0-.053-.015-.097-.033-.097-.018 0-.032-.044-.032-.098 0-.053-.015-.097-.033-.097-.018 0-.032-.03-.032-.066 0-.035-.015-.065-.033-.065-.018 0-.032-.043-.032-.097 0-.054-.015-.098-.033-.098-.018 0-.033-.044-.033-.098 0-.053-.014-.097-.032-.097-.018 0-.033-.044-.033-.098 0-.053-.014-.097-.032-.097-.018 0-.033-.03-.033-.065 0-.036-.014-.066-.032-.066-.018 0-.033-.043-.033-.097 0-.054-.014-.098-.032-.098-.018 0-.033-.044-.033-.097 0-.054-.015-.098-.032-.098-.018 0-.033-.044-.033-.098 0-.053-.015-.097-.033-.097-.017 0-.032-.03-.032-.065 0-.036-.015-.066-.033-.066-.018 0-.032-.043-.032-.097 0-.054-.015-.098-.033-.098-.018 0-.032-.044-.032-.097 0-.054-.015-.098-.033-.098-.018 0-.032-.044-.032-.098 0-.053-.015-.097-.033-.097-.018 0-.032-.03-.032-.065 0-.036-.015-.065-.033-.065-.018 0-.033-.044-.033-.098 0-.054-.014-.098-.032-.098-.018 0-.033-.044-.033-.097 0-.054-.014-.098-.032-.098-.018 0-.033-.044-.033-.098 0-.053-.014-.097-.032-.097-.018 0-.033-.03-.033-.065 0-.036-.014-.065-.032-.065-.018 0-.033-.044-.033-.098 0-.054-.015-.098-.032-.098-.018 0-.033-.044-.033-.097 0-.054-.015-.098-.033-.098-.017 0-.032-.03-.032-.065 0-.036-.015-.065-.033-.065-.018 0-.032-.044-.032-.098 0-.053-.015-.097-.033-.097-.018 0-.032-.044-.032-.098 0-.054-.015-.098-.033-.098-.018 0-.032-.044-.032-.097 0-.076-.015-.098-.065-.098-.044 0-.066.022-.066.065zm8.592 4.491c0 .036-.014.065-.032.065-.018 0-.033.044-.033.098 0 .054-.015.098-.032.098-.018 0-.033.043-.033.097 0 .054-.015.098-.033.098-.017 0-.032.044-.032.097 0 .054-.015.098-.033.098-.018 0-.032.044-.032.098 0 .053-.015.097-.033.097-.018 0-.032.044-.032.098 0 .054-.015.098-.033.098-.018 0-.032.044-.032.097 0 .054-.015.098-.033.098-.018 0-.032.03-.032.065 0 .036-.015.065-.033.065-.018 0-.032.044-.032.098 0 .053-.015.097-.033.097-.018 0-.033.044-.033.098 0 .054-.014.098-.032.098-.018 0-.033.044-.033.097 0 .054-.014.098-.032.098-.018 0-.033.044-.033.097 0 .054-.014.098-.032.098-.018 0-.033.044-.033.098 0 .053-.014.097-.032.097-.018 0-.033.044-.033.098 0 .054-.015.098-.033.098-.017 0-.032.044-.032.097 0 .054-.015.098-.033.098-.018 0-.032.044-.032.098 0 .053-.015.097-.033.097-.018 0-.032.044-.032.098 0 .054-.015.098-.033.098-.018 0-.032.029-.032.065 0 .035-.015.065-.033.065-.018 0-.032.044-.032.097 0 .054-.015.098-.033.098-.018 0-.033.044-.033.098 0 .053-.014.097-.032.097-.018 0-.033.044-.033.098 0 .053-.014.098-.032.098-.018 0-.033.043-.033.097 0 .054-.014.098-.032.098-.018 0-.033.044-.033.097 0 .054-.014.098-.032.098-.018 0-.033.044-.033.098 0 .053-.015.097-.032.097-.018 0-.033.044-.033.098 0 .054-.015.098-.032.098-.018 0-.033.043-.033.097 0 .054-.015.098-.033.098-.017 0-.032.044-.032.097 0 .054-.015.098-.033.098-.018 0-.032.044-.032.098 0 .053-.015.097-.033.097-.018 0-.032.03-.032.065 0 .036-.015.066-.033.066-.018 0-.032.044-.032.097 0 .054-.015.098-.033.098-.018 0-.032.044-.032.097 0 .054-.015.098-.033.098-.018 0-.033.044-.033.098 0 .053-.014.097-.032.097-.018 0-.033.044-.033.098 0 .054-.014.098-.032.098-.018 0-.033.043-.033.097 0 .054-.014.098-.032.098-.018 0-.033.044-.033.098 0 .053-.014.097-.032.097-.018 0-.033.044-.033.098 0 .053-.015.097-.032.097-.018 0-.033.044-.033.098 0 .054-.015.098-.033.098-.017 0-.032.044-.032.097 0 .054-.015.098-.033.098-.018 0-.032.044-.032.098 0 .053-.015.097-.033.097-.018 0-.032.03-.032.065 0 .036-.015.065-.033.065-.018 0-.032.044-.032.098 0 .054-.015.098-.033.098-.018 0-.032.042-.032.095 0 .052-.019.1-.04.108-.068.022.056.122.151.122.046 0 .084.015.084.033 0 .017.058.032.13.032.072 0 .13.015.13.033 0 .018.073.032.163.032.09 0 .163.015.163.033 0 .018.086.032.195.032.108 0 .195.015.195.033 0 .019.109.032.26.032.152 0 .26.014.26.033 0 .02.305.032.847.032s.846-.011.846-.032c0-.019.109-.033.26-.033.152 0 .26-.013.26-.032 0-.018.088-.033.196-.033.109 0 .195-.014.195-.032 0-.018.074-.033.163-.033.09 0 .163-.014.163-.032 0-.018.058-.033.13-.033.072 0 .13-.015.13-.032 0-.018.044-.033.098-.033.053 0 .098-.015.098-.032 0-.018.043-.033.097-.033.054 0 .098-.015.098-.033 0-.018.058-.032.13-.032.123 0 .13-.006.13-.098 0-.053-.015-.097-.033-.097-.017 0-.032-.044-.032-.098 0-.054-.015-.098-.033-.098-.017 0-.032-.044-.032-.097 0-.054-.015-.098-.033-.098-.018 0-.032-.044-.032-.098 0-.053-.015-.097-.033-.097-.018 0-.032-.03-.032-.065 0-.036-.015-.065-.033-.065-.018 0-.032-.044-.032-.098 0-.054-.015-.098-.033-.098-.018 0-.032-.043-.032-.097 0-.054-.015-.098-.033-.098-.018 0-.032-.044-.032-.098 0-.053-.015-.097-.033-.097-.018 0-.033-.03-.033-.065 0-.036-.014-.065-.032-.065-.018 0-.033-.044-.033-.098 0-.054-.014-.098-.032-.098-.018 0-.033-.044-.033-.097 0-.054-.014-.098-.032-.098-.018 0-.033-.044-.033-.098 0-.053-.014-.097-.032-.097-.018 0-.033-.03-.033-.065 0-.036-.015-.065-.032-.065-.018 0-.033-.044-.033-.098 0-.054-.015-.098-.033-.098-.018 0-.032-.043-.032-.097 0-.054-.015-.098-.033-.098-.018 0-.032-.044-.032-.098 0-.053-.015-.097-.033-.097-.018 0-.032-.03-.032-.065 0-.036-.015-.065-.033-.065-.018 0-.032-.044-.032-.098 0-.054-.015-.098-.033-.098-.018 0-.033-.043-.033-.097 0-.054-.014-.098-.032-.098-.018 0-.033-.03-.033-.065 0-.036-.014-.065-.032-.065-.018 0-.033-.044-.033-.098 0-.053-.014-.097-.032-.097-.018 0-.033-.044-.033-.098 0-.054-.014-.098-.032-.098-.018 0-.033-.043-.033-.097 0-.054-.014-.098-.032-.098-.018 0-.033-.03-.033-.065 0-.036-.015-.065-.033-.065-.017 0-.032-.044-.032-.098 0-.053-.015-.097-.033-.097-.017 0-.032-.044-.032-.098 0-.054-.015-.097-.033-.097-.018 0-.032-.044-.032-.098 0-.054-.015-.098-.033-.098-.018 0-.032-.03-.032-.065 0-.036-.015-.065-.033-.065-.018 0-.032-.044-.032-.098 0-.053-.015-.097-.033-.097-.018 0-.032-.044-.032-.098 0-.053-.015-.098-.033-.098-.018 0-.033-.043-.033-.097 0-.054-.014-.098-.032-.098-.018 0-.033-.029-.033-.065 0-.036-.014-.065-.032-.065-.018 0-.033-.044-.033-.098 0-.053-.014-.097-.032-.097-.018 0-.033-.044-.033-.098 0-.053-.014-.097-.032-.097-.018 0-.033-.044-.033-.098 0-.054-.015-.098-.033-.098-.017 0-.032-.029-.032-.065 0-.036-.015-.065-.033-.065-.018 0-.032-.044-.032-.098 0-.053-.015-.097-.033-.097-.018 0-.032-.044-.032-.098 0-.053-.015-.097-.033-.097-.018 0-.032-.044-.032-.098 0-.054-.015-.098-.033-.098-.018 0-.032-.029-.032-.065 0-.036-.015-.065-.033-.065-.018 0-.033-.044-.033-.098 0-.053-.014-.097-.032-.097-.018 0-.033-.044-.033-.098 0-.053-.014-.097-.032-.097-.018 0-.033-.03-.033-.066 0-.035-.014-.065-.032-.065-.018 0-.033-.043-.033-.097 0-.054-.014-.098-.032-.098-.018 0-.033.03-.033.065z"
    fill="currentColor"
  />
</svg>
```

::: tip

¿Qué es todo este código?

Son SVG, formatos de imágenes a base de gráficos vectoriales, todos esos números
son coordenadas que permiten identificar al vector cómo pintarse en la pantalla,
la gran ventaja es que su resolución es escalable en cualquier tamaño de
dispositivo y son los que usa la página original. Si quieres conocer un poco más
al respecto, [este artículo](https://graffica.info/formato-svg-ventajas/) talvez
te pueda ayudar.
:::

Ahora si, procedamos a cambiar el contenido:

```html{14-22}
<body>
  <!-- Aquí viene la barra de navegación -->
  <main class="container">
    <header class="header">
      <h1>Free During COVID-19</h1>
      <p>
        Matcha is on a mission to make your blog the biggest asset for your
        business’ growth, especially in today’s context. That’s why we’re
        making the Matcha Platform free forever to all new users who sign up
        during COVID-19.
      </p>
      <div class="platforms">
        <h5>MY BLOG IS POWERED BY</h5>
        <div class="btn-group" role="group" aria-label="Platforms">
          <button type="button" class="btn btn-secondary active">
            <!-- Insertar aquí el ícono de Shopify -->
            Shopify
          </button>
          <button type="button" class="btn btn-secondary">
            <!-- Insertar aquí el ícono de WordPress -->
            WordPress
          </button>
          <button type="button" class="btn btn-secondary">Another CMS</button>
        </div>
      </div>
  </main>
</body>
```

Y ahora, personalicemos su apariencia, haciendo el ajuste de colores y fuente:

```css
/** pricing.css */
.header h5 {
  color: #025157;
  font-size: 12px;
  line-height: 16px;
  text-transform: uppercase;
  margin-bottom: 16px;
}

.header .platforms .btn-group {
  padding: 4px;
  background-color: #f5f5f5;
  border: 1px solid #ccc;
  border-radius: 4px;
}

.header .platforms .btn-group button {
  background-color: transparent;
  color: #4b4b4b;
  width: 160px;
  height: 40px;
  font-size: 15px;
  line-height: 1;
  border: none;
}

.header .platforms .btn-group button.active {
  background-color: white;
  color: #67b54b;
  border: 1px solid #d9d9d9;
  border-radius: 4px;
}

.header .platforms .btn-group button > img {
  margin-right: 5px;
}
```

Con esto ya conocemos un componente más que podemos usar de Bootstrap, aquí
puedes revisar como te debería ir quedando:

![Sección principal de página de pricing](./assets/pricing-main-section.png)

Ahora vamos a saltar la parte del medio, dado que usa cards el cual ya lo vimos,
y vamos a aprovechar en conocer otro componente como el _acordión_.

#### Guía: Agregando la sección de Faqs

La sección de Faqs tiene 2 particularidas, el contenido está divido en 2
columnas y la forma de ver la respuesta es clickeando sobre la pregunta. A esta
última forma de interacción, se le conoce como _acordión_.

Bootstrap cuenta con un componente llamado [Collapse](https://getbootstrap.com/docs/4.4/components/collapse/)
que nos permite lograr esta interfaz.

Vamos a agregar este componente a nuestra página, tomando el [ejemplo de carousel](https://getbootstrap.com/docs/4.4/components/collapse/#accordion-example)
que viene en la documentación, comencemos por agregar la sección en nuestra
estructura y pegar el ejemplo:

```html
<body>
  <!-- Aquí viene lo construido hasta el momento -->
  <section class="faq">
    <div class="accordion" id="accordionExample">
      <div class="card">
        <div class="card-header" id="headingOne">
          <h2 class="mb-0">
            <button
              class="btn btn-link"
              type="button"
              data-toggle="collapse"
              data-target="#collapseOne"
              aria-expanded="true"
              aria-controls="collapseOne"
            >
              Collapsible Group Item #1
            </button>
          </h2>
        </div>

        <div
          id="collapseOne"
          class="collapse show"
          aria-labelledby="headingOne"
          data-parent="#accordionExample"
        >
          <div class="card-body">
            Anim pariatur cliche reprehenderit, enim eiusmod high life accusamus
            terry richardson ad squid. 3 wolf moon officia aute, non cupidatat
            skateboard dolor brunch. Food truck quinoa nesciunt laborum eiusmod.
            Brunch 3 wolf moon tempor, sunt aliqua put a bird on it squid
            single-origin coffee nulla assumenda shoreditch et. Nihil anim
            keffiyeh helvetica, craft beer labore wes anderson cred nesciunt
            sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings
            occaecat craft beer farm-to-table, raw denim aesthetic synth
            nesciunt you probably haven't heard of them accusamus labore
            sustainable VHS.
          </div>
        </div>
      </div>
      <div class="card">
        <div class="card-header" id="headingTwo">
          <h2 class="mb-0">
            <button
              class="btn btn-link collapsed"
              type="button"
              data-toggle="collapse"
              data-target="#collapseTwo"
              aria-expanded="false"
              aria-controls="collapseTwo"
            >
              Collapsible Group Item #2
            </button>
          </h2>
        </div>
        <div
          id="collapseTwo"
          class="collapse"
          aria-labelledby="headingTwo"
          data-parent="#accordionExample"
        >
          <div class="card-body">
            Anim pariatur cliche reprehenderit, enim eiusmod high life accusamus
            terry richardson ad squid. 3 wolf moon officia aute, non cupidatat
            skateboard dolor brunch. Food truck quinoa nesciunt laborum eiusmod.
            Brunch 3 wolf moon tempor, sunt aliqua put a bird on it squid
            single-origin coffee nulla assumenda shoreditch et. Nihil anim
            keffiyeh helvetica, craft beer labore wes anderson cred nesciunt
            sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings
            occaecat craft beer farm-to-table, raw denim aesthetic synth
            nesciunt you probably haven't heard of them accusamus labore
            sustainable VHS.
          </div>
        </div>
      </div>
      <div class="card">
        <div class="card-header" id="headingThree">
          <h2 class="mb-0">
            <button
              class="btn btn-link collapsed"
              type="button"
              data-toggle="collapse"
              data-target="#collapseThree"
              aria-expanded="false"
              aria-controls="collapseThree"
            >
              Collapsible Group Item #3
            </button>
          </h2>
        </div>
        <div
          id="collapseThree"
          class="collapse"
          aria-labelledby="headingThree"
          data-parent="#accordionExample"
        >
          <div class="card-body">
            Anim pariatur cliche reprehenderit, enim eiusmod high life accusamus
            terry richardson ad squid. 3 wolf moon officia aute, non cupidatat
            skateboard dolor brunch. Food truck quinoa nesciunt laborum eiusmod.
            Brunch 3 wolf moon tempor, sunt aliqua put a bird on it squid
            single-origin coffee nulla assumenda shoreditch et. Nihil anim
            keffiyeh helvetica, craft beer labore wes anderson cred nesciunt
            sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings
            occaecat craft beer farm-to-table, raw denim aesthetic synth
            nesciunt you probably haven't heard of them accusamus labore
            sustainable VHS.
          </div>
        </div>
      </div>
    </div>
  </section>
</body>
```

En este caso, estamos solo realizando la primera columna de preguntas frecuentes.

#### Challenge: Cambiando la información del acordión

Reconoce la estructura del acordión e identifica los lugares en los que se debe
modificar para cambiar el contenido del mismo.

Verifica los enlaces en la respuesta y trata de cambiar los estilos de los
textos para que queden algo similar a:

![Primera columna de FAQs](./assets/faqs-first-column.png)

<details>
  <summary>Posible solución</summary>

```html
<section class="faq">
  <div class="accordion" id="first-column-accordion">
    <div class="card">
      <div class="card-header" id="get-started-heading">
        <h2 class="mb-0">
          <button
            class="btn btn-link"
            type="button"
            data-toggle="collapse"
            data-target="#get-started-collapse"
            aria-expanded="false"
            aria-controls="get-started-collapse"
          >
            How can I get started?
          </button>
        </h2>
      </div>

      <div
        id="get-started-collapse"
        class="collapse"
        aria-labelledby="get-started-heading"
        data-parent="#first-column-accordion"
      >
        <div class="card-body">
          Getting started is easy! Simply
          <a href="#">create a free account</a> to start using the Platform and
          exploring the library. Want to start publishing? When you click the
          “Publish” button on a piece of licensed content, you’ll be prompted to
          input your credit card information before continuing. Questions?
          <a href="#">Reach out to our customer support team for assistance!</a>
        </div>
      </div>
    </div>
    <div class="card">
      <div class="card-header" id="license-content-heading">
        <h2 class="mb-0">
          <button
            class="btn btn-link collapsed"
            type="button"
            data-toggle="collapse"
            data-target="#license-content-collapse"
            aria-expanded="false"
            aria-controls="license-content-collapse"
          >
            What is licensed content?
          </button>
        </h2>
      </div>
      <div
        id="license-content-collapse"
        class="collapse"
        aria-labelledby="license-content-heading"
        data-parent="#first-column-accordion"
      >
        <div class="card-body">
          Licensed content, sometimes called syndicated content, is content
          produced by a professional publisher that can be legally licensed for
          use on your own website with no SEO penalty.
          <a href="#">Learn more</a>. The Matcha library leverages licensed
          content to provide you with a low-cost supply of professionally
          written articles that are proven to be engaging. It eliminates the
          headache and time of producing your own blog articles, allowing you to
          get back to more pressing matters. When we say, “professional
          publishers”, we mean it. Currently, our library includes articles from
          the following publishers: Oxygen Magazine, Better Nutrition, Popular
          Science, Field & Stream, Coach, RootsRated, Business2Community,
          MoneyNing, YourMoneyGeek Working Mother, Clean Eating, and Healthy
          Moms Magazine.
        </div>
      </div>
    </div>
    <div class="card">
      <div class="card-header" id="library-content-heading">
        <h2 class="mb-0">
          <button
            class="btn btn-link collapsed"
            type="button"
            data-toggle="collapse"
            data-target="#library-content-collapse"
            aria-expanded="false"
            aria-controls="library-content-collapse"
          >
            What is the Matcha content library?
          </button>
        </h2>
      </div>
      <div
        id="library-content-collapse"
        class="collapse"
        aria-labelledby="library-content-heading"
        data-parent="#first-column-accordion"
      >
        <div class="card-body">
          Matcha offers a library of more than 10,000 articles with photography
          and written by high-quality third-party publishers. You can publish an
          article from the library to your blog in a matter of minutes. In 2018
          alone, our articles garnered 8.9 million website visits for our
          customers. The data shows that readers find the articles engaging and
          perform as well or better than custom articles. You can see the study
          <a href="#">here</a>. Every week, we are bringing in hundreds of new
          articles to our library. Our library publishers include: Oxygen
          Magazine, Better Nutrition, Popular Science, Field & Stream, Coach,
          RootsRated, Business2Community, MoneyNing, YourMoneyGeek Working
          Mother, Clean Eating, and Healthy Moms Magazine.
        </div>
      </div>
    </div>
  </div>
</section>
```

```css
.faq {
  background-color: white;
  padding-bottom: 120px;
}

.faq h2 {
  color: #025157;
  font-family: "Alegreya", serif;
  margin-bottom: 60px;
}

.faq .card-header {
  background-color: white;
  border-left: 1px solid rgba(0, 0, 0, 0.125);
}

.faq .card-header h2 > button {
  color: #025157;
  font-size: 28px;
}

.faq .card .card-body a {
  color: #6abf4b;
}
```

</details>

Yay! Con esto ya vimos un nuevo componente, ¿te has puesto imaginar cómo haríamos
para poder agregar la siguiente columna? Si pasó por tu mente cosas como Flexbox,
Grid CSS, o display y floats. Cualquiera es un approach correcto, sin embargo,
Bootstrap tiene utilidades para controlar el layout en formato de [Grid](https://getbootstrap.com/docs/4.4/layout/grid/).

#### Guía: Agregando la siguiente columna de preguntas frecuentes

En este caso, dado que usaremos la grid de Bootstrap, debemos de agregar ciertos
contenedores para dividir nuestra interfaz en columnas:

```html
<section class="faq">
  <div class="container">
    <div class="row">
      <div class="col">
        <div class="accordion" id="first-column-accordion">
          <!-- Aquí viene lo que hicimos para la primera columna -->
        </div>
      </div>
      <div class="col"></div>
    </div>
  </div>
</section>
```

Agregando un contenedor con clase `container` y otro con clase `row`, podemos
agregar la cantidad de columnas que queramos usando contenedores con clase `col`.
En este caso, tocaría agregar la segunda columna.

#### Challenge: Agrega la segunda columna de preguntas frecuentes

Esta reto parece simple porque podríamos pensar que hacemos los mismos pasos,
copiar y pegar el ejemplo de Bootstrap y cambiar el contenido, sin embargo,
te recomendamos prestar especial atención a los ids que vienen en el ejemplo de
Bootstrap dado que si son iguales a los de la otra columna, puede que encuentres
un comportamiento extraño. No dudes en consultar al experto si no logras entender
del todo porqué se da dicho comportamiento.

<details>
  <summary>Posible solución</summary>

```html
<div class="col">
  <div class="accordion" id="second-column-accordion">
    <div class="card">
      <div class="card-header" id="who-uses-heading">
        <h2 class="mb-0">
          <button
            class="btn btn-link"
            type="button"
            data-toggle="collapse"
            data-target="#who-uses-collapse"
            aria-expanded="false"
            aria-controls="who-uses-collapse"
          >
            Who uses Matcha?
          </button>
        </h2>
      </div>

      <div
        id="who-uses-collapse"
        class="collapse"
        aria-labelledby="who-uses-heading"
        data-parent="#second-column-accordion"
      >
        <div class="card-body">
          Hundreds of growing and established B2C and B2B brands use Matcha on
          their ecommerce site. Matcha is specifically built for companies that
          are selling on their website direct-to-consumer and will help you to
          grow and engage your audience. We work with companies in the outdoor &
          travel, food & beverage, CPG, home & family, beauty & fashion,
          apparel, fitness, and health & wellness industries, as well as with
          B2B businesses in the marketing industry. You can see more about our
          customers <a href="#">here</a>.
        </div>
      </div>
    </div>
    <div class="card">
      <div class="card-header" id="what-do-i-need-heading">
        <h2 class="mb-0">
          <button
            class="btn btn-link collapsed"
            type="button"
            data-toggle="collapse"
            data-target="#what-do-i-need-collapse"
            aria-expanded="false"
            aria-controls="what-do-i-need-collapse"
          >
            What do I need to use Matcha?
          </button>
        </h2>
      </div>
      <div
        id="what-do-i-need-collapse"
        class="collapse"
        aria-labelledby="what-do-i-need-heading"
        data-parent="#second-column-accordion"
      >
        <div class="card-body">
          As long as you have a blog set up on your website, you can begin
          publishing to Matcha and making data-driven decisions with content
          analytics. We integrate directly with WordPress and Shopify to make
          publishing even faster, but a WordPress or Shopify blog is not
          required. If you don’t have a blog on your site, they’re typically
          easy to set up.
          <a href="#">Contact us</a> to learn more.
        </div>
      </div>
    </div>
    <div class="card">
      <div class="card-header" id="more-question-heading">
        <h2 class="mb-0">
          <button
            class="btn btn-link collapsed"
            type="button"
            data-toggle="collapse"
            data-target="#more-question-collapse"
            aria-expanded="false"
            aria-controls="more-question-collapse"
          >
            Have more questions?
          </button>
        </h2>
      </div>
      <div
        id="more-question-collapse"
        class="collapse"
        aria-labelledby="more-question-heading"
        data-parent="#second-column-accordion"
      >
        <div class="card-body">
          <a href="#">Contact us</a>! We’re happy to help.
        </div>
      </div>
    </div>
  </div>
</div>
```

El CSS que aplicamos a la primera columna funciona igual para esta segunda.

</details>

Wao! Esto ha sido bastante por hoy, tenemos ahora un sitio web con 2 páginas y
muchos componentes de Bootstrap, no olvides revisar el postwork para que sigas
practicando sobre este tema. Al final tu sección de FAQs debió quedar algo
similar a:

![FAQs de Matcha](./assets/faqs-two-columns.png)

### Desplegando nuestros cambios

Esto probablemente ya lo has venido haciendo muchas veces, pero no está demás
recordarlo.

Agrega tus cambios realizados a `git`:

```bash
$ git add -A
```

Agrega un mensaje descriptivo a tu nueva versión:

```bash
$ git commit -m "Agrega componentes de Bootstrap"
```

Sube tus cambios a Github para que tengas un respaldo y siempre lo puedas
descargar en cualquier otro ordenador:

```bash
$ git push origin <nombre-rama> # `master` si no estás trabajando en otra rama
```

Al realizar este último comando tus cambios estarán reflejados en `Netlify` y
podrás revisar tu web publicada en internet, esperando que se vea algo como (o
incluso mucho mejor):

![Resultado de home responsive](./assets/end-result.png)
