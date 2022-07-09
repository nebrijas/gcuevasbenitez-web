# Actividad dirigida 2
Aquí describo en qué consistió la realización de esta segunda actividad dirigida, la que cuenta de tres partes.

## Primera parte
Para convertir mi repositorio en una web servida desde desde Github activé en configuración de mi repositorio la opción "Pages" cuya URL es https://github.com/nebrijas/gcuevasbenitez-web/settings/pages.

En *branch* (rama) elegelegí *main* y en *folder* (directorio, carpeta) *root*. Esto posibilió que tenga una web con un `index.html` cuyo contenido es el contenido del README.md que se ha exportado/convertido a `HTML` en una.

Para convertir mi repositorio en una web servida desde desde Github activé en configuración de mi repositorio la opción "Pages" cuya URL es https://github.com/nebrijas/gcuevasbenitez-web/settings/pages.

En *branch* (rama) elegelegí *main* y en *folder* (directorio, carpeta) *root*. Esto posibilió que tenga una web con un `index.html` cuyo contenido es el contenido del README.md que se ha exportado/convertido a `HTML` en una.

## Segunda parte

Para esta segunda parte utilicé la herramienta (software) cliente de git, **Git Bash**. Para clonar el repositorio remoto, se hizo una copia en el repositorio locar, es decir, en mi ordenardor.

Los pasos fueron los siguientes:

1. Primero realicé el `git clone` con la URL https://github.com/nebrijas/gcuevasbenitez-web.
2. Luego comprobé con un `ls` para comprobar los archivos o las arpetas que tengo.
3. Tras la confirmación, apliqué el comando `cd` seguido de mi nombre de usuario en GitHub que es gcuevasbenitez-web.
4. Imprimí un `ls` para comprobar que estoy en el directorio correcto.
5. Seguí con la configuración para poder trabajar a través de `git config user.name` seguido de mi nombre de usuario gcuevasbenitez.Y luego con `git config user.email` gcuevasbenitez@gmail.com.
6. Al repetir las configuraciones `git config user.name` y `git config user.email`, los resultados de ni nombre de usuario y correo electrónico se imprimían en automático.
7. Realicé un `git remote -v` para ver el repositorio remoto.
8. Luego me trasladé la página https://github.com/settings/tokens para generar un token al que nombré **nuevo pd2**. La fecha de expiración fue de 60 días.
9. Para el scopes, pinché en **repo** y le di a generar token, el cual copié.
10. Regresé a la terminal de **Git Bash** para guardar el token.
11. Realicé el comando `echo` y escribí entre comillas mi token para crear un archivo para guarlo  a través de `> ..//token`.
12. Ejecuté in `ls  -a ../`, hacia el directorio superior, para ver si el archivo token se creo.
13. Seguido, al archivo token le realice un `cat ../.token` y me mostró el token.
14. Copié la tarea del README a un archivo que llamo ad1.md con el comendo `cp README.md ad1.md`.
15. Hice un `ls` para confirmar que se creó.
16. Realicé un `git status` para conocer mi situación.
17. Comprobando que todo está bien, añado el ad1.md con el comando `git add ad1.md`.
18. Ejecuté un `git status` para ver si el aviso cambió.
19. Hicen un `git commit -m` y entre comilla escribí un mensaje para saber la actualización que realiacé.
20. Luego ejecuté el comando `git push` para publicar en la web.
21. Realicé el comando `nano.exe ad2.md` entré al *buffer* para escribir el nombre de la actividad.
22. Luego hice un `ls` para confirmar que tenia el nuevo archivo.
23. Escribí `git add ad2.md` para agregar el archivo, luego de confirmar que no estaba a través de un `git status`.

# Tercera parte

La tercer aparte ya fue realizada y consistía en comentar, apropiadamente, todo lo que hice para realizar esta actividad, como una forma de ejercicio de programación literaria. 
