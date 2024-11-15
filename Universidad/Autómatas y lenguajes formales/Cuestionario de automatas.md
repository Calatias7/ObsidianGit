
---

### 1. Autómatas de Pila

#### Pregunta 1:
Define un autómata de pila y describe su estructura. Explica el rol de cada componente en la definición formal.

**Respuesta**: Un autómata de pila (AdP) es un autómata finito no determinista con una memoria adicional en forma de pila. La definición formal incluye:
- \(Q\): Conjunto finito de estados.
- \(Sigma): Alfabeto de entrada.
- \(Gamma): Alfabeto de la pila (símbolos de la pila).
- \(q_0\): Estado inicial.
- \(F\): Conjunto de estados de aceptación.
- (delta): Función de transición que define el cambio de estado en función del símbolo leído en la entrada y el símbolo en la cima de la pila.

#### Ejemplo 1:
Diseña un autómata de pila que acepte el lenguaje \( L = \{0^n1^n | n \geq 0\} \).

**Solución paso a paso**:
1. Apila un símbolo por cada '0' leído.
2. Cuando encuentres un '1', desapila un símbolo.
3. Si la pila está vacía al final y has leído todos los símbolos, acepta la palabra.

---

### 2. Gramáticas Libres del Contexto (GLC)

#### Pregunta 2:
¿Qué es una gramática libre del contexto (GLC)? Describe su definición formal.

**Respuesta**: Una gramática libre del contexto es una gramática que genera lenguajes libres del contexto, aquellos que pueden ser reconocidos por un autómata de pila. Está definida como \( G = (N, T, P, S) \), donde:
- \(N\): Conjunto de no terminales.
- \(T\): Conjunto de terminales.
- \(P\): Conjunto de producciones.
- \(S\): Símbolo inicial.

#### Ejemplo 2:
Escribe una GLC que genere el lenguaje \( L = \{a^nb^n | n \geq 0\} \).

**Solución**:
1. Define \(S \rightarrow aSb | \varepsilon\) en el conjunto de producciones.
2. Explica cómo cada par de 'a' y 'b' se genera de manera balanceada desde el axioma.

---

### 3. Atributos Heredados y Sintetizados

#### Pregunta 3:
Define qué son los atributos heredados y sintetizados en el contexto de gramáticas.

**Respuesta**:
- **Atributos heredados**: Son aquellos que se pasan de un nodo padre a sus hijos en el árbol de derivación.
- **Atributos sintetizados**: Son aquellos que se calculan en un nodo y se pasan hacia arriba, de los hijos hacia el nodo padre.

#### Ejemplo 3:
Dado un árbol de derivación de una expresión aritmética, muestra cómo calcular los atributos heredados y sintetizados para evaluar la expresión.

---

### 4. Análisis Sintáctico Descendente

#### Pregunta 4:
¿Qué es el análisis sintáctico descendente y cuáles son sus tipos?

**Respuesta**: El análisis sintáctico descendente intenta construir el árbol sintáctico desde el axioma hasta los símbolos terminales. Hay dos tipos principales:
1. **Análisis sintáctico con retroceso**: Prueba varias opciones de derivación, lo cual puede ser ineficiente.
2. **Análisis sintáctico predictivo**: No requiere retroceso y utiliza gramáticas LL(1) para elegir las reglas de producción con base en el primer símbolo de la entrada.

#### Ejemplo 4:
Para la gramática \( S \rightarrow aSb | \varepsilon \), realiza el análisis descendente de la cadena "aabb" utilizando un analizador LL(1).

**Solución paso a paso**:
1. Construye los conjuntos PRIMERO y SIGUIENTE para cada producción.
2. Aplica las reglas en cada paso hasta agotar la entrada o determinar que no pertenece al lenguaje.

---

### 5. Máquina de Turing

#### Pregunta 5:
Describe la estructura y funcionamiento de una Máquina de Turing.

**Respuesta**: Una Máquina de Turing es un modelo computacional que consta de una cinta infinita, un cabezal de lectura/escritura, un conjunto de estados, y una función de transición. Puede moverse hacia la izquierda o derecha en la cinta, leer o escribir símbolos y cambiar de estado.

