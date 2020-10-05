# Alineamiento vertical

Resulta que para alinear al centro verticalmente, debemos hacer uso de la
propiedad `vertical-align: middle`, sin embargo, si aplicamos solo esta propiedad
no nos quedará centrado correctamente, esto debido a que cada elemento tiene un
tamaño diferente. Para solucionar esto, podemos sacar provecho que el contenedor
tiene un tamaño fijo (`.header` con `height:45px;`) y podemos decir que cada hijo
del elemento `header` tenga un height del `100%`. Por último, después de aplicar
ambas propiedades nos daremos con la sorpresa de que no queda verticalmente
centrado ya que a pesar que los elementos tienen el mismo tamaño, no comparten
el mismo espacio que el texto debería ocupar, para esto existe la propiedad
`line-height` que nos permite indicar cuánto es el tamaño de altura que ocupará
cada línea de texto, en este caso debería ser igual al tamaño del contenedor
(45px), quedando así:

```css
.header > * {
  display: inline-block;
  font-size: 16px;
  vertical-align: middle;
  height: 100%;
  line-height: 45px;
}
```

Con esto quedaría centrado nuestro menú de navegación, pero si somos
perfeccionistas, nos daremos cuenta que el logo no está centrado verticalmente,
lo podemos solucionar agrandando su altura al 100% del contendor:

```css
.logo > img {
  height: 100%;
}
```

El último de los detalles sería cambiar el peso de la fuente en los textos del
menú de navegación y los botones ya que aunque no parezcan son distintos en la
web original:

```css
.navbar {
  width: 70%;
  text-align: center;
  color: #025157;
  font-weight: 500;
}

.actions {
  width: 15%;
  text-align: right;
  font-size: 14px;
  font-weight: 600;
}
```

Wohoo!! Finalmente hemos terminado nuestra barra de navegación. ¿Qué te pareció?
Interesante todo lo que tienes que hacer para poder darle la forma que deseas,
¿no?. Como mencionado anteriormente, existen otras técnicas que hacen esto de
una manera mucho más sencilla pero la discutiremos en su momento. No olvides
subir tus cambios a Github y revisar que se vean los cambios reflejados en tu
página alojada en Netlify.
