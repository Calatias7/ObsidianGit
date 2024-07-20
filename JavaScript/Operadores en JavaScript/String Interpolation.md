## String interpolation
La interpolación de cadenas es una característica de algunos lenguajes de programación que permite insertar el valor de variables o expresiones dentro de una cadena de texto. Esto hace que la creación de cadenas dinámicas sea más fácil y legible.

para generar una cadena en String interpolation se usa el backtick o acento invertido = ` `` `
si queremos imprimir el valor de una variable se usa el signo de dolar con llaves `${}`
*Ejemplo*
```js
let a = 5; //Declaramos la variable "a" y le asignamos el valor de 5
let b = `5`;//Declaramos la variable "b" y le asignamos un String "5"
console.log(a);//La variable "a" es igual a 5
console.log(b);//La variable "b" es igual a `5`
```
****

#### == Igual a
*Ejemplo:*
`x == y` 
```js
//Operador Igualdad ==
//Solo compara valores y hace una conversion si es necesario
console.log(`${a} == ${b} -> ${a == b}`); /* el termino ${a} == ${b}
hace que podamos observar el valor de nuestras variables
("a" y "b") formando asi nuesta cadena 

posteriormente comparamos usando la expresion ${a == b} de este modo 
el resultado nos muestra en una cadena junto con la comparacion
'5 == 5 -> true'. 
*/
```
> [!note] Comentario:
>recuerda que el operador == realiza una conversión al tipo de dato respectivo para comparar los valores por eso el resultado nos da `true` ya que cambia el tipo de dato en la variable `b`

****
####  === Igualdad exacto (se compara el tipo y dato)
*Ejemplo:*
`x === y` 
```js
console.log(`${a} === ${b} -> ${a === b}`); 
/*el termino ${a} === ${b} hace que podamos observar el valor de 
nuestras variables ("a" y "b") formando asi nuesta cadena

posteriormente comparamos usando la expresion ${a === b} de este modo
el resultado nos muestra una cadena

junto con la comparacion '5 === 5 -> false'.
*/
```
> [!note] Comentario:
>Recuerda que el operador === realiza una comparación y al ser diferentes tipos de datos en la variable `a` que es un `number` y la variable `b` que es un `String` nos da una desigualdad por lo tanto es `false`

****
#### `!=` Distinto a
*Ejemplo:*
`x != y` 
```js
console.log(`${a} != ${b} -> ${a !=b} `)/*el termino ${a} != ${b}
hace que podamos observar el valor de nuestras variables("a" y "b")
formando asi nuesta cadena, posteriormente evaluamos usando la
expresion ${a != b} de este modo el resultado nos muestra una cadena
junto con la comparacion '5 != 5 -> false'.
*/
```
> [!note] Comentario:
>Recuerda que el operador `!=` realiza una comparación entre los valores de las variables `a` que es un `Number` y `b` que es un `String` nos da el valor de `false` ya que convierte el tipo de dato de la variable `b` a `Number` por lo tanto son iguales y nos da el resultado de `false`.

****
#### `!==` Distinto exacto (se compara el tipo y dato)
*Ejemplo:*
`x !== y` 
```js
console.log(`${a} !== ${b} -> ${a !== b} `)/*el termino ${a} !== ${b}
hace que podamos observar el valor de nuestras variables("a" y "b")
formando asi nuesta cadena.

posteriormente evaluamos usando la expresion ${a != b} de este
modo el resultado nos muestra una cadena junto con la comparacion
'5 !== 5 -> true'.

*/
```
> [!note] Comentario:
>Recuerda que el operador `!==` realiza una comparación entre los valores de las variables "`a`" que es un `Number` y "`b`" que es un `String`nos da el valor de `true` ya que son distintas en el tipo de datos

****
#### `>` Mayor que 
*Ejemplo:*
`x > y` 
```js
console.log(`${a} > ${b} -> ${a < b}`);/*el termino "${a} > ${b} ->"
es texto informativo para preguntar si la variable "a" es mayor que
"b",posteriormente hacemos la operacion "${a > b}" y el resultado
es false
*/
```
> [!note] Comentario:
>Recordar que  el operador `>` realiza una comparación de los datos de la variable `a` que es `5`  y `b` que es  ` "5" ` son iguales en el valor por lo tanto nos da `false`

****
#### `>=` Mayor o igual que
*Ejemplo:*
`x >= y`
```js
console.log(`${a} >= ${b} -> ${a >= b}`);
/*el termino "${a} >= ${b} ->"es texto informativo para preguntar
si la variable "a" es mayor o igual que "b",posteriormente hacemos
la operacion "${a >= b}" y el resultado es true
*/
```
> [!note] Comentario:
>Recordar  que el operador  `>=` realiza una comparación de los datos de la variable `a` que es `5` y `b` que es `"5"` no son mayores pero si son iguales en el valor por lo tanto nos da `true`
<!--SR:!2024-07-22,3,250-->


****
#### `<` Menor que 
*Ejemplo:*
`x < y` 
```js
console.log(`${a} < ${b} -> ${a < b}`);/*el termino "${a} < ${b} ->"
es texto informativo para preguntar si la variable "a" es menor que
"b",posteriormente hacemos la operacion "${a < b}" y el resultado
es false
*/
```
> [!note] Comentario:
>Recordar que  el operador `<` realiza una comparación de los datos de la variable `a` que es `5`  y `b` que es  ` "5" ` son iguales en el valor por lo tanto nos da `false`

****
#### `<=` Menor o igual que 
*Ejemplo:*
`x <= y` 
```js
console.log(`${a} <= ${b} -> ${a <= b}`);
/*el termino "${a} <= ${b} ->"es texto informativo para preguntar
si la variable "a" es menor o igual que "b",posteriormente hacemos
la operacion "${a <= b}" y el resultado es true
*/
```
> [!note] Comentario:
> Recordar  que el operador  `<=` realiza una comparación de los datos de la variable `a` que es `5` y `b` que es `"5"` no son menores pero si son iguales en el valor por lo tanto nos da `true`

****

  