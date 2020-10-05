# Sesión: Agregando la barra de navegación

Sigue el contenido a continuación durante clase para que no te pierdas ningún
detalle de lo que estás a punto de aprender.

## Objetivos

En esta sesión aprenderás:

- Agregar etiquetas semánticas de HTML que den una mejor estructura a lo que
  estamos creando.
- Aplicar conceptos de modelo de caja y display en CSS para agregar la
  apariencia de nuestra barra de navegación.
- Agregar nuestros cambios de códigos al historial de cambios en Git y subirlos
  a GitHub.
- Desplegar los cambios a nuestra página web hosteada en Netlify.

## Contenido

### Agregando la estructura de nuestra barra de navegación

En nuestro proyecto basado en la web de Matcha, habíamos visto como agregar el
contenido princial, durante esta sesión iremos agregando la barra de navegación
y aprendiendo nuevos conceptos en el camino, adicionalmente haremos algunas
modificaciones a lo que teníamos anteriormente para que vaya quedando cada vez
mejor nuestro sitio web.

#### Concepto: Etiquetas semánticas en HTML

En la sesión anterior, conocimos algunas etiquetas como `h1`, `p` e `img`, sin
embargo, en una web completa encontramos que necesitamos seccionar partes de
nuestra interfaz para aplicar ciertos estilos o simplemente diferenciar
componentes. La etiqueta más usada para este tipo de agrupaciones es `div` y por
mucho tiempo era la única opción, al punto que terminó generando una _enfermedad_
llamada **divitis** (uso excesivo de divs):

![Divits](./assets/divitis.png)

Este problema se volvió común y causaba molestias en la legibilidad del código,
además de problemas en dónde cerrar y abrir nuevas etiquetas `div`. Debido a
esto, HTML 5 introdujo nuevas etiquetas que imitarían el comportamiento de un
div, ser un contenedor de otras etiquetas, pero adicionalmente tendría nombres
que darían un significado semántico con solo leerlo. Algunas de esas etiquetas
son:

- `header`
- `nav`
- `main`
- `section`
- `article`
- `aside`
- `footer`

Con estas etiquetas, nuestra web podría tener una estructura semántica como:

![HTML 5 - Estructura semántica](./assets/html5-semantic-tags.png)

