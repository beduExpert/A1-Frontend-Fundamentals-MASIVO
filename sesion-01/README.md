# Sesión 01: Estructura tu sitio

Sigue el contenido a continuación durante clase para que no te pierdas ningún
detalle de lo que estás a punto de aprender.

## Objetivos

En esta sesión aprenderás:

- Interactuar con la terminal para crear una estructura de archivos para tu
  proyecto.
  
- Crear una estructura base de tu página web a partir del uso de etiquetas de
  HTML.

- Personalizar la apariencia de tu página a través de cambios que se aplican a
  través de CSS.

- Usar comandos de GIT para almacenar tus cambios realizados en la red social
  más usada por los programadores (Github).

# Contenido

## Prework

Qué es Front-end y Back
# Qué es Front-end y Back

![](https://gblobscdn.gitbook.com/assets%2F-M4zarNtpC-oiRgBYNwB%2F-MGpHhIkwF3Kaufu8PcG%2F-MGpIUqTbL1NYMMap7Hm%2FfrontEse.png?alt=media&token=61c569ed-4f14-4dab-89c8-263d9e878029)

# Cómo funciona la web

Todo desarrollo de proyecto web se hace a través de código, comandos que escribimos y que luego programas usan para traducirlo en algo que entienda la computadora.
Sin embargo, es necesario entender que la computadora solo entiende 1s y 0s, lo cual es muy complejo para nosotros como humanos entender. Debido a esto, se crearon lenguajes que actúan como intermediarios entre las computadoras y humanos.

En esta sesión vamos a estar interactuando principalmente con 2 lenguajes: HTML y CSS.

![](https://lh3.googleusercontent.com/qPtheawJ9_EdeqeWhT7MczEci5NhjobPZFxNzlRPyFu0PEzef2L4jBIoARA9nc2CIjKANBG0IbE2XIf9qbpfhBC75O12LMd-S7Xb5dQ0cbdF32fOoZxj3jMoNZFM4gdqgMBtB575)

Debido a que son 2 lenguajes con propósitos distintos, es importante mantener un orden en los recursos que usaremos para construir nuestro sitio web, por lo cual es importante que usemos una estructura ordenada para tener un mejor control y entendimiento sobre cómo llevar a cabo nuestro proyecto.

Dicha estructura la construiremos usando comandos en nuestra terminal que indicarán a la computadora que realice exactamente lo que nosotros le pidamos.

# Emulador de Terminal

Un emulador de terminal es una aplicación que permite **virtualizar un intérprete de comandos** pero dentro de la propia interfaz gráfica. La mayoría de entornos de escritorio en **GNU/Linux** incorporan su propio emulador de terminal. Tienen la ventaja de posibilitar la interacción a través de la línea de comandos, pero sin necesidad de salir del entorno gráfico.

En la figura de abajo tienes un ejemplo de como se ve el **emulador de Terminal de Ubuntu.**

![](https://lh5.googleusercontent.com/Rv98V8N7bD9MJaEBJ5cZIoAMN5_My7QoHMXWbDlAvYBc3mlzgCyz0ZcBMI_pRbRDQjEUESFvu0OFwRqS5qTWRUTkm2MzmycdxQSnVNJYeNAWuHYW7hdSk2d--72uUJxAdY_THAmp)

El emulador de Terminal Linux es una **herramienta poderosa capaz** de realizar tareas de forma más rápida que mediante la interfaz gráfica del sistema operativo.

### Ejemplo:

Normalmente para crear un **directorio**(carpeta), entrarías a un Explorador de archivos, y luego damos click hasta llegar a la ubicación donde se desea crear, presionas click derecho y le das nueva carpeta o dependiendo de la computadora que utilices encontrarás un ícono que te dará un acceso rápido a realizar exactamente esta misma acción.

Como programadores, acostumbramos a realizar las mismas acciones desde la terminal usando solo el teclado, esto por la rapidez y control que se siente sobre la computadora, pero también porque en algunas actividades que realizamos (sobre todo cuando configuramos servidores) no contamos con una interfaz gráfica y la terminal se vuelve nuestra única amiga.

**A continuación te presentamos la terminal en diferentes Sistemas Operativos:**

## Git Bash (Windows)

En windows, **no existe una terminal como tal**, pero tenemos una herramienta llamada **Git Bash** que es una aplicación para entornos de Microsoft Windows que ofrece una capa de emulación para una experiencia de líneas de comandos de Git.

![](https://lh6.googleusercontent.com/zYuB5OVkgqEHW8b_Ph0auAtbBPO-5TTbsw0AUheXo-Hm-2wmf4S93xY4lX-8UqFo0Fi3i-qs1Q9PD4kopGnGDlXQ7Sd1Olx-ru_ZPi1A6z52Ehu9pIIXeQt8joRM4xpss55YRn8L)

## Emulador de Terminal en Mac

No te preocupes si tienes Sistema Operativo Mac Os, **no tendrás problema con los comandos que utilizaremos en los siguientes ejemplos.**

![](https://lh5.googleusercontent.com/kMOOnqrJ1ivvM4LCnyGoHBacI9UtVBi4O2kGU00XRy4_WM7hsavORrNW78J-bzifkkSKD3LF_5v-pHloTQC2u7Yv6nj5xyp5K0xdNKgVYEKteyINxW1SChDYC0sByw9IWYp_Ux8o)

💡 **TIP:**

La terminal también es comúnmente llamada como consola, CLI, bash (no necesariamente bien usado), shell (a pesar que no es lo mismo) y tal vez te encontrarás con otro término dependiendo de la persona de quien lo escuches o leas.

# Manos a la obra

Vamos a ver los comandos más utilizados para empezar a usar el emulador de terminal o simplemente llamada terminal.

💡 **Nota:**

No tengas miedo en escribir los comandos, recuerda que la terminal es nuestra amiga. Practica mucho y descubre como la terminal nos ayudará mucho en nuestro día a día como desarrollador.

## Anatomía de un comando

Todos los comandos se componen de:

+ Un nombre con el que se invoca el comando.
+ Opciones que modifican el comportamiento del comando. (Son opcionales).
+ Argumentos sobre los que actúa el comando. (También opcionales).

![](https://gblobscdn.gitbook.com/assets%2F-M4zarNtpC-oiRgBYNwB%2F-MJOki7bW2odHmdi2m-Q%2F-MJOnj1bvqKjYI86v6jA%2FUntitled.png?alt=media&token=c8a701a5-32bf-4686-867d-a76adef103b8)

Primero vamos a abrir nuestra terminal, no importa si tienes Sistema Operativo Linux o Mac OS, recuerda si usas Windows utiliza Git Bash.

![](https://lh4.googleusercontent.com/9HttaDwjiVhn8ktMaJyYCApstZj4Pp6v-elLqXZmIeeA6bU13ZSatZAJfjBf9qspyimdy3P4fTmRtT9UjODgDxTdnR3QdrPtSzgWyYC686yq1D3cu8ZQCkv04eVG_eQi13caVz-o)

Una vez abierto nuestro emulador de terminal, vamos a perder el miedo de usar la terminal (la terrible pantalla negra) 😅, después ya no será así.

## Ayuda y Documentación: `man`

Man es uno de los comandos más útiles que podrás encontrar, es por eso que lo ponemos en primer lugar.
Nos muestra la definición de un comando y de los distintos atributos que se pueden usar.

Para probarlo tan solo deberemos escribir  `man [ comando ]`

```shell
#Sintaxis
man [ comando ]

man ls

# Salida

LS(1)                            User Commands                           LS(1)

NAME
       ls - list directory contents

SYNOPSIS
       ls [OPTION]... [FILE]...

DESCRIPTION
       List  information  about  the FILEs (the current directory by default).
       Sort entries alphabetically if none of -cftuvSUX nor --sort  is  speci‐
       fied.

       Mandatory  arguments  to  long  options are mandatory for short options
       too.

       -a, --all
              do not ignore entries starting with .

       -A, --almost-all
              do not list implied . and ..

       --author
 Manual page ls(1) line 1 (press h for help or q to quit)
```

💡 **Nota:**

Para salir solo escribimos la letra **q**.

## Listar Archivos y Carpetas: `ls`

El siguiente comando que debes conocer es `ls`. Sirve para listar los archivos y carpetas que hay dentro del directorio en el que estés.

### Ej:

Si por defecto estás en `/home/` pues te mostrará todo lo que hay dentro.

```shell
# Sintaxis

ls [ ruta ]

bedu@bedu ~ ls Documentos/

# Salida
code Zoom
```

o si ya **estás en dicho directorio**, escribimos solo el comando `ls`

```shell
bedu@bedu ~/Documentos ls

# Salida

code Zoom web maqueta_web
```

## Cambiar de Directorio: `cd`

El comando `cd` sirve para cambiar de directorio,

### Ej:

Si estás en `/home/directorio/` y quieres pasar a `/home/directorio2/`, tendrías que escribir  cd `/home/directorio2/`

```shell
# Sintaxis

cd [ ruta ]

bedu@bedu ~/cd code

# Salida

bedu@bedu ~/Documentos/code
```

Si quisieras **pasar al directorio superior** (regresar un nivel),

### Ej:

Si estás en `/home/directorio2/` y quieres regresar a `/home/directorio/`  , tendrías que escribir el comando `cd ..`

## Crear un Nuevo Directorio: `mkdir`

El comando `mkdir` sirve para crear un nuevo directorio.

💡 **Nota:**

Hay que tener en cuenta que lo crea por defecto en el directorio en el que te encuentres (te lo indica siempre en la terminal).

Si quieres crearlo en otro directorio **deberías de incluir la ruta**.

```shell
# Sintaxis

mkdir [ carpeta ] [ directorio ]

bedu@bedu ~ mkdir Documentos/nuevo_directorio

# Salida

code Zoom nuevo_directorio maqueta_web web
```

**Protip:**

Recuerda no dejar espacios a la hora de crear nuestras carpetas por que nos podemos confundir al momento de utilizarlas en una terminal, se recomienda usar [estándares de nomenclatura](http://programacion.jias.es/2017/09/estandares-de-nomenclatura-snake-case-kebab-case-camel-case/)

## Crear un Nuevo Archivo: `touch`

El comando touch sirve para crear un nuevo archivo vacío si este no existe.

```shell
# Sintaxis

touch [ archvivoNuevo ]

bedu@bedu ~/Documentos touch index.html
bedu@bedu ~/Documentos ls

# Salida

code Zoom nuevo_directorio maqueta_web web index.html
```

ó si lo queremos crear en otra ruta:

```shell
# Sintaxis

touch [ ruta ] [ archvivoNuevo ]

bedu@bedu ~ tocuh Documentos/style.html
bedu@bedu ~ ls Documentos

# Salida

code Zoom nuevo_directorio maqueta_web web index.html style.html
```

## Borrar un Archivo / Directorio: `rm`

Si queremos borrar algún archivo o directorio podemos hacer uso del comando `rm`.

```shell
# Sintaxis

rm [ archivo ]

bedu@bedu ~/Documentos ls
code Zoom nuevo_directorio index.html style.html
bedu@bedu ~/Documentos rm index.html
bedu@bedu ~/Documentos ls

# Salida

code Zoom nuevo_directorio maqueta_web  style.html
```

o bien:

```shell
# Sintaxis

rm [ ruta ]  [ archivo ]

bedu@bedu ~ ls Documentos
code Zoom nuevo_directorio style.html
bedu@bedu ~ rm Documentos/style.html
bedu@bedu ~/Documentos ls

# Salida

code Zoom nuevo_directorio maqueta_web web
```

Si queremos borrar un directorio que contenga más archivos, podremos hacer uso del atributo `-rm -r [ directorio ]`

```
# Sintaxis

-rm -r [ directorio ]

bedu@bedu ~ /Documentos ls
code Zoom nuevo_directorio
bedu@bedu ~ /Documentos ls code
index.html
bedu@bedu ~ /Documentos rm -r code

# Salida

Zoom nuevo_directorio maqueta_web web
```

o bien:

```shell
# Sintaxis

-rm -r [ ruta ] [ directorio ]

bedu@bedu ~ ls Documentos
Zoom nuevo_directorio web

bedu@bedu ~ rm -r Documentos/web

# Salida

Zoom nuevo_directorio maqueta_web
```

## Copiar un Archivo / Directorio: `cp`

A la hora de copiar archivos vamos a necesitar el comando cp.

```shell
# Sintaxis

cp [ ruta Origen ] [ archivo ] [ ruta Destino ]

bedu@bedu ~ /Documentos ls
Zoom nuevo_directorio maqueta_web

bedu@bedu ~ /Documentos cp maqueta_web/index.html nuevo_directorio
bedu@bedu ~ /Documentos ls nuevo_directorio

# Salida

index.html
```

## Mover un Archivo / Directorio: `mv`

Para mover un directorio o archivo haremos uso del  comando `mv`. Esto solo desplaza los archivos sin copiarlos de un directorio a otro.
Funciona del mismo modo que `cp`, indicando la ruta de origen y la ruta de destino, con la diferencia que ya no vamos a tener nuestro archivo en la carpeta de origen.

```shell
# Sintaxis

cp [ ruta Origen ] [ archivo ] [ ruta Destino ]

bedu@bedu ~ /Documentos ls
Zoom nuevo_directorio maqueta_web

bedu@bedu ~ /Documentos cp maqueta_web/style.html nuevo_directorio
bedu@bedu ~ /Documentos ls nuevo_directorio

# Salida

index.html style.html
```

## Ver el Contenido de un Archivo: `cat`

`cat` simplemente nos muestra su contenido sin posibilidad de cambiarlo.

```shell
# Sintaxis

cp [ archivo ]

bedu@bedu ~ /Documentos cd maqueta_web
bedu@bedu ~ /Documentos/maqueta_web cat index.html

# Salida

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
  <title>Estoy aprendiendo a usar la terminal 🤓 </title>
</body>
</html>
```

# Git

Git es un sistema de control de versiones, esto quiere decir que te permite mantener un historial de cambios y que puedas ver los cambios realizados en cualquier momento.
Imagina un documento de Word en el que estás escribiendo un proyecto personal, agregas cierto contenido, luego pides que te lo revisen y te dicen que  reviertas el cambio, **¿cómo lo harías?.**

**Una forma podría ser, crear varios documentos, cada uno con una versión diferente:**

![](https://gblobscdn.gitbook.com/assets%2F-M4zarNtpC-oiRgBYNwB%2F-MJSKiDh3mevgFhwJiwe%2F-MJSLWpbKHq4di2bTaTS%2Fimage.png?alt=media&token=c8770094-588e-4367-9f0d-4fa792c6175b)

Obviamente, esto no es óptimo y menos cuando hacemos desarrollo web porque siempre suceden cambios y a veces es bueno revisar el avance.

**💡TIP:**

En Git una **carpeta** va a ser igual a un **repositorio**.
Cuando creamos un repositorio en Git, decimos que se encuentra de **forma local**, es decir en nuestra **computadora**.

**Algunas de las características más importantes de Git son:**

+ **Rapidez en la gestión de ramas:** debido a que Git nos dice que un cambio será fusionado mucho más frecuentemente de lo que se escribe originalmente.
+ **Gestión distribuida:** Los cambios se importan como ramas adicionales y pueden ser fusionados de la misma manera como se hace en la rama local.
+ **Gestión** eficiente de proyectos grandes.
+ **Realmacenamiento** periódico en paquetes.

## Flujo de trabajo de git

![](https://lh4.googleusercontent.com/lR6HWCiatlbCkeKyhfZrCSBYft9fMrWKV0DussNzxMCoQJnA_0e7wgKThgbcSwcHIT7rJvBEgN-9sCwt2Z6r5OLwlEdSoIaXOjtj_Uc3wPM8uLiIqXxV2_4f1bSALTsI1WJBEYuI)

**Tratando de explicar la imagen:** Tenemos nuestro **directorio local** (una carpeta en nuestro pc) con muchos archivos, Git nos irá **registrando los cambios** de archivos o códigos cuando nosotros le indiquemos, así podremos viajar en el tiempo retrocediendo cambios o restaurando versiones de código, ya sea en **Local** (nuestra pc) o de forma **Remota** (servidor externo).
En la práctica quedará más claro.

En la práctica quedará más claro. 😉

# GITHUB

**GitHub es un sistema de gestión de proyectos** y control de versiones de código, así como una plataforma de red social diseñada para desarrolladores.
¿Pero para qué se usa GitHub? Bueno, en general, permite trabajar en colaboración con otras personas de todo el mundo, planificar proyectos y realizar un seguimiento del trabajo.
GitHub es también uno de los repositorios online más grandes de trabajo colaborativo en todo el mundo.

![](https://lh4.googleusercontent.com/lR6HWCiatlbCkeKyhfZrCSBYft9fMrWKV0DussNzxMCoQJnA_0e7wgKThgbcSwcHIT7rJvBEgN-9sCwt2Z6r5OLwlEdSoIaXOjtj_Uc3wPM8uLiIqXxV2_4f1bSALTsI1WJBEYuI)

💡**TIP:**

Cuando trabajamos con GitHub, decimos que se encuentra de forma remoto, es decir en la [nube](https://azure.microsoft.com/es-es/overview/what-is-the-cloud/).

 # HTML

Para definir el contenido de nuestra página web, es necesario hacer uso de HTML (**HyperText Markup Language**).

HTML es un **lenguaje de marcad**o que nos permite expresar al navegador web (programa que usamos para navegar en internet, ejemplo: Internet Explorer, Google Chrome, Mozilla Firefox, Safari, etc) lo que queremos que se muestre a través de una sintaxis basada en etiquetas.

## ¿Qué son las etiquetas HTML?

Las etiquetas HTML son **fragmentos de código que permiten crear elementos** HTML, estructuras básicas del lenguaje de programación HTML en el que se escriben las páginas web porque es el que entienden los navegadores.
El formato de una etiqueta HTML es un fragmento de texto encerrado entre corchetes angulares < >, y cada elemento HTML tiene una etiqueta de inicio del tipo `<etiqueta>` y suele terminar con una etiqueta de cierre que lleva una barra inclinada al principio `</etiqueta>`.

**Los elementos HTML tienen dos propiedades básicas:**

+ Atributos, que se encuentran en la etiqueta de inicio
+ Contenido, ubicado entre las dos etiquetas

![](https://gblobscdn.gitbook.com/assets%2F-M4zarNtpC-oiRgBYNwB%2F-MJP-gIXhGD5zChkA2bD%2F-MJPGBvwet7Abzo8bjs7%2Fimage.png?alt=media&token=5e0e9671-d10a-4cd8-933d-807841161de0)

La estructura de una etiqueta es como sigue:

```html
<!-- Esta línea es un comentario de HTML -->

<!-- Ejemplo de la sintaxis para agregar una imagen a nuestra página -->
<img src="https://bedu.org/logo.png" alt="Logo de Bedu" />

<!-- Ejemplo de la sintaxis para agregar un párrafo a nuestra página -->
<p class="paragraph">Este es un párrafo</p>
```

En el código anterior podemos ver la sintaxis de una **imagen y un párrafo** en HTML. Si los analizamos podemos ver lo siguiente:

+ Las etiquetas empiezan con `<` seguido del nombre de la etiqueta (`img`, `p`).
+ Separados por espacios encontramos atributos. Estos siguen la sintaxis **nombre-atributo="valor-atributo"**.
+ Los atributos pueden variar dependiendo del tipo de etiqueta (las imágenes usan `src` y `alt` pero los párrafos no).
+ Para denotar el fin de la etiqueta `img`, usamos `/>`.
Mientras que para etiquetas como la de párrafo (`p`), la etiqueta de apertura termina con >, seguido del contenido de lo que representa la etiqueta, y por último la etiqueta de cierre con la sintaxis (`</nombre-etiqueta>`).

**Pro-tip:**

Al inicio puede verse complicado identificar qué etiquetas se cierran automáticamente como `<img />` y cuáles necesitan cerrarse manualmente como la etiqueta  `<p></p>`.

La clave para comprender esto es que existen etiquetas que pueden tener contenido dentro de ellas (**como texto o incluso más etiquetas**) mientras que otras etiquetas no pueden contener nada dentro de ellas (como las **imágenes**).

Por último pero no menos importantes, los comentarios son bloques de texto que no se muestran en la página web pero que sirve de información importante para los programadores que leen/escriben el código.

La sintaxis es `<!--`, seguido del texto que queremos comentar y cerrando el comentario con `-->`. Tener en cuenta que un comentario no se cierra hasta no encontrar la etiqueta de cierre.

Esto no mostraría nada en la web:

```html
<!-- Este es un comentario mal cerrado y que no permitirá mostrar el párrafo

<p>
Este párrafo está bien escrito pero no se mostrará por el comentario mal cerrado
</p>
```

![](https://lh6.googleusercontent.com/AL25SY8AHimQYO7m_cx3uXjg1jOwMcVKpgnpdcX7E4acH8ycr8oBPnhhclW8qN8qwHNNdLnTKOVL8I2nOmzJS6pWX1JVur5eOQ9ykmAcFXUleFVF89PP8aRSOwEG8xSxDi5OZkUB)

# CSS (Cascading Style Sheets)

Es un lenguaje de estilos que nos permite **personalizar la apariencia de los elementos** que hemos agregado en nuestro HTML.

Los estilos se aplican a través de selectores, que es una sintaxis particular para saber qué elemento queremos personalizar su apariencia.

**La sintaxis es la siguiente:**

```css
selector{
    nombre-propiedad: valor-propiedad;
}

/*Ejemplo*/

body{
    background-color: red;
}
```
![](https://lh6.googleusercontent.com/6-kMuqHi5sHn7Qi7cVQPV0JegLBiXj2uqssMzPc-B_oY5tRMOe256i_9ExYPO12PGSvjF969rh7VTP_TjC_Pp_W6-GJ0246a6UWa-okgwlA3gBS6vMG60NL-4h3FKUFY5Q84Hi6R)
