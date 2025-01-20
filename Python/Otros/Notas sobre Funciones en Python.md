**Notas sobre Funciones en Python**

1. **Definición y Uso de Funciones:**
   - Una función es un bloque de código que permite compactar y reutilizar partes del programa.
   - Las funciones pueden recibir datos (argumentos), procesarlos y devolver un resultado.

2. **Sintaxis de Funciones:**
   - **Definición:** `def nombre_funcion(argumentos):`
   - **Indentación:** El código dentro de la función debe estar indentado (generalmente 4 espacios).

3. **Pass:**
   - La sentencia `pass` se utiliza como un placeholder en funciones que aún no tienen implementado su código.

4. **Return vs. Print:**
   - **`return`:** Devuelve un valor desde una función y permite su uso posterior.
   - **`print`:** Muestra un valor en la consola, útil para depuración o salida de datos al usuario.
   - El uso de `return` interrumpe la ejecución del código restante en la función.

5. **Argumentos y Keyword Arguments:**
   - Los argumentos son las entradas que una función recibe.
   - Se pueden definir valores por defecto para los argumentos.
   - Los Keyword Arguments permiten especificar los argumentos en cualquier orden al llamar a la función.

6. **Scope (Alcance):**
   - **Local:** Variables definidas dentro de una función no son accesibles fuera de ella.
   - **Global:** Variables definidas fuera de cualquier función pueden ser accedidas desde cualquier parte del código.
   - Uso de `global` dentro de una función permite modificar una variable global.

7. **Indentación y Estilo de Código:**
   - PEP8 recomienda usar 4 espacios por nivel de indentación.
   - El uso de espacios o tabulaciones es una cuestión de preferencia, pero deben ser consistentes en todo el código.