En [esta lista de MDN](https://developer.mozilla.org/es/docs/HTML/HTML5/HTML5_lista_elementos#Secciones)
puedes revisar para que se utilizan cada una de estas etiquetas semánticas.

#### Challenge: Etiquetas semánticas para barra de navegación

Viendo la barra de navegación del sitio original de [Matcha](https://getmatcha.com),
¿qué etiquetas semánticas consideras que serían buenas usar?

Tomando en cuenta el contenido actual de nuestra web, ¿consideras bueno que se
ponga dentro de un contenedor? Si tu respuesta es positiva, ¿qué contenedor
semántico usarías?

#### Guía: HTML de la barra de navegación

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

#### Challenge: Agregando el contenido de la barra de navegación

Teniendo en cuenta lo siguiente:

- El link de la imagen del logo es: `https://getmatcha.com/wp-content/themes/getmatcha/img/footer_logo.svg`
- El menú de navegación se puede lograr con una lista desordenada que en HTML se
  representa a través de la etiqueta [`<ul></ul>`](https://developer.mozilla.org/es/docs/Web/HTML/Elemento/ul).
- La acción `Sign In` es un link que apunta a la dirección `/login` y la acción
  de `Start free trial` es un botón.

¿Cómo agregarías el contenido de la barra de navegación?

> Ten en cuenta que no se verá igual que la página, y eso está bien, ya que nos
> estamos enfocando solo en la estructura y luego le daremos los estilos
> necesarios para darle la apariencia esperada.

#### Posible solución: Agregando el contenido de la barra de navegación

```html
<header>
  <!-- Logo con link a la página principal -->
  <a href="/">
    <img src="https://getmatcha.com/wp-content/themes/getmatcha/img/footer_logo.svg" alt="Matcha"/>
  </a>
  <!-- Menú de navegación -->
  <nav>
    <ul>
      <li>Platform</li>
      <li>Pricing</li>
      <li>Customers</li>
      <li>Resources</li>
      <li>About</li>
    </ul>
  </nav>
  <!-- Contenedor de acciones de usuario -->
  <div>
    <a>Sign In</a>
    <button>Start free trial</button>
  </div>
</header>
```

### Personalizando la apariencia de la barra de navegación

Ya tenemos la estructura de nuestra barra de navegación, pero no se ve como la
original, así que ahora veremos como personalizar su apariencia para obtener el
estilo deseado.

#### Concepto: Estilos por defecto y modelo de caja

¿Te has percatado que la estructura que tenemos actualmente en la web tiene una
ligera separación entre el borde del navegador y el contenido?

Esto es debido a que ciertas propiedades tienen valores por defecto dependiendo
del navegador que estés usando. Esto a veces no es bueno, ya que si no sabemos
cuáles son dichos valores podemos encontrar resultados inesperados.

Para solucionar este tipo de problemas se crearon muchas herramientas como
[Reset CSS](https://meyerweb.com/eric/tools/css/reset/), [Normalize.css](https://necolas.github.io/normalize.css/)
entre otras. En nuestro caso, no necesitamos agregar todo ese CSS que alguien
más hizo, es suficiente con establecer valores que conozcamos nosotros por
defecto a algunas propiedades y trabajar a partir de ellas.

Las propiedades que normalmente se ven afectadas son las que están relacionadas
al modelo de caja, como márgenes (`margin`), rellenos (`padding`) y tamaño de
caja (`box-sizing`). El modelo de caja hace referencia a que cada elemento de
HTML que vemos en la página web al final es una caja rectangular, así le pongamos
a un botón bordes redondeados, internamente sigue siendo un rectángulo, los
textos, imágenes y absolutamente todas las etiquetas se representan internamente
como una caja rectangular. Por lo mismo, dependiendo del valor de algunas
propiedades como las mencionadas anteriormente, el tamaño de la caja (alto y
ancho) pueden verse afectadas.

![Modelo de caja](./assets/box-model.png)

En el ejemplo que estamos viendo de la separación entre el borde del navegador
y nuestro contenido actual es porque el navegador ha asignado un margen de 8px
(en el caso de Chrome) a la etiqueta `body`.

Si deseáramos quitar dicha separación, lo podemos lograr agregando el estilo:

```css
body {
  margin: 0;
}
```

> TIP: Si bien todos los valores que son una medida deben estar seguidas de una
> unidad (por ejemplo `px`), en el caso de que el valor sea 0, no es necesario,
> ya que no importa si es `0px`, `0em` o `0%`, al ser 0, quiere decir que en
> cualquier medida seguirá siendo un valor de 0.

Para no encontrarnos con más sorpresas como la del margen por defecto que pone
Chrome, vamos a resetar los valores de margen, relleno y tamaño de caja a un
valor por defecto a todos los elementos:

```css
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
```

> TIP: El selector `*` se usa para seleccionar todos los elementos de HTML.

> TIP: La propiedad `box-sizing` permite indicar qué propiedades intervienen para
> calcular el tamaño de la caja. En este caso, usamos `border-box` que es uno de
> los más utilizados, y lo que indica es que si nosotros ponemos un `width: 100px`,
> pero ponemos un padding de `10px` y un borde de `5px` a cada lado, nuestra
> caja mantendrá el ancho de `100px` pero el contenido se reducirá a `70px` de
> ancho, restando cada uno de los paddings y borders de cada lado.

#### Guía: Agregando separación entre barra de navegación y contenido

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

#### Challenge: Aplica el margen utilizando el atajo de la propiedad `margin`

¿Sabías que la propiedad `margin` puede asignar el valor de los 4 lados en una
sola línea? Si es la primera vez que escuchas esto, no dudes en _googleaerlo_ y
experimentar cambiando las 3 propiedades que hemos escrito previamente por una
sola. Luego imagina, pregunta e investiga que otras propiedades tienen el mismo
atajo.

#### Challenge: Aplica el margen al contenido

El contenido que agregamos en la sesión anterior también tiene una separación de
la barra de navegación. Esto podríamos solucionarlo agregando un margen a la
primera etiqueta de nuestro contenido (que sería el `h1`), sin embargo, esto no
sería óptimo porque si en algún momento insertáramos algo antes del `h1` nuestro
margen no funcionaría como deseamos. Para evitar esto, podemos usar un contenedor
que englobe a todo nuestro contenido y aplicar el margen a dicho contenedor.

#### Guía: Cambiando el modelo de caja del menú de navegación

En este punto ya tenemos las separaciones deseadas entre los bloques más grandes
de contenido, sin embargo nuestro menú de navegación aun no tiene la apariencia
del sitio original, ya que se muestran de forma vertical (uno debajo del otro),
mientras que el diseño original lo muestra horizontalmente.

#### Concepto: Display `block` vs `inline`

¿Por qué se muestra por defecto uno debajo de otro? Esto es debido a los estilos
que las etiquetas tienen asignadas por defecto, y este comportamiento está
relacionado a la propiedad `display`. El navegador asigna a las etiquetas de HTML
la propiedad `display` con valores `block` o `inline`. Los elementos con
`display: block;` usan todo el ancho disponible de su contenedor, es decir, si
nosotros creamos 4 etiquetas `<p></p>`, una seguida de la otra, vamos a ver que
cada texto que pongamos se mostrará uno debajo de otro porque por defecto su
ancho será del 100%. Mientras que los elementos con `display: inline;` usan solo
el espacio necesario para mostrar su contenido.

Algunos ejemplos de elementos con display `block` son: `div`, `p`, `ul`, `h1`,
`header`, `section`, `aside`, `nav`, y muchos más.

Y algunos ejemplos de elementos con display `inline` son: `img`, `a`, `span`,
`strong`, entre otros.

Teniendo en cuenta esta información, nuestro menú de navegación está basado de
las etiquetas `ul` y `li` que tienen display `block` y `list-item` (se comporta
como display `block` si no hay un valor especificado, puedes leer más al respecto
[aquí](https://developer.mozilla.org/en-US/docs/Web/CSS/display-listitem))
respectivamente.

Una solución podría ser reemplazar el display de los `li` a `inline`.

```css
li {
  display: inline;
}
```

Si aplicamos este estilo, nuestro menú se verá ahora de manera horizontal, pero
se seguirían viendo 3 filas: una para el logo, otra para el menú y la última
para las acciones de usuario.

Para evitar las 3 filas, tendríamos que poner a cada elemento contenedor (`a`,
`nav` y `div`) el display `inline`, sin embargo, al cambiar a este valor de
`display` nos encontramos que perdemos ciertas propiedades como `margin-top`,
`margin-bottom`, `height`, es decir, por más que le pongamos un valor, este no
se ve reflejado, y este es el comportamiento correcto que se define para los
elemento scon `display: inline;`. Ante esto, podemos usar otro valor llamado
`inline-block` que mezcla lo mejor de `block` e `inline`, permitiendo cambiar
el layout a un comporamiento como el `inline` pero permitiendo cambiar los
márgenes verticales y la altura como cualquier elemento con display `block`.

Pongamos a prueba este nuevo display, asignándolo a todos los hijos directos de
la etiqueta header:

```css
.header > * {
  display: inline-block;
}
```

¡Muy bien! Con esto conseguimos que estén alineados. ¿Qué tal si le damos un poco
de espacio a cada parte de la barra de navegación? Si tomamos el contenedor (la
etiqueta `header` para la barra de navegación) como un todo equivalente al 100%
y a cada uno de sus hijos les damos un porcentaje de ancho. Podríamos decir que
el logo va a usar un 15% del tamaño de su contenedor, el menú de navegación un
70% y las acciones de usuario el 15% restante. Para aplicar estos estilos podemos
ponerle atributos de clase para que sean más fáciles de identificar:

```html
<header class="header">
  <!-- Logo con link a la página principal -->
  <a href="/" class="logo"></a>
  <!-- Menú de navegación -->
  <nav class="navbar"></nav>
  <!-- Contenedor de acciones de usuario -->
  <div class="actions"></div>
</header>
```


```css
.logo {
  width: 15%;
}

.navbar {
  width: 70%;
}

.actions {
  width: 15%;
}
```

¿Viste lo que pasó? Las acciones de usuario se fueron debajo de los demás
elementos de la barra de navegación. ¿Por qué te imaginas que esto pasó? ¿Serán
nuestras matemáticas (15 + 75 + 15 = 100) :thinking:?

Tranquilxs, esto se debe a que cuando le dijimos que le ponga el `display: inline-block`
a cada uno de los hijos del `header`, los espacios entre cada etiqueta tomaron
un tamaño también, sí, leíste bien, los espacios, aquellas teclas ENTER que
presionamos para que nuestro código se vea más bonito, puedes hacer la prueba
quitando las separaciones:

```html
<header class="header">
  <!-- Logo con link a la página principal -->
  <a href="/" class="logo"></a><!-- Menú de navegación --><nav class="navbar"></nav><!-- Contenedor de acciones de usuario --><div class="actions"></div>
</header>
```

Resulta que al darle un display `inline-block` a los espacios de nuestro código
le damos la posibilidad de tener un tamaño porque al final representan un texto
vacío, el tamaño variará dependiendo del tamaño de fuente que tenga su contenedor.
Si bien, quitando los espacios entre cada etiqueta soluciona el problema, no es
una solución escalable, puesto que si agregamos algo más dentro de la etiqueta
`header` tendríamos el mismo problema y terminaríamos con una sola línea de
código muy larga. [Otras soluciones](https://css-tricks.com/fighting-the-space-between-inline-block-elements/)
implican agregarle son utilizar comentarios entre los saltos de línea, poner un
margin negativo a cada elemento, quitar la etiqueta de cierre y demás.

En nuestro caso usaremos el _hack_ del `font-size`, resulta que si lo que le da
tamaño a los espacios en blanco es el tamaño de la fuente, podemos darle un
tamaño de fuente 0 al contenedor y luego asignar el tamaño de fuente correcto
en cada elemento hijo. Hagamos una prueba, teniendo en cuenta que el tamaño de
la fuente será de 16px para el menú de navegación:

```css
.header {
  margin-top: 40px;
  margin-left: 20px;
  margin-right: 20px;
  font-size: 0;
}

.header > * {
  display: inline-block;
  font-size: 16px;
}
```

¡Eso es magia! En realidad no, es sufrir con CSS :sweat:.

#### Challenge: Alineación de texto en la barra de navegación

Nuestra barra de navegación va tomando forma, pero, ¿qué tal si vamos alineando
el texto?, considerando que el menú de navegación debería tener el texto centrado
mientras que las acciones deberían estar alineado a la derecha. ¿Qué propiedad
vas a usar para alinear el texto? ¿A qué elementos aplicarás el alineado?

#### Posible solución: Alineación de texto en la barra de navegación

```css
.navbar {
  width: 70%;
  text-align: center;
}

.actions {
  width: 15%;
  text-align: right;
}
```

#### Challenge: Agregando estilos restantes

A continuación completa los siguientes requerimientos:

1. Todos los textos dentro de la barra de navegación deben usar la fuente
   `sans-serif` y el alto de la barra debe ser de `45px`.
2. El texto del menú de navegación debe tener una separación a los costados de
   `25px`, además debe ser del color `#025157`.
3. El tamaño de fuente para las acciones debe ser de `14px` y cada una de las
   acciones debe tener una separación hacia los lados de `10px`. El color del
   texto `Sign In` debe ser `#67b54b` y el botón de `Start free trial` debe tener
   color de texto blanco, color de fondo `#67b54b`, un  relleno de `14px` hacia
   los costados y `12px` en la parte inferior y superior. Por último el botón
   no debe tener borde, pero un radio de borde de `5px` para tener esquinas
   redondeadas.

#### Posible solución

```css
.header {
  margin-top: 40px;
  margin-left: 20px;
  margin-right: 20px;
  font-size: 0;
  height: 45px;
  font-family: sans-serif;
}

.navbar {
  width: 70%;
  text-align: center;
  color: #025157;
}

.menu-item {
  display: inline;
  margin-right: 25px;
  margin-left: 25px;
}

.actions {
  width: 15%;
  text-align: right;
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

¡Excelente! Ya estamos muy cerca de terminar. Lo único que nos hace falta es
alinear los elementos de nuestra barra de navegación, esto lo resolveremos
usando un hack debido a que el comportamiento del `inline-block` no nos da una
forma sencilla de resolverlo (más adelante veremos como hacer este tipo de
problemas con otras técnicas que nos evitarán tantos _hacks_).

#### Guía: Alineamiento vertical

Resulta que para alinear al centro verticalmente, debemos hacer uso de la
propiedad `vertical-align: middle`, sin embargo, si aplicamos solo esta propiedad
no nos quedará centrado correctamente, esto debido a que cada elemento tiene un
tamaño diferente. Para solucionar esto, podemos sacar provecho que el contenedor
tiene un tamaño fijo (`.header` con `height:45px;`) y podemos decir que cada hijo
del elemento `header` tenga un height del `100%`. Por último, después de aplicar
ambas propiedades nos daremos con la sorpresa de que no queda verticalmente
centrado ya que a pesar que los elementos tienen el mismo tamaño, no comparten
el mismo espacio que el texto debería ocupar, para esto existe la propiedad
`line-height` que nos permite indicar cuánto es el tamaño de altura que ocupará
cada línea de texto, en este caso debería ser igual al tamaño del contenedor
(45px), quedando así:

```css
.header > * {
  display: inline-block;
  font-size: 16px;
  vertical-align: middle;
  height: 100%;
  line-height: 45px;
}
```

Con esto quedaría centrado nuestro menú de navegación, pero si somos
perfeccionistas, nos daremos cuenta que el logo no está centrado verticalmente,
lo podemos solucionar agrandando su altura al 100% del contendor:

```css
.logo > img {
  height: 100%;
}
```

El último de los detalles sería cambiar el peso de la fuente en los textos del
menú de navegación y los botones ya que aunque no parezcan son distintos en la
web original:

```css
.navbar {
  width: 70%;
  text-align: center;
  color: #025157;
  font-weight: 500;
}

.actions {
  width: 15%;
  text-align: right;
  font-size: 14px;
  font-weight: 600;
}
```

Wohoo!! Finalmente hemos terminado nuestra barra de navegación. ¿Qué te pareció?
Interesante todo lo que tienes que hacer para poder darle la forma que deseas,
¿no?. Como mencionado anteriormente, existen otras técnicas que hacen esto de
una manera mucho más sencilla pero la discutiremos en su momento. No olvides
subir tus cambios a Github y revisar que se vean los cambios reflejados en tu
página alojada en Netlify.

#### Final Challenge: Agrega los estilos correctos al contenido principal

Te habrás dado cuenta que con lo visto hoy, puedes hacer cambios en los estilos
del HTML de la sesión anterior, como por ejemplo:

1. Cambia la fuente de los textos utilizados. Las que utiliza Matcha son privadas,
   pero tu puedes agregar fuentes gratuitas utilizando el repositorio de fuentes:
   [`Google Fonts`](https://fonts.google.com/).
2. Agrega las separaciones que existe entre cada texto que aparece en el
   contenido principal.
3. Cambia los estilos del formulario.

Vamos a hacer un challenge guiado, con una dinámica distinta, vas a aplicar
estos cambios en el repositorio de algunx de tus compañerxs:

1. Escoge un compañerx al que le harás una solicitud de cambio en su código, una
   vez sepas quién será (no importa si alguien más escoge a la misma persona),
   pídele el link de su repositorio de Github (que te lo comparta por slack tal
   vez).
2. Ingresa a su repositorio de Github y dale clic al botón de `Fork` ubicado a
   la misma altura que el nombre de su repositorio. Por ejemplo:

   ![Fork de un repositorio](./assets/fork.png)

   Esto creará una copia del proyecto de tu compañerx en tu cuenta de Github,
   esto permitirá que puedas hacer cambios en su proyecto sin afectar lo que
   viene trabajando.
3. Clona su proyecto para empezar a realizar cambios, para esto, ingresa a tu
   carpeta general de proyectos en la terminal (en este ejemplo diremos que es
   la carpeta _Documents_) y ejecuta el comando de `git clone` seguido del link
   del repositorio que se creó en tu cuenta.

   ```bash
   $ # En el ejemplo de la imagen anterior, el link del proyecto se vería así:
   $ # https://github.com/ivandevp/demo-static-repo-deploy.git
   $ git clone https://github.com/<tu-usuario-github>/<nombre-del-proyecto>.git
   ```

   Una vez clonado, `git` habrá creado una carpeta con el nombre del repositorio
   (`demo-static-repo-deploy` en el caso del ejemplo) y podrás ingresar a ella
   para ver el código con el comando `cd`.

   ```bash
   $ # En el ejemplo sería: `cd demo-static-repo-deploy`
   $ cd <nombre-del-proyecto>
   ```
4. Antes de empezar a hacer tus cambios, vamos a crear una `rama` en la que
   podrás hacer modificaciones sin fastidiar a los demás miembros de tu equipo.
   El concepto de rama lo verás a profundidad en el postwork, de momento imagina
   que si estás en una línea de tiempo, acabas de crear una versión paralela
   donde tu podrás avanzar y hacer cambios sin alterar la línea de tiempo
   original. Sabemos que es complicado de imaginar y un concepto complejo de
   entender a la primera, pero estamos segurxs de que lo entenderás conforme lo
   vayas usando. Mientras, usa este comando en la terminal:

   ```bash
   # Los nombres de las ramas normalmente son en minúscula y si es más de una
   # palabra, va separada por guiones. Ejemplo: `estilos-navegacion`, `formulario`.
   # Normalmente trata de describir en pocas palabras en lo que trabajarás.
   # Para este ejemplo mi rama se llamará `estilos-generales`
   $ git checkout -b <nombre-rama> # git checkout -b estilos-generales
   ```
5. Realiza algún cambio, ayuda a tu compañerx a agregar un estilo o alguna
   etiqueta de HTML que le faltó en la sesión o cambia la fuente o color de algo
   que tu sientas le puede ayudar a que se vea mejor su proyecto, esta elección
   es tuya. Puedes usar los requerimientos del reto final si no tienes idea de
   qué agregar.
6. Una vez que hayas agregado tus cambios, agrégalos a `git`:

   ```bash
   $ git add .
   $ git commit -m "Cambia color de la fuente"
   # A diferencia de antes, el último comando, `git push`, se hace hacia la rama
   # que has creado, esto con la intención de que tus cambios se creen en la
   # línea de tiempo paralela y no la original.
   # En este ejemplo sería: `git push origin estilos-generales`
   $ git push origin <nombre-rama>
   ```
7. Esto habrá subido cambios a Github y te saldrá una alerta en tu copia del
   repositorio similar a la de la siguiente imagen:

   ![Alerta de Pull Request](./assets/pr-alert.png)

   En este ejemplo, la rama se llama `session-2`, en tu caso, aparecerá el nombre
   de rama que elegiste. Dale click al botón `Compare & pull request`.
8. Te llevará a una página como la siguiente:

   ![Pull Request](./assets/pr.png)

   Esto es el formulario de apertura de un Pull Request (solicitud de cambio).
   Normalmente te pondrá un título que será el mismo que usaste como mensaje del
   commit. Además te dejará un espacio para que agregues comentarios y dejes
   saber al autor original del proyecto qué cambios hiciste, te recomendamos que
   le escribas una descripción detallada de los cambios que hiciste, y una vez
   terminado le des clic al botón `Create pull request`.
9. Con esto habrás enviado una solicitud de cambio al repositorio de tu compañerx,
   ahora queda en él/ella que lo acepte o rechace (esperemos que lo acepte). El
   Pull Request se verá algo como:

   ![Pull Request enviado](./assets/pr-sent.png)

   Si tu compañerx decide aceptarlo, hará clic en el botón `Merge pull request`,
   caso contrario, le dará en `Close pull request`, en caso de usar este último
   botón, es aconsejable comentar antes el porqué no lo piensa aceptar.

   Con esto habrás realizado lo que se conoce como una [`contribución`](https://blog.nearsoftjobs.com/tu-primera-contribuci%C3%B3n-a-open-source-un-ganar-ganar-c5c93fbb93eb)
   en el mundo del desarrollo de software open source.

Una vez realizada esta introducción al trabajo colaborativo en Git, busca que
tu proyecto se vea algo así:

![Resultado Final - Sesión 2](./assets/end-result.png)

De esta manera es como se trabaja colaborativamente en el mundo profesional,
sin afectar el avance de tus compañerxs, haciendo solicitudes y discutiendo
el por qué deben de ser o no aprobadas, además de contribuir y aprender del
código de otros. ¡Felicidades! Has progresado mucho (sabemos que hay dudas,
es normal, tienes que ponerte a investigar por tu cuenta y practicar mucho
más, pero vas por muy buen camino).
