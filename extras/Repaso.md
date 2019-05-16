# Repaso Git, Bootstrap y Sass


[![N|Solid](https://cdn.svgporn.com/logos/git.svg)](https://git-scm.com/docs/git-help)


# Comandos Git

- git config - Usado para establecer una __configuración__ específica de usuario. Por ejemplo configurar el email.
  > git config --global user.email alumno1@gmail.com

    *zsh
    > gcf  - muestra la lista de configuracion

- git init - Lo usamos para __crear__ un nuevo repositorio de Git.
    > git init
    
- git add - __Agregamos__ archivos modificados y nuevos (sin seguimiento) al directorio actual y sus subdirectorios al staging area (el index) ademas de prepararlo para ser incluidos en el proximo commit
    > git add nombre_de_archivo

     *zsh
    > ga

- git clone - Para clonar un repositorio
    > git clone https://github.com/tu_nombre_de_usuario/tu_repositorio


- git commit - Agrega los cambios hechos de manera local al repositorio local
    > git commit -m "Primer commit"

     *zsh
    > gcmsg

- git status - Muestra la lista de archivos que se han modificado, junto con los que seran añadidos o estan comprometidos
    > git status 

    *zsh
    > gst

- git push - Envía los cambios que se han hecho en la rama principal al remoto que está asociado con el directorio que estamos trabajando
    > git push  origin master

    *zsh
    > ggpush

- git checkout - Se puede usar para crear ramas o cambiar entre ellas

    - Crear la rama 
        > git checkout -b <nombre-de-rama>
        > gcb * 
  
    - Cambiar de rama
        > gco <nombre-de-rama>
        > gcm - lleva a rama master

- git remote - Conectar a un repositorio remoto
    > git remote -v

- git branch - Se usa para listar, crear o borrar ramas
    > git branch
    - Borrarla
        > git branch -d <nombre-de-rama>

    > gb

- git pull - Para poder fusionar todos los cambios que se han hecho en el repositorio local
    > git pull origin <nombre-de-rama>

    > ggl

- git merge  - Fusiona una rama con otra rama activa
    > git merge <nombre-de-rama>

- git diff - Permite ver las diferencias o hacer una lista de conflictos
    > git diff --base <nombre-de-archivo>
    
    - Para ver los conflictos que hay entre ramas que están por ser fusionadas 
    > git diff <source-branch> <target-branch>
    
    - Para solo ver una lista de todos los conflictos presentes usa:
    > git diff
    
    > gd

- git log - Muestra la lista de commits de una rama
    > glo

- git stash - Ayuda a salvar cambios que no están por ser comprometidos inmediatamente
    > git stash

    > gstl






# Sass
[![N|Solid](https://imagebox.com/app/wp-content/uploads/2014/01/sass-logo.png)](https://git-scm.com/docs/git-help)


fuente:  [https://www.hostinger.com.ar/tutoriales/comandos-de-git](https://www.hostinger.com.ar/tutoriales/comandos-de-git)