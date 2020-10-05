# Agregando el contenido de la barra de navegación

## REQUISITOS
- Tener Git Bash si usas Windows.
- Tener conocimientos básicos de HTML y CSS

## INSTRUCCIONES

Teniendo en cuenta lo siguiente:

- El link de la imagen del logo es: `https://getmatcha.com/wp-content/themes/getmatcha/img/footer_logo.svg`
- El menú de navegación se puede lograr con una lista desordenada que en HTML se
  representa a través de la etiqueta [`<ul></ul>`](https://developer.mozilla.org/es/docs/Web/HTML/Elemento/ul).
- La acción `Sign In` es un link que apunta a la dirección `/login` y la acción
  de `Start free trial` es un botón.

¿Cómo agregarías el contenido de la barra de navegación?

> Ten en cuenta que no se verá igual que la página, y eso está bien, ya que nos
> estamos enfocando solo en la estructura y luego le daremos los estilos
> necesarios para darle la apariencia esperada.

<details>
  <summary>Solución</summary>

  ### Posible solución: Agregando el contenido de la barra de navegación

  ```html
  <header>
    <!-- Logo con link a la página principal -->
    <a href="/">
      <img src="https://getmatcha.com/wp-content/themes/getmatcha/img/footer_logo.svg" alt="Matcha"/>
    </a>
    <!-- Menú de navegación -->
    <nav>
      <ul>
        <li>Platform</li>
        <li>Pricing</li>
        <li>Customers</li>
        <li>Resources</li>
        <li>About</li>
      </ul>
    </nav>
    <!-- Contenedor de acciones de usuario -->
    <div>
      <a>Sign In</a>
      <button>Start free trial</button>
    </div>
  </header>
  ```
</details>

