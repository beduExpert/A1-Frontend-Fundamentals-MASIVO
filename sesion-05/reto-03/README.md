# Cambiando el flujo del formulario de registro en la sección de publicidad

## REQUISITOS
- Tener Git Bash si usas Windows.
- Tener conocimientos básicos de HTML
- Tener conocimientos básicos de CSS (Flexbox)
- Tener conocimientos básicos de CSS (Gid)

## INSTRUCCIONES

El formulario está siendo desbordado debido a que está alineado en un flujo 
horizontal (`row`), para mejorar esta experiencia es necesario volverlo vertical.
¿Cómo hacemos?

:::tip
El contenedor del formulario usa Flexbox.
:::


<details>
  <summary>Posible Solución</summary>

```css
@media (max-width: 575px) {
  .publish > form {
    flex-direction: column;
  }

  .publish > form > div {
    height: 50px;
    margin-top: 10px;
  }

  .publish > form > div > input {
    width: 65%;
  }
}
```

Adicionalmente agregamos algunos estilos para mejorar la apariencia y ancho de
nuestro formulario.

</details>

