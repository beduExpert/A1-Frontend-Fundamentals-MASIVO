# Sesión 06: Bootstrap

Sigue el contenido a continuación durante clase para que no te pierdas ningún
detalle de lo que estás a punto de aprender.

## Objetivos

En esta sesión aprenderás:

- Usar componentes de Bootstrap para nuestra página.

- Reutilizar clases de Bootstrap.

- Desplegar los cambios a nuestra página web hosteada en Netlify.

## Contenido

### Agregando Bootstrap

# Framework CSS

Antes de continuar con el desarrollo de nuestro proyecto, hemos decidido hacer una pausa con las demás secciones de la página y darnos el tiempo de refactorizar ciertas partes haciendo uso de un framework de CSS, **¿pero qué es este último término?**

Hasta ahora, nosotros hemos escrito todo el código CSS para tener nuestro proyecto como se ve ahora, lo cual está genial porque hemos puesto en práctica varios conceptos y aprendido un montón de cosas en el camino, pero, **¿te has puesto a pensar qué tan factible es hacer esto a una empresa en cada proyecto que desarrolle?**

Definitivamente es demasiado tiempo que la mayoría de empresas no está dispuesta a invertir, o no al menos en cada proyecto, ante esto, muchas empresas y personas de la comunidad (personas que hacen código CSS como tú) han optado por crear código que pueda ser reutilizable en más de un proyecto además de una colección de componentes interactivos que suelen estar presentes en una amplia variedad de páginas, a dicha colección reutilizable se le denomina **Framework CSS**.

Usar un framework de CSS puede tener una curva de aprendizaje al inicio que tal vez te dé la sensación que te toma más tiempo que hacer tu proyecto con CSS, sin embargo, una vez que le agarres el truco verás que tu velocidad de desarrollo irá incrementando poco a poco.

+ [Bootstrap](https://getbootstrap.com/)
+ [Materialize](https://materializecss.com/)
+ [Foundation](https://get.foundation/)
+ [Bulma](https://bulma.io/)
+ [Semantic UI](https://semantic-ui.com/)
+ [Tailwind CSS](https://tailwindcss.com/)

Como verás, existen más opciones a las que listamos aquí, pero estas suelen ser de las más usadas, cuando revises cada una de ellas, verás algunas similitudes en la galería de componentes que tienen disponibles, pero a su vez notarás diferencias en la apariencia de las mismas.

Para nuestro proyecto, usaremos **Bootstrap** y a continuación estas son las razones:

+ Es un framework muy usado al día de hoy.
+ La base de componentes con las que cuenta hace que migrar a otro Framework sea un proceso más sencillo.
+ Buena demanda en el mercado.

Adicionalmente, Bootstrap es un framework desarrollado por **Twitter** que tiene una comunidad grande debido al gran uso que tiene en muchos proyectos de diversa índole, dado esto, hace que las dudas que puedan surgir para lograr ciertos objetivos sea más sencillo debido al soporte de la comunidad.

# Etiqueta `<link />`

En las primeras sesiones habíamos revisado la etiqueta `<link />` y alguno de sus atributos como rel, type y href. Sin embargo, en la nueva etiqueta que acabamos de añadir, usa un par de atributos más (**integrity y crossorigin**).

Ambos atributos son usados para implementar una funcionalidad de seguridad llamada [**integridad de subrecurso**](https://developer.mozilla.org/en-US/docs/Web/Security/Subresource_Integrity) que permiten asegurar que el recurso (CSS) pueda ser obtenido correctamente y no sufra ningún problema de seguridad cuando el navegador lo descargue en nuestra página web.
Para mayor detalle, puedes revisar esta respuesta en [**Stackoverflow**](https://stackoverflow.com/questions/32039568/what-are-the-integrity-and-crossorigin-attributes).

Con esta etiqueta añadida, ya tenemos los estilos de Bootstrap a nuestra disposición. Ahora practiquemos el concepto de [**refactorización**](https://blog.ahierro.es/refactorizacion-de-codigo/).

# Interactividad con JavaScript

Es en este punto donde nos toca hablar de JavaScript.
Recordando lo visto en la primera sesión, habíamos indicado que principalmente existen 3 lenguajes utilizados en el lado del **Front-end: HTML, CSS y JavaScript**. Hasta el momento, nosotros hemos implementado HTML y CSS. Sin embargo, **JavaScript**, es el que tiene el poder de agregar dinamismo a una página web.

Esto quiere decir que con este lenguaje de programación nosotros podemos agregar reacción a eventos (por ejemplo, cuando damos clic a un botón y queremos que mande un mensaje o muestre una sección oculta), entre muchas otras funcionalidades.

Dado que ahora nosotros queremos que un menú que no está visible se muestre al darle click a un ícono de menú hamburguesa, esto solo es posible a través de JavaScript, sin embargo, Bootstrap ha intentado abstraer toda esa funcionalidad que es común en páginas webs para que nosotros con solo importar su código fuente podemos obtener toda esa funcionalidad sin escribir una sola línea de JavaScript.

Si quieres conocer los fundamentos de porqué es mejor ingresar la etiqueta `<script></script>` antes de cerrar el body del HTML, puedes leer esta pregunta y respuesta de [**Stack Overflow**](https://es.stackoverflow.com/questions/25088/cuál-es-el-mejor-lugar-para-colocar-los-tag-scripts-src-en-html).
