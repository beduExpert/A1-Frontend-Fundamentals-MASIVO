## Segundo texto

Así que, ¿por qué no le agregamos el siguiente texto que encontramos en la web
de `Matcha`? ¿Qué peso jerárquico y por ende qué etiqueta le pondrías al
encabezado? ¿Y si fuese un párrafo en vez de un encabezado? ¿Cuál sería la
diferencia?

##### Posible solución

```html
<!DOCTYPE html>
<html>
  <head>
    <!-- Aquí va información importante pero no visible dentro del navegador -->
    <title>Matcha</title>
  </head>
  <body>
    <!-- Esto es lo que se verá en el navegador web -->
    <h1>Build your blog. Build your business.</h1>
    <h4>
      Instantly publish articles, drive more traffic, grow your email list, and
      see your blog’s impact on sales.
    </h4>
    <!-- O usando un párrafo -->
    <!--
      <p>
        Instantly publish articles, drive more traffic, grow your email list, 
        and see your blog’s impact on sales.
      </p>
    -->
  </body>
</html>
```

La principal diferencia es el peso semántico que le queremos dar al texto, si
el texto que queremos mostrar no es necesariamente diferente a cualquier otro
texto que tengamos en la web, probablemente un párrafo funcione bien y luego
podríamos cambiar su apariencia para darle los efectos visuales deseados, sin
embargo, si deseamos resaltar dicho texto sobre otros existentes, podemos usar
un encabezado para darle una jerarquía y diferenciarlo de los demás.

