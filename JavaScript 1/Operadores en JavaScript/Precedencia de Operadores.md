### Precedencia de Operadores

La precedencia de operadores determina el orden en el que se evalúan las operaciones en una expresión.

1. **Operadores de Agrupación**
    - `()` y `{}` Paréntesis y corchetes : Agrupan expresiones para alterar el orden de evaluación.
    - Ejemplo: `(a + b) * c`
2. **Operadores Unarios**
    - `++` Incremento: `++a` o `a++`
    - `--` Decremento: `--a` o `a--`
    - `+` Operador unario más: `+a`
    - `-` Operador unario menos: `-a`
    - `!` Negación lógica: `!a`
3. **Operadores de Exponenciación**
    - `**` Exponenciación: `a ** b`
4. **Operadores Aritméticos**
    - `*` Multiplicación: `a * b`
    - `/` División: `a / b`
    - `%` Módulo: `a % b`
    - `+` Suma: `a + b`
    - `-` Resta: `a - b`
5. **Operadores Relacionales**
    - `<` Menor que: `a < b`
    - `<=` Menor o igual que: `a <= b`
    - `>` Mayor que: `a > b`
    - `>=` Mayor o igual que: `a >= b`
6. **Operadores de Igualdad**
    - `(==)` Igual a: `a == b`
    - `!=` Distinto de: `a != b`
    - `(===)` Estrictamente igual a: `a === b`
    - `!==` Estrictamente distinto de: `a !== b`
7. **Operadores Lógicos**
    - `&&` AND lógico: `a && b`
    - `||` OR lógico: `a || b`
8. **Operadores de Asignación**
    - `(=)` Asignación simple: `a = b`
    - `+=` Asignación con suma: `a += b`
    - `-=` Asignación con resta: `a -= b`
    - `*=` Asignación con multiplicación: `a *= b`
    - `/=` Asignación con división: `a /= b`
    - `%=` Asignación con módulo: `a %= b`
    - `**=` Asignación con exponenciación: `a **= b`
<!--SR:!2024-07-22,3,250!2024-07-22,3,250!2000-01-01,1,250-->

##### Ejemplo:

```js
// se revisa de izquierda a derecha
let a = 12/3+2*3-1;
//paso 1. Division 12/3 = 4
//paso 2. Multiplicacion 2 * 3 = 6
//paso 3. Suma 4 + 6 = 10
//paso 4. Resta 10 - 1 = 9
console.log(a) // el valor de nuestra variable "a" es 9
```