#### Ejemplo 5:
Diseña una Máquina de Turing que acepte el lenguaje \( L = \{w \in \{a, b\}^* | w = w^R \} \), donde \( w^R \) es la reversa de \( w \).

**Solución**:
1. Describe los estados y transiciones que permitan comparar caracteres del inicio y el final, moviéndose hacia el centro de la cadena.
2. Si todos coinciden, la Máquina de Turing termina en un estado de aceptación.

---

### 6. Análisis de Gramática y Transformación para LL(1)

#### Pregunta 6:
Explica cómo transformar una gramática para que cumpla las condiciones LL(1).

**Respuesta**: Para que una gramática sea LL(1), debe cumplir con las siguientes condiciones:
1. No debe ser ambigua.
2. Debe estar factorada por la izquierda.
3. No debe tener recursividad por la izquierda.

#### Ejemplo 6:
Convierte la gramática \( S \rightarrow Sa | Sb | a \) en una gramática LL(1).

**Solución**:
1. Elimina la recursividad por la izquierda.
2. Factoriza la gramática para evitar ambigüedades.

---

### 7. Ejercicios de Cálculo de Conjuntos PRIMERO y SIGUIENTE

#### Pregunta 7:
Dada la gramática \( E \rightarrow TE' \), \( E' \rightarrow +TE' | \varepsilon \), \( T \rightarrow FT' \), \( T' \rightarrow *FT' | \varepsilon \), \( F \rightarrow (E) | id \), calcula los conjuntos PRIMERO y SIGUIENTE.

