# Agregando la sección principal

## REQUISITOS
- Tener Git Bash si usas Windows.
- Conocer como instalar Bootstrap.

## INSTRUCCIONES

La sección principal de la página es un título y una descripción, parece ser
algo similar a la del `index.html`. ¿Cómo lo harías en esta página?

<details>
  <summary>Posible solución</summary>

```html
<body>
  <!-- Aquí viene la barra de navegación -->
  <main class="container">
    <header class="header">
      <h1>Free During COVID-19</h1>
      <p>
        Matcha is on a mission to make your blog the biggest asset for your
        business’ growth, especially in today’s context. That’s why we’re
        making the Matcha Platform free forever to all new users who sign up
        during COVID-19.
      </p>
  </main>
</body>
```

```css
/** Aquí vienen los estilos definido previamente */
main {
  margin-top: 184px;
  text-align: center;
}

h1 {
  color: #025157;
  font-family: "Alegreya", serif;
  font-size: 60px;
  margin-bottom: 24px;
}

.header {
  padding-bottom: 184px;
}

.header p {
  color: #46484c;
  max-width: 680px;
  margin: 0 auto;
  margin-bottom: 72px;
}
```

</details>
