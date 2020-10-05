# Agregando la portada del video

## REQUISITOS
- Tener Git Bash si usas Windows.
- Tener conocimientos básicos de HTML y CSS

## INSTRUCCIONES

Bien, nuestro videos ya cuenta con controles de reproducción, además soporta más
de un formato para optimizar la experiencia de nuestros usuarios. Sin embargo,
sería genial poder definir la imagen que queremos que se vea antes de que se
reproduzca el video. ¿Nos ayudas a agregar esta funcionalidad?

::: tip
Esta funcionalidad también se logra a través de un atributo de la etiqueta
`<video></video>`.
:::

<details>
  <summary>Posible solución</summary>

Agrega el atributo `poster` a la etiqueta `<video></video>`, asignándole el link
de la imagen de portada como valor.

```html
<section>
  <video
    controls
    poster="https://cdn.videvo.net/videvo_files/video/premium/video0036/thumbnails/computer_code00_small.jpg"
  >
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
```

</details>

