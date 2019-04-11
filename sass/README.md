# Sass

#### Índice
- [Comandos útiles](#comandos-útiles)
- [Características](#que-lo-hace-tan-útil)
- [Cómo trabajaremos](#cómo-trabajaremos)

#### Sass (Syntactically Awesome StyleSheets)
Es una extensión de CSS que le añade poder y elegancia al lenguaje.

Es comúnmente llamado un pre-procesador de CSS. Ayuda a mantener grandes hojas de estilos de una manera organizada, permitiendo usar variables, reglas anidadas, mixins, importaciones, entre otros. Es compatible con la sintaxis de CSS.

##### Un sistema sencillo

 Hoy en día sencillo comenzar a usar Sass, una de las características más importantes de este lenguaje es que lo que veremos en adelante es opcional. En Sass, a diferencia de otros pre-procesadores, podemos escribir CSS tradicional sin problemas. Como se compila a CSS tradicional no es necesario instalar nada extra en tu servidor.


Para instalarlo en ruby seguir el siguiente [tutorial](https://medium.com/@alanmaciel/c%C3%B3mo-agregar-bootstrap-a-tu-rails-app-6c4ae91ceff9)


# Que lo hace tan útil

- [Variables](#variables)
- [Anidamientos](#anidamientos)
- [Imports](#imports)
- [Mixins](#mixins)
- [Estructuras de control](#estructuras-de-control)
- [Funciones](#funciones)


# Variables
Son pequeñas piezas de información almacenadas con un identificador, que podemos reutilizar a lo largo de nuestros proyectos, lo cual nos da mucha flexibilidad y facilidad para trabajar con colores, medidas, fuentes y otros detalles de manera consistente.

__cómo se definen__

> $nombre_variable: valor;


Las variables en Sass tienen los siguientes tipos:
1. cadenas, números y colores
    * Entiende al igual que css para colores.
    * __Operaciones__
        * Concatenado

        ```
        $cadena = 'valor';

        @if ($cadena == 'valor') {} //true

        // concatenar
        $cadena: 'hola';
        $cadena1: 'mundo'

        $cadena3: $cadena + cadena1;
        ```

        * Operaciones matemáticas, comparaciones. Se recomienda que las operaciones matemáticas vayan entre paréntesis.
        ```
        $numero1: 6em;
        $numero2: 2em;

        $resultado: ($numero1 / $numero2);

        ```

        __Ámbito de las variables__

        Son locales y solo están definidos en su selector. Para generar una variable global agrego el prefijo !global.

        > p { $font-size: 14px !global }


2. __listas__
    * Espacios separados por comas. puedo usar @each para iterar sobre sus elementos.

        ```
        $lista: facebook, twitter, instagram;

        @each $item in $lista {
            .icon-#{$item} {
                background-image: url('../../images/#{$item}.png');
                background-size: 10%;
                content: "{$item}";
                width:30px;

            }
        }
        ```
    * Puedo usarlas para interpolaciones, independiente de dónde utilizamos la variable Sass debe  compilar su contenido para mostrar el valor así puedo utilizar variables como nombres de propiedades e incluso sus selectores.

    ```
    $image: 'icon.png';

    p {
        background-image: url('#{$image}')
    }
    ```
3. __mapas__

  Los __mixins__ representan una de las __características más importantes de Sass__ y es por supuesto una de las más usadas por ser tan poderosa y conveniente, además de la gran cantidad de posibilidades que se pueden lograr usándolos.

  ```
  // variables.scss

  $colors : (
  background-color: #efefef,
  color-complement-4: #B9BE00, // Main Primary color */
  color-secondary-2-3: #F8FE00,
  color-secondary-1-4: #E0E600,
  color-primary-2: #939700
  );
  ```

  ```
  // custom.scss

  a {
      color:map-get($colors,color-complement-4);
      text-decoration: none;

      &:visited {
          color:map-get($colors,color-secondary-2-3);
      }
      &:hover {
          color:map-get($colors,color-secondary-1-4);
      }
      &:active {
          color:map-get($colors,color-primary-2);
      }
  }

  ```



4. __valores booleanos__
    * Condicionales: true o false
    ```
        $va1: 1; // trueQue lo hace tan
        $foo: 0; // true
        $boo: '';// true
        $baz: 'cadena' //true
        $joe: true; //true

        $var: null; //false
        $foo: false; //false

    ```
5. __null__
    * Declaro una variable pero no le asigno un valor, para no correr el peligro de reasignar un valor a una variable que ha sido asignada anteriormente uso !default

    > $var: null //nada

    > $var: 6 !default (devuelve la definición original si es diferente de null)


# Anidamientos
Anido selectores para **evitar repetición de código**. Nos permite escribir menos, y crear código más conciso y mejor estructurado, haciéndolo más fácil de entender y dejándolo mejor organizado. También nos **ahorra  tiempo al trabajar en proyectos grandes** donde debemos escribir estilos para muchos componentes distintos.

* Notas
    * No es conveniente anidar mas de 3 niveles. Dos niveles es lo recomendado.
    * Siempre usaremos clases o etiquetas para selectores muy generales, no es recomendado usar ids o atributos.
    * Mantener buen indentado (óptimo 4 espacios), ayuda a visualizar mejor también poner cada selector y cada propiedad en una línea separada.

* Referirse al achivo _ _header.scss_ para ver cambios.


# Imports
Sirven para concatener de manera sencilla varios archivos en un solo .css , es como agregar otra etiqueta link sobre HTML, la diferencia está en que se hace directamente sobre el archivo .css. __Las variables, mixins y funciones definidas en un archivo importado, estarán disponibles en el archivo que las importa.__

- Acepta varios formatos.
    - Podemos referenciar directamente
        > @import '/archivo.css';

    - También podemos utilizar url y podemos agregar media queries
        > @import url(archivo.css) screen and (min-width:800px) ;

    - Puedo importar solo por nombre de archivo, se importará en el lugar donde hicimos el import.
        > @import 'layout'


# Partials
Podemos crear archivos parciales que contengan pequeños trozos de código para incluir en otro archivo Sass.     
Es una gran manera de modularizar nuestros CSS y mantener las cosas de manera fácil, un archivo __parcial__ es simplemente un archivo con guión bajo por delante, por ejemplo __\_partial.scss__.    
El guión bajo le permite saber a Sass que este archivo es parcial y que no debe generar un CSS, los parciales en Sass se usan con la directiva __@import__


# Mixins
  Sirven para crear bloques de código que aceptan argumentos y que se pueden incluir en cualquier parte de mi hoja de estilos.


  Esta directiva permite __definir__ snippets o __bloques de código__ que podemos __reusar__ en cualquier parte de un documento de Sass. Estos bloques de código pueden contener cualquier número de propiedades con sus valores, selectores, puede también contener estructuras de control, y además pueden aceptar argumentos que cambian su resultado brindándonos mucha flexibilidad para crear partes de código reusable.

  ```
  @mixin nombre {
    //contenido
    propiedad: valor;
  }

  @mixin box {
    padding: 10px;
    background-color: $color1;
  }
  ```

  No se concatena por si solo así que debemos hacer uso de la directiva  _@include box;_ dentro del selector.

  ```
  .box {
    @include box;

  }
  ```
  Podemos pasarles argumentos,

  ```
  @mixin nombre($arg, $foo, $bar) {
      propiedad: $arg;
      otra-propiedad: $foo;
      otra-mas: $bar;
  }
  ```
  Y en el código que lo carga invocarlo

  ```
  .selector {
    // Otras propiedades y valores...
    @include mixin; // mixin sencillo
    @include mixin($arg, $foo, $bar); // mixin con argumentos
  }
  ```

  Podemos agregar __argumentos opcionales__ y con __valores por defecto__ indicando su valor directamente o usando la variable null.

  ```
  @mixin nombre($arg: null, $foo: 20px) {
    propiedad: $arg; // Si no se le pasa un valor, Sass elimina esta linea
    otra-propiedad: $foo; // Si no le pasamos nada: 20px
  }
  ```
  La directiva __@content__ nos permite tener piezas de código  completas dentro de los mismos, por ejemplo en media queries:

 ```
  @mixin min-width($width) {
      @media (mix-width: $width) {
          @content;
      }
  }

  @include min-width(1024px) {
      .selector {
          propiedad: valor;
          // etc
      }
  }

  // Se compila a
  @media (min-width: 1024px) {
      .selector {
          propiedad: valor;
          // etc
      }
  }
  ```
# Estructuras de control

Una condición es una expresión que al ser evaluada devolverá verdadero o falso.

```
$var: 2;
@if $var == 2 {
    .sel {
        propiedad: 2;
    }
} @else if $var == 1 {
    .sel {
        propiedad: 1;
    }
} @else {
    .sel {
        propiedad: 0;
    }
}
```

__Ciclos__ nos permiten iterar sobre una lista de elementos.

```
$redes: (facebook, #3b5998), (twitter, #00aced), (gplus, #dd4b39);

@each $red, $color in $redes {
    .btn-#{$red} {
        background: {
            color: $color;
            image: url('../img/icon-#{$red}.png');
        }
    }
}
```

__For__ itera la cantidad de veces que le decimos.
```
    @for $i from 1 through 12 {
        .col#{$i} {
            margin: 0 10px;
            width: (60px * $i);
        }
    }
```

__While__, itera indefinidamente finaliza cuando llega a false.
```
$e : 1;

@while $e < 12 {
    .pre#{$e} {
       margin-left: (60px * $e) + (20px * $e);
   }
   $e: $e + 1;
}

```



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
Fuentes

  1. [Libro de Sass](https://uniwebsidad.com/libros/sass/capitulo-1)

Herramientas

  * [Generador de combinaciones de colores](https://coolors.co/app)
  * [Pigments para Atom, preview de colores](pigments)
