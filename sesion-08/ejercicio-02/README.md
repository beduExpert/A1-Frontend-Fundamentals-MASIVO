# Agregando el script que enviará el correo

Una vez que todos los formularios tienen el mismo identificador, agregaremos un
script de JavaScript que se encargará de detectar estos formularios y agregarle
la funcionalidad enviar el correo de bienvenida.

Para esto, debemos de crear un archivo llamado `app.js` al mismo nivel que los
archivos `index.html` y `styles.css`. Posteriormente copiaremos el siguiente
código y lo pegaremos en este nuevo archivo:

```js
// app.js
const $forms = document.querySelectorAll(".signup-form");

const getTemplate = () => {
  return fetch("./template.html").then((response) => response.text());
};

const sendEmailToApi = (address, template) => {
  fetch(`https://bedu-email-sender-api.herokuapp.com/send`, {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
    },
    body: JSON.stringify({
      address: address,
      template: template,
    }),
  })
    .then((results) => {
      console.log(results);
    })
    .catch((error) => {
      console.error(error);
    });
};

const sendEmail = (event) => {
  event.preventDefault();
  const email = event.target.querySelector("input").value;
  getTemplate()
    .then((template) => {
      sendEmailToApi(email, template);
    })
    .catch((error) => {
      console.log(error, "error al convertir el template.");
    });
};

for (let i = 0; i < $forms.length; i++) {
  $forms[i].addEventListener("submit", sendEmail);
}
```

Este script es el código que será responsable de obtener el email que ingrese el
usuario y el template que nosotros crearemos para que se envíe al email.

Para que este script se pueda ejecutar en nuestra página es necesario que lo
agreguemos en nuestro HTML, al igual que hicimos con los scripts de Bootstrap,
debemos de agregalos antes de cerrar la etiqueta `</body>`, haciendo uso de la
etiqueta `<script></script>`. Debemos de agregarlo de la siguiente forma:

```html
<body>
  <!-- Contenido de nuestra página -->
  <script src="./app.js"></script>
</body>
```

Con esto ya tenemos todo listo para dedicarnos a crear nuestra plantilla del
email de bienvenida y probar que se envíe correctamente.
