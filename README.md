# Teoría de Lenguajes Formales, Gramáticas y Autómatas

## Introducción

- **Objetivo:** Introducir conceptos teóricos sobre Teoría de Lenguajes Formales, Gramáticas y Autómatas.
- **Aplicación:** Curso universitario de Traductores, Procesadores, Compiladores e Intérpretes de lenguajes de programación.
- **Teoría de Gramáticas y Lenguajes Formales:** Herramienta matemática para el diseño de lenguajes de programación.
- **Autómatas:** Construcción y reconocimiento de lenguajes de programación.

## Origen y Desarrollo

- **Lingüística:**
    
    - Origen en la escuela estructuralista americana (años 50).
    - **Avram Noam Chomsky (1928-):** Figura destacada por sus teorías formales sobre gramáticas y lenguajes.
    - **Gramática universal:** Caracteriza las propiedades generales de cualquier lenguaje humano.
    - **Publicaciones:** Chomsky (1956; 1959; 1962; 1963).
- **Informática:**
    
    - **Gramática Formal:** Importancia para la especificación de lenguajes de programación.
    - **ALGOL 60:** Definición de sintaxis usando gramática libre de contexto.
    - **Algoritmos de traducción y compilación:** Diseño riguroso basado en teorías de Chomsky.
    - **Aplicaciones:** Informática Teórica, Inteligencia Artificial, Procesamiento de lenguajes naturales, Reconocimiento del Habla.

## Teoría de Autómatas

- **Ingeniería Eléctrica:**
    
    - **Claude Elwood Shannon (1916-2001):** Bases para la aplicación de Lógica Matemática a circuitos.
    - **Publicaciones:** Shannon (1949; 1954; 1956).
- **Definición:**
    
    - Sistemas que reciben, transforman y producen información.
    - **Aplicaciones:**
        - Lógica de Circuitos Secuenciales
        - Teoría de Control de Sistemas
        - Teoría de la Comunicación
        - Arquitectura de Ordenadores
        - Redes Conmutadoras y Codificadoras
        - Teoría de Sistemas Evolutivos y Auto-reproductivos
        - Reconocimiento de patrones
        - Redes Neuronales
        - Reconocimiento y procesamiento de lenguajes de programación
        - Traducción de lenguajes
        - Teoría de Lenguajes Formales

## Aplicación en el Curso

- **Analizadores Léxicos:** Uso de lenguajes, gramáticas y autómatas de tipo 3.
- **Analizadores Sintácticos:** Uso de lenguajes, gramáticas y autómatas de tipo 2.

****
# Definiciones Previas

## 2.1 Símbolo

- **Definición:** Entidad abstracta que no se define,  dejada como axioma.
- **Ejemplos:**
    - **Letras:** $( a, b, c, …, z)$
    - **Dígitos:** $(0, 1, …, 9)$
    - **Otros caracteres:** $(+, -, *, /, ?)$
    - **Palabras reservadas:** $( then, begin, end, else)$
---
## 2.2 Vocabulario o Alfabeto

- **Definición:** Conjunto finito y no vacío de símbolos.
- **Notación:** $a \in V$ indica que el símbolo $a$ pertenece al alfabeto $V$.
- **Ejemplos:**
    - $V_1 = \{ A, B, C, ..., Z \}$
    - $V_2= \{a,b,c,d,0,1,2,3,4,*,+ \}$
    - $V_3 = \{ 0, 1 \}$
    - $V_4 = \{ if, then, begin, end, else, a, b, ;, =, > \}$
    - Tablas ASCII y EBCDIC.
---

[[Tablas ASCII y EBCDIC]]

---
## 2.3 Cadena
- **Definición:** Secuencia finita de símbolos de un alfabeto.
- **Ejemplos:**
  - $abcb$ es una cadena del alfabeto $V_2$
  - $a+2*b$ es una cadena del alfabeto $V_2$
  - $000111$ es una cadena del alfabeto $V_3$
  - $if a > b then b = a ;$ es una cadena del alfabeto $V_4$

## 2.4 Longitud de Cadena
- **Definición:** Número de símbolos en una cadena.
- **Ejemplos:**
  - $| abcb |→ 4$
  - $| a + 2*b |→ 5$
  - $| 000111 |→ 6$
  - $| if a > b then a = b ; |→ 9$

## 2.5 Cadena Vacía
- **Definición:** Cadena sin símbolos, denotada por $\lambda$.
- **Longitud:** $|\lambda|$= 0.

## 2.6 Concatenación de Cadenas
- **Definición:** Combinación de dos cadenas $\alpha$ y $\beta$ formando una nueva cadena $\alpha\beta$.
- **Elemento Neutro:** $\lambda,$ es decir, $\alpha\lambda = \lambda\alpha = \alpha$.

## 2.7 Universo del Discurso

- **Definición:** Conjunto de todas las cadenas formadas con los símbolos de un alfabeto $V$, se denomina universo del discurso de $V$ y se representa por $W(V)$.
- **Propiedad:** $W(V)$ es infinito e incluye la cadena vacía.
- **Ejemplo:**
    - $V = \{a\}$
    - $W(V) = \{\lambda, a, aa, aaa, aaaa, ...\}$

## 2.8 Lenguaje
- **Definición:** Subconjunto del universo del discurso de un alfabeto.
- **Método de Definición:** Por propiedades que cumplen las cadenas.
- **Ejemplo:** Conjunto de palíndromos sobre el alfabeto $\{0,1\}$:
- 
    - $\lambda$
    - $0$
    - $1$
    - $00$
    - $11$
    - $010$
    - $0110$
    - $000000$
    - $101101$
    - $111111$
    - $100001$
    - $001100$
    - $1101011$
    - $0010100$

## 2.9 Lenguaje Vacío

- **Definición:** Conjunto vacío, denotado por $\{∅\}$.
- **Diferencia:**
    -  $\{∅\}$ cardinalidad = 0
    - $\{\lambda\}$ cardinalidad = 1

## 2.10 Gramática

- **Definición:** Ente formal que especifica finitamente el conjunto de cadenas que constituyen un lenguaje.

## 2.11 Autómata

- **Definición:** Construcción lógica que recibe una entrada y produce una salida basada en lo recibido hasta el momento.
- **Aplicación en Procesadores de Lenguaje:** Recibe una cadena de símbolos y determina si pertenece a un lenguaje específico. 