## Helpers 

#### Configurar Oh My ZSH!

Zsh es una terminal interactiva que nos permite trabajar de manera mas eficiente en la consola.

Oh My ZSH es un framework desarrollado por la comunidad para gestionar la configuraci�n de ZSH.
Es muy util porque sugiere rutas si le das al tabulador y se puede interactuar con las opciones que te da y sobre todo por su integraci�n con Git.

#### Instalaci�n
****
> sudo apt-get install zsh

Instalar Oh my ZSH!

> sh -c "$(wget https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"

#### Customizar

Podemos agregar un tema, el agnoster, vamos al repositorio oficial y seguimos la [gu�a de instalaci�n de temas](https://github.com/robbyrussell/oh-my-zsh/wiki/Themes) 


1.  Chequear compatibilidad (debe mostrar iconos, si no se ven ir a paso 2)
   > echo "\ue0b0 \u00b1 \ue0a0 \u27a6 \u2718 \u26a1 \u2699"

2. Tengo las fuentes parcheadas? 
   ``` 
   Preferencias de la terminal
   __perfiles__ guardar un nuevo perfil
   En __Command__ ir a la opci�n "correr el comando en lugar de mi shell"
   Custom command: zsh

   En Colores seleccionar "Solarized Dark"
   En Fuentes elegir "Meslo" (si no aparece ir al paso 3)
   En Tama�o 14 pt
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

4. Probamos si est�n configuradas las tipograf�as
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

Zsh se puede ampliar f�cilmente utilizando extensiones. Al igual que con los temas por defecto oh-my-zsh incluye muchas extensiones, que se encuentran en el directorio ~/.oh-my-zsh/plugins. Antes de activar una extensi�n es buena idea mirar en su directorio para ver qu� es lo que hace. Veremos la extensi�n para Bundler, que tiene un fichero _bundler. Si una extensi�n dispone de un fichero que comienza con un gui�n bajo quiere decir que a�ade funcionalidad de __autocompletado__ a una orden. La extensi�n hace tambi�n otras cosas, por ejemplo a�ade varios alias de las �rdenes m�s frecuentes en Bundler y tambi�n hace que varias �rdenes relacionadas con Rails se lancen con bundle exect para no tener que teclearlo cada vez que queramos ejecutarlas.

Hay otras extensiones que pueden ser �tiles. La extensi�n brew a�ade autocompletado, al igual que la extensi�n gem. Otras son menos �tiles, como las extensiones rails3 y ruby que simplemente a�aden algunos alias. Para activar estas extensiones tenemos que incluirlas en la opci�n plugins del fichero .zshrc de la siguiente manera:

```
    # ~/.zshrc

    plugins=(git bundler brew gem)
```

Zsh-autosuggestions: Sirve para completar comandos, sugiere basado en nuestra lista de comandos. Para seleccionar el comando propuesto presionamos la flecha derecha.

### Instalaci�n
1. Clonar el repositorio, todo ir� a parar a ~/.zsh/zsh-autosuggestions.
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

[Instalaci�n video tutorial](https://www.youtube.com/watch?v=0SwiLFPqWLg)

[Agregar plugins](https://medium.com/wearetheledger/oh-my-zsh-made-for-cli-lovers-installation-guide-3131ca5491fb)

[https://github.com/robbyrussell/oh-my-zsh/tree/master/plugins/rails](https://github.com/robbyrussell/oh-my-zsh/tree/master/plugins/rails)


[Instrucciones de instalaci�n](http://railscasts.com/episodes/308-oh-my-zsh?language=es&view=asciicast)

