# Javascript


Usando Javascript en Rails
[https://guias.makeitreal.camp/ruby-on-rails-ii/usando-javascript-y-jquery-en-rails](https://guias.makeitreal.camp/ruby-on-rails-ii/usando-javascript-y-jquery-en-rails)


 [tutorial](https://developer.mozilla.org/es/docs/Learn/JavaScript/First_steps/Qu%C3%A9_es_JavaScript)


![capas de la tecnologia web](https://mdn.mozillademos.org/files/13502/cake.png?raw=true "Title")

# INTRODUCTION TO JAVASCRIPT

### Tipos de datos

Son las clasificaciones que le damos a los diferentes tipos de datos que usamos en programaci�n. En JavaScript existen 7 tipos fundamentales. 

_Number_: numericos, cualquier numero : 4, 8, 1516, 23.42.

_String_: Cualquier grupo de caracteres en tu teclado (letras, numeros, espacios, simbolos, etc.) los vamos a rodear con comillas simples o dobles.

_Boolean_: Estos tipos de datos tiene solo dos valores posibles, verdadero o falso (sin comillas). 

_Null_: Este tipo de dato representa la ausencia de un valor, usa la palabra null (sin comillas).

_Undefined_: Este tipo de dato esta definido por la palabra undefined. Representa la ausencia de valor aunque tiene un uso diferente a null.

_Symbol_: Una nueva caracteristica del lenguaje, los sÃ­mbolos son identificadores nicos usados en codigo mas complejo.

_Object_: Colecciones de data relacionados.


Los primeros 6 son considerados primitivos. Son los tipos de datos mas basicos, los objetos pueden ser mas complejos. 

```
    console.log('Location of Codecademy headquarters: 575 Broadway, New York City');
    console.log(40);
```

### Variables

Se definen con _var_, _let_ y _const_
Podemos definirlas sin valor predeterminado
> let price; 
> var price;

_var_ se uso hasta la nueva version de ES6

_let_ se introdujo con la nueva version

```
let meal = 'Enchiladas';
 
```

_const_ Se introdujo en ES6, representa a las constantes. No puede cambiar su valor en el tiempo de ejecucion.


### Operadores matematicos
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

#### Interpolacion con strings
En IE6 podemos insertar o interpolar variables en strings usando literales.

```
const myPet = 'armadillo';
console.log(`I own a pet ${myPet}.`);
// Output: I own a pet armadillo.
```
Recordar que debemos usar las comillas invertidas para interpolar
```
`
${myPet}

```


 


