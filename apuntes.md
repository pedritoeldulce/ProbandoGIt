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
- Repositorio: 

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