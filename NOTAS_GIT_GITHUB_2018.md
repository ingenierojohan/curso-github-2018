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
git status
git config --list
git add -A               (Agrega todo los archivos stage)
git add [archivo]        (Agrega solo un Archivo)

```
