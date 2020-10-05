# Agregando estilos de Bootstrap al proyecto

Ahora que ya sabemos que vamos a usar un framework de CSS y que será Bootstrap,
necesitamos agregarlo a nuestro proyecto para empezar a usarlo.

La forma de agregar Boostrap es a través de links externos que hacen referencia
a un archivo de CSS y algunos archivos de **JavaScript**. Este término puede que
sea nuevo o tal vez lo recuerdes desde el prework de la primera sesión. En
cualquier caso, JavaScript es el único lenguaje de programación que el navegador
soporta nativamente, y es el lenguaje que nos permite agregar interacción y
funcionalidad a nuestra web. En este curso, no estaremos programando en
JavaScript, pero dado que Bootstrap lo usa para ciertos componentes, lo usaremos
a través del framework sin que nosotros necesariamente tengamos que programar.

Empecemos agregando solo el CSS, para esto, debemos ingresar a la sección de
[empezar con Bootstrap](https://getbootstrap.com/docs/4.4/getting-started/introduction/#css),
en el apartado de `CSS` encontraremos una etiqueta `<link />` con una sintaxis
similar a la que nosotros usamos para indicarle a nuestro HTML dónde encontrar
los estilos de nuestra web. Vamos a copiar toda esa línea de código y la vamos
a pegar en nuestro `index.html`. La ubicación en la cual lo peguemos es
importante, dado que `CSS` al ser un lenguaje en cascada, si coincide algún
nombre de clase que usa Boostrap con alguna que nosotros estamos, podríamos
terminar sobreescribiendo los nombres y el que prevalezca dependerá del orden en
el que encuentre nuestras hojas de estilo.

Por lo tanto, nosotros queremos agarrar la mayoría de estilos que Bootstrap nos
trae consigo, pero en caso algo no esté alineado con nuestro diseño, debemos de
personalizarlo, por ello pondremos primero el `<link />` de Bootstrap seguido
por el nuestro, quedando algo como:

```html
<head>
  <!-- Aquí van las otras etiquetas del head -->
  <link
    rel="stylesheet"
    href="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css"
    integrity="sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh"
    crossorigin="anonymous"
  />
  <link rel="stylesheet" type="text/css" href="./styles.css" />
</head>
```
