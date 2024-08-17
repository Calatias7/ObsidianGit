## Valor dentro del rango
```js
//valor dentro del rango
let min = 0, max = 5;/* definimos la varible "min" y le asignamos
el valor de 0 y definimos la varible "max" y le asignamos el valor
de 5*/

let dato = 3; /* definimos la variable "dato" y le asignaos el 
valor de 3.
Esta variable la usaremos para determinar si el valor esta dentro
del rango de las varibles "min" y "max" */

let dentroRango = dato >= min && dato <= max ;/*definimos la variable
"dentroRango" esta variable se encargara de verificar si estamos dentro
del rango asignado.

le asignacion "dato >= min" determina si la varible "dato" es mayor
o igual al valor de la variable "min".
usando el operador logico and $$ y la asignacion "dato <= max",
determinamos si tambien la varible "dato" es menor o igual al valor
de la variable "max"*/

console.log(`valor dentro del rango:`, dentroRango)
/* Mostramos el resultado de la operacion dado que en este caso la
variable "dato" tiene el valor de 3 y se encuentra entre el rango
de la variable "min" con el valor 0 y "max" con el valor 5
nuestro resultado es true*/
```
