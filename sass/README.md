# Sass
***
#### Índice
- [Comandos útiles](#comandos-útiles)
- [Características](#que-lo-hace-tan-util)
- [Cómo trabajaremos](#como-trabajaremos)

#### Sass (Syntactically Awesome StyleSheets)
Es una extensión de CSS que le añade poder y elegancia al lenguaje.

Es comúnmente llamado un pre-procesador de CSS. Ayuda a mantener grandes hojas de estilos de una manera organizada, permitiendo usar variables, reglas anidadas, mixins, importaciones, entre otros. Es compatible con la sintaxis de CSS.

##### Un sistema sencillo

 Hoy en día sencillo comenzar a usar Sass, una de las características más importantes de este lenguaje es que lo que veremos en adelante es opcional. En Sass, a diferencia de otros pre-procesadores, podemos escribir CSS tradicional sin problemas. Como se compila a CSS tradicional no es necesario instalar nada extra en tu servidor.


Para instalarlo en ruby seguir el siguiente [tutorial](https://medium.com/@alanmaciel/c%C3%B3mo-agregar-bootstrap-a-tu-rails-app-6c4ae91ceff9)


#### Que lo hace tan útil

- [Variables](#variables)
- [Anidamientos](#anidamiento)
- [Imports](#imports)
- [Mixins](#mixins)
- [Estructuras de control](#estructuras-de-control)
- [Funciones](#funciones)


# Variables
Asigno valores reusables a lo largo de los archivos.


# Anidamientos
Anido selectores para evitar repetición de código.


# Imports
Sirven para concatener de manera sencilla varios archivos en un solo .css , es como agregar otra etiqueta link sobre HTML, la diferencia está en que se hace directamente sobre el archivo .css

- Acepta varios formatos.
    - Podemos referenciar directamente
        > @import '/archivo.css';

    - También podemos utilizar url y podemos agregar media queries
        > @import url(archivo.css) screen and (min-width:800px) ;

    - Puedo importar solo por nombre de archivo, se importará en el lugar donde hicimos el import. Las variables, mixins y funciones definidas en un archivo importado, estarán disponibles en el archivo que las importa.
        > @import 'layout'


# Mixins
Sirven para crear bloques de código que aceptan argumentos y que se pueden incluir en cualquier parte de mi hoja de estilos.


# Estructuras de control
Puedo crear condicionales, ciclos y mas.


# Funciones
Puedo realizar diferentes tipos de operaciones y evitar utilizar código adicional.

***
# Cómo trabajaremos
La idea es que tengamos una carpeta para las hojas de estilos y otra para sass y otra para la salida del código.
```
mkdir stylesheets && cd stylesheets && mkdir scss && mkdir css
touch scss/main.scss && touch css/main.css
```

# Comandos útiles
Para __compilarlo__
```
cd stylesheets
sass input.scss:output.CSS
```
Para __seguimiento en vivo__
```
cd stylesheets
sass --watch scss:css
```

# Opciones del compilador (Flags)
Para __seguimiento en vivo__
```
cd stylesheets
sass --watch scss:css
```
- __style__ cómo debe compilar el archivo. Tiene 3 opciones


1. **Nested**: Es la opción por defecto, es bueno si queremos revisar nuestro código.
> sass --style nested scss/style.scss:css/style.css

2. **Expanded**: Muestra el código expandido, las llaves de cierre están en su propia línea, se mantienen los comentarios. Es bueno para ver cómo la salida está formateada.
> sass --style expanded scss/style.scss:css/style.css

3. **Compact**:  Cada selector y sus propiedades están en una sola línea.
> sass --style compact scss/style.scss:css/style.css

4. **Compressed**: Se usa en producción, entrega un archivo minified. Salva tiempo de parseo y tamaño, no está hecha para ser leída por humanos.
> sass --style compressed scss/style.scss:css/style.css


- __Comentarios__

    > // Este es un comentario de una línea que no se compilará

- __Source Maps__
    * Mapa del código Sass que apunta a los archivos fuente.
    * Podemos controlarlo desde el flag __sourcemap__ el valor necesita el símbolo de igual, tiene 3 valores:
        * auto,
        * inline (genera el source map en el mismo archivo css) y
        * none (no genera el source map)
***
