# Quitando separación superior del título

## REQUISITOS
- Tener Git Bash si usas Windows.
- Tener conocimientos básicos de HTML
- Tener conocimientos básicos de CSS (Flexbox)
- Tener conocimientos básicos de CSS (Gid)

## INSTRUCCIONES

Si nos fijamos en la página original, el título no queda tan seeparado del borde
superior, esto se debe a la misma razón que el caso anterior, ¿cómo harías para
mejorar su apariencia?

<details>
  <summary>Posible Solución</summary>

```css
@media (max-width: 575px) {
  .navbar,
  .actions {
    display: none;
  }

  main {
    margin-top: 130px;
  }

  h1 {
    font-size: 30px;
  }
}
```

</details>

