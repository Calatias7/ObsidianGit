
**Solución 1:** Operador de Formato %
```python

# Declaracion de variables

nombre = ""
apellido = ""

#Solicitud de Datos
print(">>> Introduce tu nombre: ")
nombre = input("> ")
print(">>> Introduce tu apellido: ")
apellido = input("> ")

#Mensaje en Pantalla: Operador de Formato %
print("Hola %s %s, gusto en conocerte!" %(nombre,apellido))
```

___

**Solución 2:** Método .format()

Realiza una operación de formato de cadena. La cadena en la que se llama a este método puede contener texto literal o campos de reemplazo delimitados por llaves **{}**. Cada campo de reemplazo contiene el índice numérico (**0,1,2,3 ...**)  de un argumento posicional o el nombre de un argumento de palabra clave.

Devuelve una copia de la cadena donde cada campo  se reemplaza con el valor de cadena del argumento correspondiente.
```python
# Declaracion de variables
nombre = ""
apellido = ""

# Solicitud de Datos
print(">>> Introduce tu nombre: ")
nombre = input("> ")
print(">>> Introduce tu apellido: ")
apellido= input("> ")

# Mensaje en Pantalla: Metodo .format()
print("Hola {0} {1}, gusto en conocerte!".format(nombre,apellido))
```

>[!Tip]
>**`input`:** Captura el texto que el usuario ingresa y lo almacena en la variable `nombre` y lo mismo con la variable `apellido`
>**`format`:** Reemplaza los marcadores `{0}` y `{1}` por los valores de las variables `nombre` y `apellido`.

___

**Solución 3:** _f-strings_

Los literales de cadena con formato tienen el prefijo **'f'** (Disponibles desde la version de **Python 3.6**) y son similares a las cadenas de formato aceptadas por **str.format()**. Contienen campos de reemplazo rodeados por llaves **{}**. Los campos de reemplazo son expresiones, que se evalúan en tiempo de ejecución y luego se les da formato usando el protocolo **format()**:
```python

# Declaracion de variables
nombre = ""
apellido = ""

# Solicitud de Datos
print(">>> Introduce tu nombre: ")
nombre = input("> ")
print(">>> Introduce tu apellido: ")
apellido= input("> ")

# Mensaje en Pantalla: f-strings
print(f"Hola {nombre} {apellido}, gusto en conocerte!")
```