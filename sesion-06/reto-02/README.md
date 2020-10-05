# Revisando el responsive de las acciones del navbar

## REQUISITOS
- Tener Git Bash si usas Windows.
- Conocer como instalar Bootstrap.
- Saber que es un framework

## INSTRUCCIONES

Si comenzamos por cambiar el tamaño del navegador a uno más pequeño, llegaremos
a un punto en el que nuestra barra de navegación se rompe:

![Estilos de acciones en el navbar rotos](../assets/broken-navbar-actions.png)

<details>
  <summary>Posible solución</summary>

En este caso, el problema viene dado por que la clase `actions` tiene una
propiedad `width` asignándola al 15% del tamaño de su contenedor, y dado que
Bootstrap está usando Flexbox para manejar el ancho de sus elementos, no es
necesaria dicha propiedad. Así que una solución es eliminar dicha propiedad,
quedando la clase `actions` de la siguiente manera:

```css
.actions {
  text-align: right;
  font-weight: 600;
  font-size: 14px;
}
```

</details>
