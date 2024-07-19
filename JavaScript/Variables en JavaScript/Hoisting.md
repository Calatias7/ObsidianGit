El término "hoisting" (elevación) en JavaScript se refiere al comportamiento del lenguaje en el que las declaraciones de variables y funciones se mueven ("elevan") al comienzo de su contexto de ejecución antes de que se ejecute el código. Esto significa que las variables y funciones pueden ser utilizadas antes de ser declaradas en el código fuente.
### Hoisting de Variables:

En el caso de las variables declaradas con `var`, el hoisting eleva solo la declaración, no la inicialización. La inicialización ocurre en el lugar donde se define en el código.

```js
console.log(miVariable); // undefined
var miVariable = 10;
console.log(miVariable); // 10

```
Aquí, la declaración `var miVariable;` se eleva al principio del contexto de ejecución, pero la asignación `miVariable = 10;` permanece en su lugar.

Al usar `let` no aplica el concepto de hoisting
