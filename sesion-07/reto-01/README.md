# Agrega colores usados en las tarjetas

## REQUISITOS
- Tener Git Bash si usas Windows.
- Tener Node instalado
- Tener SASS instalado

## INSTRUCCIONES

Dentro de las tarjetas de los posts, hay 3 colores distintos para los distintos
textos que tenemos. Usa el devtools para encontrar esos colores y defínelos en
el archivo de `_global.scss`.

<details>
  <summary>Posible solución</summary>

Definimos los colores en `_global.scss`:

```scss{7-9}
/** _global.scss */

/** colores */
$dark-green-title: #025157;
$dark-green-text: #135359;
$white: #ffffff;
$gray: #4a4a4a;
$light-gray: #979797;
$light-green: #67b54b;
```

</details>

