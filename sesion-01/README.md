# Sesión: Estructura tu sitio

Sigue el contenido a continuación durante clase para que no te pierdas ningún
detalle de lo que estás a punto de aprender.

## Objetivos

En esta sesión aprenderás:

- Interactuar con la terminal para crear una estructura de archivos para tu
  proyecto.
- Crear una estructura base de tu página web a partir del uso de etiquetas de
  HTML.
- Personalizar la apariencia de tu página a través de cambios que se aplican a
  través de CSS.
- Usar comandos de GIT para almacenar tus cambios realizados en la red social
  más usada por lxs programadorxs (Github).
- Desplegar tu página para que sea visible a todo el mundo de una manera
  sencilla y gratuita.

## Contenido

### Creando la estructura de tu proyecto

Todo desarrollo de proyecto web se hace a través de código, comandos que
escribimos y que luego programas usan para traducirlo en algo que entienda la
computadora. Sin embargo, es necesario entender que la computadora solo entiende
1s y 0s, lo cual es muy complejo para nosotros como humanos entender. Debido a
esto, se crearon lenguajes que actúan como intermediarios entre las computadoras
y humanos. En esta sesión vamos a estar interactuando principalmente con 2
lenguajes: **HTML y CSS**.

Debido a que son 2 lenguajes con propósitos distintos, es importante mantener un
orden en los recursos que usaremos para construir nuestro sitio web, por lo cual
es importante que usemos una estructura ordenada para tener un mejor control y
entendimiento sobre como llevar a cabo nuestro proyecto. Dicha estructura la
construiremos usando comandos en nuestra terminal que indicarán a la computadora
que realice exactamente lo que nosotros le pidamos.

#### Concepto: Terminal

La terminal es un programa de computadora que nos sirve para indicar acciones
específicas que deseamos realizar. Todo lo que normalmente estamos acostumbrados
a realizar a través de la interfaz gráfica que nos aparece en nuestras pantallas
del computador y que con ayuda del _mouse_ y el _teclado_ podemos indicar lo que
queremos hacer es posible realizarlo a través de **comandos** escritos en la
terminal.

Por ejemplo, normalmente para crear un directorio (carpeta), entrarías a un
_Explorador de archivos_, y luego darías click hasta llegar a la ubicación donde
se desea crear, presionas click derecho y le das nueva carpeta o dependiendo de
la computadora que utilices encontrarás un ícono que te dará un acceso rápido a
realizar exactamente esta misma acción.

Si bien este flujo es normal y probablemente no lo dejemos de hacer por la
rapidez, velocidad, costumbre, entre otros factores. Como programadorxs,
acostumbramos a realizar las mismas acciones desde la terminal usando solo el
teclado, esto por la rapidez y control que se siente sobre la computadora, pero
también porque en algunas actividades que realizamos (sobre todo cuando
configuramos servidores) no contamos con una interfaz gráfica y la terminal se
vuelve nuestra única amiga.

> TIP: La terminal también es comúnmente llamada como _consola_, _CLI_, _bash_
> (no necesariamente bien usado), _shell_ (a pesar que no es lo mismo) y tal vez
> te encontrarás con otro término dependiendo de la persona de quien lo escuches
> o leas.

#### Guía: Creación de estructura de proyecto

1. Abrir la terminal (tener en cuenta que la interfaz puede cambiar dependiendo
   del sistema operativo que tengas).

2. Por defecto, cuando abrimos la terminal este se ubica en el directorio
   principal (_home_) de nuestro computador. Podemos verificar cuál es dicho
   directorio a través del comando `pwd`.

   ```bash
   $ pwd # Present Working Directory
   /Users/bedu
   ```

