# Sesión: Agregando la barra de navegación

Sigue el contenido a continuación durante clase para que no te pierdas ningún
detalle de lo que estás a punto de aprender.

## Objetivos

En esta sesión aprenderás:

- Crear ramas y jalar cambios entre versiones  

- Agregar contenido de video a nuestra web.

- Cambiar el posicionamiento de los elementos HTML.

- Estructurar los elementos dentro de un contenedor de manera flexible.

- Usar comandos de git para obtener cambios realizados por terceros.

- Desplegar los cambios a nuestra página web hosteada en Netlify.

## Contenido

### Recuperando los últimos cambios

En la sesión anterior, vimos como realizar cambios a proyectos que no somos
propietarios, esto lo logramos a través de un flujo de Pull Request en Github.
Debido a que estos cambios son realizados en la computadora de otras personas,
es necesario realizar algunos comandos de git para obtener estas modificaciones
y seguir trabajando sobre ellas en nuestro propio ordenador.

#### Concepto: `git fetch` y `git merge`

Los comandos `git fetch` y `git merge` son los comandos que usamos para obtener
cambios realizados directamente en Github y que no lo tenemos en nuestro entorno
de desarrollo.

`git fetch` es un comando que recupera todos los cambios realizados en el servidor
remoto (ejemplo: Github) y que no las tenemos en nuestra computadora.

`git merge` por otro lado nos permite mezclar cambios de otras ramas hacia nuestra
rama actual de trabajo.

> TIP: ¿Recuerdas el concepto de ramas? Tal vez ahora puedas tener un poco más
> de contexto para entenderlo mejor. Siempre que nosotros trabajamos en un
> repositorio monitoreado por Git, lo hacemos sobre una rama (`master` por
> defecto); sin embargo, cuando queremos realizar cambios sobre el proyecto de
> alguien más es conveniente crear una rama paralela y realizar estos cambios
> sobre ella, ya que si por algún motivo se terminara deshaciendo el cambio o sea
> algo que tome mucho más tiempo de implementar, no afectaría a lo que se tiene
> ya avanzado. Con este flujo, podemos alterar nuestro código sin perjudicar al
> resto y una vez que lo decidamos, hacer un Pull Request si en caso queremos
> enviar una solicitud de cambios a alguien más, o simplemente mezclar los cambios
> a nuestra versión de código principal para agregar lo nuevo que trabajamos.

#### Guía: Obteniendo cambios con `git fetch` y `git merge`

Como siempre que queremos aplicar cambios relacionados con Git, es necesario que
nos movamos en la terminal hacia la carpeta de nuestro proyecto. Una vez dentro,
vamos a realizar los siguientes pasos:

1. Escribiremos `git fetch` para traer los cambios que se realizaron desde otro
   ordenador, ya sea cambios que tu hiciste o que alguien te mandó un Pull Request
   y terminaste aceptando.

   ```bash
   $ git fetch # Este comando arrojará algo similar a las siguientes líneas
   remote: Enumerating objects: 12, done.
   remote: Counting objects: 100% (12/12), done.
   remote: Compressing objects: 100% (7/7), done.
   remote: Total 7 (delta 3), reused 0 (delta 0), pack-reused 0
   Unpacking objects: 100% (7/7), 1.66 KiB | 1.66 MiB/s, done.
   From https://github.com/<nombre-de-usuario>/<nombre-de-repo>
   * [new branch]      <nombre-rama> -> origin/<nombre-rama>
     5626041..5b6fd55  master           -> origin/master
   ```

   Lo que nos dice este comando es que trajo cambios desde Github, cambios en la
   rama original (master en el ejemplo) y cambios en nuevas ramas en caso de
   existir. Adicionalmente, nos indica que la nueva rama ha sido almacenada en
   algo llamado `origin/<nombre-rama>` y los cambios que se hicieron en la rama
   master se encuentran `origin/master`. ¿Logras ver el patrón? Cualquier cambio
   lo encontrarás en una _rama_ llamada `origin/<nombre-de-rama>`.

