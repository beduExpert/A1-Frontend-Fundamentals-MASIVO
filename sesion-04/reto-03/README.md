# Grid con 2 filas y 2 columnas

## REQUISITOS
- Tener Git Bash si usas Windows.
- Tener conocimientos de CSS (Flexbox)
- Tener conocimientos de CSS (Gid)
- Conocer el modelo de caja 

## INSTRUCCIONES

Como en la mayoría de propiedades de CSS, existen muchos atajos para poner
propiedades relacionadas en una sola. Las columnas y filas de CSS Grid no son la
excepción, por lo cual, este reto consiste en obtener el mismo resultado de las
columnas y filas del grid usando la propiedad de atajo.


<details>
  <summary>Posible Solución</summary>

```css
.features {
  display: grid;
  grid-template: repeat(2, 1fr) / repeat(2, 330px);
}
```

</details>