3. Una vez que sepas en donde te encuentras probablemente quieras ir a alguna
   otra ubicación para crear la carpeta del proyecto. Digamos que queremos
   crearlo dentro de la carpeta _Documents_ (el nombre puede variar dependiendo
   del sistema operativo). El comanto que nos permite acceder o movernos de
   ubicación es `cd`. A diferencia del comando anterior, éste es procedido por
   el nombre del directorio al que nos queremos mover.

   ```bash
   $ cd Documents # "Change Directory" a Documents
   ```

   > TIP: Si quieres verificar que realmente se haya cambiado de ubicación,
   > puedes usar el comando anterior para comprobarlo:
   >
   > ```bash
   > $ pwd
   > /Users/bedu/Documents
   > ```

4. Ahora que ya te encuentras donde deseas crear tu proyecto, es momento de
   crear un directorio donde almacenarás todos los archivos que terminarás
   utilizando. Para crear dicho directorio puedes usar el comando `mkdir`, al
   igual que `cd`, este comando necesita que le indiques el nombre del
   directorio que deseas crear.

   ```bash
   $ mkdir matcha # Make Directory "matcha"
   ```

5. El comando que acabas de ejecutar, ha creado una carpeta llamada `matcha`,
   una forma de verificar si se ha creado es listando todo lo que se encuentra
   en la ubicación actual. Para esto, usa el comando `ls`.

   ```bash
   $ ls # List
   matcha   another-directory    some-file.txt
   ```

   > TIP: Dependiendo de la configuración de tu terminal, puede que te muestre
   > las carpetas con un formato diferente al de los archivos, en caso contrario,
   > lo puedes diferenciar debido a que la mayoría de archivos contienen un
   > punto (`.`) seguido de la extensión (nombre particular, ejemplo: txt, doc,
   > xls, etc) mientras que los directorios no.

6. Una vez comprobado que tu directorio se creó correctamente, accede a él
   (recuerda el comando `cd` para cambiar de ubicación y `pwd` para verificar).
   Una vez dentro, el comando para crear archivos es `touch` seguido del nombre
   del archivo que deseas usar. Para este caso, crearemos solo uno llamado
   `index.html` (en este caso _.html_ es la extensión que usaremos).

   ```bash
   $ cd matcha # Change directory a "matcha"
   $ pwd # Present Working Directory
   /Users/bedu/Documents/matcha
   $ touch index.html # Crea archivo "index.html"
   $ ls # Lista contenido
   index.html
   ```

¡Genial! Acabas de crear la estructura mínima de tu proyecto usando la terminal
de tu computadora, ahora tienes el poder sobre ella y poco a poco te irás
olvidando de tu _mouse_ o _touchpad_. Lo que acabas de crear debe tener una
estructura similar a:

```text
Documents/
└── matcha/
    └── index.html
```

### Estructura tu página web

#### Concepto: HTML

Para definir el contenido de nuestra página web, es necesario hacer uso de `HTML`
(HyperText Markup Language). Este lenguaje de marcado nos permite expresar al
navegador web (programa que usamos para navegar en internet, ejemplo: Internet
Explorer, Google Chrome, Mozilla Firefox, Safari, etc) lo que queremos que se
muestre a través de una sintaxis basada en _etiquetas_.

La estructura de una etiqueta es como sigue:

```html
<!-- Esta línea es un comentario de HTML -->

<!-- Ejemplo de la sintaxis para agregar una imagen a nuestra página -->
<img src="https://bedu.org/logo.png" alt="Logo de Bedu" />

<!-- Ejemplo de la sintaxis para agregar un párrafo a nuestra página -->
<p class="paragraph">Este es un párrafo</p>
```

En el código anterior podemos ver la sintaxis de una imagen y un párrafo en HTML.
Si los analizamos podemos ver lo siguiente:

- Las etiquetas empiezan con `<` seguido del nombre de la etiqueta (`img`, `p`).
- Separados por espacios encontramos atributos. Estos siguen la sintaxis
  `nombre-atributo="valor-atributo"`.
- Los atributos pueden variar dependiendo del tipo de etiqueta (las imágenes
  usan `src` y `alt` pero los párrafos no).
