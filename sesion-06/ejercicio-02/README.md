# Agregando el navbar

Comencemos por comentar la barra de navegación que actualmente tenemos para
evitar que se mezcle con la barra de navegación de Bootstrap.

```html
<body>
  <!-- Esto es lo que se verá en el navegador web -->
  <!-- <section class="fixed-header">
    <header class="header">
      <a href="/" class="logo">
        <img
          src="https://getmatcha.com/wp-content/themes/getmatcha/img/footer_logo.svg"
          alt="Matcha"
        />
      </a>
      <nav class="navbar">
        <ul class="menu">
          <li class="menu-item">Platform</li>
          <li class="menu-item">Pricing</li>
          <li class="menu-item">Customers</li>
          <li class="menu-item">Resources</li>
          <li class="menu-item">About</li>
        </ul>
      </nav>
      <div class="actions">
        <a>Sign In</a>
        <button>Start free trial</button>
      </div>
    </header>
  </section> -->
</body>
```

De tal forma podemos agregar la [barra de navegación de ejemplo](https://getbootstrap.com/docs/4.4/components/navbar/#supported-content)
que nos da Bootstrap y adaptarla a lo que nosotros necesitamos:

```html
<body>
  <!-- Nuestra barra de navegación comentada va aquí -->
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <a class="navbar-brand" href="#">Navbar</a>
    <button
      class="navbar-toggler"
      type="button"
      data-toggle="collapse"
      data-target="#navbarSupportedContent"
      aria-controls="navbarSupportedContent"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <span class="navbar-toggler-icon"></span>
    </button>

    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav mr-auto">
        <li class="nav-item active">
          <a class="nav-link" href="#"
            >Home <span class="sr-only">(current)</span></a
          >
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Link</a>
        </li>
        <li class="nav-item dropdown">
          <a
            class="nav-link dropdown-toggle"
            href="#"
            id="navbarDropdown"
            role="button"
            data-toggle="dropdown"
            aria-haspopup="true"
            aria-expanded="false"
          >
            Dropdown
          </a>
          <div class="dropdown-menu" aria-labelledby="navbarDropdown">
            <a class="dropdown-item" href="#">Action</a>
            <a class="dropdown-item" href="#">Another action</a>
            <div class="dropdown-divider"></div>
            <a class="dropdown-item" href="#">Something else here</a>
          </div>
        </li>
        <li class="nav-item">
          <a
            class="nav-link disabled"
            href="#"
            tabindex="-1"
            aria-disabled="true"
            >Disabled</a
          >
        </li>
      </ul>
      <form class="form-inline my-2 my-lg-0">
        <input
          class="form-control mr-sm-2"
          type="search"
          placeholder="Search"
          aria-label="Search"
        />
        <button class="btn btn-outline-success my-2 my-sm-0" type="submit">
          Search
        </button>
      </form>
    </div>
  </nav>
</body>
```

Debería verse algo similar a:

![Barra de navegación de ejemplo de Bootstrap agregada](../assets/bootstrap-default-navbar.png)

¡Vamos a adaptarla a lo que necesitamos!
