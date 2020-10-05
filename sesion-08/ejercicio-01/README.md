# Homologando los formularios

Dado que tenemos múltiples formularios en nuestra web que invitan al usuario a
dejar su email y suscribirse a nuestros servicios, debemos de homologarlos de
alguna manera para que todos al hacer click en el botón de suscribirse puedan
realizar la misma acción (enviar un correo de bienvenida).

Para lograr este objetivo, podemos asignar una clase a todas las etiquetas
`<form />` o contenedores del formulario en caso de no contar con esta etiqueta.

La clase que vamos a asignar será `signup-form`, dado que el servicio que
agregaremos posteriormente buscará todos los formularios con esta clase para
realizar el envío de correo de bienvenida correctamente.

Debería quedarte algo como:

```html
<form class="signup-form">
  <input type="email" placeholder="Enter email address" />
  <button type="submit">
    Try it now &rarr;
  </button>
</form>
```
