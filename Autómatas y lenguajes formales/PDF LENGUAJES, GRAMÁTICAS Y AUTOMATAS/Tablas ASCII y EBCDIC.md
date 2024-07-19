## Tabla ASCII
ASCII (American Standard Code for Information Interchange) es un código de caracteres que se utiliza para representar texto en computadoras y dispositivos de comunicación. Cada carácter se representa mediante un valor numérico en el rango de 0 a 127. ASCII fue desarrollado en los años 60 y se basa en el alfabeto inglés.

### Características
- **Rango:** 0-127
- **Tipo:** Código de 7 bits
- **Uso:** Amplio uso en sistemas informáticos y de telecomunicaciones.
- **Compatibilidad:** Compatible con muchos sistemas operativos y protocolos de red.

### Estructura
- **0-31 y 127:** Caracteres de control (no imprimibles)
- **32-126:** Caracteres imprimibles (letras, números, signos de puntuación, etc.)

### Tabla de Caracteres ASCII
| Valor | Carácter | Descripción      |
|-------|----------|------------------|
| 0     | NUL      | Null             |
| 1     | SOH      | Start of Heading |
| 2     | STX      | Start of Text    |
| ...   | ...      | ...              |
| 65    | A        | Letra A          |
| 66    | B        | Letra B          |
| ...   | ...      | ...              |
| 97    | a        | Letra a          |
| 98    | b        | Letra b          |
| ...   | ...      | ...              |
| 127   | DEL      | Delete           |

## Tabla EBCDIC
EBCDIC (Extended Binary Coded Decimal Interchange Code) es un código de caracteres desarrollado por IBM y utilizado principalmente en sus sistemas mainframe. Cada carácter se representa mediante un valor numérico en el rango de 0 a 255. EBCDIC es un código de 8 bits.

### Características
- **Rango:** 0-255
- **Tipo:** Código de 8 bits
- **Uso:** Predominantemente en sistemas IBM mainframe.
- **Compatibilidad:** Menos compatible con sistemas modernos en comparación con ASCII.

### Estructura
- **0-63 y 255:** Caracteres de control (no imprimibles)
- **64-254:** Caracteres imprimibles (letras, números, signos de puntuación, etc.)

### Tabla de Caracteres EBCDIC
| Valor | Carácter | Descripción      |
|-------|----------|------------------|
| 0     | NUL      | Null             |
| 1     | SOH      | Start of Heading |
| 2     | STX      | Start of Text    |
| ...   | ...      | ...              |
| 193   | A        | Letra A          |
| 194   | B        | Letra B          |
| ...   | ...      | ...              |
| 129   | a        | Letra a          |
| 130   | b        | Letra b          |
| ...   | ...      | ...              |
| 255   | NUL      | Null             |

## Comparación ASCII vs EBCDIC

| Característica   | ASCII           | EBCDIC          |
|------------------|-----------------|-----------------|
| Bits por carácter| 7               | 8               |
| Rango de valores | 0-127           | 0-255           |
| Uso principal    | Sistemas informáticos y telecomunicaciones| Sistemas IBM mainframe |
| Compatibilidad   | Alta            | Baja            |

### Ventajas y Desventajas

**ASCII:**
- **Ventajas:** Amplia adopción, compatibilidad con la mayoría de los sistemas modernos.
- **Desventajas:** Limitado a 128 caracteres, no incluye caracteres de otros idiomas.

**EBCDIC:**
- **Ventajas:** Compatible con sistemas IBM, mayor rango de caracteres.
- **Desventajas:** Menos compatible con sistemas modernos, menos adoptado fuera de los entornos IBM.
