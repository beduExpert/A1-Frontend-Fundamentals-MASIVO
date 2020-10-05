# Grid con 3 columnas iguales

## REQUISITOS
- Tener Git Bash si usas Windows.
- Tener conocimientos de CSS (Flexbox)

## INSTRUCCIONES

Queremos indicar que nuestra grid va a contener 3 columnas del mismo ancho 
relativo al espacio disponible en la pantalla. ¿Cómo lo lograrías usando la 
función `repeat(cantidad, tamaño)`?

<details>
  <summary>Posible Solución</summary>

```css
.features {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
}
```

</details>

