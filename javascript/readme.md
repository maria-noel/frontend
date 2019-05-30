# Javascript


Usando Javascript en Rails
[https://guias.makeitreal.camp/ruby-on-rails-ii/usando-javascript-y-jquery-en-rails](https://guias.makeitreal.camp/ruby-on-rails-ii/usando-javascript-y-jquery-en-rails)


 [tutorial](https://developer.mozilla.org/es/docs/Learn/JavaScript/First_steps/Qu%C3%A9_es_JavaScript)


![capas de la tecnologia web](https://mdn.mozillademos.org/files/13502/cake.png?raw=true "Title")

# INTRODUCIÓN A JAVASCRIPT

Es un lenguaje de programación que te permite crear contenido nuevo y dinámico, controlar archivos de multimedia, crear imágenes animadas y muchas otras cosas más. (Aunque, no todo, pero es increíble lo que puedes llegar a hacer con tan sólo unas pocas líneas de código de JavaScript). 

### Tipos de datos

Son las clasificaciones que le damos a los diferentes tipos de datos que usamos en programación. En JavaScript existen 7 tipos fundamentales. 

_Number_: numéricos, cualquier numero : 4, 8, 1516, 23.42.

_String_: Cualquier grupo de caracteres en tu teclado (letras, números, espacios, símbolos, etc.) los vamos a rodear con comillas simples o dobles.

_Boolean_: Estos tipos de datos tiene solo dos valores posibles, verdadero o falso (sin comillas). 

_Null_: Este tipo de dato representa la ausencia de un valor, usa la palabra null (sin comillas).

_Undefined_: Este tipo de dato esta definido por la palabra undefined. Representa la ausencia de valor aunque tiene un uso diferente a null.

_Symbol_: Una nueva característica del lenguaje, los símbolos son identificadores únicos usados en código mas complejo.

_Object_: Colecciones de data relacionados.


Los primeros 6 son considerados primitivos. Son los tipos de datos mas básicos, los objetos pueden ser mas complejos. 


#### Debugeando

Con console.log podemos debugear e incluso probar el código en el modo consola del navegador.

```
    console.log('Location of Codecademy headquarters: 575 Broadway, New York City');
    console.log(40);
```

### Variables

Se definen con _var_, _let_ y _const_
Podemos definirlas sin valor predeterminado
> let price; 
> var price;

_var_ se uso hasta la nueva versión de ES6

_let_ se introdujo con la nueva versión, es un nuevo formato 

```
let meal = 'Enchiladas';

let nombre = 'María';

let edad = 39;

```

_const_ Se introdujo en ES6, representa a las constantes. No puede cambiar su valor en el tiempo de ejecución.


### Operadores matemáticos
```
let w = 4;
w = w + 1;

console.log(w); // Output: 5
```
#### Operadores de incremento y decremento
```
let a = 10;
a++;
console.log(a); // Output: 11


let b = 20;
b--;
console.log(b); // Output: 19

```
#### Concatenado con variables
```
let myPet = 'armadillo';
console.log('I own a pet ' + myPet + '.'); 
// Output: 'I own a pet armadillo.'
```

#### Interpolación con strings
En IE6 podemos insertar o interpolar variables en strings usando literales.

```
const myPet = 'armadillo';
console.log(`I own a pet ${myPet}.`);
// Output: I own a pet armadillo.
```
Recordar que debemos usar las comillas invertidas para interpolar
> `${myPet}`



#### Prompt

Se usa para obtener datos de les usuaries.

> var nombre = prompt("Cual es tu nombre?");
> console.log(nombre);

#### Funciones, también conocidas como métodos

Evitan tener código duplicado y su reutilización.

```
    function promptData() 
    {
        console.log('hola');
        console.log('y');
        console.log('adiós');
    }

    // necesito llamarla
    promptData();

    function suma(num1, num2) {
        return num1 + num2;
    }
    suma(2,3);
```


#### Operadores aritméticos

```
    // Sumas
    console.log(4+8)

    // Restas
    console.log(8-4);

    // Multiplicación
    console.log(2*4);

    // División
    console.log(10/2);

    // Módulo -- revuelve el resto
    console.log(9%2);

    // Incremento
    var num = 10;
    num++; // simular a hacer num = num + 1;
    console.log(num);

    // según la posición será el valor 
    console.log(--num);

    // Decremento
    var num = 10;
    num--; // similar a hacer num = num - 1;
    console.log(num);

    
```







 


