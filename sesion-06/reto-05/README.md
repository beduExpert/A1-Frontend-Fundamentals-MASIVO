# Cambiando los estilos de los elementos del carousel

## REQUISITOS
- Tener Git Bash si usas Windows.
- Conocer como instalar Bootstrap.

## INSTRUCCIONES

¡Yay! Ya tenemos casi listo nuestro carousel y con interactividad gracias a
Bootstrap. Ahora es tu turno de darle los toques finales. Elimina los espacios
en blanco dentro de las tarjetas y cambia el color y el borde que engloca al
botón de ver los casos de éxito.

<details>
  <summary>Posible solución</summary>

Para eliminar el espacio superior entre la imagen y el borde de la tarjeta,
debemos de eliminar el `margin-top` que todos los elementos `<figure></figure>`
tienen.

```css
.success-stories .stories-carousel figure {
  margin-top: 0;
}
```

Y para elimianr el borde y color de fondo del botón en la parte inferior,
debemos de sobreescribir las propiedads de `background-color` y `border-color`
que Bootstrap le puso por coincidir en el nombre de clase que usan. Para lograr
esto, podemos agregar las propiedades a los estilos que tenemos de la clase
`card-footer`:

```css
.success-stories .stories-carousel .card .card-footer {
  margin-bottom: 20px;
  background-color: transparent;
  border-color: transparent;
}
```

</details>