- Para denotar el fin de la etiqueta `img`, usamos `/>`.
- Mientras que para etiquetas como la de párrafo (`p`), la etiqueta de apertura
  termina con `>`, seguido del contenido de lo que representa la etiqueta, y por
  último la etiqueta de cierre con la sintaxis (`</nombre-etiqueta>`).

> TIP: Al inicio puede verse complicado identificar que etiquetas se cierran
> automáticamente (como `<img />`) y cuáles necesitan cerrarse manualmente como
> la etiqueta `<p></p>`. La clave para comprender esto es que existen etiquetas
> que pueden tener contenido dentro de ellas (como texto o incluso más etiquetas)
> mientras que otras etiquetas no pueden contener nada dentro de ellas (como
> las imágenes).

Por último pero no menos importantes, los comentarios son bloques de texto que
no se muestran en la página web pero que sirve de información importante para
lxs programadorxs que leen/escriben el código. La sintaxis es `<!--`, seguido
del texto que queremos comentar y cerrando el comentario con `-->`. Tener en
cuenta que un comentario no se cierra hasta no encontrar la etiqueta de cierre.

Esto no mostraría nada en la web:

```html
<!-- Este es un comentario mal cerrado y que no permitirá mostrar el párrafo

<p>
Este párrafo está bien escrito pero no se mostrará por el comentario mal cerrado
</p>
```

#### Guía: Creando nuestro HTML

Es momento de abrir nuestro editor de texto (ejemplo: Visual Studio Code) y
abrir el directorio que creamos en dicho editor, selecciona tu archivo
`index.html` y prepárate para ensuciarte las manos.

Las etiquetas mínimas a incluir en todos los documentos de HTML que creemos son:

```html
<!DOCTYPE html>
<html>
  <head>
    <!-- Aquí va información importante pero no visible dentro del navegador -->
    <title>Matcha</title>
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

#### Guía: Agregando el home de Matcha

Siguiendo el diseño del sitio original de [`Matcha`](https://getmatcha.com),
podemos ver que lo primero que nos muestra son textos de diferentes tamaños y
colores además de un formulario y una imagen.

Para agregar el texto principal podríamos usar un párrafo (etiqueta `<p></p>`),
sin embargo, este texto quiere reflejar lo que nos permite realizar el servicio
de `Matcha` y por ende dar un mayor énfasis y diferenciarlo de los demás textos.

Para lograr este efecto _semántico_ en nuestro sitio web, podemos usar los
_headings_ (encabezados). Estos nos ayudan a dar un énfasis jerárquico de
acuerdo al número que nosotros utilicemos, siendo posible usar del 1 al 6,
con 1 como el de mayor peso jerárquico y 6 lo contrario.

En este caso, queremos el texto inicial es el de mayor peso jerárquico por lo
que usaremos el heading de peso 1, y esto lo indicamos haciendo uso de la
etiqueta `<h1></h1>`.

Aplicándolo a nuestro código existente:

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
  </body>
</html>
```

Abre este archivo en tu navegador y mira el resultado. ¡Tu primera página web!
Claro, solo es un texto, pero es un gran primer paso!

##### Challenge: Segundo texto

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

#### Challenge: Texto promocional

¿Cómo harías para agregar el texto promocional? ¿Te has dado cuenta que dentro
del mismo texto hay algunas palabras que tienen un mayor énfasis (formato en
_negrita_)? ¿Cómo harías para cambiar el formato de solo esas palabras?

Probablemente ya habrás pensado que existe una etiqueta para eso, no te
intimides y pregúntale a San Google (se volverá en uno de tus mejores amigos).

#### Guía: Agregando un formulario

Los formularios en HTML hacen uso de etiquetas particulares para denotar el tipo
de _control_ (caja de texto, botones, etc) que se va a usar en el formulario.

