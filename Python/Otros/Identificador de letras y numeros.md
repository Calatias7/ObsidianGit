```python

def es_numero(cadena):
    # Verifica si la cadena es un número entero o decimal
    try:
        if cadena.endswith('.'):
            return False
        float(cadena)  # Intenta convertir a número
        return True
    except ValueError:
        return False

# Solicitar entrada al usuario
entrada = input("Ingrese una cadena (máx. 25 caracteres): ")

# Verificar longitud
if len(entrada) > 25:
    print("Error: La cadena no debe superar los 25 caracteres.")
else:
    if es_numero(entrada):
        print("La entrada es un número.")
    else:
        print("La entrada es una cadena de texto.")

```