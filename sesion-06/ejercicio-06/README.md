# Eliminando flechas de control de carousel

Las flechas no las necesitamos y no están encajando bien en el comportamiento
por defecto de nuestro carousel, así que podemos eliminarlos. Como lo habíamos
analizado previamente, las flechas son los elementos `<a></a>` que estaban al
final del carousel, asegúrate de eliminarlos del código:

```html
<a
  class="carousel-control-prev"
  href="#carouselExampleIndicators"
  role="button"
  data-slide="prev"
>
  <span class="carousel-control-prev-icon" aria-hidden="true"></span>
  <span class="sr-only">Previous</span>
</a>
<a
  class="carousel-control-next"
  href="#carouselExampleIndicators"
  role="button"
  data-slide="next"
>
  <span class="carousel-control-next-icon" aria-hidden="true"></span>
  <span class="sr-only">Next</span>
</a>
```
