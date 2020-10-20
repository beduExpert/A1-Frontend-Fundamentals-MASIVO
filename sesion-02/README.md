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

# Etiquetas semánticas en HTML

En la sesión anterior, conocimos algunas etiquetas como `h1`, `p`, `img`, sin embargo, en una web completa encontramos que necesitamos seccionar partes de nuestra interfaz para aplicar ciertos estilos o simplemente diferenciar componentes. 
La etiqueta más usada para este tipo de agrupaciones es div y por mucho tiempo era la única opción, al punto que terminó generando una enfermedad llamada divitis (uso excesivo de divs):

![](https://lh4.googleusercontent.com/Vvqs1ZN9-DZcXg4Ui6kTlIWLoyR6JMMaFuxERNg2RHWFyLCgfWc1qlnhrGSF7tr-gi-lK4bspC4lc2xvZyPdm-IQdjDqxjNiqFq8w5VhglGiW_-Sik2Gd4OV2dmUKVWdqyKw2Uxg)

Este problema se volvió común y causaba molestias en la legibilidad del código, además de problemas en dónde cerrar y abrir nuevas etiquetas div. 

Debido a esto, HTML 5 introdujo nuevas etiquetas que imitaban el comportamiento de un div, ser un contenedor de otras etiquetas, pero adicionalmente tendría nombres que darían un significado semántico con solo leerlo. 
Algunas de esas etiquetas son:

+ header
+ nav
+ main
+ section
+ article
+ aside
+ footer

**Con estas etiquetas, nuestra web podría tener una estructura semántica como:**

![](https://lh3.googleusercontent.com/RNY0TC6kvHj7K-vquMjDcw4YoX31B5roP_muNAxrq86euodR64W-WP8SMdVFnl0eUh4FIQWB1Kkngj8Vx4t5SyiIbKnUaQNW5_29v4LflyTRp3aELB1Jtw97wIYLKH8F0Ac1eWwH)

En esta lista de [**MDN**](https://developer.mozilla.org/es/docs/HTML/HTML5/HTML5_lista_elementos#Secciones) puedes revisar para que se utilizan cada una de estas etiquetas semánticas.

️### Pregunta:

Viendo la [**barra de navegación del sitio**](https://bedu-fef.netlify.app/) original de Matcha.

**¿Qué etiquetas semánticas consideras que serían buenas usar?**

Tomando en cuenta el contenido actual de nuestra web, ¿consideras bueno que se ponga dentro de un contenedor? Si tu respuesta es positiva, **¿qué contenedor semántico usarías?**

Comparte tu respuesta con tus compañeros.

# Modelo de Caja

**¿Te has percatado que la estructura que tenemos actualmente en la web tiene una ligera separación entre el borde del navegador y el contenido?**

Esto es debido a que ciertas propiedades tienen valores por defecto dependiendo del navegador que estés usando. Esto a veces no es bueno, ya que si no sabemos cuáles son dichos valores podemos encontrar resultados inesperados.

Para solucionar este tipo de problemas se crearon muchas herramientas como:

+ [Reset CSS](https://meyerweb.com/eric/tools/css/reset/)
+ [Normalize.css ](https://necolas.github.io/normalize.css/)

En nuestro caso, no necesitamos agregar todo ese CSS que alguien más hizo, es suficiente con establecer valores que conozcamos nosotros por defecto a algunas propiedades y trabajar a partir de ellas.

Las propiedades que normalmente se ven afectadas son las que están relacionadas al modelo de caja, como márgenes margin, rellenos padding y tamaño de caja `box-sizing`. 

El modelo de caja hace referencia a que cada elemento de HTML que vemos en la página web al final es una caja rectangular, así le pongamos a un botón bordes redondeados, internamente sigue siendo un rectángulo, los textos, imágenes y absolutamente todas las etiquetas se representan internamente como una caja rectangular. 
Por lo mismo, dependiendo del valor de algunas propiedades como las mencionadas anteriormente, el tamaño de la caja (alto y ancho) pueden verse afectadas.

El modelo de caja es uno de los conceptos fundamentales para entender una vasta variedad de propiedades de CSS. 
La documentación de [**Mozilla Developer Network**](https://developer.mozilla.org/es/docs/Learn/CSS/Building_blocks/El_modelo_de_caja) (MDN para los amigos) contiene un muy buen artículo al respecto pero es un poco extenso. Si tienes interés, te recomendamos leerlo.


💡**TIP:**

Enfócate en las propiedades de `width`, `height`, `margin`, `padding`, `border` y `box-sizing`. Además, entiende la diferencia entre una caja en bloque y una caja en línea. Encontrarás un apartado que habla sobre el display, de momento lo puedes obviar ya que para ello el siguiente apartado te debería dar una mejor idea.

![](https://lh5.googleusercontent.com/H4fAkRrj8dtDOLivZYaaAmuMPmFpEIVebaoxtoVS6UxHa7KoBWh6RuJkwplayq0l568pl8GIez3lOIReNR4D2EsnS10RKQqb2SZaBwA5tNv3rwIiej6VZUQTR2Gl4JrQKYTmW2Oh)

En el ejemplo que estamos viendo de la separación entre el borde del navegador y nuestro contenido actual es porque el navegador ha asignado un margen de 8px (en el caso de Chrome) a la etiqueta `body`.

```css
body{
    margin:0
}
```

💡**TIP:**

Si bien todos los valores que son una medida deben estar seguidas de una unidad (por ejemplo px), en el caso de que el valor sea 0, no es necesario, ya que no importa si es `0px`, `0em` o 0%, al ser 0, quiere decir que en cualquier medida seguirá siendo un valor de 0.

Para no encontrarnos con más sorpresas como la del margen por defecto que pone Chrome, vamos a resetear los valores de margen, relleno y tamaño de caja a un valor por defecto a todos los elementos:

```css
*{
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}
```

💡**TIP:**

El selector `*` se usa para seleccionar todos los elementos de HTML.
La propiedad box-sizing permite indicar qué propiedades intervienen para calcular el tamaño de la caja.
En este caso, usamos `border-box` que es uno de los más utilizados, y lo que indica es que si nosotros ponemos un `width: 100px`, pero ponemos un padding de 10px y un borde de 5px a cada lado, nuestra caja mantendrá el ancho de 100px pero el contenido se reducirá a `70px` de ancho, restando cada uno de los paddings y borders de cada lado.

# Display block o inline

Esto es debido a los estilos que las etiquetas tienen asignadas por defecto, y este comportamiento está relacionado a la propiedad display. El navegador asigna a las etiquetas de HTML la propiedad display con valores block o inline. Los elementos con `display: block;` usan todo el ancho disponible de su contenedor, es decir, si nosotros creamos 4 etiquetas `<p></p>`, una seguida de la otra, vamos a ver que cada texto que pongamos se mostrará uno debajo de otro porque por defecto su ancho será del 100%. Mientras que los elementos con display: inline; usan solo el espacio necesario para mostrar su contenido.

Algunos ejemplos de elementos con display block son: `div`, `p`, `ul`, `h1`, `header`, `section`, `aside`, `nav`, y muchos más.

Teniendo en cuenta esta información, nuestro menú de navegación está basado de las etiquetas ul y li que tienen display block y list-item (se comporta como display block si no hay un valor especificado, puedes leer más al respecto en la **[documentación de Mozilla Developer Network)](https://developer.mozilla.org/en-US/docs/Web/CSS/display-listitem)**.

Una solución podría ser reemplazar el display de los `li` a `inline`.

```css
li{
    display: inline
}
```
