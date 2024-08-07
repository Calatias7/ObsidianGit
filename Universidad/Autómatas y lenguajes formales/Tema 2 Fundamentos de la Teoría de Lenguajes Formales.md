### 2.5 Operaciones con Lenguajes

#### Unión de lenguajes
- **Definición**:
  Consideremos dos lenguajes diferentes definidos sobre el mismo alfabeto $L1 ⊂ W(Σ)$ y $L2 ⊂ W(Σ)$. Se denomina unión de ambos lenguajes al lenguaje formado por las palabras de ambos lenguajes:
  $$L1 ∪ L2 = { x | x ∈ L1   ó   x ∈ L2 }$$

- **Propiedades**:
  - **Operación cerrada**: La unión de dos lenguajes definidos sobre el mismo alfabeto será otro lenguaje definido sobre ese alfabeto.
  - **Propiedad asociativa**: $(L1 ∪ L2) ∪ L3 = L1 ∪ (L2 ∪ L3)$
  - **Existencia de elemento neutro**: $L ∪ ∅ = ∅ ∪ L = L$
  - **Propiedad conmutativa**: $L1 ∪ L2 = L2 ∪ L1$
  - **Propiedad de idempotencia**: $L ∪ L = L$
 
#### Concatenación de lenguajes
- **Definición**:
  Consideremos dos lenguajes definidos sobre el mismo alfabeto, $L1$ y $L2$. La concatenación o producto de estos lenguajes es el lenguaje:
  $L1L2 = \{ xy | x ∈ L1 y x ∈ L2 \}$
  - La concatenación de lenguajes con el lenguaje vacío es:
  $∅L = L∅ = ∅$

- **Propiedades**:
  - **Operación cerrada**: La concatenación de lenguajes sobre el mismo alfabeto es otro lenguaje sobre ese alfabeto.
  - **Propiedad asociativa**: $(L1 L2) L3 = L1 (L2 L3)$
  - **Elemento neutro**: Cualquiera que sea el lenguaje considerado, el lenguaje de la palabra vacía cumple que: $\{λ\}L = L\{λ\} = L$

#### Potencia de un lenguaje
- **Definición**:
  Se define la potencia i-ésima de un lenguaje a la operación de concatenarlo consigo mismo i veces.
  $$L^i = LLL...L$$
 $$|-----------|$$
  $$       i     $$

- **Relaciones**:
  -  $$L^{i+1} = L^iL = LL^i \, (i > 0)$$
  - $$L^iL^j = L^{i+j} \, (i, j > 0)$$
  - Para que las relaciones se cumplan para $i$, $j$ = $0$, se define:
  $L^0 = \{λ\}$ , (cualquiera que sea $L$)

#### Clausura positiva de un lenguaje
- **Definición**:
  Se define la clausura positiva de un lenguaje L:
  $$L^+ = \bigcup_{i=1}^{∞} L_i$$ 
  Lenguaje obtenido uniendo el lenguaje con todas sus potencias posibles excepto $L^0$. Si $L$ no contiene la palabra vacía, la clausura positiva tampoco.

- **Ejemplo**:
  Ya que cualquier alfabeto $Σ$ es un lenguaje sobre él mismo (formado por las palabras de longitud 1), al aplicarle esta operación se observa que:
  $$Σ^+ = W(Σ) - \{λ\}$$ 

#### Cierre o Clausura de un lenguaje
- **Definición**:
  Se define el cierre o clausura de un lenguaje L como:
  $$L^* = \bigcup_{i=0}^{∞} L^i$$ 
  Lenguaje obtenido uniendo el lenguaje con todas sus potencias posibles, incluso $L^0$. Todas las clausuras contienen la palabra vacía.

- **Relaciones**:
  - $$L^* = L^+ ∪ \{λ\} $$
  - $$L^+ = L L^* = L^* L$$ será imposible obtener la palabra vacía

- **Ejemplo**:
  Ya que el alfabeto Σ es un lenguaje sobre sí mismo, al aplicársele esta operación:
  $$Σ^* = W(Σ)$$ 
  Se denominará $Σ^*$ al lenguaje universal o "universo del discurso" sobre el alfabeto $Σ$.

#### Reflexión de lenguajes
- **Definición**:
  Se llama lenguaje reflejo o inverso de $L$, representándose por:
  $$L^{-1} = \{ x^{-1} | x ∈ L \}$$
  Lenguaje que contiene las palabras inversas a las palabras de $L$.