La mayoría de cajas de texto se definen con la etiqueta `<input />` y su
comportamiento por defecto depende del uso del valor de un atributo, llamado
`type`. Esta etiqueta no lleva contenido dentro de la misma, por lo que la
manera de cerrar la etiqueta es automática usando `/>` en vez de `</input>`.

El `input` más común usado en los formularios es:

```html
<input type="text" />
```

Usando este tipo de _input_, la web mostrará una caja de texto que permitirá
ingresar cualquier tipo de texto (números, letras, caracteres especiales, etc),
mientras que usando otros tipos podemos agregar algunas validaciones por defecto
que tenga el navegador. En este formulario, tenemos necesitamos obtener un
correo electrónico del usuario. Para este caso, usaremos el tipo `email`.

```html
<input type="email" />
```

Para terminar el formulario necesitamos agregar un botón, y eso lo logramos a
través de la etiqueta `<button></button>`. Debido a que el texto del botón se
pone entre las etiquetas, el cerrado de la etiqueta no es automático. Además del
texto es importante indicar el tipo de acción que realizará cuando se le de
click al botón. En este caso queremos que el formulario envíe el correo que el
usuario ingresa y por ende el tipo es a usar es `submit`.

Un detalle importante es que los controles de formulario deben estar contenidos
por una etiqueta `<form></form>`. Nuestro HTML del formulario quedaría así:

```html
<form>
  <input type="email" />
  <button type="submit">
    Try it now &rarr;
  </button>
</form>
```

Este formulario por si solo no hará ninguna acción, por el momento solo
dejaremos que esté visible, la funcionalidad la dejaremos para después.

#### Challenge: Agregando la imagen

