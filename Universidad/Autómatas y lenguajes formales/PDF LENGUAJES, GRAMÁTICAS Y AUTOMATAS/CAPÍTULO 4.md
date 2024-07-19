# Relaciones Entre Cadenas

## Relaciones de Derivación

### 4.1 Relación de Derivación Directa
Sea una gramática $G = (VN, VT, S, P)$. Si $α → β$ es una producción es decir $( α → β ) ∈ P$ y $γ α ρ$ es una cadena es decir $γ α ρ ∈ V^+$, entonces las cadenas $γ α ρ$ y $γ β ρ$ están en la relación de derivación directa de la gramática $G$. Esto se puede expresar como:

$$γ α ρ → γ β ρ$$

Se dice que la cadena $γ α ρ$ deriva directamente de $γ β ρ$, o que $γ α ρ$ produce directamente $γ β ρ$ en la gramática $G$. De ahí el nombre de producciones para los elementos de $P$.

#### Ejemplo 4.1.1
Sea la gramática: $G = (VT, VN, S, P)$ donde:
- $VT = {a, b}$
- $VN = \{S\}$
- Conjunto de producciones:
  - $S → ab$
  - $S → aSb$

Se obtiene la siguiente derivación directa, al sustituir la primera regla en la segunda:
- $S → aabb$

### 4.2 Relación de Derivación
Sean $\alpha_1$ y $\alpha_m$ cadenas pertenecientes a $V^+$, se dice que están en relación de derivación en la gramática G si existen $α_1,α_2,α_3,..., α_m$ tales que:

$$α_1 → α_2$$
$$α_2 → α_3$$
 $$α_3 → α_4$$
$$. . .$$
$$α_{(m − 1)} → α_m$$

Se escribirá entonces:

$$α_1 → α_m$$

Diciéndose que $α_m$ deriva de $α_1$, o que $α_1$ produce $α_m$ 
#### Ejemplo 4.2.1
Sea la gramática $G = (\{S, A, B\}, \{a, b, c, d\}, S, P)$ donde $P$ son las siguientes reglas de producción, numeradas para su posterior identificación:

$S →^1 ASB →^5 aASB →^2 abSB →^4 abdB →^6 abddcd$

Por aplicación de derivaciones inmediatas a partir del símbolo inicial se obtiene la derivación:
6
- $S → abddcd$

Las derivaciones inmediatas necesarias para llegar a la derivación anterior se muestran a continuación, indicando en cada paso el número de la regla aplicada:
1. $S → ASB (1)$
2. $ASB → aASB (5)$
3. $aASB → abSB (2)$
4. $abSB → abdB (4)$
5. $abdB → abddcd (6)$
