# Agregando múltiples formatos de video

A continuación agregaremos los elementos `<source />` dentro de la etiqueta de
`<video></video>`.

```html
<body>
  <!-- Contenido previo -->
  <!-- ... -->

  <!-- Contenedor de video -->
  <section>
    <video controls>
      <source
        type="video/webm"
        src="https://cdn.videvo.net/videvo_files/video/premium/video0036/small_watermarked/computer_code00_preview.webm"
      />
      <source
        type="video/mp4"
        src="https://cdn.videvo.net/videvo_files/video/premium/video0036/small_watermarked/computer_code00_preview.mp4"
      />
    </video>
  </section>
</body>
```

Como te podrás dar cuenta, cada etiqueta `<source />` hace referencia a un formato
distinto, y le indicamos dicho formato a través del atributo `type` para poder
diferenciarlo, y mediante el atributo `src` indicamos donde encontrar el video
en el formato especificado.
