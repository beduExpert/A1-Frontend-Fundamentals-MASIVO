# Mejorando la experiencia móvil de las tarjetas de características

## REQUISITOS
- Tener Git Bash si usas Windows.
- Tener conocimientos básicos de CSS (Flexbox)
- Tener conocimientos básicos de CSS (Gid)

## INSTRUCCIONES

Hasta este punto tenemos las características alineadas correctamente, sin embargo,
todavía no dan una buena apariencia, debido al ancho que ocupan en la pantalla 
se ve reducido y también porque la imagen no da una buena experiencia en este
tamaño de pantalla. ¿Cómo la mejoramos?


<details>
  <summary>Posible Solución</summary>

```css
@media (max-width: 575px) {
  /** Estilos de portada principal y sección de publicidad */
  .features {
    grid-template: repeat(4, 1fr) / 1fr;
    padding-left: 0;
    padding-right: 0;
  }
  
  .feature-image {
    display: none;
  }
}
```
</details>