2. Ahora que ya tenemos nuestros cambios en nuestra computadora, aun estos no se
   verán reflejados en nuestro código, esto debido a que `git fetch` solo se
   encarga de _descargar_ los cambios. Para poder juntar los cambios descargados
   con lo que nosotros tenemos en nuestro proyecto se usa `git merge`, checa el
   ejemplo:

   ```bash
   # En este caso queremos combinar los cambios que se hicieron a la rama master.
   # Si tu quisieras obtener cambios de otra rama, podrías cambiar `master` por
   # la rama que desees.
   $ git merge origin/master
   Updating 5626041..5b6fd55
   Fast-forward
    ruta/al/archivo/modificado.html | 277 ------------------------------------
    1 file changed, 277 deletions(-)
   ```

   En el ejemplo, el _merge_ causó que se obtengan 277 cambios (borrado de
   código para este caso) y se juntaron sin generar ningún conflicto entre los
   cambios que estaban en el proyecto antes de unir los cambios que descargamos.

   Esto variará dependiendo de los cambios que hayas realizado, si agregaste
   código, salrá los archivos que se modifcaron y cuántas líneas se alteraron,
   de igual forma con alguna actualización o eliminación.

   > Tip: En ocasiones, se modificó algo en Github, pero al mismo tiempo tu
   > también hiciste modificaciones en la misma ubicación (archivo) y tocaron
   > líneas de código similares. Cuando esto sucede, git no sabe qué cambios se
   > deberían preservar, si los cambios que hiciste en tu computadora o los que
   > está por juntar, a esto se le llaman `conflictos` y dependiendo de los
   > cambios, puede llegar a ser tedioso de corregir. Si te llegara a pasar,
   > puedes consultar [este enlace](https://help.github.com/es/enterprise/2.19/user/github/collaborating-with-issues-and-pull-requests/resolving-a-merge-conflict-using-the-command-line)
   > de Github no bien traducido al español pero con buena y simple información
   > de cómo solucionarlo, si te trabas, no dudes en consultarlo durante la
   > sesión :wink:.

### Agregando el video

#### Concepto: Elementos media en HTML5

Elementos media hace referencia a archivos multimedia (ejemplo: audio, video) y
afortunadamente al momento que lees esto los navegadores tienen soporte nativo
para este tipo de recursos, pues, si en algún momento escuchaste sobre Flash o
ActionScript, probablemente sabrás que era una tarea compleja obtener un recurso
multimedia en la web, más aun, que sea compatible para la mayoría de navegadores
sin que el usuario tenga que instalar o habilitar algo.

> TIP: Si quieres conocer un poco más acerca de la historia de multimedia en la
> web, MDN nos cuenta un poco en la [documentación acerca de audio y video](https://developer.mozilla.org/es/docs/Learn/HTML/Multimedia_and_embedding/Video_and_audio_content).

Bueno, ahora que sabemos que HTML5 nos provee soporte nativo para audio y video,
¿cómo agregamos el video a nuestra web? HTML5 nos provee 2 etiquetas para trabajar
con audio y video, sorpresivamente dichas etiquetas son: `<audio></audio>` y
`<video></video>`, además a través de JavaScript (aun no veremos de esto) podemos
manipular la reproducción del contenido multimedia y mejorar la experiencia que
el navegador nos ofrece por defecto. Para nuestro proyecto, solo usaremos las
etiquetas pero no te limitamos a que averigües sobre la interacción con JavaScript.

#### Guía: Agregando la etiqueta video de HTML5

¡Manos a la obra! Antes de agregar el video, debemos de saber qué video vamos a
utilizar en nuestra web, si inspeccionamos la web de Matcha, encontraremos que
usa un video que está almacenado en una plataforma externa llamada Wistia, en
este caso, dicha plataforma provee una forma diferente de agregar el video, por
lo cual usaremos nuestro propio video y una manera más estándar de agregarlo.

Los recursos que usaremos serán:

- [Portada](https://cdn.videvo.net/videvo_files/video/premium/video0036/thumbnails/computer_code00_small.jpg),
  cuando el video no haya sido reproducido, mostrará una imagen de portada.
- [Video en formato Webm](https://cdn.videvo.net/videvo_files/video/premium/video0036/small_watermarked/computer_code00_preview.webm),
  este es el video que se reproducirá cuando el navegador soporte la codificación
  de videos con formato `webm`.
- [Video en formato MP4](https://cdn.videvo.net/videvo_files/video/premium/video0036/small_watermarked/computer_code00_preview.mp4),
  este video es el más común y probablemente con mayor soporte, por lo que será
  nuestra opción por defecto en caso el navegador que usamos no soporte
  codificación de otros formatos.

::: tip
El video que estamos usando en el ejemplo fue obtenido de un repositorio de videos
gratis para usar sin fines de uso comercial. Si en caso, deseas usar otro video
diferente al de los ejemplos, eres libre de hacerlo. Solo considera que deberás
contar con la imagen de portada y el video en al menos un formato que funcione
en tu navegador.

La web desde la que fue obtenido el video en mención es [Videvo](https://www.videvo.net/).
:::

::: tip
La página comentada en el tip anterior solo da la opción de descargar el video,
si quieres obtener el link del video que usa esa página, puede ser un buen momento
para que le preguntes al mentor de la sesión _¿cómo usar el devtools del navegador?_.
:::

Una vez con los recursos a usar definidos, empecemos. Como el video junto con
un texto promocional irán alineados de manera distinta al contenido que tenemos
actualmente en nuestra web, vamos a agruparlos en un contenedor. Por lo tanto,
luego del contenedor que actualmente tenemos para la pantalla inicial de nuestra
web, agregaremos:

```html
<body>
  <!-- Contenido previo -->
  <!-- ... -->

  <!-- Contenedor de video -->
  <section>
    <video></video>
  </section>
</body>
```

Para indicarle a la etiqueta `<video></video>` qué video queremos ver, se puede
usar de 2 maneras:

1. A través de un atributo `src` en la etiqueta.
2. Agregando una etiqueta `<source />` dentro de la etiqueda de video.

¿Cuándo usamos qué opción?

Bueno, la primera es usada cuando solo tenemos un formato de video, ya que el
atributo `src` solo se puede definir una vez dentro de la etiqueta. En cambio,
la segunda opción nos permite usar varias etiquetas `<source />` dentro de la
etiqueta video, lo cual nos permite agregr diferente tipos de formato tomando
el orden en que se agregaron como orden parra intentar mostra el video.

Empecemos por agregar el video con el atributo `src`:

```html
<body>
  <!-- Contenido previo -->
  <!-- ... -->

  <!-- Contenedor de video -->
  <section>
    <video
      src="https://cdn.videvo.net/videvo_files/video/premium/video0036/small_watermarked/computer_code00_preview.mp4"
    ></video>
  </section>
</body>
```

Esto nos mostrará el video en el navegador, pero, ¿te diste cuenta que no lo
podemos reproducir?

#### Challenge: Agregando controles de reproducción al video

Resulta que por defecto el navegador no agrega controles de reproducción al video,
¿puedes buscar cómo agregárselo?

::: tip
Lo que buscas es un atributo de la etiqueta `<video></video>`.
:::

<details>
  <summary>Solución</summary>

Agrega el atributo `controls` a la etiqueta `<video></video>`.

```html
<body>
  <!-- Contenido previo -->
  <!-- ... -->

  <!-- Contenedor de video -->
  <section>
    <video
      controls
      src="https://cdn.videvo.net/videvo_files/video/premium/video0036/small_watermarked/computer_code00_preview.mp4"
    ></video>
  </section>
</body>
```

</details>

Bien, una vez visto cómo agregar los controles a nuestro video y poder reproducirlo
en la web, realicemos el cambio para poder agregar múltiples formatos, este cambio
no lo podrás ver reflejado como tal en la web, puesto que seguirás viendo el video,
esto es una táctica de optimización sobre todo, ya que poder tener diversos formatos
adaptados para diversos navegadores y usuarios nos da un mayor rango de probabilidad
de encontrar algún formato que sea más eficiente para cada usuario.

#### Guía: Agregando múltiples formatos de video

A continuación agregaremos los elementos `<source />` dentro de la etiqueta de
`<video></video>`.

```html
<body>
  <!-- Contenido previo -->
  <!-- ... -->

  <!-- Contenedor de video -->
  <section>
    <video controls>
      <source
        type="video/webm"
        src="https://cdn.videvo.net/videvo_files/video/premium/video0036/small_watermarked/computer_code00_preview.webm"
      />
      <source
        type="video/mp4"
        src="https://cdn.videvo.net/videvo_files/video/premium/video0036/small_watermarked/computer_code00_preview.mp4"
      />
    </video>
  </section>
</body>
```

Como te podrás dar cuenta, cada etiqueta `<source />` hace referencia a un formato
distinto, y le indicamos dicho formato a través del atributo `type` para poder
diferenciarlo, y mediante el atributo `src` indicamos donde encontrar el video
en el formato especificado.

#### Challenge: Agregando la portada del video

Bien, nuestro videos ya cuenta con controles de reproducción, además soporta más
de un formato para optimizar la experiencia de nuestros usuarios. Sin embargo,
sería genial poder definir la imagen que queremos que se vea antes de que se
reproduzca el video. ¿Nos ayudas a agregar esta funcionalidad?

::: tip
Esta funcionalidad también se logra a través de un atributo de la etiqueta
`<video></video>`.
:::

<details>
  <summary>Solución</summary>

Agrega el atributo `poster` a la etiqueta `<video></video>`, asignándole el link
de la imagen de portada como valor.

```html
<section>
  <video
    controls
    poster="https://cdn.videvo.net/videvo_files/video/premium/video0036/thumbnails/computer_code00_small.jpg"
  >
    <source
      type="video/webm"
      src="https://cdn.videvo.net/videvo_files/video/premium/video0036/small_watermarked/computer_code00_preview.webm"
    />
    <source
      type="video/mp4"
      src="https://cdn.videvo.net/videvo_files/video/premium/video0036/small_watermarked/computer_code00_preview.mp4"
    />
  </video>
</section>
```

</details>

#### Challenge: Agrega la sección de publicidad

Ya tenemos el video en nuestra página, ahora, si revisamos la web de Matcha, nos
vamos a dar cuenta que tiene un texto publicitario junto con un formulario
similar al que utilizamos en la parte de inicio, el reto consiste en que lo puedas
agregar, aun no es necesario alinearlo, no hay problema que todo se vea debajo,
no intentes usar el `display: inline-block` de la sesión anterior, puesto que
estaremos usando otra manera más adelante.

::: tip
Ya que tienes que agregar un encabezado, seguido de un párrafo y un formulario,
te recomendamos envolver todos estos elementos en un contenedor (idealmente
semántico).
:::

Ten en cuenta lo siguiente:

- Usa la fuente que deseas para el encabezado de la sección
- El color de fuente del encabezado y del texto que precede al formulario es
  `#025157`
- El color de fuente del párrafo es `#343434`
- Dependiendo del selector que usaste, ¿cómo reutilizarías tus estilos del
  formulario de la parte inicial para este nuevo formulario muy similar?

<details>
  <summary>Posible solución</summary>

Agregamos el HTML dentro de un `article` aplicando los estilos necesarios a
través de clases.

```html
<section>
  <video
    controls
    poster="https://cdn.videvo.net/videvo_files/video/premium/video0036/thumbnails/computer_code00_small.jpg"
  >
    <source
      type="video/webm"
      src="https://cdn.videvo.net/videvo_files/video/premium/video0036/small_watermarked/computer_code00_preview.webm"
    />
    <source
      type="video/mp4"
      src="https://cdn.videvo.net/videvo_files/video/premium/video0036/small_watermarked/computer_code00_preview.mp4"
    />
  </video>
  <article class="publish">
    <h3>Publish to your blog in minutes, not hours.</h3>
    <p>
      Your blog is your most powerful asset to build, engage, and retain a
      loyal audience. But you don’t have hours to create content that may or
      may not work. With Matcha, instantly publish from our library of
      10,000+ professionally written articles and build your email list
      faster with our powerful conversion tool.
    </p>
    <form>
      <p>Start publishing today:</p>
      <div>
        <input type="text" placeholder="Enter email" />
        <button>Start My Trial</button>
      </div>
    </form>
  </article>
</section>
```

```css
.publish {
  /* container styles if any */
}

.publish h3 {
  font-family: 'Alegreya', serif;
  font-size: 40px;
  line-height: 48px;
  color: #025157;
}

.publish > p {
  font-size: 16px;
  color: #343434;
  line-height: 1.5;
  margin-bottom: 20px;
}

.publish > form {
  display: flex;
}

.publish > form p {
  color: #025157;
  margin-right: 18px;
}
```

Resultando algo así:

![Contenido publicitario](./assets/publish.png)

</details>

### Alineando video con contenido publicitario

Para alinear el contenido al lado del video, probablemente podríamos usar el
`display: inline-block` que hicimos en la sesión anterior, sin embargo, esto
nos forzaría a realizar algunos _hacks_ para obtener el resultado esperado, es
por ello que ahora vamos a conocer una manera más flexible y simple de lograr
esto, a través de `Flexbox`.

#### Concepto: Flexbox

Flexbox es un método disponible en CSS para alinear y estructurar visualmente
el contenido de un elemento HTML. Flexbox nos permite usar la propiedad de
`display` para indicar cuando un elemento y su contenido, en caso de tener,
puede alinearse de manera flexible.

El elemento que recibe la propiedad `display: flex` se le conoce como **flex container**,
mientras que a los elementos contenidos en el elemento en mención se le conoce
como **flex items**.

Es posible controlar el posicionamiento del contenido desde el _flex container_
aplicando propiedades de alineamiento tanto vertical como horizontal.

Cuando se define un _flex container_, sus elementos hijos (_flex items_) se
modifican a ponerse uno al lado de otro, debido a que por defecto, el contenido
toma una dirección de `row` (horizontal). La dirección se puede modificar a
vertical a través de la propiedad `flex-direction` que se aplica al _flex container_.

A través de las propiedades `justify-content` y `align-items` se puede modificar
el alineamiento de los hijos dependiendo de la dirección que estén siguiendo.
Por ejemplo, si quisieramos que los _flex items_ estén alineados al centro
horizontalmente, esto se podría lograr con `justify-content: center` siempre y
cuando el `flex-direction` sea `row`. Puesto que `justify-content` alinea a los
_flex items_ en el eje principal, mientras que `align-items` lo ahce en el eje
secundario. Por lo tanto, notar en el ejemplo anterior que si el `flex-direction`
fuera `column` (vertical) para alinear horizontalmente, necesitaríamos usar la
propiedad `align-items`.

#### Guía: Alineamiento horizontal con flexbox

Para llevar esto a cabo, revisemos nuestra estructura actual, probablemente se
vea algo así:

```html
<!-- Contenedor -->
<section>
  <!-- Video -->
  <video></video>
  <!-- Contenido de publicidad -->
  <article></article>
</section>
```

> TIP: No interesa si tienes un `div` en vez del `section` o `article`, pero si
> es importante que tengas un contenedor de display `block` por defecto.

Ya que tenemos claro la estructura, debemos de definir quién va a ser el _flex container_
y quiénes los _flex items_. Para nuestro caso, el `section` sería nuestro flex
container ya que es quien va a controlar la alineación del video y el contenido
publicitario. Por ende, aplicaremos una clase y le agregaremos la propiedad de
`display: flex`.

```html
<!-- Contenedor -->
<section class="promo">
  <!-- Video -->
  <video></video>
  <!-- Contenido de publicidad -->
  <article></article>
</section>
```

```css
.promo {
  display: flex;
}
```

Con solo agregar esta propiedad verás que el contenido publicitario se puso al
lado del video. Sin embargo, notaremos 2 cosas principalmente:

- El video y contenido publicitario abarcan todo el ancho del navegador.
- Están muy apegados a la imagen que la precede y al borde inferior del navegador.
- El contenido publicitario no está alineado al centro del alto del video.

Resolvamos cada uno de estos problemas en orden. Empecemos, por limitar el ancho
que abarca esta nueva sección. Esto lo podemos hacer especificando un ancho
menor al del que tiene actualmente (100%) y para no poner una medida exacta que
funcione solo para un tamaño de pantalla, podemos usar la unidad de `%` para
hacerlo relativo. ¿Qué tal si probamos con un 70%?

```css
.promo {
  display: flex;
  width: 70%;
}
```

Esto acortó el texto pero del lado derecho, sin embargo, nosotros queremos que
el contenido se centre, de tal forma que quede el mismo espacio a cada lado.
Esto lo podríamos lograr poniendo un `margin-left` pero calcular la medida nos
podría resultar tal vez un poco inexacta. Un _hack_ común cuando quieres lograr
un centrado horizontal en elementos que son contenedores es usando `margin: auto`.
Esta propiedad lo que hace es calcular un margen automático a cada uno de los
lados dependiendo del espacio que tenga libre. Por lo tanto, como nosotros hemos
indicado que nuestro contenedor tiene un ancho de 70% sobre una pantalla que
equivale al 100%, le quedan 30% para repartir en el margen y como el valor a
aplicar a cada lado es el mismo (_auto_), el navegador reparte la misma
proporción a cada uno de los extremos (15% en nuestro caso).


```css
.promo {
  display: flex;
  width: 70%;
  margin: auto;
}
```

¡Eso es magia! En realidad, es CSS :sweat_smile:.

Bien, ahora agreguemos un poco de separación entre la imagen superior y el borde
inferior del navegador, lo cual podríamos lograrlo usando un `margin-top` y
`margin-bottom`. Espera, pero ya le hemos dicho que el margen sea automático,
¿cómo hacemos? Esto lo podemos lograr indicando que el contenedor tendrá un
margen superior e inferior de 100px por ejemplo y que a los costados mantendrá
un margen automático.

```css
.promo {
  display: flex;
  width: 70%;
  margin: 100px auto;
}
```

Esto ya va tomando forma, es momento de volver a Flexbox y comenzar a alinear
a los _flex items_. Primero, vamos a alinear verticalmente al centro para que
nuestro contenido publicitario no se vea con espacio en blanco en la parte
inferior.

```css
.promo {
  display: flex;
  width: 70%;
  margin: 100px auto;
  align-items: center;
}
```

Bien, de esta manera el contenido publicitario ya queda alineado verticalmente
al centro respecto del video. Sin embargo, ¿parece que falta una separación entre
el video y el contenido, no? No te preocupes, esto lo vamos a solucionar
definiendo el tamaño que van a ocupar cada uno de ellos más adelante.

#### Challenge: Agregando contenedor al video para agregar imagen

¿Te diste cuenta que hay una imagen debajo del video que no hemos agregado ni
considerado? ¿Cómo va a afectar esto lo que llevamos actualmente? Bien, es tu
momento de aplicar Flexbox por tu cuenta, vas a necesitar meter el video dentro
de un contenedor para que luego puedas agregar la imagen debajo y puedas
alinearlos con Flexbox.

La imagen lo puedes encontrar [aquí](https://getmatcha.com/wp-content/themes/getmatcha/img/see_how_it_works.png).

::: tip
Como la imagen irá debajo del video, el contenedor debe de cambiar la dirección
de los elementos a `column`.
:::


<details>
  <summary>Posible Solución</summary>

Envuelve el video en un contenedor, agrega la imagen, asigna `display: flex` al
contenedor y cambia la dirección a `column`. Luego alinea los flex items.

```html
<section class="promo">
  <article class="explanatory-video">
    <video><!-- Fuentes del video --></video>
    <img
      src="https://getmatcha.com/wp-content/themes/getmatcha/img/see_how_it_works.png"
      alt="See how it works"
    />
  </article>
  <!-- Contenido publicitario -->
  <!-- ... -->
</section>
```

```css
.explanatory-video {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.explanatory-video img {
  width: 120px;
  margin-top: 10px;
}
```

Resultando algo como:

![Alineamiento de video](./assets/video-alignment.png)

</details>

¡Genial, ya casi terminamos! Solo nos falta tomar en cuenta el espacio que está
tomando el video y contenido publicitario, este último ocupa mucho más espacio
que el video pero en la página original no aparenta ser tanta la diferencia.
Imaginemos que queremos que ocupen el mismo espacio cada uno, para lograr dicho
efecto, tenemos que indicar a cada uno de los _flex item_ que agarren la misma
proporción de espacio. Esto es posible lograr usando la propiedad `flex` sobre
cada uno de los _flex item_, seguido de su valor que puede ser un valor entero
indicando la proporción, por ejemplo, si le damos `flex: 1` a un _flex item_ y
al otro le damos `flex: 2`, el navegador interpretará que el segundo _flex item_
debe ocupar el doble de espacio que el primero. Como nosotros queremos el mismo
espacio para el video como para el contenido publicitario, quedaría así:

```html
<section class="promo">
  <article class="explanatory-video"></article>
  <article class="publish"></article>
</section>
```

```css
.explanatory-video {
  display: flex;
  flex-direction: column;
  align-items: center;
  flex: 1;
}

.publish {
  flex: 1;
}
```

Como verás, es posible asignar la propiedad `flex` a un elemento que en si mismo
es un contenedor flexible (`display: flex`).

¡Yay! Con esto logramos tener nuestro video y contenido publicitario alineados
usando Flexbox. No creas que hemos visto todas las propiedades que trae Flexbox
consigo, aun nos faltan varias, pero al menos el concepto principal si podemos
decir que lo hemos revisado.

### Volviendo la barra de navegación fija

Ahora que nuestra página tiene un poco más de contenido y ya tenemos que hacer
scrolling para navegar por ella, nuestra barra de navegación se pierde por lo
mismo que vamos decendiendo en el contenido de la página, sin embargo, esta
sección puede ser importante para nuestro usuario en cualquier momento y sería
bueno tenerla siempre accesible para ellos, ¿cómo podríamos hacer que al hacer
scroll la barra de navegación se mantenga?

#### Concepto: `position: fixed`

La solución es la propiedad `position` con el valor de `fixed`. Esto debido a
que esta propiedad `position` permite que el elemento al que se le aplica, salga
del flujo normal de la web. Por ejemplo, nosotros hemos ido escribiendo etiquetas
de HTML que al verse en la web solo se han puesto una debajo de otra (para los
que son `display: block`) o al lado (para los que son `display: inline`), pero
no hemos visto que un elemento se ponga encima de otro o en algún lugar particular
sin afectar a los que los rodean. A este comportamiento es lo que nos referimos
con salir del flujo, al aplicar esta propiedad nos vamos a topar con que el
contenido se pone en un lugar específico sin importarle si está afectando a otros
elementos, adicional a esto, nos habilita otras propiedades para controlar su
posicionamiento como `top`, `left`, `bottom` y `right`.

#### Guía: Aplicando `position:fixed`

Ya que nuestra barra de navegación tiene estilos y está funcionando, vamos a
envolverla en un contenedor en el cual podamos agregar esta propiedad y así no
realizar muchos cambios a lo que tenemos actualmente.

```html
<body>
  <!-- Este es el contenedor que envuelve a la barra de navegación -->
  <section class="fixed-header">
    <header class="header"></header>
  </section>
  <!-- HTML restante -->
  <!-- ... -->
</body>
```

Una vez agregado el contenedor, procedemos a agregar la propiedad `position` con
valor `fixed`.

```css
.fixed-header {
  position: fixed;
}
```

¿Qué pasó? ¿Viste que nuestra barra de navegación se rompió? No te preocupes,
ahora lo solucionamos, como lo mencionamos anteriormente, se salió del flujo de
la web y por ende se puso en una posición distinta sin importarle el resto de
contenido de la web. Apliquemos las propiedades que nos permiten controlar su
posición:

```css
.fixed-header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
}
```

¡Uff! Con esto ya se ve como antes, ¿pero qué está sucediendo? Las propiedades
que hemos agregado nos permite decirle al navegador dónde queremos que se ubique
el contenido. Primero le decimos que se coloque en la parte superior del
navegador (`top: 0`), luego le pedimos que se coloque al borde izquierdo de la
pantalla (`left: 0`) y por último, para que ocupe todo el ancho de la pantalla,
le decimos que se extienda hasta el borde derecho del navegador (`right: 0`).

¿Has probado hacer scroll? ¡La barra de navegación nos acompaña! Sin embargo,
no se ve bien cuando pasa a través de un contenido, porque se ve como si
estuviera encimado el texto de la barra de navegación :thinking:.

Esto podemos solucionar, poniéndole el mismo color de fondo que tiene todo el
documento, pero solo al contenedor que acabamos de crear:

```css
.fixed-header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  background-color: #fffbf7;
}
```

!Ahora sí! Nuestra barra de navegación quedó fija al borde superior de la
pantalla mientras hacemos scroll y no se encima el contenido. Dependiendo de que
tan observador seas, te podrás haber percatado que el título principal de la
página se subió, esto debido a que la barra de navegación se salió del flujo y
el espacio que ocupaba quedó rezagado, por ende, el título se subió, lo que
podemos hacer es ponerle un margen (o agregarle en caso que lo tenga) del tamaño
que ocupaba la barra de navegación.

Actualmente, nuestro contenido principal, tiene un margen superior de `200px`, y
la barra de navegación tiene un alto de `45px` y adicionalmente cuenta con un
margen superior de `40px`. Por lo que a nuestro contenido principal, deberíamos
de poner ahora un margen superior de `285px` para conservar el aspecto que tenía
antes de volver nuestra barra de navegación fija.

```css
main {
  margin-top: 285px;
  text-align: center;
}
```

### Desplegando nuestros cambios

Esto probablemente ya lo has venido haciendo muchas veces, pero no está demás
recordarlo.

Agrega tus cambios realizados a `git`:

```bash
$ git add -A
```

Agrega un mensaje descriptivo a tu nueva versión:

```bash
$ git commit -m "Convierte barra de navegación en fija"
```

Sube tus cambios a Github para que tengas un respaldo y siempre lo puedas
descargar en cualquier otro ordenador:

```bash
$ git push origin <nombre-rama> # `master` si no estás trabajando en otra rama
```

Al realizar este último comando tus cambios estarán reflejados en `Netlify` y
podrás revisar tu web publicada en internet, esperando que se vea algo como (o
incluso mucho mejor):

![Resultado de sesión 3](./assets/result.png)
