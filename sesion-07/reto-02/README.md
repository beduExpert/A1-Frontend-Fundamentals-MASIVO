# Agrega la tercera columna

## REQUISITOS
- Tener Git Bash si usas Windows.
- Tener Node instalado
- Tener SASS instalado

## INSTRUCCIONES

Hasta el momento vimos como insertar la primera columna, ahora solo nos falta
agregar la última columna. En general, debido a que estamos usando clases de
Bootstrap y los estilos por clase en nuestro Sass, no deberíamos necesitar de
ningún cambio en el SCSS al menos que nos falte personalizar algo. Es tu turno
de agregar la última columna y quedar listos con el blog.

<details>
  <summary>Posible solución</summary>

En este caso, solo fue necesario agrega la misma estructura y clases que
utilizamos en nuestra segunda columna pero con el texto cambiado:

```html{10-38}
<section class="container blog">
  <div class="row">
    <div class="col">
      <!-- Aquí va la columna de descripción -->
    </div>
    <div class="col">
      <!-- Aquí va la segunda columna -->
    </div>
    <div class="col">
      <div class="card">
        <img
          src="https://getmatcha.com/wp-content/uploads/2019/06/arnel-hasanovic-MNd-Rka1o0Q-1049x699.jpg"
          class="card-img-top"
          alt="What Is Licensed Content and How Does It Help Your Business Grow?"
        />
        <div class="card-body">
          <h5 class="card-title">
            What Is Licensed Content and How Does It Help Your Business Grow?
          </h5>
          <p class="metadata">
            <strong class="category">Performance Blogging </strong>
            <strong class="read-time">• 6 mins read</strong>
          </p>
          <p class="card-text">
            TL;DR: Licensed content, sometimes called syndicated content, is
            content produced by a professional publisher that can be legally
            licensed for...
            <span class="read-more">+ <a>Read More</a></span>
          </p>
          <div class="author d-flex align-items-center">
            <img
              src="https://secure.gravatar.com/avatar/c2f0381c76fae0875a4c15deb4e0a2f8?s=96&d=retro&r=g"
              alt="Rob Glover"
            />
            <p>Rob Glover</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
```

Resultando en algo como:

![Estructura de blog con 3 columnas completas](../assets/blog-3-columns.png)

</details>