Es tu turno de agregar la última parte de la estructura que tenemos pensado para
esta sesión, la imagen. La cual puedes obtenerla desde este [link](https://getmatcha.com/wp-content/themes/getmatcha/img/capterra.png).

No dudes en googlear, preguntar al experto y tus compañeros y probar todo lo
que te imagines. Recuerda que tu máquina no se malogrará si pones una etiqueta
que no existe o que está mal escrita.

#### Concepto: CSS

CSS (Cascading Style Sheets) es un lenguaje de estilos que nos permite
personalizar la apariencia de los elementos que hemos agregado en nuestro HTML.

Los estilos se aplican a través de _selectores_, que es una sintaxis particular
para saber qué elemento queremos personalizar su apariencia. La sintaxis se ve
así:

```css
selector {
  nombre-propiedad: valor-propiedad;
}
```

Para agregar el CSS tenemos que crear un archivo, para eso nos vamos a la
terminal y creamos un archivo `styles.css`.

```bash
$ pwd
/Users/bedu/Documents/matcha
$ touch styles.css
$ ls
index.html    styles.css
```

Al agregarlo, nuestro editor lo mostrará en el explorador de archivos,
selecciona el archivo para comenzar agregar los estilos.

#### Guía: Agregando color al texto principal

La primera propiedad que veremos será la de `color` y la usaremos para cambiar
el color de los textos que hemos agregado.

Los valores de los colores pueden ser expresados de diversas maneras, en este
caso usaremos el formato hexadecimal. El texto de la página original usa el
color `#025157`. Y este color debemos aplicarlo al elemento `h1`, por lo que
nuestro CSS se vería así:

```css
h1 {
  color: #025157;
}
```

Recarga tu navegador para que puedas ver los cambios reflejados. ¡Ahora ya tienes
tu texto con color!

#### Challenge: Cambia los colores

Los colores que van a aplicar son los siguientes:

- Texto que va debajo del título: `#46484c`
- Texto promocional: `#8b8b8bcc`
- Texto del botón: `#fff`

#### Challenge: Cambia el color de fondo

Ahora te toca buscar, ¿qué propiedad usarías para cambiar el color de fondo?
¿Qué selector usarías para cambiar el color de fondo de toda la página?

Los colores a usar son:

- Color de fondo de la página: `#fffbf7`
- Color de fondo del botón: `#025157`

Ya está lista tu página para poder subirla a internet, para esto primero debes
tenerla pública en algún lugar. Eso lo veremos a continuación.

#### Concepto: Git y Github

Git es un sistema de control de versiones, esto quiere decir que te permite
mantener un historial de cambios y que puedas ver los cambios realizados en
cualquier momento.

Imagina un documento de Word en el que estás escribiendo un proyecto personal,
agregas cierto contenido, luego pides que te lo revisen y te dicen que reviertas
el cambio, ¿cómo lo harías?. Una forma podría ser, crear varios documentos, cada
uno con una versión diferente:

- Proyecto_v1.docx
- Proyecto_v2.docx
- Proyecto_final.docx
- Proyecto_final_ahora_si.docx
- Proyecto_por_favor_termina.docx

Obviamente, esto no es óptimo y menos cuando hacemos desarrollo web porque
siempre suceden cambios y a veces es bueno revisar el avance.

`Git` es la solución en el desarrollo de software ante este problema. Para esto,
primero debemos de decirle a Git que comience a ver los cambios de nuestro
proyecto:

```bash
$ pwd
/Users/bedu/Documents/matcha
$ git init # Inicia el repositorio que Git seguirá
Initialized git repository.
```

Con esto ya le hemos dicho a Git que comience a seguir los cambios, hay un
comando que nos permite saber qué cambios hemos realizado:

```bash
$ git status # Cambios que hemos realizado
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        created:   index.html
        created:   styles.css

no changes added to commit (use "git add" and/or "git commit -a")
```

Para que estos cambios sean guardados, debemos agregarlos a un registro llamado
`staging directory`, esto lo logramos aplicando el comando `git add` seguido del
nombre de archivo que queremos agregar.

```bash
$ git add index.html
$ git add styles.css
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        created:   index.html
        created:   styles.css
```

> TIP: Si tienes muchos archivos y no deseas agregar uno por uno, puedes hacerlo
> usando `git add -A` y si te encuentras en la carpeta principal del proyecto,
> también puedes usar `git add .`.

Por último hay que crear la versión del proyecto con una descripción que nuestro
yo del futuro nos permita recordarlo fácilmente. Eso lo logramos con el comando
`git commit`.

```bash
$ git commit -m "Agrega estructura inicial del proyecto"
```

Con esto ya tenemos listo una versión, pero no es suficiente, qué pasa si
quieres seguir avanzando este proyecto en otro computador. Probablemente tendrías
que almacenar tu proyecto en un USB y copiarlo cada vez que lo quieras usar.
Esto no es óptimo para nada, por lo cual vamos a enlazar nuestro proyecto con
una plataforma en la nube llamada Github.

Para esto, crearemos un repositorio en Github, el cual nos permitirá almacenar
nuestras versiones en internet y a la vez tener un lugar accesible desde
cualquier computador en cualquier momento.

Una vez creado el repositorio, Github nos proveerá una URL para enlazar nuestro
proyecto. Se verá algo como: `https://github.com/<nombre-usuario>/<nombre-proyecto>.git`.

```bash
$ git remote add origin https://github.com/<nombre-usuario>/<nombre-proyecto>.git
```

Con esto, hemos enlazado el proyecto a un repositorio de Github y le hemos puesto
un alias llamado `origin`.

Para subir los cambios a Github, debemos de subirlo a través del alias que estamos
usando:

```bash
$ git push origin master
```

En este comando (`git push`) le hemos dicho a dónde con el alias `origin` y le
hemos dicho en qué rama, `master`, y que este concepto por el momento no lo
definiremos pero será muy importante comprenderlo.

Si ingresas al link del repositorio, podrás ver que están tus archivos `index.html`
y `styles.css`. Más adelante veremos como recuperar dichos cambios.

#### Challenge: Sube una nueva versión a Github

Agrega cambios de CSS a tu proyecto, puede ser el color o cualquier otra propiedad
que te llamó la intención probar. Luego sigue los comandos de Git que acabas de
ver para subir un nuevo cambio.

### Sube tu página web a internet

El proceso de publicar tu página web en internet es conocido en el lenguaje
coloquial de programadorxs como `deploy` y es lo que vamos a hacer ahora.

Para hacer `deploy` de un sitio web hay muchas formas y dependen en ocasiones
de diversos factores como el servicio de hosting que tengas pensado usar, el
lenguaje de programación que usas para procesar las peticiones, entre otros.

En nuestro caso, la web está basada únicamente en HTML y CSS, y en este módulo
solo le agregaremos algunos recursos estáticos (imágenes, fuentes) y tal vez
algo muy mínimo de JavaScript. A este tipo de sitios se les conoce como web
estáticas, y cualquier servicio de hosting soporta archivos estáticos.

> TIP: Hosting es el servicio de hospedaje que se mantiene activo para que
> cualquier usuario tenga acceso a nuestra web a través de internet. Imagina que
> es una computadora que no es controlada por ti, pero que se mantiene encendida
> y conecta a internet todo el tiempo, de tal manera que cuando alguien consulte
> tu sitio, esta computadora se encargue de indicar el HTML, CSS y demás recursos
> que se deben mostrar.

El servicio que usaremos para _deployar_ nuestro sitio será [Netlify](https://www.netlify.com/).
Una herramienta moderna, fácil de usar y gratuita que nos ayudará a hospedar
nuestro proyecto en internet.

#### Guía: Subiendo el proyecto a Netlify

Lo primero que debemos hacer, es registrarnos en el sitio de [Netlify](https://www.netlify.com/).
Te recomendamos que utilices tu cuenta de GitHub como registro ya que en caso de
utilizar otro método, más adelante será necesario que se vincule de todas maneras.

Una vez dentro de la plataforma de Netlify con la sesión inciada, nos aparecerá
una sección llamada `Sites` mostrando una barra de búsqueda y un botón con el
texto `New site from Git`. Daremos clic a dicho botón:

![Paso 1 - Crear un sitio desde Git](./assets/step-1.png)

Esta nos llevará a otra pantalla en la cual tendremos que seleccionar el
proveedor de proyectos basado en Git donde se encuentra nuestro repositorio.
En nuestro caso, seleccionaremos GitHub el cual estamos usando:

![Paso 2 - Seleccionar Github](./assets/step-2.png)

Una vez autorizado el acceso a nuestros repos de GitHub, nos mostrará la lista
de repositorios que tenemos en nuestra cuenta, seleccionar el del proyecto que
hemos trabajado durante la sesión de hoy. Luego nos mostrará una pantalla como
esta:

![Paso 3 - Configuración de deploy](./assets/step-3.png)

En este paso, no es necesario realizar ningún cambio ya que nuestro sitio
respeta las convenciones usadas por defecto y no usa ninguna herramienta de
optimización como veremos en futuras sesiones. Procedemos a dar clic en el botón
`Deploy site` y nos mostrará:

![Paso 4 - Sitio desplegado](./assets/step-4.png)

Aquí podrás ver que se ha generado una URL aleatoria, en la cual si le das clic,
podrás ver el resultado final:

![Paso 5 - Resultado final](./assets/step-5.png)

Con esto, ya tienes tu sitio publicado en internet y un link que cualquiera
puede ver. Así que, ¡comparte con tus amigxs y familiares lo que has logrado en
tu primera sesión!

> TIP: El nombre aleatorio que Netlify genera en el link es algo complejo de
> memorizar y no se ve muy amigable como para compartirlo en redes sociales,
> no te preocupes, este se puede configurar en la pantalla donde te avisó que
> tu sitio estaba listo, atrévete a experimentar y cambia el nombre del dominio
> para que se vea más cool y sea más fácil de recordar con quienes lo compartas.


