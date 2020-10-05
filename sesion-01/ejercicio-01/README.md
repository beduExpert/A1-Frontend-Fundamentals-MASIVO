# Creación de estructura de proyecto

## REQUISITOS 
- Tener Git Bash si usas Windows.
- Tener un editor de código instalado
- Tener una cuenta en GitHub.

## INSTRUCCIONES

1. Abrir la terminal (tener en cuenta que la interfaz puede cambiar dependiendo
   del sistema operativo que tengas).

2. Por defecto, cuando abrimos la terminal este se ubica en el directorio
   principal (_home_) de nuestro computador. Podemos verificar cuál es dicho
   directorio a través del comando `pwd`.

   ```bash
   $ pwd # Present Working Directory
   /Users/bedu
   ```

3. Una vez que sepas en donde te encuentras probablemente quieras ir a alguna
   otra ubicación para crear la carpeta del proyecto. Digamos que queremos
   crearlo dentro de la carpeta _Documents_ (el nombre puede variar dependiendo
   del sistema operativo). El comanto que nos permite acceder o movernos de
   ubicación es `cd`. A diferencia del comando anterior, éste es procedido por
   el nombre del directorio al que nos queremos mover.

   ```bash
   $ cd Documents # "Change Directory" a Documents
   ```

   > TIP: Si quieres verificar que realmente se haya cambiado de ubicación,
   > puedes usar el comando anterior para comprobarlo:
   >
   > ```bash
   > $ pwd
   > /Users/bedu/Documents
   > ```

4. Ahora que ya te encuentras donde deseas crear tu proyecto, es momento de
   crear un directorio donde almacenarás todos los archivos que terminarás
   utilizando. Para crear dicho directorio puedes usar el comando `mkdir`, al
   igual que `cd`, este comando necesita que le indiques el nombre del
   directorio que deseas crear.

   ```bash
   $ mkdir matcha # Make Directory "matcha"
   ```

5. El comando que acabas de ejecutar, ha creado una carpeta llamada `matcha`,
   una forma de verificar si se ha creado es listando todo lo que se encuentra
   en la ubicación actual. Para esto, usa el comando `ls`.

   ```bash
   $ ls # List
   matcha   another-directory    some-file.txt
   ```

   > TIP: Dependiendo de la configuración de tu terminal, puede que te muestre
   > las carpetas con un formato diferente al de los archivos, en caso contrario,
   > lo puedes diferenciar debido a que la mayoría de archivos contienen un
   > punto (`.`) seguido de la extensión (nombre particular, ejemplo: txt, doc,
   > xls, etc) mientras que los directorios no.

6. Una vez comprobado que tu directorio se creó correctamente, accede a él
   (recuerda el comando `cd` para cambiar de ubicación y `pwd` para verificar).
   Una vez dentro, el comando para crear archivos es `touch` seguido del nombre
   del archivo que deseas usar. Para este caso, crearemos solo uno llamado
   `index.html` (en este caso _.html_ es la extensión que usaremos).

   ```bash
   $ cd matcha # Change directory a "matcha"
   $ pwd # Present Working Directory
   /Users/bedu/Documents/matcha
   $ touch index.html # Crea archivo "index.html"
   $ ls # Lista contenido
   index.html
   ```

¡Genial! Acabas de crear la estructura mínima de tu proyecto usando la terminal
de tu computadora, ahora tienes el poder sobre ella y poco a poco te irás
olvidando de tu _mouse_ o _touchpad_. Lo que acabas de crear debe tener una
estructura similar a:

```text
Documents/
└── matcha/
    └── index.html
```
