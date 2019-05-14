## Helpers 

#### Configurar Oh My ZSH!

Zsh es una terminal interactiva que nos permite trabajar de manera mas eficiente en la consola.

Oh My ZSH es un framework desarrollado por la comunidad para gestionar la configuración de ZSH.
Es muy util porque sugiere rutas si le das al tabulador y se puede interactuar con las opciones que te da y sobre todo por su integración con Git.

#### Instalación

> sudo apt-get install zsh

Instalar Oh my ZSH!

> sh -c "$(wget https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"

#### Cus
tomizar

Podemos agregar un tema, el agnoster, vamos al repositorio oficial y seguimos la [guia de instalación de temas](https://github.com/robbyrussell/oh-my-zsh/wiki/Themes) 


1.  Chequear compatibilidad (debe mostrar iconos, si no se ven ir a paso 2)
   > echo "\ue0b0 \u00b1 \ue0a0 \u27a6 \u2718 \u26a1 \u2699"

2. Tengo las fuentes parcheadas? 
   ``` 
   Preferencias de la terminal
   __perfiles__ guardar un nuevo perfil
   En __Command__ ir a la opcion "correr el comando en lugar de mi shell"
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

4. Probamos si estn configuradas las tipografas
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



##### fuentes:
[Oh_my_ZSH](https://ohmyz.sh/)

[Atajos](https://github.com/robbyrussell/oh-my-zsh/wiki/Cheatsheet)

[Instalar oh my ZSH en Ubuntu](https://geekytheory.com/como-instalar-oh-my-zsh-en-ubuntu)

[Instalación video tutorial](https://www.youtube.com/watch?v=0SwiLFPqWLg)