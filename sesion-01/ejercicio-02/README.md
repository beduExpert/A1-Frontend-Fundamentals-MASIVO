# Creando nuestro HTML

## REQUISITOS

- Tener Git Bash si usas Windows.
- Tener un editor de código instalado

## INSTRUCCIONES

Es momento de abrir nuestro editor de texto (ejemplo: Visual Studio Code) y
abrir el directorio que creamos en dicho editor, selecciona tu archivo
`index.html` y prepárate para ensuciarte las manos.

Las etiquetas mínimas a incluir en todos los documentos de HTML que creemos son:

```html
<!DOCTYPE html>
<html>
  <head>
    <!-- Aquí va información importante pero no visible dentro del navegador -->
   
  </head>
  <body>
    <!-- Esto es lo que se verá en el navegador web -->
  </body>
</html>
```

Analicemos las etiquetas del código anterior:

- `<!DOCTYPE html>`. Esta etiqueta rompe con el patrón de las sintaxis vistas
  anteriormente, pero no te preocupes, es una de las únicas que tienen una
  sintaxis particular y la usarás para indicarle al navegador web la versión
  de HTML que usarás. En este caso, esta sintaxis está indicando que usaremos
  `HTML 5`. Resulta que `HTML` ha pasado por diversas versiones, la diferencia
  entre ellas son principalmente las capacidades que estas soportan, por ejemplo,
  más adelante te darás cuenta que existen etiquetas que te ayudarán a expresar
  mejor el tipo de contenido que estas reflejarán al navegador (ejemplo: `nav`,
  `section`, `header`, `footer`, entre otras) que en versiones anteriores del
  lenguaje no existían.

  Ejemplo de cómo indicar al navegador que usaremos HTML 4:

  ```html
  <!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
  ```

  ¿Mejor nos quedamos con `HTML 5` no?

- `<html></html>`. Es momento de que te enteres que todo en HTML es una
  estructura jerárquica, y como en toda jerarquía siempre existe un extremo a
  partir del cual todo inicia. Esta es la etiqueta que indica el punto de partida
  de la página, todo lo que se encuentre dentro será el contenido que el
  navegador tomará en cuenta para mostrar a lxs usuarixs. Esta etiqueta en
  particular tiene 2 _"hijos"_ que encontrarás en todas las páginas web:
  `<head></head>` y `<body></body>`.

- `<head></head>`. En esta etiqueta se encontrará toda la información relevante
  del sitio web pero que no se muestran como tal. Por ejemplo, acá podemos
  indicar el título de la página, el ícono, si debe de importar algún estilo que
  personalice la apariencia de nuestro contenido, información de la descripción
  de la página para que se muestren en los resultados de búsqueda de internet,
  etc.

- `<title></title>`. Esta etiqueta permite indicar cuál es el título que el
  navegador debe mostrar cuando un usuario este navegando en nuestro sitio web.

- `<body></body>`. Esta etiqueta nos sirve para delimitar todo el contenido de
  la página web y es dentro de esta que encontramos todo lo que vemos cada vez
  que visitamos un sitio. Botones, textos, imágenes y demás se definen dentro
  de esta etiqueta.


## Segundo texto

Así que, ¿por qué no le agregamos el siguiente texto que encontramos en la web
de `Matcha`? ¿Qué peso jerárquico y por ende qué etiqueta le pondrías al
encabezado? ¿Y si fuese un párrafo en vez de un encabezado? ¿Cuál sería la
diferencia?

##### Posible solución

```html
<!DOCTYPE html>
<html>
  <head>
    <!-- Aquí va información importante pero no visible dentro del navegador -->
    <title>Matcha</title>
  </head>
  <body>
    <!-- Esto es lo que se verá en el navegador web -->
    <h1>Build your blog. Build your business.</h1>
    <h4>
      Instantly publish articles, drive more traffic, grow your email list, and
      see your blog’s impact on sales.
    </h4>
    <!-- O usando un párrafo -->
    <!--
      <p>
        Instantly publish articles, drive more traffic, grow your email list, 
        and see your blog’s impact on sales.
      </p>
    -->
  </body>
</html>
```

La principal diferencia es el peso semántico que le queremos dar al texto, si
el texto que queremos mostrar no es necesariamente diferente a cualquier otro
texto que tengamos en la web, probablemente un párrafo funcione bien y luego
podríamos cambiar su apariencia para darle los efectos visuales deseados, sin
embargo, si deseamos resaltar dicho texto sobre otros existentes, podemos usar
un encabezado para darle una jerarquía y diferenciarlo de los demás.