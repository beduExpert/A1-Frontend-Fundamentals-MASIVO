# Cambiando de posición a los indicadores del carousel

El siguiente problema a solucionar son los indicadores, ya que estos en realidad
están en la interface, pero dado que por defecto son de color blanco y se
posicionan sobre los elementos del carousel, estos no se logran ver. Podemos
analizar sus estilos por defecto en el devtools:

![Estilos de los indicadores del carousel](../assets/carousel-indicators.png)

Lo que se puede notar de acá es que el valor de la propiedad `position` es
`absolute`, lo cual hace que salga del flujo original del documento, y a través
de la propiedad `bottom: 0` logra ubicarlo en la parte inferior de la tarjeta que
tiene una posición diferente a `static`.

Para poder ubicar los indicadores debajo de los elementos de carousel debemos de
sobreescribir la propiedad `position`:

```css
.success-stories .stories-carousel .carousel-indicators {
  position: initial; /** ó: position: static; */
}
```

:::tip

El valor `initial` hace que la propiedad asignada tome el valor inicial que esta
propiedad fue asignada. Para mayor información puedes consultar la
[documentación oficial de MDN](https://developer.mozilla.org/es/docs/Web/CSS/initial).

:::

Con esto, deberíamos lograr tener un resultado simila a:

![Indicadores de carousel con position static](../assets/carousel-indicators-position.png)

Si bien los indicadores ahora ya no se encuentran sobre la imagen, aparecen en
la parte superior del carousel, esto debido a que respeta el flujo del documento
y en el HTML la lista ordenada de indicadores viene escrita antes de los
elementos del carousel, por lo que tendremos que invertir el orden resultando en
algo como:

```html
<article class="stories-carousel">
  <div
    id="carouselExampleIndicators"
    class="carousel slide"
    data-ride="carousel"
  >
    <div class="carousel-inner">
      <!-- Elementos del carousel van aquí -->
    </div>
    <ol class="carousel-indicators">
      <li
        data-target="#carouselExampleIndicators"
        data-slide-to="0"
        class="active"
      ></li>
      <li data-target="#carouselExampleIndicators" data-slide-to="1"></li>
      <li data-target="#carouselExampleIndicators" data-slide-to="2"></li>
    </ol>
  </div>
</article>
```

Después de este cambio, la posición de los indicadores estará correcta pero aun
veremos que aparenta no estar centrada. Este problema puede deberse a que el
contenedor de los indicadores está tomando un ancho diferente al de las tarjetas.
Y si revisamos los estilos de la clase `.card` encontraremos lo siguiente:

```css
.success-stories .stories-carousel .card {
  max-width: 370px;
  width: 100%;
  background-color: #fff;
  border-radius: 10px;
}
```

Hay un ancho máximo definido, que dependiendo del tamaño de la pantalla que lo
estemos viendo, nos podremos topar con este detalle. Dado que esta propiedad
está indicando que si el ancho del contenedor supera los 370px, se deberá
aplicar esta medida. Si bien es algo que permite una buena apariencia, está
definida en un lugar erróneo, dado que al aplicarse solo a las tarjetas, los
indicadores no toman la misma medida. Podríamos optar por aplicarle la misma
propiedad a los indicadores, pero mejor aun podríamos establer dicha propiedad
a un elemento que contenga tanto a los elementos del carousel como a los
indicadores. Este elemento puede ser el div con clase `carousel` dado que
contiene a todos los elementos que forman parte del carousel y eliminar la
propiedad del elemento `div.card`:

```css
.success-stories .stories-carousel .carousel {
  max-width: 370px;
}

.success-stories .stories-carousel .card {
  width: 100%;
  background-color: #fff;
  border-radius: 10px;
}
```
