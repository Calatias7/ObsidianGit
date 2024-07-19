```js
let a = 5; //Declaramos la variable "a" y le asignamos el valor de 5
let b = `5`;//Declaramos la variable "b" y le asignamos un String "5"
console.log(a);//La variable "a" es igual a 5
console.log(b);//La variable "b" es igual a `5`
```

####  `(==)`Igual a
*Ejemplo:*
`x == y` 
```js

//Operador Igualdad ==
//Solo compara valores y hace una conversion si es necesario
console.log("a == b ->", a == b);/*el termino "a==b ->" es texto informativo para preguntar si la variable "a" es igual a "b",
posteriormente hacemos la comparacion a == b y el resultado es true

ya que el operador == realiza una conversion al tipo de dato respectivo para comparar los valores
*/
```
****

####  `(===)`Igualdad exacto (se compara el tipo y dato)
*Ejemplo:*
`x === y` 
```js
//Operador Igualdad Estricta o Exacto ===
//Se compara el valor y el tipo de dato
console.log("a===b ->", a === b);/*el termino "a===b ->" es texto informativo para preguntar si la variable "a" es igual a "b",
posteriormente hacemos la comparacion y el resultado es false

ya que el operador "===" realiza una comparacion y al ser diferentes tipos de datos en la variable "a" que es un number 
y la variable "b" que es un String nos da una desigualdad por lo tanto es false
*/
```
****

#### `!=` Distinto a
*Ejemplo:*
`x != y` 
```js
//Operador Distinto a
//Compara valor y convierte el tipo de dato si es necesario
console.log("a != b ->", a != b);/*el termino "a!=b ->" es texto
informativo para preguntar si la variable "a" es distinta a "b",
posteriormente hacemos la operacion y el resultado es false.

ya que el operador != realiza una comparacion entre los valores
de las variables "a" que es un Numbre y "b" que es un String 
nos da el valor de false ya que convierte el tipo de dato de la
variable "b" a number por lo tanto son iguales y nos da el 
resultado de false
*/
```
****

#### `!==` Distinto exacto o extricto (se compara el tipo y dato)
*Ejemplo:*
`x !== y` 
```js
//Operador Distinto extrico
//Se compara el valor y el tipo de dato
console.log("a !== b ->", a != b);/*el termino "a!==b ->" es texto 
informativo para preguntar si la variable "a" es distinta a "b",
posteriormente hacemos la operacion y el resultado es true.

ya que el operador != realiza una comparacion entre los valores
de las variables "a" que es un Numbre y "b" que es un String 
nos da el valor de true ya que son distintas en el tipo de datos
*/
```
****

#### `>` Mayor que 
*Ejemplo:*
`x > y` 
```js
console.log("a > b ->", a > b);/*el termino "a > b ->" es texto
informativo para preguntar si la variable "a" es mayor que "b",
posteriormente hacemos la operacion "a > b" y el resultado es false

ya que el operador > realiza una comparacion de los datos de la
variable "a" que es 5 y "b" que es `5` son iguales en el valor
por lo tanto nos da false*/
```
****

#### `>=` Mayor o igual que 
*Ejemplo:*
`x >= y` 
```js
console.log("a >= b ->", a >= b);/*el termino "a >= b ->" es texto
informativo para preguntar si la variable "a" es mayor o igual que
"b",posteriormente hacemos la operacion "a >= b" y el resultado es
true

ya que el operador >= realiza una comparacion de los datos de la
variable "a" que es 5 y "b" que es `5` no son mayores pero si son
iguales en el valor por lo tanto nos da true
*/
```
****

#### `<` Menor que 
*Ejemplo:*
`x < y` 
```js
//menor que
console.log("a < b ->", a < b);/*el termino "a < b ->" es texto
informativo para preguntar si la variable "a" es menor que "b",
posteriormente hacemos la operacion "a < b" y el resultado es false
ya que el operador < realiza una comparacion de los datos de la
variable "a" que es 5  y "b" que es `5` son iguales en el valor
por lo tanto nos da false
```
****

#### `<=` Menor o igual que 
*Ejemplo:*
`x <= y` 
```js
//menor o igual que
console.log("a <= b ->", a <= b);/*el termino "a <= b ->" es texto
informativo para preguntar si la variable "a" es menor o igual que
"b",posteriormente hacemos la operacion "a <= b" y el resultado es
true

ya que el operador <= realiza una comparacion de los datos de la
variable "a" que es 5  y "b" que es `5` no son menores pero si son
iguales en el valor por lo tanto nos da true
*/
```
***

###### Temas relacionados
[[String Interpolation]]
