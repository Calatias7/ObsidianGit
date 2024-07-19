En el contexto de bases de datos, una **tabla** es una estructura que organiza datos en filas y columnas. Es el componente fundamental de una base de datos relacional y permite almacenar información de manera estructurada y accesible.

### Estructura de una Tabla

1. **Filas (Registros)**: Cada fila en una tabla representa una única entrada o registro de datos. Cada registro contiene información completa sobre una entidad específica.
2. **Columnas (Campos)**: Cada columna en una tabla representa un atributo de los datos. Por ejemplo, en una tabla de `Clientes`, las columnas podrían ser `ID`, `Nombre`, `Correo Electrónico`, etc.

### Ejemplo de una Tabla de Base de Datos Relacional

#### Tabla: Clientes

| ID  | Nombre        | Correo Electrónico        | Teléfono     |
| --- | ------------- | ------------------------- | ------------ |
| 1   | John Doe      | john.doe@example.com      | 123-456-7890 |
| 2   | Jane Smith    | jane.smith@example.com    | 098-765-4321 |
| 3   | Alice Johnson | alice.johnson@example.com | 555-123-4567 |
|     |               |                           |              |

### Componentes de una Tabla

- **Nombre de la Tabla**: Identificador único para la tabla dentro de la base de datos.
- **Campos (Columnas)**: Nombres de las columnas que describen los atributos de la tabla.
- **Filas (Registros)**: Conjunto de valores en cada columna que representa una entrada completa en la tabla.
- **Tipos de Datos**: Cada columna tiene un tipo de dato definido (por ejemplo, `INT`, `VARCHAR`, `DATE`).
### Creación de una Tabla en SQL
```sql
CREATE TABLE Clientes (
    ID INT PRIMARY KEY,
    Nombre VARCHAR(100),
    Correo_Electronico VARCHAR(100),
    Telefono VARCHAR(15)
);
```

### Inserción de Datos en una Tabla
```sql
INSERT INTO Clientes (ID, Nombre, Correo_Electronico, Telefono)
VALUES (1, 'John Doe', 'john.doe@example.com', '123-456-7890');

```

### Consulta de Datos en una Tabla
```sql
SELECT * FROM Clientes;

```

### Diagrama de una Tabla

```mermaid
classDiagram
    class Clientes {
        INT ID
        VARCHAR(100) Nombre
        VARCHAR(100) Correo_Electronico
        VARCHAR(15) Telefono
    }

```

### Uso de Tablas en Bases de Datos

- **Organización de Datos**: Permiten organizar grandes volúmenes de datos de manera estructurada.
- **Relaciones entre Datos**: Facilitan la creación de relaciones entre diferentes conjuntos de datos mediante claves primarias y foráneas.
- **Consulta y Manipulación de Datos**: Las tablas son la base para realizar operaciones CRUD (Crear, Leer, Actualizar, Eliminar) en bases de datos relacionales.
****

###### Temas relacionados
[[Tipos de Datos en Base de datos]]

****
