# Agrega la imagen descriptiva de Matcha para email

## REQUISITOS
- Tener Git Bash si usas Windows.
- Tener una cuenta de Netifly

## INSTRUCCIONES


Ya vimos como insertar el logo de Matcha para el email, ahora es tu turno de
ingresar la segunda fila con la imagen descriptiva de lo que es Matcha.

El link de la imagen es: `https://getmatcha.com/wp-content/themes/getmatcha/css/../img/home_people.png`.

<details>
  <summary>Posible solución</summary>

```html{20-26}
<table
  style="width: 100%; max-width: 600px; text-align: center; background-color: #fffbf7; color: #025157;"
>
  <tr>
    <td>
      <a
        href="https://fervent-almeida-b80b1e.netlify.com/"
        target="_blank"
        style="display:block;"
      >
        <img
          style="width: 50px; margin-top: 15px; margin-bottom: 15px;"
          src="https://getmatcha.com/wp-content/uploads/2020/01/Icon-green.png"
          alt="Matcha"
        />
      </a>
    </td>
  </tr>
  <tr>
    <td>
      <img
        style="width: 100%;"
        src="https://getmatcha.com/wp-content/themes/getmatcha/css/../img/home_people.png"
        alt="People at Matcha"
      />
    </td>
  </tr>
  <tr>
    <!-- Aquí irá el texto de bienvenida y el cta -->
  </tr>
  <tr>
    <!-- Aquí irá las características que Matcha provee -->
  </tr>
  <tr>
    <!-- Aquí irá el pie de página con enlaces a redes sociales -->
  </tr>
</table>
```

Resultando en algo como:

![Email de bienvenida - 2 primeras filas](../assets/email-2-first-rows.png)

</details>
