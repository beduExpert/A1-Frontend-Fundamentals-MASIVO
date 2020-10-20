# Sesión: Agregando filas y columnas con CSS Grid

Sigue el contenido a continuación durante clase para que no te pierdas ningún
detalle de lo que estás a punto de aprender.

## Objetivos

En esta sesión aprenderás:

- Usar diferentes propiedades de Felxbox

- Estructurar elementos en formato de filas y columnas.

- Posicionar elementos en base a la posición de otros de manera flexible.

- Usar comandos de git para obtener cambios realizados por terceros.

- Desplegar los cambios a nuestra página web hosteada en Netlify.

## Contenido


Aquí podrás entender el concepto detrás del por qué nuestra web debe ser adaptable a diversos **tamaños de dispositivos**, así como las diversas tácticas para llevar este proceso a cabo.

Primero, tengamos en cuenta qué es el diseño **web adaptable** (responsive web design) y para esto la [**documentación oficial de MDN**](https://developer.mozilla.org/es/docs/Desarrollo_Web/Web_adaptable), tiene un breve resumen de que trata, a su vez, menciona los puntos más resaltantes que consisten en este concepto.

Tener en cuenta que en este enlace se listen recursos complementarios que no es necesario prestar atención en este momento del prework (puedes hacerlo si en caso deseas profundizar).Adentrando en materia, el equipo de [**Google**](https://developers.google.com/web/fundamentals/design-and-ux/responsive) tiene a disposición una guía sobre los aspectos básicos que conforman el diseño web adaptable y que nos puede dar una gran idea de qué trata y cómo lograrlo incluso a través de un ejemplo que se hace mención en el artículo.

# Media Queries

Si leíste el artículo de Google Developers, habrás notado de la existencia de esta característica que CSS nos permite utilizar para poder hacer nuestros sitios web adaptables a diversos tamaños de dispositivos. Es importante, que profundicemos un poco más en entender de qué trata dado que lo pondremos en práctica durante la sesión.

Para esto, puedes revisar el siguiente artículo para complementar lo mencionado en la [**guía de Google Developers**](https://desafiohosting.com/que-es-una-media-query/).

Ten en cuenta que los [**media queries**](https://css-tricks.com/css-media-queries/) te permiten implementar funcionalidades más allá de solo personalizar estilos para una web en diversos dispositivos, y nosotros en la sesión solo nos concentramos en algunas de sus capacidades.

💡 **Recuerda:**

Una forma de agregar condiciones de estilos en base a tamaño de dispositivos es a través de la característica de CSS llamada media queries.
Esta característica nos permite sobreescribir diferentes estilos en base a condiciones (**breakpoints**) que nosotros podemos definir.

Veamos un ejemplo de la sintaxis:

```css
@media (breakpoint){
    /*Aplica estilos particulares para este tamaño*/
}
```

Los **breakpoints** son las condiciones que nosotros establecemos, normalmente en base al **ancho de un dispositivo**, también se pueden agrupar un conjunto de condiciones en un mismo **media query**.

```css
@media (max-width: 575px){
    body{
        background-color: yellow;
    }
}
```

En el ejemplo estamos diciendo que todos los dispositivos que tengan un **ancho máximo de 575px** tendrá un color de fondo amarillo, si pruebas esto en tu proyecto, verás que en una vista móvil el fondo será amarilla, pero si sales del emulador, tu página volverá a tener el color de fondo que tenía antes.

**Este es el poder que los media queries te dan.**

Nosotros trabajaremos con los [**siguientes breakpoints**](https://getbootstrap.com/docs/4.1/layout/overview/) para personalizar nuestros estilos.
