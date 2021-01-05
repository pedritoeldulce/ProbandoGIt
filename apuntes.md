## Clase 1 

### Version
- Conjunto de nuevas caracteristicas y funcionalidades de un software disponibles para usuario final.

### Sistema de Control de Versiones
- Herramienta para el manejo de las diferentes versiones del software.

### Repositorio
- Lugar donde guardas todos los archivos divididos por nodos (commit)

### Comandos de configuración - GIT
- Usa el archivo de configuración global

        git config --global

    `git config --global user.name`:  Configur el nombre de usuario 

    `git config --global user.email`: Configura el email para trabajar con git

### Crear repositorio
Puede ser o no una carpeta vacía
Al iniciar se creará una carpeta `.git`

`git init`: comando que inicia nuestro repositorio

### Estados de Git

1) Área de trabajo  ----------------- 2) Área de preparación ----------  3) Repositorio (.git)

- Área de trabajo: Es todo lo que podemos ver, carpetas ocultas `.git` no es espacio de trabajo (sin seguimiento)   
- Área de preparación: Punto intermedio donde se preparan los archivos para luego pasar al repositorio, un comando que nos ayuda para identifiar el repositorio es `git status`
- Repositorio: carpeta .git

`git add` mueve los archivos del espacio de trabajo al área de preparación. Podemos agregar archivos por archivos (indicando el nombre) o todos los  archivos a la vez con el punto `.`, el punto indica que se agreguen todos los archivos de la carpeta donde estoy, más no todo el proyecto.

`git commit` Almacena los archivos en le repositorio, la Sintaxis `git commit -m "mensaje"`

`git log` Muestra todo los commit
`git log --oneline` muestra un resumen de la bitacora

## Clase 2

Diferencia archivos nuevos de archivo modificados.

Solo aplica a los archivos modificados en un solo paso van a apasar al area de preparacion y luego al repositio Git en un solo paso

    git commit -am "Actualiza la documentacion y limpieza estilos"

`git commit -am` "": archivos modificados, se usa para guardar solo archivos modificados

`git add archivo/.` : para guardar archivos nuevos


### Deshacer cambios realizados despues de un commit
- Se utiliza el siguiente comando

    git checkout <nombre del archivo>, se borra todos los cambios del arrchivo
    
    git checkout -f: forzamos que todos los cambios se resetean

### Quitando archivos del area de preparacion

    git restored --staged

Reestablece el archivo a su contenido anterior, perdiendo los cambios realizados

    git reset

quita de la zona de preparacion para el proximo commit

### Ver los cambios realizados en cada archivo

    git diff

Nos permite ver la diferencia entre lo que estamos haciendo con lo que tenemos almacenado en nuestro repositorio

## Clase 3

### Historial de cambios

El comando `git checkout` nos ayuda a navegar entre los commits, con esto podemos ir a cualquier commit

    git checkout 

    git checkout <hash de commit>

    7b645a3 (HEAD -> master) Navegando entre los commit; git checkout
    73c8283 Actualizar la documentacion
    57f15fc Se agrega la pagina de equipo
    52c931c Se agrega un enlace a la pagina Index
    52282cc Se agrega la página Nuestro equipo a Index
    c4fe487 Actualiza documentacion y limpiza de estilos
    f9c96cb Se ordena los archivos en carpetas images y styles
    6af561f agregué una imagen y lo llamé desde el index.html
    8b3fe36 Agregamos los requisitos del proyecto
    92cf08b mi Primer commit, inicia el proyecto
 

 La cabecera nos indica en que commit nos encontramos, por defecto nos encontramos el último commit.
 Los hash son códigos de cada commit que los indentifican a cada uno, también nos sirve para navegar entre ellos, copiando una parte de sus dígitos (7 como mínimo)

Pasamos del actual (7b645a3) al commit con el hash 52282cc "Se agrega la página Nuestro equipo a Index"

    git checkout 52282cc


Para retroceder en el tiempo o regresar al primer commit, utilizamos el comando

    git checkout master


