# Agregar última sección de email de bienvenida

## REQUISITOS
- Tener Git Bash si usas Windows.
- Tener una cuenta de Netifly

## INSTRUCCIONES

Para cerrar con broche de oro este curso, te tocará implementar el footer del
email de bienvenida, esto significa agregar el código necesario paa la última
fila de la tabla que estructura nuestro correo de bienvenida.

Para esto deberás insertar imágenes que estén dentro de enlaces para
redireccionar a los usuarios cuando hagan click. Si deseas usar las mismas
imágenes que te mostramos al inicio puedes usar los siguientes links:

- [Ícono de Instagram](https://images.vexels.com/media/users/3/137380/isolated/preview/1b2ca367caa7eff8b45c09ec09b44c16-icono-de-instagram-logo-by-vexels.png)
- [Ícono de Twitter](https://images.vexels.com/media/users/3/137419/isolated/preview/b1a3fab214230557053ed1c4bf17b46c-icono-de-twitter-logo-by-vexels.png)
- [Ícono de Facebook](https://images.vexels.com/media/users/3/137253/isolated/preview/90dd9f12fdd1eefb8c8976903944c026-icono-de-facebook-logo-by-vexels.png)
- [Ícono de LinkedIn](https://images.vexels.com/media/users/3/140687/isolated/preview/f705441ceeb70b9920ce6c37d80f5603-linkedin-distorsionado-icono-redondo-by-vexels.png)

- [Link de Instagram](https://www.instagram.com/matchacontent)
- [Link de Twitter](https://twitter.com/matchacontent)
- [Link de Facebook](https://www.facebook.com/matchacontent/)
- [Link de LinkedIn](https://linkedin.com/company/matchacontent)

La fuente que usamos en el ejemplo es: `'Times New Roman', Times, serif`.

<details>
  <summary>Posible solución</summary>

```html
<tr>
  <td
    style="
      padding-top: 20px;
      padding-bottom: 20px;
      font-family: 'Times New Roman', Times, serif;
      color: #46484c;
      font-size: 16px;
    "
  >
    <p>Follow us on:</p>
    <div>
      <a
        href="https://www.instagram.com/matchacontent"
        style="display: inline-block; width: 50px; height: 50px;"
      >
        <img
          style="width: 100%;"
          src="https://images.vexels.com/media/users/3/137380/isolated/preview/1b2ca367caa7eff8b45c09ec09b44c16-icono-de-instagram-logo-by-vexels.png"
          alt="Instagram"
        />
      </a>
      <a
        href="https://www.facebook.com/matchacontent/"
        style="display: inline-block; width: 50px; height: 50px;"
      >
        <img
          style="width: 100%;"
          src="https://images.vexels.com/media/users/3/137253/isolated/preview/90dd9f12fdd1eefb8c8976903944c026-icono-de-facebook-logo-by-vexels.png"
          alt="Facebook"
        />
      </a>
      <a
        href="https://twitter.com/matchacontent"
        style="display: inline-block; width: 50px; height: 50px;"
      >
        <img
          style="width: 100%;"
          src="https://images.vexels.com/media/users/3/137419/isolated/preview/b1a3fab214230557053ed1c4bf17b46c-icono-de-twitter-logo-by-vexels.png"
          alt="Twitter"
        />
      </a>
      <a
        href="https://linkedin.com/company/matchacontent"
        style="display: inline-block; width: 50px; height: 50px;"
      >
        <img
          style="width: 100%;"
          src="https://images.vexels.com/media/users/3/140687/isolated/preview/f705441ceeb70b9920ce6c37d80f5603-linkedin-distorsionado-icono-redondo-by-vexels.png"
          alt="LinkedIn"
        />
      </a>
    </div>
    <p>
      © 2020 Matcha. All Rights Reserved
    </p>
  </td>
</tr>
```

</details>
