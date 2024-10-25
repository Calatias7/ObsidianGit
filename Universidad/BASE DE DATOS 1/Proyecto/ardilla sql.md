ingresan al debian donde tiene instalado el db2
ingresen con el usuario de la base de datos `su - db2inst1`
ejecuten el siguente comando para buscar los JDBC de db2

```shell
find /opt/ibm/db2 -name "db2jcc*.jar"
```
![[Pasted image 20241022065037.png]]
Para conectar DB2 con SQuirreL SQL, debes usar uno de los controladores JDBC listados en tu búsqueda. En tu caso, los archivos que son controladores JDBC son:

1. `/opt/ibm/db2/V11.1/java/db2jcc4.jar`
2. `/opt/ibm/db2/V11.1/java/db2jcc.jar`

**Verifica la IP del servidor DB2**:utilizando el comando `ifconfig` o `ip a` en el servidor
![[Pasted image 20241022065533.png]]

en mi caso es `192.168.1.3`


copian los archivos antes mencionados a su maquina fisica pueden usar WINscp
![[Pasted image 20241022070849.png]]

se dirijen a donde estan los archivos en mi caso es `/opt/ibm/db2/V11.1/java/` copian y pegan los archivos `db2jcc4.jar` y `db2jcc.jar` a donde se les facilite encontrarlos
![[Pasted image 20241022071112.png]]
### Pasos para configurarlo en SQuirreL SQL:

Abre SQuirreL SQL.

Ve a **Drivers** en el menú principal.

Selecciona **DB2** o crea un nuevo driver si no aparece.
![[Pasted image 20241022071415.png]]
En la configuración del driver, agrega el archivo **`db2jcc4.jar`** como el archivo JAR para el controlador. 

le dan add y añaden los jar dejando en `db2jcc4.jar` como primero
![[Pasted image 20241022071528.png]]

5. Configura la URL de conexión como:
```
jdbc:db2://<hostname>:<port>/<database>

```


Para ver qué puerto está utilizando DB2, puedes usar el siguiente comando dentro de la interfaz de comandos de DB2 (DB2 Command Line Processor, `db2`).

1. **Inicia la interfaz de comandos de DB2**:
   Primero, asegúrate de estar conectado a la instancia de DB2:

   ```bash
   db2 connect to <nombre_base_datos>
   ```
 en mi caso fue
   ```bash
   db2 connect to VMENDEZ
   ```

   Si no sabes el nombre de la base de datos, puedes usar el siguiente comando para listar las bases de datos en la instancia:

   ```bash
   db2 list db directory
   ```

2. **Consulta el puerto en uso**:
   Una vez conectado, puedes ejecutar el siguiente comando para ver los detalles de la configuración de comunicación de DB2, que incluye el puerto en uso:

   ```bash
   db2 get dbm cfg | grep -i svcename
   ```

   Este comando devolverá el valor de `SVCENAME`, que es el nombre del servicio configurado para la comunicación TCP/IP. El nombre del servicio puede ser un nombre o un número de puerto.
![[Pasted image 20241022070022.png]]
en mi caso el puerto de db2 es el 50001

no olviden levantar el db2 

`db2start`
 ![[Pasted image 20241022070359.png]]
![[Pasted image 20241022071648.png]]

ahora se van al apartado de aliasses y crean uno nuevo

![[Pasted image 20241022071801.png]]

en driver seleccionan el de db2 
en name el que ustedes quieran 
la url la que habias dicho anteriormente 
en usar name el usuario con el que se conecta en la base de datos
y su respectiva contraseña

le dana test 
![[Pasted image 20241022072120.png]]
y luego connect si sale todo bien 
![[Pasted image 20241022072030.png]]

y luego ya le pueden dar en connect
 y ya crearon el enlace de db2 a squirrel sql

lo mismo con oracle

solo que como es en la maquina fisica usen el cmd para ver su ip con `ipcofig`

el JDBC si lo descargue en el Sitio oficial de oracle y el driver use el ORACLE thin driver
![[Pasted image 20241022072951.png]]

En el alisses pueden usar ya sea el usuario que creamos o el `sys as sysdba`
es mejor usar el sys as system ante cualquer duda

el puerto por defecto es 1521 y la base es XE


![[Pasted image 20241022072247.png]]
![[Pasted image 20241022072829.png]]


y ya podran tener db2 y oracle al mismo tiempo funcionado e interactuando sin la nececidad de los shell
solo que con db2 tiene que tener la maquina virtal prendida y el db2 inicializado

![[Pasted image 20241022073235.png]]


