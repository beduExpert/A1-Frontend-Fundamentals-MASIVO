# Agregando primera columna del blog

De esta manera ya hemos indicado que la sección de blog va a utilizar tres
columnas. Comencemos por agregar el contenido de la primera columna:

```html{4-34}
<section class="container blog">
  <div class="row">
    <div class="col">
      <h2 class="title">Learn how to grow your ecommerce business.</h2>
      <article class="process-list">
        <div class="process">
          <div class="process-icon">
            <img src="./icons/build.svg" alt="Build icon" />
          </div>
          <div class="process-description">
            <h3>Build</h3>
            <p>and scale your ecommerce store</p>
          </div>
        </div>
        <div class="process">
          <div class="process-icon">
            <img src="./icons/attract.svg" alt="Attract icon" />
          </div>
          <div class="process-description">
            <h3>Attract</h3>
            <p>your target audience and grow site traffic</p>
          </div>
        </div>
        <div class="process">
          <div class="process-icon">
            <img src="./icons/convert.svg" alt="Convert icon" />
          </div>
          <div class="process-description">
            <h3>Convert</h3>
            <p>readers to subscribers and customers</p>
          </div>
        </div>
      </article>
      <button>Read the blog</button>
    </div>
    <div class="col"></div>
    <div class="col"></div>
  </div>
</section>
```

Hemos ido agregando clases que luego utilizaremos para cambiar la apariencia que
se tiene por defecto.

:::tip

En este caso, estamos usando rutas relativas para las imágenes, si no tienes
estas imágenes las puedes encontrar en:

