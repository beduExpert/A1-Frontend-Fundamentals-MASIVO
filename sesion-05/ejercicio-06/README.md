# Haciendo responsive la sección de características principales

De momento ya tenemos de manera responsive nuestra portada inicial,
≥adicionalmente acabamos de cambiar el flujo de nuestra sección publicitaria
que usa Flexbox. La siguiente sección que corresponde a la de publicidad no se
desborda del ancho del dispositivo pero debido a que está estructurada con Grid
CSS, está manteniendo la cantidad de columnas y filas que definimos cuando estaba
en un dispositivo más grande. Para solucionar este problema, es necesario cambiar
la relación de filas y columnas. En este caso, sería bueno mantener cuatro filas
y una columna, para que cada tarjeta vaya debajo una de la otra.

Tomando en consideración la estructura:

```html
<section class="features">
  <article class="feature-card"></article>
  <article class="feature-card"></article>
  <article class="feature-card"></article>
  <article class="feature-card"></article>
</section>
```

Podemos cambiar el CSS para dispositivos pequeños:

```css
@media (max-width: 575px) {
  /** Estilos para la sección principal y de publicidad */
  .features {
    grid-template: repeat(4, 1fr) / 1fr;
  }
}
```

Bien, con esto ya logramos posicionar las tarjetas en un flujo vertical, sin
embargo faltan 2 cosas, quitar el espacio a los lados y quitar la imagen que no
es necesaria mostrarla en la experiencia móvil.
