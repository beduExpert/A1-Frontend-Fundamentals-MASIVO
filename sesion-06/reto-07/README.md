# Agrega la segunda columna de preguntas frecuentes

Esta reto parece simple porque podríamos pensar que hacemos los mismos pasos,
copiar y pegar el ejemplo de Bootstrap y cambiar el contenido, sin embargo,
te recomendamos prestar especial atención a los ids que vienen en el ejemplo de
Bootstrap dado que si son iguales a los de la otra columna, puede que encuentres
un comportamiento extraño. No dudes en consultar al experto si no logras entender
del todo porqué se da dicho comportamiento.

<details>
  <summary>Posible solución</summary>

```html
<div class="col">
  <div class="accordion" id="second-column-accordion">
    <div class="card">
      <div class="card-header" id="who-uses-heading">
        <h2 class="mb-0">
          <button
            class="btn btn-link"
            type="button"
            data-toggle="collapse"
            data-target="#who-uses-collapse"
            aria-expanded="false"
            aria-controls="who-uses-collapse"
          >
            Who uses Matcha?
          </button>
        </h2>
      </div>

      <div
        id="who-uses-collapse"
        class="collapse"
        aria-labelledby="who-uses-heading"
        data-parent="#second-column-accordion"
      >
        <div class="card-body">
          Hundreds of growing and established B2C and B2B brands use Matcha on
          their ecommerce site. Matcha is specifically built for companies that
          are selling on their website direct-to-consumer and will help you to
          grow and engage your audience. We work with companies in the outdoor &
          travel, food & beverage, CPG, home & family, beauty & fashion,
          apparel, fitness, and health & wellness industries, as well as with
          B2B businesses in the marketing industry. You can see more about our
          customers <a href="#">here</a>.
        </div>
      </div>
    </div>
    <div class="card">
      <div class="card-header" id="what-do-i-need-heading">
        <h2 class="mb-0">
          <button
            class="btn btn-link collapsed"
            type="button"
            data-toggle="collapse"
            data-target="#what-do-i-need-collapse"
            aria-expanded="false"
            aria-controls="what-do-i-need-collapse"
          >
            What do I need to use Matcha?
          </button>
        </h2>
      </div>
      <div
        id="what-do-i-need-collapse"
        class="collapse"
        aria-labelledby="what-do-i-need-heading"
        data-parent="#second-column-accordion"
      >
        <div class="card-body">
          As long as you have a blog set up on your website, you can begin
          publishing to Matcha and making data-driven decisions with content
          analytics. We integrate directly with WordPress and Shopify to make
          publishing even faster, but a WordPress or Shopify blog is not
          required. If you don’t have a blog on your site, they’re typically
          easy to set up.
          <a href="#">Contact us</a> to learn more.
        </div>
      </div>
    </div>
    <div class="card">
      <div class="card-header" id="more-question-heading">
        <h2 class="mb-0">
          <button
            class="btn btn-link collapsed"
            type="button"
            data-toggle="collapse"
            data-target="#more-question-collapse"
            aria-expanded="false"
            aria-controls="more-question-collapse"
          >
            Have more questions?
          </button>
        </h2>
      </div>
      <div
        id="more-question-collapse"
        class="collapse"
        aria-labelledby="more-question-heading"
        data-parent="#second-column-accordion"
      >
        <div class="card-body">
          <a href="#">Contact us</a>! We’re happy to help.
        </div>
      </div>
    </div>
  </div>
</div>
```

El CSS que aplicamos a la primera columna funciona igual para esta segunda.

</details>