Comandos adicionales, Opciones de visualización del historial

    git log --raw

`git log --raw`: Muestra los archivos que se modificaron, agregaron entre commits

`git log --oneline -<number>`: indica el numero de commit que desee visualizar


NOTA: Podemos darle formato a los mensajes que da Git.

    git log --pretty=format:"El autor del commit %h fue %an"


### Comandos LS

El comando `ls` es muy útil para ver los archivos y directorios que tenemos dentro del directorio en el que estamos.

Las opciones disponibles con este comando son las siguientes:

`ls -a`: Nos muestra los archivos y directorios dentro del directorio actual, incluyendo los archivos y directorios ocultos.

        PEDRITO@PEDRITO-PC MINGW64 ~/PROYECTOS PAOLO/PruebaGit (main)
        $ ls -a
        ./  ../  .git/  apuntes.md  images/  index.html  pages/  readme.md  styles/


`ls -l`: Muestra toda la información : usuario, grupo, permisos, tamaño, fecha y hora de creación.

        PEDRITO@PEDRITO-PC MINGW64 ~/PROYECTOS PAOLO/PruebaGit (main)
        $ ls -l
        total 10
        -rw-r--r-- 1 PEDRITO 197121 4948 Jan  5 03:01 apuntes.md
        drwxr-xr-x 1 PEDRITO 197121    0 Jan  5 00:23 images/
        -rw-r--r-- 1 PEDRITO 197121  546 Jan  5 00:23 index.html
        drwxr-xr-x 1 PEDRITO 197121    0 Jan  5 00:23 pages/
        -rw-r--r-- 1 PEDRITO 197121  254 Jan  5 00:23 readme.md
        drwxr-xr-x 1 PEDRITO 197121    0 Jan  5 00:23 styles/


`ls -lh`: Muestra la mismo informacion que *ls -l* pero con las unidades de tamaño en KB, MB, etc.

        PEDRITO@PEDRITO-PC MINGW64 ~/PROYECTOS PAOLO/PruebaGit (main)
        $ ls -lh
        total 10K
        -rw-r--r-- 1 PEDRITO 197121 5.5K Jan  5 03:03 apuntes.md
        drwxr-xr-x 1 PEDRITO 197121    0 Jan  5 00:23 images/
        -rw-r--r-- 1 PEDRITO 197121  546 Jan  5 00:23 index.html
        drwxr-xr-x 1 PEDRITO 197121    0 Jan  5 00:23 pages/
        -rw-r--r-- 1 PEDRITO 197121  254 Jan  5 00:23 readme.md
        drwxr-xr-x 1 PEDRITO 197121    0 Jan  5 00:23 styles/


## RAMAS

Comando para craer otra rama:

    git checkout -b development


Ejemplo en el Git bush

    PEDRITO@PEDRITO-PC MINGW64 ~/PROYECTOS PAOLO/PruebaGit (main)
    $ git checkout -b development
    Switched to a new branch 'development'

    PEDRITO@PEDRITO-PC MINGW64 ~/PROYECTOS PAOLO/PruebaGit (development)


Comando que permite conocer cuantas ramas tenemos en el Git:

    git branch


ejemplo:

    
    PEDRITO@PEDRITO-PC MINGW64 ~/PROYECTOS PAOLO/PruebaGit (development)
    $ git branch
    * development
    main


El comando --all muestra informacion de todas las ramas, muestra todo el texto.

    git log --oneline --all


