#  # Definición Formal de Lenguaje

## Definición de Lenguaje
El lenguaje $L(G)$ generado por una gramática $G$  es el conjunto de todas las sentencias que puede generar $G$. Es decir, expresado formalmente:

$$L(G) = {η ∈ VT^*/S → η}$$

Una sentencia pertenece a $L(G)$ si:
- Está compuesta de símbolos terminales.
- La sentencia puede derivarse del símbolo inicial $S$ aplicando las reglas de producción de la gramática.

### 6.1 Propiedad
Dos gramáticas son equivalentes si ambas generan el mismo lenguaje. $G_1$ y $G_2$ son equivalentes si  $L(G_1) = L(G_2)$.

### Ejemplo 6.2
Sea la gramática definida por $G_2 = (\{S\}, \{0,1\}, S, P)$ donde  $P = \{ (S \rightarrow 000S111), (0S1 \rightarrow 01) \}$.

**Solución:**
La única forma de generar sentencias es aplicando cualquier número de veces la primera producción y terminando con la aplicación de la segunda. Por consiguiente, el lenguaje que genera esta gramática es el conjunto infinito de instrucciones que se indica a continuación:
$$L(G_2) = \{ 0^{3n}1^{3n} / n \geq 1 \}$$

### Ejemplo 6.3
Si la segunda producción de la gramática del ejemplo 6.2 fuese $S \rightarrow 01$, el lenguaje sería:
$$L(G_3) = \{ 0^{3n+1}1^{3n+1} / n \geq 0 \}$$
### Ejemplo 6.4

Sea la gramática $G_4 = (\{S\}, \{a, b\}, S, P)$ donde $P = \{(S \rightarrow aSb), (S \rightarrow ab)\}$. Determinar el lenguaje que genera.

**Solución:** Aplicando la primera producción $n-1$veces, seguida por la aplicación de la segunda producción, se tiene que:
$S \rightarrow aSb \rightarrow aaSbb \rightarrow a^3Sb^3 \rightarrow \ldots \rightarrow a^{(n-1)}Sb^{(n-1)} \rightarrow a^n b^n$

El lenguaje generado:
$$L(G_4) = \{a^n b^n n \ge 1 \}$$
---

### Ejemplo 6.5

Dada la gramática $G_5 = (\{S, A\}, \{a, b\}, S, P)$ donde $P = \{(S \rightarrow abAS), (abA \rightarrow baab), (S \rightarrow a), (A \rightarrow b)\}$. Determinar el lenguaje que genera.

**Solución:** Se generan sentencias del lenguaje aplicando las reglas hasta que se pueda ver la forma general del lenguaje.

$$\begin{aligned}
S &\rightarrow abAS \rightarrow baabS \rightarrow baaba \\
S &\rightarrow a \\
S &\rightarrow abAS \rightarrow abbS \rightarrow abba \\
S &\rightarrow abAS \rightarrow abAbAS \rightarrow \ldots \rightarrow (abA)^n S \rightarrow (abb)^n a \\
S &\rightarrow abAS \rightarrow abAbAS \rightarrow \ldots \rightarrow (abA)^n S \rightarrow (baab)^n a \\
S &\rightarrow abAS \rightarrow abAbAS \rightarrow abbaab \\
S &\rightarrow abAS \rightarrow abAbAS \rightarrow baababba \\
S &\rightarrow abAS \rightarrow abAbAS \rightarrow abAbAbAS \rightarrow baababbbaaba
\end{aligned}$$

$L(G_5)$ = {cadenas que contienen $abb$ y $baab$  intercambiándose y reproduciéndose cualquier número de veces, y terminando siempre con el símbolo $a$ }

Se puede observar que la forma de expresar este lenguaje no es simple, y surge la necesidad de tener una herramienta que permita describir los lenguajes de otra forma.

