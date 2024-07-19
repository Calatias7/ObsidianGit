## Operadores Incremento/Decremento  
```js  
let a,b,c;//Declaracion de variables  
```
****

#### `++` Incremento  
*Ejemplo :* Pre-Incremento `++X` ó Post-Incremento `X++`  

1.  Pre-Incremento `++X`
```js  
//Pre-Incremento  
a=0;  
++a; /* el Pre-Incremeto, incrementa a 1 automaticamete el valor 
en esta variable*/  
console.log(a);//nuestra variable `a` vale 1  
```  
2. Post-Incremento `X++` 
```js
//Post-incremento  
a++; /*la variable `a` tiene el valor de 1 al usar el post-incremento
obtiene el incremento de 1 la proxima vez que se utilize la variable
*/  

console.log(a);/*en este caso al usar la variable obtendra el
valor de 2*/ 

```
****

#### `--` Decremento  

*Ejemplo :* Pre-Decremento `--X` ó Post-Decremento `X--`  

1. Pre-Decremento `--X`
```js  
//Pre-Decremento  
--a; /*Nuestra variable `a` tiene el valor de 2 al usar el 
Pre-Decremeto, Decremeta automaticamente al valor en 1*/

console.log(a);//nuestra variable `a` obtiene el valor 1
```  
2.  Post-Decremento `X--`
```js
//Post-Decremento  
a--; /*la variable `a` tiene el valor de 1 al usar el post-Decremento
obtiene un Decremento de 1 la proxima vez que se utilize la variable
*/  
console.log(a);/*en este caso al usar la variable obtendra el valor
de 0 */
```

****  

### *Ejemplo*  

```js  

a=5;//la variable "a" tiene el valor de 5  
b=2;//La variable "b" tiene el valor de 2  
/*La manera que se ejecuta y analizan las operaciones son 
de DERECHA a IZQUIERDA*/  

c = ++a * b--;//el resultado de esta operacion es 12

/* Al usar el Pre-Incremento el la variable "a" obtiene
automaticamente el valor de 6, posterioemente tenemos un
Post-Decremento en la variable "b" por lo cual la siguente
vez que se utilize se Decrementa la variable "b". 
entonces la multiplicacion quedaria como 6*2 = 12 por lo tanto
nuestra variable C tiene el valor de 12  
*/  
console.log(a);//el valor de la variable "a" es 6  
connsole.log(b);/*el valor de la variable "b" es 1  
ya que volvimos a usar la variable por lo tanto  
se decrementa*/  
console.log(c);//el valor de la variable "c" es 12  

```