Ejemplo

    PEDRITO@PEDRITO-PC MINGW64 ~/PROYECTOS PAOLO/PruebaGit (development)
    $ git log --oneline --all
    ab1f34a (HEAD -> development) Agregando imagen de noa en index.html, esta es una prueba de que el texto es demasiado grande y que no se muestre
    d2d4fa7 Agrega informacion en apuntes.md e index.html
    9873ba1 (origin/master, origin/main, main) Comando adicionales con -gitlog-
    9e92843 Uso del comando chekout, viajando entre commit
    73c8283 Actualizar la documentacion
    57f15fc Se agrega la pagina de equipo
    52c931c Se agrega un enlace a la pagina Index
    52282cc Se agrega la página Nuestro equipo a Index
    c4fe487 Actualiza documentacion y limpiza de estilos
    f9c96cb Se ordena los archivos en carpetas images y styles
    6af561f agregué una imagen y lo llamé desde el index.html
    8b3fe36 Agregamos los requisitos del proyecto
    92cf08b mi Primer commit, inicia el proyecto


El comando --graph muestra los commit de las ramas; los `*` representan los commits

    PEDRITO@PEDRITO-PC MINGW64 ~/PROYECTOS PAOLO/PruebaGit (development)
    $ git log --oneline --all --graph
    * ab1f34a (HEAD -> development) Agregando imagen de noa en index.html, esta es una prueba de que el texto es demasiado grande y que no se muestre
    * d2d4fa7 Agrega informacion en apuntes.md e index.html
    * 9873ba1 (origin/master, origin/main, main) Comando adicionales con -gitlog-
    * 9e92843 Uso del comando chekout, viajando entre commit
    * 73c8283 Actualizar la documentacion
    * 57f15fc Se agrega la pagina de equipo
    * 52c931c Se agrega un enlace a la pagina Index
    * 52282cc Se agrega la página Nuestro equipo a Index
    * c4fe487 Actualiza documentacion y limpiza de estilos
    * f9c96cb Se ordena los archivos en carpetas images y styles
    * 6af561f agregué una imagen y lo llamé desde el index.html
    * 8b3fe36 Agregamos los requisitos del proyecto
    * 92cf08b mi Primer commit, inicia el proyecto


Nota:  A partir de la version 2.23 de GIT, hay 2 opciones de cambiar de rama
1) `git checkout main`
2) `git switch main`

    PEDRITO@PEDRITO-PC MINGW64 ~/PROYECTOS PAOLO/PruebaGit (development)
    $ git checkout main
    Switched to branch 'main'
    Your branch is up to date with 'origin/main'.

    PEDRITO@PEDRITO-PC MINGW64 ~/PROYECTOS PAOLO/PruebaGit (main)



El comando: `git log --oneline --all --graph --decorate`, muestra

    PEDRITO@PEDRITO-PC MINGW64 ~/PROYECTOS PAOLO/PruebaGit (main)
    $ git log --oneline --all --graph --decorate
    * 4b634c4 (HEAD -> main) actualiza styles para la clase master
    * 5750340 Agrega main a la pagina equipo
    | * 6048af5 (development) Agregando mas info
    | * 17dd904 Agrengando info a apuntes.md
    | * ab1f34a Agregando imagen de noa en index.html, esta es una prueba de que el texto es demasiado grande y que no se muestre
    | * d2d4fa7 Agrega informacion en apuntes.md e index.html
    |/
    * 9873ba1 (origin/master, origin/main) Comando adicionales con -gitlog-
    * 9e92843 Uso del comando chekout, viajando entre commit
    * 73c8283 Actualizar la documentacion
    * 57f15fc Se agrega la pagina de equipo
    * 52c931c Se agrega un enlace a la pagina Index
    * 52282cc Se agrega la página Nuestro equipo a Index
    * c4fe487 Actualiza documentacion y limpiza de estilos
    * f9c96cb Se ordena los archivos en carpetas images y styles
    * 6af561f agregué una imagen y lo llamé desde el index.html
    * 8b3fe36 Agregamos los requisitos del proyecto
    * 92cf08b mi Primer commit, inicia el proyecto


Se aprecia las 2 ramas (development y main)

### Merge

El comando `git merge` 

NOTA:
*  Si los archivos que se modifican no son los mismos en ambas ramas, el `merge` se hace muy simple
* Si se llegan a modificar el mismo archivo en ambas ramas, habrá conflictos y hay que ayudar la propio git

estos es lo que nuevo que agregue en la rama dev