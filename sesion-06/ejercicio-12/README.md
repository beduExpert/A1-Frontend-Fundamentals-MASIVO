# Agregando la siguiente columna de preguntas frecuentes

En este caso, dado que usaremos la grid de Bootstrap, debemos de agregar ciertos
contenedores para dividir nuestra interfaz en columnas:

```html
<section class="faq">
  <div class="container">
    <div class="row">
      <div class="col">
        <div class="accordion" id="first-column-accordion">
          <!-- Aquí viene lo que hicimos para la primera columna -->
        </div>
      </div>
      <div class="col"></div>
    </div>
  </div>
</section>
```

Agregando un contenedor con clase `container` y otro con clase `row`, podemos
agregar la cantidad de columnas que queramos usando contenedores con clase `col`.
En este caso, tocaría agregar la segunda columna.
