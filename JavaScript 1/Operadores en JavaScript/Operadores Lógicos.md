# Operadores Lógicos

```js
let a = true;/*Declaramos la variable "a" y le asignamos
el valor de true*/
let b = false;/*Declaramos la variable "b" y le asignamos
el valor de false*/
console.log(a);//la variable "a" tiene el valor de "true"
console.log(b);//la variable "b" tiene el valor de "false"
```
****

####  `&&` (AND lógico)
Devuelve `true` si ambos operandos son `true`. Si uno de los operandos es `false`, devuelve `false`.
 *Ejemplo :*  `X && Y` 
######  <center>Tabla de verdad del operador AND</center>
|   X   | Operador |   Y   | Resultado |
| :---: | :------: | :---: | :-------: |
| true  |    &&    | true  | true      |
| true  |    &&    | false | false     |
| false |    &&    | true  | false     |
| false |    &&    | true  | false     |
```js
//operador logico AND
/*regresa true si ambos operandos son true de 
otro caso regresa false*/

console.log(`${a} && ${b} ->  ${a && b}`);

/*el termino "${a} && ${b} ->" es texto informativo para mostrar
los valores de las variables "a" y "b", ${a && b} es la ejecucion 
de la operacion en este caso la varibale "a" es igual a "true" 
y la varibale "b" es igual a "false" segun la tabla de valores
el resultado es "false" */
```
****

####  `||` (OR lógico)
Devuelve `true` si al menos uno de los operandos es `true`. Solo devuelve `false` si ambos operandos son `false`.
 *Ejemplo :*  `X || Y` 
 ######  <center>Tabla de verdad del operador OR</center>
|   X   | Operador |   Y   | Resultado |
| :---: | :------: | :---: | :-------: |
| true  |   \|\|   | true  |   true    |
| true  |   \|\|   | false |   true    |
| false |   \|\|   | true  |   true    |
| false |   \|\|   | false |   false   |
```js
//operador logico OR
/*regresa true si cualquiera de los operandos son true de otro
caso regresa false*/

console.log(`${a} || ${b} ->  ${a || b}`);

/*el termino "${a} && ${b} ->" es texto informativo para mostrar
los valores de las variables "a" y "b", ${a || b} es la ejecucion
de la operacion en este caso la varibale "a" es igual a "true"
y la varibale "b" es igual a "false" segun la tabla de valores
el resultado es "true" */
```
****

####  `!`(NOT lógico)
Invierte el valor lógico del operando. Si el operando es `true`, devuelve `false`, y viceversa.
 *Ejemplo :*  `!X` 
 
 ######  <center>Tabla del operador NOT</center>

| Operador | Valor | Resultado |
| :------: | :---: | :-------: |
|    !     | true  |   false   |
|    !     | false |   true    |
```js
//operador logico NOt
/*Invierte el valor original, true -> false, false -> true */

console.log(`${a}-> ${!a}`);

/*el termino "${a}->" es texto informativo para mostrar
el valor de las variable "a", ${!a} es la ejecucion
de la operacion en este caso la varibale "a" es igual a "true"
y al aplicar el operador logico NOt a nuestra variable "a"
segun la tabla el resultado es "false" */
```

> [!note] Comentario:
> El operador lógico `NOT` es un operador Unario ya que solo requiere un valor para poder trabajar correctamente, a diferencia de los operadores `AND` y `OR` que son binarios ya que estos requieren dos valores

****
[[Obsidian/JavaScript 1/Operadores en JavaScript/Ejemplo de operador lógicos]]