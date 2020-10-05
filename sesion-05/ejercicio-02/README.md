# Agregando meta viewport

Antes de personalizar la apariencia en la experiencia móvil de nuestro sitio,
debemos de agregar una etiqueta de metadatos que permite al navegador saber
cómo manejar nuestro sitio cuando se accede desde un tipo de dispositivo
diferente.

Estamos hablando de una etiqueta `<meta />` que nos permite establecer
características por defecto de nuestror `viewport`.

```html
<!DOCTYPE html>
<html>
  <head>
    <meta
      name="viewport"
      content="width=device-width,initial-scale=1.0,user-scalable=no"
    />
    <!-- Resto de etiquetas del head -->
  </head>
  <body>
    <!-- ... -->
  </body>
</html>
```

:::tip

Notar que hemos puesto esta etiqueta `<meta />` dentro del `<head></head>` de
nuestro código y no dentro del `<body></body>` como la mayoría de etiquetas que
hemos ido aprendiendo hasta el momento. Esto es debido a que no tiene ninguna
representación visual y sobretodo sirve para informar al navegador de cómo tratar
cierto tipo de contenido.

:::

En el valor del atributo `content` de esta etiqueta hemos establecido ciertas
reglas tales como indicar que el width siempre va a hacer el tamaño del dispositivo
del cuál se está viendo nuestro sitio web, a su vez, por defecto indicamos que
la escala inicial de la página es de 1, esto nos sirve para dispositivos táctiles
que tienen capacidad de hacer zoom y que pueden alterar la escala en la que se
visualiza la página y por último indicamos que el usuario no pueda hacer zoom
desde una pantalla táctil.

Aplicando este cambio a nuestro sitio veremos que todo el texto se sobrepone y
que la experiencia termina siendo muy mala. Ejemplo:

![Aplicando viewport a nuestra página](../assets/viewport.png)
