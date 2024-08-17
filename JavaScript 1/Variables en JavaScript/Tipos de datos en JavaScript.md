# Tipos de Datos
###### Number
Almacena Valores Numéricos

*Ejemplo:*
```js
10,-40,3.9,-15.66, etc;

let miEntero = 10;
let miFlotante = 7.9;
```

###### String 
Almacena codenas de caracteres 
*Ejemplo:*

```js
"hola" ,'adios', `saludos`

let miCadena ="hola";
let miCadena ='adios';
let micadena = `saludos`;
```

###### Boolean 
Almacena un valor lógico
*Ejemplo:*

```js
true o false;

let miBoolean = true;
let miBoolean = false;

```

###### Null
Ausencia de la referencia de un objeto
 *Ejemplo:*
```js
null;

let miNull = null;

```

###### Undefined
Ausencia de valor
 *Ejemplo:*
```js
undefined;

let miUndefined = undefined;

```

# Typeof
`typeof` es un operador en varios lenguajes de programación que se utiliza para obtener el tipo de un valor o una variable en tiempo de ejecución. En JavaScript, por ejemplo, el operador `typeof` devuelve una cadena que indica el tipo del operando.

### Uso en JavaScript:

En JavaScript, `typeof` se utiliza de la siguiente manera:
```js
let miEntero = 10;
console.log(typeof miEntero);       // "number"

let miCadena ="hola";
console.log(typeof miCadena);       // "string"

let miBoolean = true;
console.log(typeof miBoolean);      // "boolean"

let miNull = null;
console.log(typeof miNull);         // "object" 

let miUndefined = undefined;
console.log(typeof miUndefined);    // "undefined" 

```
### Consideraciones:

- En JavaScript, `typeof` es muy útil para verificar el tipo de una variable antes de realizar operaciones sobre ella, evitando errores en tiempo de ejecución.
- El valor `null` en JavaScript es un caso especial y `typeof miNull` devuelve `"object"`. Esto es considerado un error de diseño en el lenguaje pero se mantiene por compatibilidad con versiones anteriores.

