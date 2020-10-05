# Ajustando el ancho del banner Capterra

Si bien nuestra página principal ya va tomando una mejor apariencia, la imagen
con el texto _Capterra_ y las estrellas se desbordan del ancho del dispositivo,
esto normalmente es debido a que el ancho de la imagen supera el ancho
disponible en el dispositivo.

Si analizamos el banner nos vamos a dar cuenta que esta no cuenta con estilos,
para adaptarlo al ancho del dispositivo podemos establecerle un `width: 100%`
cuando se encuentre en dispositivos pequeños, ya que si lo aplicamos de forma
genérica afectaríamos su apariencia en dispositivos medianos y grandes (donde ya
se veían bien).

Agreguemos una clase al banner y modifiquemos sus estilos:

```html
<main>
  <!-- Contenido previo al banner -->
  <figure class="banner">
    <img
      src="https://getmatcha.com/wp-content/themes/getmatcha/img/capterra.png"
      alt="Capterra"
    />
  </figure>
  <!-- Contenido posterior al banner -->
</main>
```

```css
@media (max-width: 575px) {
  /** Media queries previos al banner **/
  .banner > img {
    width: 100%;
  }
}
```

Con los cambios realizados hasta el momento, nuestra web en dispositivos
pequeños deberían de verse así:

![Resultado parcial de la página responsiva](../assets/home-responsive.png)
