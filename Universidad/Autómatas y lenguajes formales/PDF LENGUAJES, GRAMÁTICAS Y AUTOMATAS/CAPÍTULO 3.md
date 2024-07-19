# Definición Formal de Gramática

## Definición de Gramática
Una gramática es una cuádrupla:
$$G = ( VT , VN , S , P )$$

### Elementos de la Gramática
- **VT**: Conjunto finito de símbolos terminales.
- **VN**: Conjunto finito de símbolos no terminales.
- **S**: Símbolo inicial, pertenece a **VN**.
- **P**: Conjunto de producciones o reglas de derivación.

### Vocabulario Terminal y No Terminal
- **Cadenas del lenguaje**: Formadas con símbolos de **VT**.
- **VT**: Definido por enumeración de los símbolos terminales.
- **VN**: Símbolos auxiliares, no figuran en las sentencias del lenguaje.
- **VN**: Definido por enumeración de los símbolos no terminales.

### Relaciones entre VT y VN
- **Intersección**: $\{VN\} ∩ \{VT\} = \{∅\}$
- **Unión**: $\{VN\} ∪ \{VT\} = \{V\}$

### Inclusión de la Cadena Vacía
- $V^+: V − \{λ\}$
- $V^*: V + \{λ\}$

### Símbolo Inicial
- **S**: Símbolo no terminal, punto de partida para aplicar reglas de la gramática.

## Producciones
- **P**: Reglas que se aplican desde el símbolo inicial para obtener las cadenas del lenguaje.
- **Definición de P**: Enumeración de las producciones, en forma de reglas o mediante un metalenguaje como BNF(Backus Naur Form) o EBNF (Extended Backus Naur Form.
---

[[BNF y EBNF]]

---
### Ejemplos de Gramáticas
#### Ejemplo 3.1
$G = (VT, VN, S, P)$ 
Donde:
$VT = {a, b}$
$VN = {S}$
Producciones $P$ es: 
   - $S → ab$
   - $S → aSb$

#### Ejemplo 3.2
$G = ( \{a, b, c, d\}, \{S, A, B\}, S, P)$
$P$:
   - $S → ASB$
   - $A → b$ 
   - $aaA → aaBB$ 
   - $S → d$
   - $A → aA$ 
   - $B → dcd$

#### Ejemplo 3.3
$G = (VN, VT, S, P)$
Donde:
$VN = \{<número>, <dígito>\}$
$VT = \{0, 1, 2, 3, 4, 5, 6, 7, 8, 9\}$
$S = <número>$
- Las reglas de producción $P$:
    - $<número> ::= <dígito> <número>$
    - $<número> ::= <dígito>$
    - $<dígito> ::= 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9$

#### Ejemplo 3.4
$G = (VN, VT, S, P)$
$VN = \{<dígito>, <otroDígito>, <Base2>, <vacío>\}$
$VT = \{0, 1\}$
$S = < Base2 >$
P:
- $< Base2 > ::= <dígito> < otroDígito >$
-$< otroDígito > ::= <dígito> <otroDígito> | < vacío >$
- $<dígito> ::= 0 | 1$
- $< vacío > ::= λ$

> [!PDF|important] [[libro lenguajes  formales y AUTOMATAs.pdf#page=17&selection=11,0,16,69&color=important|libro lenguajes  formales y AUTOMATAs, p.17]]
> > 3.5 Notación 
> > Se usará la que se describe a continuación, por ser la más extendida en la bibliografía Aho y Ullman (1973a, 1973b), Hopcroft y Ullman (1979), Aho et al. (1986), Sanchís y Morales (1986), Alfonseca et al. (1987), y Sánchez y Valverde (1989).
> 
> 

### Vocabulario Terminal
- Letras minúsculas del comienzo del abecedario: $a, b, c, …, g$.
- Operadores: $+, -, * , /, …$
- Caracteres especiales: #, @, (, ), ., ;, …
- Dígitos: $0, 1, …, 9$
- Palabras reservadas de lenguajes de programación: $if, then, else, …$

### Vocabulario No Terminal
- Letras mayúsculas del comienzo del abecedario: $A, B, …, G.$
- Nombres en minúscula entre paréntesis angulares: $<expresión>, < operador >, …$

>[!note] Observacion:
>La única excepción suele ser el símbolo inicial que se representa con $S$
>
### Vocabulario General
- Letras mayúsculas del final del abecedario: $U, V, W, X, Y, Z$.

### Cadenas Terminales
- Letras minúsculas del final del abecedario: $t, u, v, x, y, z$.

### Cadenas con Símbolos Terminales y No Terminales
- Letras minúsculas griegas: $α, β, γ, δ, ε$.