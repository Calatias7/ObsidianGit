### ¿Qué es SQL?

**SQL (Structured Query Language)** es un lenguaje de programación estándar diseñado para gestionar y manipular bases de datos relacionales. SQL permite a los usuarios crear, leer, actualizar y eliminar datos almacenados en bases de datos.

### Principales Características de SQL

1. **Declarativo**: SQL es un lenguaje declarativo, lo que significa que los usuarios especifican _qué_ datos desean obtener o modificar, sin necesidad de indicar _cómo_ hacerlo.
2. **Estándar**: SQL es un estándar internacionalmente reconocido para gestionar bases de datos relacionales, con implementaciones en sistemas de bases de datos como MySQL, PostgreSQL, SQL Server, Oracle, entre otros.
3. **Versátil**: SQL permite realizar una amplia gama de operaciones sobre los datos, incluyendo consultas, inserciones, actualizaciones, eliminaciones y administración de estructuras de base de datos.
****

### Principales Sentencias de SQL

#### Consultas (SELECT)

La sentencia `SELECT` se utiliza para recuperar datos de una o más tablas.

```sql
SELECT Nombre, Correo_Electronico
FROM Clientes
WHERE ID = 1;
```
****

#### Inserciones (INSERT)

La sentencia `INSERT` se utiliza para agregar nuevos registros a una tabla.

```sql
INSERT INTO Clientes (ID, Nombre, Correo_Electronico, Telefono)
VALUES (3, 'Alice Johnson', 'alice.johnson@example.com', '555-123-4567');
```
****


#### Actualizaciones (UPDATE)

La sentencia `UPDATE` se utiliza para modificar datos existentes en una tabla.
```sql
UPDATE Clientes
SET Correo_Electronico = 'alice.newemail@example.com'
WHERE ID = 3;
```
****


#### Eliminaciones (DELETE)

La sentencia `DELETE` se utiliza para borrar registros de una tabla.
```sql
DELETE FROM Clientes
WHERE ID = 3;
```
****


### Creación y Gestión de Estructuras de Base de Datos

#### Crear Tabla (CREATE TABLE)

La sentencia `CREATE TABLE` se utiliza para crear nuevas tablas en la base de datos.
```sql
CREATE TABLE Clientes (
    ID INT PRIMARY KEY,
    Nombre VARCHAR(100),
    Correo_Electronico VARCHAR(100),
    Telefono VARCHAR(15)
);
```
****


#### Modificar Tabla (ALTER TABLE)

La sentencia `ALTER TABLE` se utiliza para modificar la estructura de una tabla existente.
```sql
ALTER TABLE Clientes
ADD FechaNacimiento DATE;
```
****


#### Eliminar Tabla (DROP TABLE)

La sentencia `DROP TABLE` se utiliza para eliminar una tabla de la base de datos.
```sql
DROP TABLE Clientes;
```
****

### Funciones y Agregaciones en SQL

#### Funciones de Agregación

SQL proporciona funciones para realizar cálculos en un conjunto de valores.

**COUNT**: Cuenta el número de filas.
```sql
SELECT COUNT(*) FROM Clientes;
```
****


**SUM**: Suma los valores de una columna.
```sql
SELECT SUM(Precio) FROM Ventas;
```
****


**AVG**: Calcula el promedio de los valores de una columna.
```sql
SELECT AVG(Edad) FROM Empleados;
```
****


**MAX**: Encuentra el valor máximo de una columna.
```sql
SELECT MAX(Salario) FROM Empleados;
```
****


**MIN**: Encuentra el valor mínimo de una columna.
```sql
SELECT MIN(Salario) FROM Empleados;
```
****

##### Temas relacionados
[[CRUD Operations |Operaciones CRUD]]
[[Que es una base de datos]]
[[Tipos de sentencias SQL]]

****

