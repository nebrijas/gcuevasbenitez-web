# Repositorio de trabajo 
Estas son las actividades del módulo de Periodismo de datos II: herramientas digitales para la visualización y presentación de datos (2021-2022).

## Actividades 

1. [Actividad dirigida 1](ad1.md)
2. [Actividad dirigida 2](ad2.md)
3. [Actividad dirigida 3](ad3.md)
4. [Actividad dirigida 4](ad4.md)

## El recorrido de aprendizaje 
En la asignatura de Periodismo de Datos II: Herramientas Digitales para la Visualización y Presentación de Datos he aprendido sobre nuevos programas y lenguajes que me ayuda a comprender mejor este mundo de la programación.
Voy a especificar según las cuatro actividades dirigidas que he visto desde el inicio de la asignatura, que forma parte del Máster Universitario en Periodismo Digital y de Datos de la Universidad Nebrija.

### Actividad dirigida 1

Aquí aprendimos y usamos le lenguaje de marcado **Markdown**. En él, a través del **GitHub**, analizamos una visualización usada en un medio de comunicación con la mayor cantidad de elementos que nos permite la sintaxis de **Markdown**.

Lo primero es que para destacar los títulos usamos el #, mientras más # usamos eso significada que el título se iría reduciendo.
Otro punto a destacar es la colocación de asteriscos. Con un asterisco delante y al final de una palabra, esta se pone en formato *cursiva*. Lo mismo funciona para una frase o un párrafo completo. Con dos asteriscos delante y dos asteriscos detrás, la frase o la palabra aparecía en **negrita**.
También aprendí sobre cómo usar los hipervínculos en **Markdown**. Lo primero es colocar entre [] la palabra o frase que quiero que tenga el enlace, seguida, y si dar espacio, coloco entre () el enlace que se abrirá.

### Actividad dirigida 2

La considero la práctica más importante porque después de ella todo lo demás fue más fácil.

Aquí convertimos el contenido de **GitHub** a página web con la misma opción que ofrece este alojador de proyecto. Aquí aprendí sobre el uso **Git Bash**, para clonar mi repositorio en un archivo local y hacer los cambios desde esta terminal para luego pasarlo a **GitHub**.

Lo aprendido con **Git Bash**: `cd` me ayudó a identificar en qué repositorio me encontraba, con el `ls` pude visualizar el contenido dentro de mi carpeta. Dentro pude usar el `nano` para editar los archivos directamente.

Otros importantes comandos fueron el `git status`, para comprobar el estado de los archivos `git add`, para agregar las modificaciones desde el repositorio local al repositorio de **GitHub**.
Con ` git commit -m "Mensaje"` es para agregar un comentario para aclarar los cambios realizados en un archivo. Con `git push` se suben los cambios al repositorio de **GitHub**.  
Señalé que esta fue la actividad más importante porque todas las demás actividades consistían en esos pasos, pasar los archivos del repositorio local al **GitHub**.

### Actividad dirigida 3

Aquí aprendí sobre la programación literaria, que consiste en documentar minuciosamente sobre un código, si ha habido un problema, cómo se resolvió y cómo se implementó. Esto ayuda a que quien lo lea pueda entenderlo.

En esta actividad hemos usado el cuaderno de **Jupyter** con documentos de Python, y como estos mismos se pueden visualizar en la web de **GitHub** descargándolos con formato de Markdown. En este cuaderno podemos hacer la práctica de programación literaria a medida en que empleamos código.

De forma predetermina, las celdas del cuaderno están en formato de código, para convertirlo en **Markdown** tendría que salir del espacio de escritura, seleccionar la celda y con el atajo de teclado presionamos `m`.

Como todo lo que se hace en Jupyter se actualiza en local, para llevarlo al **GitHub**, usamos la terminal de Git Bash y seguimos los mismos pasos que en la actidad dirigida pasada. 

### Actividad dirigida 4

Para esta actividad también usamos Jupyter en archivo **Python**, para también hacer un ejercicio de programación literaria que al final lo usamos para recopilar datos de una tabla y visualizarlo.

Usamos una API sobre los casos de coronavirus en el mundo. Una API es una interfaz de programación de aplicaciones que ayuda a un software comunicarse entre sí mediante un conjunto de definiciones y protocolos. 

Usamos la variable de dataframe para sacar fragmentos de información en los datos. Un dataframe es la estructura de datos fundamental de Pandas, que representa una tabla de datos panel con indexación integrada.

Para hacer un gráfico se usó la expresión `df_rt_pa.set_index('Date')['Cases'].plot(title="Casos de COVID-19 en Panamá desde el 20/01/2020 hasta el 29/06/2022")`.
