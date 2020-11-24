# Sesión 07: Optimizando la producción de CSS

Sigue el contenido a continuación durante clase para que no te pierdas ningún
detalle de lo que estás a punto de aprender.

## Objetivos

En esta sesión aprenderás:

- Sobre preprocesadores de CSS.
- Optimizar la producción de CSS con Sass.
- Agregar las secciones restantes de la página original de Matcha.

## Contenido

# Preprocesadores de CSS

En las sesiones pasadas hemos venido implementando nuestra página web con HTML y CSS, y en la última usamos Bootstrap para utilizar componentes preconstruidos por alguien más, sin embargo eso no significó que dejemos de escribir CSS y dado que es algo muy común, puede llegar momentos en el que el mantenimiento de nuestro código CSS sea un poco tedioso.

![](https://gblobscdn.gitbook.com/assets%2F-M4zarNtpC-oiRgBYNwB%2F-MJK59UO38IGataECHy_%2F-MJK6f2alVB5td2Zs85A%2Fimage.png?alt=media&token=497bd36e-5a9a-40ab-b601-06300f5d8147)

Este tipo de código puede ser necesario para ser lo más específico posible y no alterar estilos que no deseamos, pero si modificamos la estructura de nuestro HTML, modificar estos estilos se puede volver una tarea compleja. Por otro lado, en muchos selectores distintos hemos usado algunas propiedades similares como los colores y las fuentes, pero **¿te imaginas que decidamos cambiar de colores o fuentes?**

Exactamente lo descrito anteriormente es lo que un preprocesador nos permite, nos provee un lenguaje con habilidades potentes que al final terminan convirtiéndose a CSS, permitiendo de esta manera que nuestra experiencia de desarrollo sea más llevadera.

**Alguno de los preprocesadores más conocidos son:**

+ [Sass](https://sass-lang.com/)
+ [Less](http://lesscss.org/)
+ [Stylus](https://stylus-lang.com/)
+ [PostCSS](https://postcss.org/) (aunque no es un preprocesador per sé)

En esta sesión vamos a estar usando Sass, debido a la fácil adaptación que encontraremos luego de haber visto CSS además de su comunidad que lo respalda habiendo sido utilizado en varios proyectos muy usados como [**Bootstrap**](https://getbootstrap.com/docs/4.0/getting-started/theming/#sass).

# Node.js y NPM

![](https://gblobscdn.gitbook.com/assets%2F-M4zarNtpC-oiRgBYNwB%2F-MJK59UO38IGataECHy_%2F-MJK75SmCNkK2Aj0QaLd%2Fimage.png?alt=media&token=bc358120-b966-4254-bbb5-9d87506a6089)

En este curso no hemos tenido la oportunidad de interactuar con el lenguaje de programación llamado JavaScript, el mayor acercamiento ha sido cuando agregamos los scripts de Bootstrap para que funcione el **carousel** y que el menú hamburguesa despliegue las opciones navegación al hacer clic sobre el mismo.

Sin embargo, debes de enterarte que JavaScript es un lenguaje que por mucho tiempo se ejecutaba solo en el navegador a través del uso de la etiqueta `<script></script>`, pero desde el 2009 la adopción de ejecutar JavaScript en las computadoras sin necesidad de un navegador fue creciendo más y más.

Y el mecanismo de ejecutar JavaScript en cualquier computador es posible gracias a [**Node.js**](https://nodejs.org/en/) que como tal es un entorno de ejecución de JavaScript instalable en cualquier ordenador.

Cuando instalas **Node.js**, viene por defecto con otros programas, uno de ellos es llamado npm (Node Package Manager) que tiene la función de proveer un comando en la terminal que te permite indicarle qué módulo escrito en JavaScript queremos usar en nuestro proyecto y el se encarga de buscarlo, descargarlo y ponerlo disponible para nosotros. Imagínate que le hubieras dicho que quieres usar Bootstrap en su proyecto, a través de un comando le podrías decir a npm que vaya y lo descargue por ti y tu solamente agregar la etiqueta `<link />` o `<script></script>`, a diferencia de como lo hicimos nosotros que fue ir a la página de la documentación oficial, buscar los links y luego copiar y pegarlos en el proyecto.

Esto no se vuelve escalable cuando usas muchas librerías, y **npm** nos ayuda con este problema.

💡 **Nota:**

En nuestro proyecto, como descrito en el prework, **deberás haber instalado Node.js** y a través de npm haber instalado sass como un módulo global, es decir, disponible para ejecutarlo como un comando en cualquier parte de nuestro ordenador.
