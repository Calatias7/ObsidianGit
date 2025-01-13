#  Variables y Memoria RAM en Python

## **Concepto de Variable**

Una variable es un contenedor o identificador que se utiliza para almacenar datos en la memoria RAM.

- En Python, las variables no necesitan declararse con un tipo específico; su tipo se determina automáticamente en tiempo de ejecución.
- Las variables son referencias a ubicaciones en la memoria donde los datos están almacenados.

**Sintaxis básica:**

```python
nombre_variable = valor
```

>[!note] Nota: 
>En Python no se puede usar una variable sin antes haberle asignado un valor.


**Características:**

1. Pueden cambiar su valor durante la ejecución del programa.
2. Pueden contener diferentes tipos de datos como números, cadenas, listas, etc.

---

## **Concepto de Memoria RAM en Python**

La memoria RAM es donde se almacenan los datos y las instrucciones que el programa necesita para ejecutarse.

- Cada vez que se asigna un valor a una variable, Python reserva un espacio en la RAM para almacenar ese valor.
- Python utiliza un **gestor de memoria** que se encarga de liberar espacio automáticamente (garbage collector).

### **Cómo funciona en Python**

1. **Asignación de Memoria**: Cuando defines una variable, Python guarda el valor en un lugar de la memoria y asocia la variable con ese valor.
2. **Identidad y Referencia**: Cada valor tiene una identidad única (dirección en la memoria), que puedes verificar con la función `id()`.

Ejemplo:

```python
x = 10  # Python asigna memoria para almacenar el valor 10
print(id(x))  # Muestra la dirección en memoria de x
```

---

## **Ejemplo Completo**

### Variables y cómo se almacenan en memoria

```python
# Asignar valores a variables
a = 5           # Entero
b = "Hola"      # Cadena de texto
c = [1, 2, 3]   # Lista

# Imprimir variables
print(a)  # Salida: 5
print(b)  # Salida: Hola
print(c)  # Salida: [1, 2, 3]

# Ver dirección en memoria
print(id(a))  # Muestra la dirección de la variable 'a'
print(id(b))  # Muestra la dirección de la variable 'b'
```

---

### Gestión de Memoria Automática

Python utiliza el **recolector de basura** para liberar memoria cuando un objeto ya no es referenciado por ninguna variable.

```python
x = 100
y = x  # Ambas variables apuntan al mismo objeto en memoria
x = None  # El valor 100 todavía está referenciado por 'y'

print(y)  # Salida: 100
```

---

## **Notas importantes**

- Una **variable** no almacena el valor directamente, sino que referencia una ubicación en memoria.
- La RAM es limitada, por lo que es importante evitar ocuparla innecesariamente (por ejemplo, creando objetos grandes sin necesidad).
- Usa funciones como `del` para eliminar referencias explícitamente, aunque no suele ser necesario debido al recolector de basura.
