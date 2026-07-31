##  Probando Git

### Primeros comandos 

Entonces primero que todo para agregar archivos git add . 

para los mensajes del commit  >> git commit -m "" 

para hacer push , git push

ya estaremos viendo otros mas avanzados 


Para el dia de hoy 31 de julio estare aprendiendo a usar git con el libro de git-scm 


### Del capítulo 1:

#### 1.6 First-Time Git Setup

### Del capítulo 2 (Git Basics):

*2.1 Getting a Git Repository

*2.2 Recording Changes to the Repository

*2.3 Viewing the Commit History

*2.4 Undoing Things

*2.5 Working with Remotes

### Del capítulo 3 (Git Branching):

*3.1 Branches in a Nutshell

*3.2 Basic Branching and Merging

*3.3 Branch Management

*3.5 Remote Branches


**Siempre que queramos conectarnos con nuestro usuario

git config --global user.name "GabrielBlanc0o"
git config --global user.email "miemail@123.com"

Cuando creamos un repo , por defecto git nos crea una rama master por defecto
para cambiar el  nombre de la rama predeterminadad usaremos el comando

git config --global init.defaultBranch main <---- aqui va el nombre de la rama que iremos a usar 
en este caso ps main


### Capitulos 2

Entramos siempre con cd como siempre a la carpeta donde queramos tener nuestro proyecto

Inicializamos el proyecto con git init

luego hacemos track a los archivos que por ejemplo queramos agregar 

si la extension de los archivos es por ejemplo, en el lenguaje de programacion C

git add *.c <-- Aqui va la extension de los archivos que queramos agregar 

agregamos el archivo de Licencia comun con --> git add LICENSE


Cuando necesitemos clonar un repositorio , unicamente debemos usar el argumento clone 

y si queremos clonar el repo y agregar un nombre personalizado a la carpeta que contenga todo el contenido del repo

solo debemos agregar el prefijo al lado de la URL del repositorio



<---Ejemplo con repo normal--->

git clone https://github.com/libgt2/libgt2

<---Ejemplo con un nombre directorio personalizado --->

git clone https://github.com/libgt2/libgt2 mylibgit


## Ver historial de comandos

Listo para ver el historial de commits usaremos el comando

git log 

Este comando nos mostrara todos los commits



--- La bandera -p , muestra la diferencia introducida en cada confirmacion

Al ejecutar -log con -p , mostrara cada commit con sus cambios realizados , su identificador unico registrado 
por cada commit pusheado , y mas info importante.
 
