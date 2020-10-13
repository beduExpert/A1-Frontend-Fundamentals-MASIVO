# HTML de la barra de navegación

Para nuestra barra de navegación usaremos la etiqueta `header` ya que es la
cabecera de nuestra página. Dentro de esta etiqueta pondremos otros 3
contenedores: un link conel logo dentro, el menú de navegación y el contenedor
de acciones de usuario.

```html
<header>
  <!-- Logo con link a la página principal -->
  <a>
    <img />
  </a>
  <!-- Menú de navegación -->
  <nav></nav>
  <!-- Contenedor de acciones de usuario -->
  <div></div>
</header>
```

> TIP: La etiqueta `a` sirve para agregar un enlace interno o externo. Para
> indicar la dirección de dicho enlace se usa el atributo `href` y su contenido
> interno puede ser un texto, una imagen o combinación de estos u otros
> elementos. En nuestro caso, queremos que el link apunte a la página inicial,
> esto se puede lograr escribiendo `/` (barra diagonal) que hace referencia a la
> raíz (punto de partida) de la página.



# Agregando separación entre barra de navegación y contenido

Si se percataron, la barra de navegación en la página original no está pegada al
borde superior del navegador, en cambio, esta se encuentra a una distancia fija
y el contenido de igual manera se encuentra a una distancia específica de la
barra de navegación.

Para agregar este tipo de espaciados, podemos usar la propiedad `margin`, que
nos permite poner un margen de separación entre elementos, ya sea en cualquiera
de los 4 lados de la caja (arriba, derecha, abajo e izquierda).

Para el caso de la barra de navegación agregaremos un margen superior de `40px` y
un margen a cada lado de `20px`. Ya que este margen queremos dárselo a toda la
barra, se lo aplicaremos al elemento `header`. Para evitar que en caso
agreguemos algún otro header en alguna sección de la página, vamos a agregarle
un atributo de clase a la etiqueta header y aplicar el estilo a dicha etiqueta a
través del selector de clase:

```html
<header class="header">
  <!-- Contenido del header -->
</header>
```

```css
.header {
  margin-top: 40px;
  margin-left: 20px;
  margin-right: 20px;
}
```

