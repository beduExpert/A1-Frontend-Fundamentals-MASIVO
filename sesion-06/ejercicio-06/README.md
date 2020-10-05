# Agregando carousel de Bootstrap

Al igual que con el navbar, Bootstrap cuenta con un [componente de Carousel](https://getbootstrap.com/docs/4.4/components/carousel/)
que nos permitirá cambiar automáticamente los casos de éxito. Para esto,
comencemos por comentar nuestro código actual del carousel de casos de éxito:

```html
<article class="stories-carousel">
  <!-- <div class="card">
    <div class="card-media">
      <figure>
        <img
          src="https://getmatcha.com/wp-content/uploads/2019/05/profile-headshot-square.png"
          alt="Everly worker"
        />
      </figure>
      <div class="company">
        <img
          src="https://getmatcha.com/wp-content/uploads/2019/05/everly_logo_blue_v3_x60@2x.png"
          alt="Everly"
        />
      </div>
    </div>
    <div class="card-body">
      <h4>Everly</h4>
      <h3>
        Early-Stage CPG Brand Increases Lead Conversion 20x, Ecommerce
        Revenue 20%
      </h3>
      <div class="results">
        <img
          src="https://getmatcha.com/wp-content/themes/getmatcha/img/icon_cart.png"
          alt="Cart icon"
        />
        <p>22% of monthly revenue influenced by content</p>
      </div>
    </div>
    <div class="card-footer">
      <button>See Case Study</button>
    </div>
  </div> -->
</article>
```

Y agreguemos el [código de ejemplo de Bootstrap](https://getbootstrap.com/docs/4.4/components/carousel/#with-indicators),
agregaremos ese ejemplo en particular porque tiene los indicadores que
permitirán manipular el slide que se quiere ver a través de un click:

```html
<article class="stories-carousel">
  <!-- Aquí debería estar el código que acabamos de comentar -->
  <div
    id="carouselExampleIndicators"
    class="carousel slide"
    data-ride="carousel"
  >
    <ol class="carousel-indicators">
      <li
        data-target="#carouselExampleIndicators"
        data-slide-to="0"
        class="active"
      ></li>
      <li data-target="#carouselExampleIndicators" data-slide-to="1"></li>
      <li data-target="#carouselExampleIndicators" data-slide-to="2"></li>
    </ol>
    <div class="carousel-inner">
      <div class="carousel-item active">
        <img src="..." class="d-block w-100" alt="..." />
      </div>
      <div class="carousel-item">
        <img src="..." class="d-block w-100" alt="..." />
      </div>
      <div class="carousel-item">
        <img src="..." class="d-block w-100" alt="..." />
      </div>
    </div>
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
  </div>
</article>
```

Buscando entender el contenido del HTML del ejemplo de Bootstrap, podemos ver
que primero tenemos una lista ordenada (`<ol></ol>`), dicha lista son los
indicadores que se ven como líneas sobre la imagen para indicar cuál es la que
se está mostrando y cuántos elementos hay dentro del carousel. Seguido
encontramos el `div.carousel-inner` que contiene 3 divs con clase `carousel-item`
que contiene cada uno de los elementos del carousel dentro (en este caso las
etiquetas `<img />`). Por último están 2 enlaces que representan las flechas que
se sobreponen sobre los elementos del carousel para controlar manualmente si
queremos avanzar o retroceder en el carousel.
