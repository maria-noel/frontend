# Javascript


Usando Javascript en Rails
[https://guias.makeitreal.camp/ruby-on-rails-ii/usando-javascript-y-jquery-en-rails](https://guias.makeitreal.camp/ruby-on-rails-ii/usando-javascript-y-jquery-en-rails)


 [tutorial](https://developer.mozilla.org/es/docs/Learn/JavaScript/First_steps/Qu%C3%A9_es_JavaScript)


![capas de la tecnologia web](https://mdn.mozillademos.org/files/13502/cake.png?raw=true "Title")

# INTRODUCI�N A JAVASCRIPT

Es un lenguaje de programaci�n que te permite crear contenido nuevo y din�mico, controlar archivos de multimedia, crear im�genes animadas y muchas otras cosas m�s. (Aunque, no todo, pero es incre�ble lo que puedes llegar a hacer con tan s�lo unas pocas l�neas de c�digo de JavaScript). 

### Tipos de datos

Son las clasificaciones que le damos a los diferentes tipos de datos que usamos en programaci�n. En JavaScript existen 7 tipos fundamentales. 

_Number_: num�ricos, cualquier numero : 4, 8, 1516, 23.42.

_String_: Cualquier grupo de caracteres en tu teclado (letras, n�meros, espacios, s�mbolos, etc.) los vamos a rodear con comillas simples o dobles.

_Boolean_: Estos tipos de datos tiene solo dos valores posibles, verdadero o falso (sin comillas). 

_Null_: Este tipo de dato representa la ausencia de un valor, usa la palabra null (sin comillas).

_Undefined_: Este tipo de dato esta definido por la palabra undefined. Representa la ausencia de valor aunque tiene un uso diferente a null.

_Symbol_: Una nueva caracter�stica del lenguaje, los s�mbolos son identificadores �nicos usados en c�digo mas complejo.

_Object_: Colecciones de data relacionados.


Los primeros 6 son considerados primitivos. Son los tipos de datos mas b�sicos, los objetos pueden ser mas complejos. 


#### Debugeando

Con console.log podemos debugear e incluso probar el c�digo en el modo consola del navegador.

```
    console.log('Location of Codecademy headquarters: 575 Broadway, New York City');
    console.log(40);
```

### Variables

Se definen con _var_, _let_ y _const_
Podemos definirlas sin valor predeterminado
> let price; 
> var price;

_var_ se uso hasta la nueva versi�n de ES6

_let_ se introdujo con la nueva versi�n, es un nuevo formato 

```
let meal = 'Enchiladas';

let nombre = 'Mar�a';

let edad = 39;

```

_const_ Se introdujo en ES6, representa a las constantes. No puede cambiar su valor en el tiempo de ejecuci�n.


### Operadores matem�ticos
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

#### Interpolaci�n con strings
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

#### Funciones, tambi�n conocidas como m�todos

Evitan tener c�digo duplicado y su reutilizaci�n.

```
    function promptData() 
    {
        console.log('hola');
        console.log('y');
        console.log('adi�s');
    }

    // necesito llamarla
    promptData();

    function suma(num1, num2) {
        return num1 + num2;
    }
    suma(2,3);
```


#### Operadores aritm�ticos

```
    // Sumas
    console.log(4+8)

    // Restas
    console.log(8-4);

    // Multiplicaci�n
    console.log(2*4);

    // Divisi�n
    console.log(10/2);

    // M�dulo -- revuelve el resto
    console.log(9%2);

    // Incremento
    var num = 10;
    num++; // simular a hacer num = num + 1;
    console.log(num);

    // seg�n la posici�n ser� el valor 
    console.log(--num);

    // Decremento
    var num = 10;
    num--; // similar a hacer num = num - 1;
    console.log(num);

    
```







 


