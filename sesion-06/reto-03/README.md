# Corrige el menú desplegado en un móvil

## REQUISITOS
- Tener Git Bash si usas Windows.
- Conocer como instalar Bootstrap.
- Saber que es responsive design

## INSTRUCCIONES

Ahora con el menú funcionando en dispositivos pequeños, notaremos que la
alineación de las opciones y tal vez el color del texto no se logra a percibir
muy bien, para esto puedes usar algunos estilos en el media query para adaptarlo
como tu prefieras.

![Menú responsive desplegado](../assets/responsive-menu.png)

<details>
  <summary>Posible solución</summary>

Este reto es libre, por ejemplo, en nuestro caso cambiamos el color de fuente de
cada uno de los items del menú para un mejor contraste y cambiamos el color del
menú hamburguesa.

```css
.navbar-light .nav-item .nav-link {
  color: #025157;
}

.navbar-light .navbar-toggler {
  border-color: #025157;
}

.navbar-light .navbar-toggler-icon {
  background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' width='30' height='30' viewBox='0 0 30 30'%3e%3cpath stroke='rgb(3, 81, 77)' stroke-linecap='round' stroke-miterlimit='10' stroke-width='2' d='M4 7h22M4 15h22M4 23h22'/%3e%3c/svg%3e");
}
```

</details>