- [Ícono de build](https://github.com/ivandevp/bedu-fullstack-js/blob/master/docs/sesiones/07-email-bienvenida/end-result/icons/build.svg)
- [Ícono de attract](https://github.com/ivandevp/bedu-fullstack-js/blob/master/docs/sesiones/07-email-bienvenida/end-result/icons/attract.svg)
- [Ícono de convert](https://github.com/ivandevp/bedu-fullstack-js/blob/master/docs/sesiones/07-email-bienvenida/end-result/icons/convert.svg)

Estos íconos fueron guardados en una carpeta `icons` en la raíz del proyecto. Si
utilizas otra ruta para guardar estos íconos asegúrate de cambiarle la ruta
relativa.

:::

Como vemos en el resultado de esta estructura, toma ciertos estilos por defecto
pero que no son exactamente lo que queremos. Vamos a cambiar su apariencia
usando Sass. Empecemos por solucionar el ancho del contenedor de la sección:

```scss
/** main.scss */
.blog {
  background-color: #ffffff;
  max-width: unset;
  padding: 5% 10%;
}
```

Con esto ya tenemos el fondo de color blanco aplicado correctamente a la sección
de blog y también el margen respectivo. Ahora vamos a terminar de crear los
estilos de la primera columna, y podemos percatarnos de que los estilos son muy
similares, es decir, vamos a usar los mismos colores que en otras secciones, así
como tamaño y tipos de fuente. ¿Qué tal si las almacenamos en un único lugar y
que si en algún momento tuviéramos que cambiar el tipo de fuente o color de la
marca, lo haríamos en un solo lugar y no en todos los que usamos? Esto es posible
gracias a que Sass nos provee el uso de [variables](https://sass-lang.com/documentation/variables).

Para esto vamos a crear un archivo llamado `_global.scss` en la carpeta `scss`.

La estructura debería quedar:

```text
.
+-- scss/
+----- _global.scss
+----- main.scss
+-- index.html
+-- styles.css
```

Posteriormente vamos a crear algunas variables para los colores que vamos a
utilizar en esta columna:

```scss
/** _global.scss */
$dark-green-title: #025157;
$dark-green-text: #135359;
$white: #ffffff;
```

Con las variables definidas, podremos usarlas en nuestro `main.scss` haciendo
referencia al nombre de la variable y si en algún momento cambiaran los colores
por un rediseño de marca por ejemplo, solo tendríamos que cambiarlo en nusetro
archivo `_global.scss` y esto afectaría a todos los lugares que la usan.

Por último, vamos a hacer una clase placeholder que otras clases puedan usar
como base, esto lo haremos para el título, ya que la fuente, color y tamaño es
común en otras secciones de la página. Para esto usaremos la funcionalidad de
[extensión o herencia](https://sass-lang.com/documentation/at-rules/extend) que
Sass nos provee. Empecemos por crear una variable para la fuente del título:

```scss{8-9}
/** _global.scss */

/** colores */
$dark-green-title: #025157;
$dark-green-text: #135359;
$white: #ffffff;

/** fuentes */
$font-title: "Alegreya", serif;
```

Y ahora definamos la clase de placeholder:

```scss{11-15}
/** _global.scss */

/** colores */
$dark-green-title: #025157;
$dark-green-text: #135359;
$white: #ffffff;

/** fuentes */
$font-title: "Alegreya", serif;

/** placeholders */
%base-title {
  font-family: $font-title;
  color: $dark-green-text;
}
```

De esta forma ya hemos creado valores que a través de un identificador, podemos
usarla en nuestro código. Probablemente te quede una duda, cómo vamos a hacer
para que nuestro `main.scss` use los valores que hemos definido en otro archivo
llamado `_global.scss`. Para esto aprovecharemos la característica de módulos de
Sass, que a través de una regla llamada [`@use`](https://sass-lang.com/documentation/at-rules/use)
podemos indicar que tenga acceso a las variables definidas en el otro archivo.

Utilicemos `@use` para usar nuestras variables en el archivo `main.scss`:

```scss{2,5}
/** main.scss */
@use 'global' as *;

.blog {
  background-color: $white;
  max-width: unset;
  padding: 5% 10%;
}
```

Dado que `@use` hace uso de un _namespace_ para identificar todas las variables
que se exportan desde el módulo que indicamos, en nuestro caso le hemos puesto
un `*` para no tener que estar escribiendo un nombre de espacio antes de cada
vaiable que queramos usar. A su vez, hicimos la prueba cambiando el color de
fondo de la sección usando la variable `$white` que definimos en el otro archivo.

Ahora si estamos listos para agregar nuestros estilos a la primera columna,
empecemos por el título:

```scss{9-11}
/** main.scss */
@use 'global' as *;

.blog {
  background-color: $white;
  max-width: unset;
  padding: 5% 10%;

  .title {
    @extend %base-title;
  }
}
```

Acá hicimos uso de la regla `@extend` para heredar la clase de placeholder que
definimos en el archivo `_global.scss` y además usamos la funcionalidad de
[`nesting`](https://sass-lang.com/documentation/style-rules/declarations#nesting)
que nos permite definir selectores dentro de otros selectores, esto terminaría
compilándose en el css a `.blog .title` sin la necesidad que nosotros lo
escribamos de dicha forma.

Ahora, pongamos un poco de estilos a la lista de procesos:

```scss{13-20}
/** main.scss */
@use 'global' as *;

.blog {
  background-color: $white;
  max-width: unset;
  padding: 5% 10%;

  .title {
    @extend %base-title;
  }

  .process-list {
    margin-top: 40px;
    margin-bottom: 36px;

    .process {
      margin-bottom: 25px;
    }
  }
}
```

Hemos agregado un poco de espaciado a la lista de procesos y entre cada uno de
los procesos, ahora vamos a definir propiedades específicas para el texto que
está dentro de cada proceso. Usaremos el [`parent selector`](https://sass-lang.com/documentation/style-rules/parent-selector)
de Sass para hacer referencia al selector padrer y aplicar un selector de CSS
más específico:

```scss{20-31}
/** main.scss */
@use 'global' as *;

.blog {
  background-color: $white;
  max-width: unset;
  padding: 5% 10%;

  .title {
    @extend %base-title;
  }

  .process-list {
    margin-top: 40px;
    margin-bottom: 36px;

    .process {
      margin-bottom: 25px;

      & > div {
        & > h3 {
          color: $dark-green-title;
          margin-bottom: 0;
          font-size: 30px;
          font-weight: 500;
        }
        & > p {
          color: $dark-green-text;
          margin: 0;
        }
      }
    }
  }
}
```

Y ahora agreguemos estilos para el ícono de cada uno de los procesos:

```scss{33-42}
/** main.scss */
@use 'global' as *;

.blog {
  background-color: $white;
  max-width: unset;
  padding: 5% 10%;

  .title {
    @extend %base-title;
  }

  .process-list {
    margin-top: 40px;
    margin-bottom: 36px;

    .process {
      margin-bottom: 25px;

      & > div {
        & > h3 {
          color: $dark-green-title;
          margin-bottom: 0;
          font-size: 30px;
          font-weight: 500;
        }
        & > p {
          color: $dark-green-text;
          margin: 0;
        }
      }

      .process-icon {
        width: 60px;
        height: 60px;
        margin-right: 10px;
        text-align: center;

        img {
          height: 100%;
        }
      }
    }
  }
}
```

Por último, agreguemos los estilos del botón:

```scss{33-42}
/** main.scss */
@use 'global' as *;

.blog {
  background-color: $white;
  max-width: unset;
  padding: 5% 10%;

  .title {
    @extend %base-title;
  }

  .process-list {
    margin-top: 40px;
    margin-bottom: 36px;

    .process {
      margin-bottom: 25px;

      & > div {
        & > h3 {
          color: $dark-green-title;
          margin-bottom: 0;
          font-size: 30px;
          font-weight: 500;
        }
        & > p {
          color: $dark-green-text;
          margin: 0;
        }
      }

      .process-icon {
        width: 60px;
        height: 60px;
        margin-right: 10px;
        text-align: center;

        img {
          height: 100%;
        }
      }
    }
  }

  button {
    height: auto;
    border-top-left-radius: 8px;
    border-bottom-left-radius: 8px;
    padding: 12px;
    width: 180px;
    margin-bottom: 15px;
  }
}
```
