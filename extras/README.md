## Helpers 

#### Configurar Oh My ZSH!

Zsh es una terminal interactiva que nos permite trabajar de manera mas eficiente en la consola.

Oh My ZSH es un framework desarrollado por la comunidad para gestionar la configuración de ZSH.
Es muy util porque sugiere rutas si le das al tabulador y se puede interactuar con las opciones que te da y sobre todo por su integración con Git.

#### Instalación
****
> sudo apt-get install zsh

Instalar Oh my ZSH!

> sh -c "$(wget https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"

#### Customizar

Podemos agregar un tema, el agnoster, vamos al repositorio oficial y seguimos la [guí­a de instalación de temas](https://github.com/robbyrussell/oh-my-zsh/wiki/Themes) 


1.  Chequear compatibilidad (debe mostrar iconos, si no se ven ir a paso 2)
   > echo "\ue0b0 \u00b1 \ue0a0 \u27a6 \u2718 \u26a1 \u2699"

2. Tengo las fuentes parcheadas? 
   ``` 
   Preferencias de la terminal
   __perfiles__ guardar un nuevo perfil
   En __Command__ ir a la opción "correr el comando en lugar de mi shell"
   Custom command: zsh

   En Colores seleccionar "Solarized Dark"
   En Fuentes elegir "Meslo" (si no aparece ir al paso 3)
   En Tamaño 14 pt
   ```
3. Instalar powerline fonts (fuentes parcheadas)

    ``` 
    # clone
    git clone https://github.com/powerline/fonts.git --depth=1
    # install
    cd fonts
    ./install.sh
    # clean-up a bit
    cd ..
    rm -rf fonts
    ``` 

4. Probamos si están configuradas las tipografí­as
   > echo "\ue0b0 \u00b1 \ue0a0 \u27a6 \u2718 \u26a1 \u2699"

5. Modificar el usuario por defecto para remover el "user@hostname"
   ``` 
   vi ~/.zshrc

   ZSH_THEME="agnoster"
    ```
6. Reiniciar la consola

Si queremos eliminar el domain name:

```
prompt_context() {
    if [[ "$USER" != "$DEFAULT_USER" || -n "$SSH_CLIENT" ]]; then
        prompt_segment black default "%(!.%{%F{yellow}%}.)$USER"
    fi
}
```

# Extendiendo

Zsh se puede ampliar fácilmente utilizando extensiones. Al igual que con los temas por defecto oh-my-zsh incluye muchas extensiones, que se encuentran en el directorio ~/.oh-my-zsh/plugins. Antes de activar una extensión es buena idea mirar en su directorio para ver qué es lo que hace. Veremos la extensión para Bundler, que tiene un fichero _bundler. Si una extensión dispone de un fichero que comienza con un guión bajo quiere decir que añade funcionalidad de __autocompletado__ a una orden. La extensión hace también otras cosas, por ejemplo añade varios alias de las órdenes más frecuentes en Bundler y también hace que varias órdenes relacionadas con Rails se lancen con bundle exect para no tener que teclearlo cada vez que queramos ejecutarlas.

Hay otras extensiones que pueden ser útiles. La extensión brew añade autocompletado, al igual que la extensión gem. Otras son menos útiles, como las extensiones rails3 y ruby que simplemente añaden algunos alias. Para activar estas extensiones tenemos que incluirlas en la opción plugins del fichero .zshrc de la siguiente manera:

```
    # ~/.zshrc

    plugins=(git bundler brew gem)
```

Zsh-autosuggestions: Sirve para completar comandos, sugiere basado en nuestra lista de comandos. Para seleccionar el comando propuesto presionamos la flecha derecha.

### Instalación
1. Clonar el repositorio, todo irá a parar a ~/.zsh/zsh-autosuggestions.
    > git clone https://github.com/zsh-users/zsh-autosuggestions ~/.zsh/zsh-autosuggestions
2. Agregar lo siguiente a .zshrc
    > source ~/.zsh/zsh-autosuggestions/zsh-autosuggestions.zsh
3. Empezar una nueva terminal

#### Si no funciona 

Clonar en $ZSH_CUSTOM/plugins (by default ~/.oh-my-zsh/custom/plugins)

	> git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

Add the plugin to the list of plugins for Oh My Zsh to load (inside ~/.zshrc):

	> plugins=(zsh-autosuggestions)

Abrir otra consola


##### fuentes:
[Oh_my_ZSH](https://ohmyz.sh/)

[Atajos](https://github.com/robbyrussell/oh-my-zsh/wiki/Cheatsheet)

[Instalar oh my ZSH en Ubuntu](https://geekytheory.com/como-instalar-oh-my-zsh-en-ubuntu)

[Instalación video tutorial](https://www.youtube.com/watch?v=0SwiLFPqWLg)

[Agregar plugins](https://medium.com/wearetheledger/oh-my-zsh-made-for-cli-lovers-installation-guide-3131ca5491fb)

[https://github.com/robbyrussell/oh-my-zsh/tree/master/plugins/rails](https://github.com/robbyrussell/oh-my-zsh/tree/master/plugins/rails)


[Instrucciones de instalación](http://railscasts.com/episodes/308-oh-my-zsh?language=es&view=asciicast)

