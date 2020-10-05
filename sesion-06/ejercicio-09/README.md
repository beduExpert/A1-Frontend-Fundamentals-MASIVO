# Guía: Agregando una nueva página

Hasta este momento, todo nuestro código a estado dentro del `index.html` que por
defecto es el archivo que todo navegador busca al acceder a un sitio web, ahora
vamos a crear un nuevo archivo en el que vamos a ir agregando código y también
vamos a reutilizar estilos que hemos venido desarrollando hasta el momento.

Empecemos por crear un nuevo archivo para el HTML y otro parar sus estilos en la
carpeta principal del proyecto:

```sh
$ pwd # asegúrate que sea la carpeta del proyecto
/ruta/al/proyecto
$ touch pricing.html
$ ls
index.html   pricing.html   style.css
$ touch pricing.css
index.html   pricing.html   style.css   pricing.css
```

Ahora, enlacemos la estructura principal de la nueva página (html, head, body):

```html
<!-- pricing.html -->
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta
      name="viewport"
      content="width=device-width,initial-scale=1.0,user-scalable=no"
    />
    <title>Matcha - Pricing</title>
    <link
      rel="stylesheet"
      href="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css"
      integrity="sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh"
      crossorigin="anonymous"
    />
    <link rel="stylesheet" type="text/css" href="./pricing.css" />
  </head>
  <body>
    <script
      src="https://code.jquery.com/jquery-3.4.1.slim.min.js"
      integrity="sha384-J6qa4849blE2+poT4WnyKhv5vZF5SrPo0iEjwBvKU7imGFAV0wwj1yYfoRSJoZ+n"
      crossorigin="anonymous"
    ></script>
    <script
      src="https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js"
      integrity="sha384-Q6E9RHvbIyZFJoft+2mJbHaEWldlvI9IOYy5n3zV9zzTtmI3UksdQRVvoxMfooAo"
      crossorigin="anonymous"
    ></script>
    <script
      src="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.min.js"
      integrity="sha384-wfSDF2E50Y2D1uUdj0O3uMBJnjuUD4Ih7YwaYd1iqfktj0Uod8GCExl3Og8ifwB6"
      crossorigin="anonymous"
    ></script>
  </body>
</html>
```

En este caso, hemos aprovechado en incluir el enlace al nuevo archivo de CSS que
hemos creado así como a los archivos de estilos y scripts de Bootstrap.

Ahora, dado que la barra de navegación será la misma, agreguemos la estructura
y CSS necesaria de entrada para tener lo mismo que en el `index.html`:

```html{20-62}
<!-- pricing.html -->
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta
      name="viewport"
      content="width=device-width,initial-scale=1.0,user-scalable=no"
    />
    <title>Matcha - Pricing</title>
    <link
      rel="stylesheet"
      href="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css"
      integrity="sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh"
      crossorigin="anonymous"
    />
    <link rel="stylesheet" type="text/css" href="./pricing.css" />
  </head>
  <body>
    <nav class="navbar navbar-expand-lg fixed-top navbar-light">
      <a class="navbar-brand" href="#">
        <img
          src="https://getmatcha.com/wp-content/themes/getmatcha/img/footer_logo.svg"
          alt="Matcha"
        />
      </a>
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
        <ul class="navbar-nav mx-auto">
          <li class="nav-item active">
            <a class="nav-link" href="#">Platform</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="pricing.html">Pricing</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Customers</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Resources</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">About</a>
          </li>
        </ul>
        <form class="form-inline my-2 my-lg-0 actions">
          <a>Sign In</a>
          <button>Start free trial</button>
        </form>
      </div>
    </nav>
    <script
      src="https://code.jquery.com/jquery-3.4.1.slim.min.js"
      integrity="sha384-J6qa4849blE2+poT4WnyKhv5vZF5SrPo0iEjwBvKU7imGFAV0wwj1yYfoRSJoZ+n"
      crossorigin="anonymous"
    ></script>
    <script
      src="https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js"
      integrity="sha384-Q6E9RHvbIyZFJoft+2mJbHaEWldlvI9IOYy5n3zV9zzTtmI3UksdQRVvoxMfooAo"
      crossorigin="anonymous"
    ></script>
    <script
      src="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.min.js"
      integrity="sha384-wfSDF2E50Y2D1uUdj0O3uMBJnjuUD4Ih7YwaYd1iqfktj0Uod8GCExl3Og8ifwB6"
      crossorigin="anonymous"
    ></script>
  </body>
</html>
```

```css
/** pricing.css */
@import url("https://fonts.googleapis.com/css?family=Alegreya:900|Open+Sans|Slabo+27px&display=swap");

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background-color: #fffbf7;
  font-family: "Open Sans", sans-serif;
}

.navbar {
  background-color: #fffbf7;
}

.navbar-light .nav-item .nav-link {
  color: #025157;
}

.navbar-light .navbar-toggler {
  border-color: #025157;
}

.navbar-light .navbar-toggler-icon {
  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' width='30' height='30' viewBox='0 0 30 30'%3e%3cpath stroke='rgb(3, 81, 77)' stroke-linecap='round' stroke-miterlimit='10' stroke-width='2' d='M4 7h22M4 15h22M4 23h22'/%3e%3c/svg%3e");
}

.actions {
  text-align: right;
  font-weight: 600;
  font-size: 14px;
}

.actions > * {
  margin-right: 10px;
  margin-left: 10px;
}

.actions a {
  color: #67b54b;
}

.actions button {
  color: white;
  background-color: #67b54b;
  padding-left: 14px;
  padding-right: 14px;
  padding-top: 12px;
  padding-bottom: 12px;
  border: 0;
  border-radius: 5px;
}
```

Con estos estilos y estructura extraídas de nuestro `index.html` obtenemos la
misma barra de navegación.
