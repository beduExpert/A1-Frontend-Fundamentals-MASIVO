# Revisando el responsive del navbar

Si activamos el emulador de responsive para nuestra web veremos que un
comportamiento diferente sucede en nuestra barra de navegación:

![Responsive navbar](../assets/responsive-navbar.png)

¡La barra de navegación no aparece 😱!

Si revisamos los estilos en el devtools, nos daremos cuenta que hay un media
query que se está aplicando a las clases `navbar` y `actions` indicando que
tenga un `display: none;`, así que para solucionar este problema, procederemos
a borrar ese estilo de nuestro media query.

![Responsive navbar mostrándose otra vez](../assets/responsive-navbar-2.png)

Notaremos que ahora tenemos una especie de ícono (comunmente llamado
_menú hamburguesa_) que al darle click debería de mostrarnos el menú, pero dicha
característica aun no funciona. ¿A qué se puede deber?
