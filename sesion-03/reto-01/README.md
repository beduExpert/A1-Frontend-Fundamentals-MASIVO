# Agregando controles de reproducción al video

## REQUISITOS
- Tener Git Bash si usas Windows.
- Tener conocimientos básicos de HTML y CSS
- Tener conocimientos básicos de Git

## INSTRUCCIONES

Resulta que por defecto el navegador no agrega controles de reproducción al video,
¿puedes buscar cómo agregárselo?

::: tip
Lo que buscas es un atributo de la etiqueta `<video></video>`.
:::

<details>
  <summary>Posible solución</summary>

Agrega el atributo `controls` a la etiqueta `<video></video>`.

```html
<body>
  <!-- Contenido previo -->
  <!-- ... -->

  <!-- Contenedor de video -->
  <section>
    <video
      controls
      src="https://cdn.videvo.net/videvo_files/video/premium/video0036/small_watermarked/computer_code00_preview.mp4"
    ></video>
  </section>
</body>
```

</details>