**Solución paso a paso**:
1. **PRIMERO**: Identifica los terminales que pueden iniciar cada producción.
   - PRIMERO(E) = PRIMERO(T) = \{ (, id \}
   - PRIMERO(E') = \{ +, \varepsilon \}
2. **SIGUIENTE**: Determina qué terminales pueden seguir a cada símbolo no terminal en una derivación.
   - SIGUIENTE(E) = \{ ), \$ \}
   - SIGUIENTE(T) = SIGUIENTE(E') = \{ +, ) , \$ \}.

---

### 1. Autómatas de Pila y Lenguajes Independientes del Contexto

1. **¿Cuál es la diferencia entre un autómata de pila determinista (APD) y un autómata de pila no determinista (APND)?**  
   *Respuesta esperada*: Un APD tiene una única transición definida para cada combinación de entrada y símbolo en la cima de la pila, mientras que un APND puede tener múltiples transiciones para la misma combinación, permitiendo opciones alternativas.

2. **¿Por qué los lenguajes libres del contexto no pueden ser aceptados por autómatas finitos?**  
   *Respuesta esperada*: Los autómatas finitos no tienen una memoria auxiliar como una pila para almacenar información adicional, lo cual es necesario para verificar propiedades como el balanceo de símbolos (ej. \(a^n b^n\)), lo que sí pueden hacer los autómatas de pila.

3. **Describe el funcionamiento de una transición \(\varepsilon\)-movimiento en un autómata de pila.**  
   *Respuesta esperada*: En un \(\varepsilon\)-movimiento, el autómata cambia de estado y/o modifica la pila sin leer ningún símbolo de la entrada. Esto permite decisiones adicionales en el análisis.

---

### 2. Gramáticas y Lenguajes Libres del Contexto

4. **Explica la diferencia entre una gramática regular y una gramática libre del contexto.**  
   *Respuesta esperada*: Una gramática regular tiene producciones limitadas a una forma específica (A → aB o A → a) y puede ser reconocida por un autómata finito, mientras que una gramática libre del contexto permite producciones de la forma \(A \rightarrow \alpha\), donde \(A\) es un no terminal y \(\alpha\) puede ser cualquier combinación de terminales y no terminales.

5. **¿Qué significa que una gramática sea ambigua? Da un ejemplo.**  
   *Respuesta esperada*: Una gramática es ambigua si existe al menos una cadena que tiene más de un árbol de derivación. Ejemplo: La gramática \(S \rightarrow SS | a\) es ambigua, ya que una cadena como "aa" puede derivarse de múltiples maneras.

6. **¿Cuál es el propósito de escribir gramáticas en la forma BNF (Backus-Naur Form)?**  
   *Respuesta esperada*: La notación BNF se utiliza para definir la sintaxis de lenguajes de programación, simplificando la expresión de gramáticas libres del contexto mediante reglas y notación estandarizada.

---

### 3. Atributos Heredados y Sintetizados

7. **Explica cómo funcionan los atributos heredados en un árbol de derivación y proporciona un ejemplo.**  
   *Respuesta esperada*: Los atributos heredados son valores que se transmiten desde un nodo padre a sus hijos en el árbol de derivación. Por ejemplo, en la evaluación de expresiones aritméticas, un operador puede pasar su contexto a los operandos para ser evaluados en conjunto.

8. **Describe una situación en la que sería útil utilizar atributos sintetizados en lugar de heredados.**  
   *Respuesta esperada*: Los atributos sintetizados son útiles cuando queremos calcular un valor acumulativo a medida que se recorre el árbol hacia arriba, como al evaluar el resultado de una expresión matemática en un nodo final de la derivación.

---

### 4. Análisis Sintáctico y Conjuntos PRIMERO y SIGUIENTE

9. **¿Cuál es el propósito de los conjuntos PRIMERO y SIGUIENTE en el análisis sintáctico descendente?**  
   *Respuesta esperada*: El conjunto PRIMERO permite identificar los símbolos terminales que pueden aparecer al inicio de las producciones de un no terminal, mientras que el conjunto SIGUIENTE identifica los terminales que pueden seguir a un no terminal en una derivación. Estos conjuntos ayudan a construir analizadores predictivos sin retroceso (LL(1)).

10. **Dada la producción \(A \rightarrow BCD\), describe cómo calcularías PRIMERO(A) si los conjuntos PRIMERO(B), PRIMERO(C), y PRIMERO(D) ya están calculados.**  
    *Respuesta esperada*: PRIMERO(A) incluirá todos los elementos de PRIMERO(B). Si \(\varepsilon\) está en PRIMERO(B), entonces se incluirán también los elementos de PRIMERO(C); si \(\varepsilon\) está en PRIMERO(C), se incluirán los elementos de PRIMERO(D).

---

### 5. Analizadores LL(1) y LR(1)

11. **Explica qué significa que una gramática sea LL(1).**  
    *Respuesta esperada*: Una gramática LL(1) permite el análisis sintáctico de izquierda a derecha (Left-to-right) utilizando derivación por la izquierda (Leftmost) y necesita observar solo un símbolo de la entrada para decidir la producción aplicable, sin retroceso.

12. **Describe el proceso de construcción de la tabla de análisis sintáctico predictivo LL(1) para una gramática simple.**  
    *Respuesta esperada*: Primero, calcula los conjuntos PRIMERO y SIGUIENTE. Luego, para cada producción \(A \rightarrow \alpha\), coloca en la tabla los símbolos en PRIMERO(\(\alpha\)) en la fila de \(A\). Si \(\alpha\) puede derivar \(\varepsilon\), coloca SIGUIENTE(A) en la misma fila.

13. **¿En qué casos no se puede construir un analizador LL(1) para una gramática?**  
    *Respuesta esperada*: No se puede construir un analizador LL(1) si la gramática es ambigua, si tiene recursión por la izquierda o si los conjuntos PRIMERO de diferentes producciones para el mismo no terminal se superponen.

---

### 6. Máquina de Turing y Computabilidad

14. **¿Qué significa que un lenguaje sea Turing-decidible?**  
    *Respuesta esperada*: Un lenguaje es Turing-decidible si existe una Máquina de Turing que acepta todas las cadenas del lenguaje y rechaza todas las cadenas fuera del lenguaje, terminando en ambos casos.

15. **¿Cuál es la diferencia entre una Máquina de Turing determinista y una no determinista?**  
    *Respuesta esperada*: Una Máquina de Turing determinista tiene una única transición posible para cada combinación de estado y símbolo de entrada, mientras que una no determinista puede tener múltiples opciones de transición, permitiendo la exploración de múltiples caminos en paralelo.

---

---

### 1. Autómatas de Pila

1. **Explica la diferencia entre un autómata finito y un autómata de pila.**
   *Respuesta esperada*: Un autómata finito no tiene memoria adicional y solo puede procesar entradas con transiciones en función del estado actual y el símbolo de entrada. Un autómata de pila, en cambio, tiene una pila que permite almacenar y recuperar información de manera que puede reconocer patrones más complejos, como lenguajes independientes del contexto.

2. **¿Cuál es la función de transición en un autómata de pila y cómo se representa?**
   *Respuesta esperada*: La función de transición, \(\delta\), define los cambios de estado y las operaciones en la pila en función del estado actual, el símbolo de entrada, y el símbolo en la cima de la pila. Se representa como \(\delta(q, a, X) = (p, \gamma)\), donde \(q\) es el estado actual, \(a\) es el símbolo de entrada, \(X\) es el símbolo en la cima, \(p\) es el nuevo estado, y \(\gamma\) es la nueva cadena en la pila.

3. **Describe el comportamiento de un autómata de pila no determinista (APND) en comparación con un APD.**
   *Respuesta esperada*: Un APND puede tener múltiples opciones de transición para una misma combinación de estado, entrada y cima de la pila, permitiendo múltiples caminos para una misma entrada. En cambio, un APD tiene una única transición para cada combinación posible.

4. **¿Cómo se puede modificar un autómata de pila para aceptar un lenguaje por "pila vacía" en lugar de por "estado final"?**
   *Respuesta esperada*: Se puede agregar una transición al final que vacíe la pila si la cadena es aceptada y asegurar que la pila esté vacía al llegar al estado de aceptación.

---

### 2. Gramáticas Libres del Contexto (GLC)

5. **¿Qué condiciones debe cumplir una gramática para ser considerada libre del contexto?**
   *Respuesta esperada*: En una GLC, cada producción tiene la forma \(A \rightarrow \alpha\), donde \(A\) es un símbolo no terminal y \(\alpha\) es una cadena de terminales y no terminales. Esto significa que el lado izquierdo de cada producción es un solo símbolo no terminal.

6. **Diferencia entre una derivación por la izquierda y una derivación por la derecha.**
   *Respuesta esperada*: En una derivación por la izquierda, siempre se expande el no terminal más a la izquierda en cada paso. En una derivación por la derecha, se expande el no terminal más a la derecha. Esto afecta el orden en que se genera la cadena.

7. **Explica el uso de notación BNF en la definición de gramáticas y proporciona un ejemplo.**
   *Respuesta esperada*: La notación BNF (Backus-Naur Form) es una forma estandarizada para definir gramáticas y se usa comúnmente para definir la sintaxis de lenguajes de programación. Ejemplo: 
   ```
   <expresión> ::= <expresión> + <término> | <término>
   <término> ::= <factor> * <factor> | <factor>
   ```.

8. **¿Cómo se utiliza un árbol de derivación para representar una cadena generada por una GLC?**
   *Respuesta esperada*: Un árbol de derivación muestra gráficamente cómo se expande el símbolo inicial a través de las producciones de la gramática hasta formar la cadena terminal. El nodo raíz es el símbolo inicial, y los nodos hojas representan los símbolos terminales de la cadena derivada.

---

### 3. Atributos Heredados y Sintetizados

9. **¿Qué tipo de información pueden transportar los atributos heredados en un árbol de derivación? Da un ejemplo.**
   *Respuesta esperada*: Los atributos heredados pueden transportar información contextual de un nodo padre a sus hijos. Ejemplo: En una expresión aritmética, un operador puede pasar su tipo (suma o resta) como atributo a sus operandos.

10. **Da un ejemplo de cómo se puede utilizar un atributo sintetizado para evaluar una expresión en un árbol de derivación.**
    *Respuesta esperada*: En una expresión como \(3 + 4 * 5\), el valor de cada operación se sintetiza hacia el nodo raíz. Cada nodo sintetiza su valor a partir de sus hijos y lo pasa hacia arriba en el árbol.

11. **¿Cuál es la diferencia principal entre los atributos heredados y los atributos sintetizados?**
    *Respuesta esperada*: Los atributos heredados se transmiten desde los nodos padres hacia los hijos, mientras que los atributos sintetizados se calculan en los hijos y se transmiten hacia los padres.

---

### 4. Análisis Sintáctico y Construcción de Árboles

12. **¿Qué es un analizador sintáctico y cuál es su función en un compilador?**
    *Respuesta esperada*: Un analizador sintáctico (o parser) toma la cadena de tokens generada por el analizador léxico y construye un árbol de derivación para verificar que la estructura sintáctica cumpla con las reglas de la gramática del lenguaje.

13. **¿Cuáles son las ventajas y desventajas de los analizadores sintácticos ascendentes en comparación con los descendentes?**
    *Respuesta esperada*: Los analizadores ascendentes pueden manejar una clase más amplia de gramáticas, incluidas algunas ambiguas, pero son más complejos. Los analizadores descendentes, en cambio, suelen ser más simples y rápidos, pero no pueden manejar gramáticas ambiguas.

14. **Explica cómo se construye un analizador LL(1) y cuáles son sus limitaciones.**
    *Respuesta esperada*: Un analizador LL(1) utiliza una tabla de análisis predictivo que indica qué producción aplicar en cada paso, sin retroceso, al analizar la entrada de izquierda a derecha. Su principal limitación es que solo funciona con gramáticas LL(1), es decir, gramáticas sin ambigüedades y sin recursión a la izquierda.

15. **Describe el proceso de cálculo de los conjuntos PRIMERO y SIGUIENTE para una gramática simple.**
    *Respuesta esperada*: 
   - **PRIMERO**: Incluye los terminales que pueden aparecer al principio de cualquier derivación de un no terminal.
   - **SIGUIENTE**: Incluye los terminales que pueden seguir a un no terminal en alguna derivación. Se calculan de manera iterativa aplicando reglas hasta que no haya cambios.

---

### 5. Máquina de Turing y Decidibilidad

16. **¿Cuáles son los componentes de una Máquina de Turing y cuál es la función de cada uno?**
    *Respuesta esperada*: 
   - **Cinta**: Almacena la entrada y actúa como memoria infinita.
   - **Cabezal de lectura/escritura**: Lee y escribe en la cinta y se mueve a la izquierda o derecha.
   - **Conjunto de estados**: Define los posibles estados de la máquina.
   - **Función de transición**: Indica cómo cambiar de estado, qué escribir y en qué dirección mover el cabezal.

17. **¿Qué significa que un problema sea indecidible en el contexto de las Máquinas de Turing?**
    *Respuesta esperada*: Un problema es indecidible si no existe ninguna Máquina de Turing que pueda determinar en todos los casos si una entrada pertenece al lenguaje o no (no termina para todas las entradas).

18. **Explica el concepto de "Lenguaje Recursivo" y cómo se diferencia de un "Lenguaje Recursivamente Enumerado".**
    *Respuesta esperada*: Un lenguaje es recursivo si existe una Máquina de Turing que lo reconoce y siempre termina. Un lenguaje es recursivamente enumerable si existe una Máquina de Turing que acepta todas las cadenas en el lenguaje, pero puede no terminar para cadenas fuera del lenguaje.

19. **¿Cómo se puede utilizar una Máquina de Turing para decidir si una cadena es un palíndromo?**
    *Respuesta esperada*: Una Máquina de Turing puede mover el cabezal desde ambos extremos hacia el centro, comparando caracteres y asegurando que coincidan. Si se encuentran diferencias, la máquina rechaza; si llega al centro sin errores, la acepta.

---

### 6. Transformaciones y Optimización de Gramáticas

20. **¿Por qué es importante eliminar la recursividad por la izquierda en una gramática LL(1)?**
    *Respuesta esperada*: La recursividad por la izquierda causa ciclos que impiden el análisis predictivo sin retroceso. Para que una gramática sea LL(1), no debe tener recursión a la izquierda.

21. **Explica el proceso de factorización por

 la izquierda en una gramática. Proporciona un ejemplo.**
    *Respuesta esperada*: La factorización por la izquierda reestructura las producciones de manera que no haya elecciones ambiguas para el primer símbolo. Ejemplo: De \(A \rightarrow aB | aC\), se transforma a \(A \rightarrow aD\), \(D \rightarrow B | C\).

22. **¿Qué significa que una gramática sea no ambigua? ¿Cómo puedes detectar la ambigüedad en una gramática?**
    *Respuesta esperada*: Una gramática es no ambigua si toda cadena tiene un único árbol de derivación. La ambigüedad se detecta cuando una cadena puede derivarse de múltiples maneras con la misma gramática.

---
