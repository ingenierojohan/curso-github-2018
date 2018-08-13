# NOTAS SOBRE GIT y GITHUB
> ***Fecha*** : 2018-03-03  
> ***Autor*** : Johan Ramirez
***

### ***Instalacion de GIT en Maquina Local ( Linux ) :***
``` 
$: sudo apt-get install git xclip
```

### ***Saber la Version de GIT :***
```   
$: git --version
( git version 2.7.4 )
```

### ***Personalizacion GIT :***
```
$: git config --global user.name "Johan Ramirez"
$: git config --global user.email "ingenierojohan@gmail.com"
$: git config --global color.ui true
$: git config --global color.status auto
$: git config --global color.branch auto
$: git config --global color.interactive auto
```
   
### ***Crear el REPOSITORIO :***
`git init` :  Nos crea un repositorio de manera local y lo hará en la carpeta donde estamos posicionados o se le puede pasar [nombre_de_la_carpeta] y creará la carpeta con ese nombre.
```
$ : cd /home/johan/DATOS/PLATZI/CURSO_GIT_GITHUB_2018
$ : git init 
```

### ***Estados de los Archivos en GIT:***
Git tiene 3 Estados principales:    
* confirmado (committed) : Datos almacenado de manera segura en la base de datos local.
* modificado (modified) : Archivos Modificados pero no guardados en base de datos
* preparado (staged) : Marcado el Archivo en su version actual para que vaya en la proxima confirmacion.

### ***Secciones en un Proyecto GIT :***
* Directorio de Trabajo ( Working Directory )
* Area de Preparacion ( staging Area )
* Directorio de Git ( Git Directory )


### ***El flujo de trabajo básico en Git es algo así:***
1. Modificas una serie de archivos en tu directorio de trabajo.
2. Preparas los archivos, añadiendolos a tu área de preparación.
3. Confirmas los cambios, lo que toma los archivos tal y como están en el área de preparación, y almacena esas instantáneas de manera permanente en tu directorio de Git.


### ***Comandos GIT :***
```
git init                 ( Inicializamos el Repositorio )
git status               ( Ver el status de Git )
git config --list

--- Enviando al Stage ---
git add -A               ( Agrega todo los archivos stage )
git add [archivo]        ( Agrega solo un Archivo al stage )
git rm --cached          ( Nos devolvemos un paso, Lo saca del stage )
git rm -f [file]         ( Elimina el archivo por completo, del Stage y del Directorio )

--- Enviando al Git Repo ---
git commit -m            ( Agregamos comentarios de los cambios, y almacena esas instantáneas de manera permanente en directorio de Git )
git commit --ammend      ( anexa nuevos cambios al commit anterior )

--- Log ---
git log                   ( Ver los commit almacenados en Git)
git superlog              (script para ver mas info)                      

--- Tags ---
git tag -a [version] -m [mensaje]

--- Borrado ---
git reset --soft [SHA 1]        elimina los cambios hasta el staging area
git reset --mixed [SHA 1]       elimina los cambios hasta el working area
git reset --hard [SHA 1]        regresa hasta el commit del [SHA 1]

--- Crear Nuevas Ramas ---
git branch [nombre]
git checkout -b [nombre_rama]       ( Crea Rama y se Mueve a Ella)

--- Moverse entre Ramas y Commits
git checkout [nombre/sha1]

```
### ***Etiquetas Git*** ###
__git tag__ : Nos permite agregar etiquetas a nuestros cambios.

-a para la anotación  
-m para el mensaje  
-l nos muestra la lista de etiquetas  
-f para renombrar  
-d para borrar 

Podemos Etiquetar commint anteriores agregando el HASH : ` git tag 0.5 13fbe687c86446e12c6e274d152cf7d8e58d64d9`


### ***GIT LOG*** ###
Truco : 
```
$ : git config --global alias.superlog "log --graph --abbrev-commit --decorate --date=relative --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all"
```
`$: git superlog` 

* git log --oneline
* git log --graph
* git log -2

### ***Diferencias entre Commits***
`git diff [version1] [version2]` : 
Nos muestra las cambios de ese commit.
* rojo: fueron cambios que se quitaron
* verde: se agregaron cosas

`git diff [tag1] [tag2]`


### ***Borrar Commit*** ###
`git reset --soft [SHA1]`:  
 Nos permite quitar los cambios de un commit específico. Deja los archivos en el staging area, listos para hacer un commit.

Hay que tener en cuenta que si usas git reset --soft
Tienes 10 commits y borras el numero 7, los commits 8, 9 y 10 también se borran, y tendras un nuevo commit que tomara el numero 8.

`git reset --mixed [SHA1]`:  
 Nos elimina los cambios, también del staging area. Los archivos físicos se mantienen.

`git reset --hard [SHA1]`:   
Nos elimina los cambios incluso del working directory, es el más peligroso de todos porque podemos perder parte de nuestro trabajo.

Antes de hacer uso del (__Reset Hard__), utilicen este código para pasar todo el log a un file de resguardo.  
`git log > log.txt`  
`git log--oneline --decorate > log.txt`


### ***GIT branch (Múltiples variantes del repositorio)***
Las ramas son muy importantes si quieres trabajar con un equipo y no quieres tocar la rama master para no crear conflictos,

`git branch [nombre]` :se crea una nueva rama
* -l: listamos las ramas
* -d/-D [nombre]: borramos rama
* -m [nombre] [nombre_nuevo]: para renombrar ramas

`git checkout [nombre/sha1]`: Nos permite mover entre ramas y entre commits, no vamos a borrar nada. Acá es donde podemos movernos en el tiempo.

`git checkout -b [nombre_rama]`: Nos permite crear una nueva rama sin necesidad de usar branch
