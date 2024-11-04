se van al siguiente link 

https://www.ibm.com/support/pages/download-db2-fix-packs-version-db2-linux-unix-and-windows

estos son los fixpacks de db2 para descargar el OBDC db2 for windows
![[Pasted image 20241022145617.png]]

- ahora bien 
- antes de descargar algún archivo 
- vayan a su maquina virtual en donde este instalado db2 
- ingresan  con el usuario de la base de datos y ejecutan lo siguiente :`db2level`

![[Pasted image 20241022145755.png]]
aca les aparece la version de db2 y lo importante el fix pack

en mi caso es la version 11.1.4.4 y el fixpack 4

ahora en link buscan la version v11.1 y el fixpack4 en este caso podemos observar que tenemos hasta el fixpack 7 con un asterisco  lo que indica que es el Fix Pack final para esta versión es recomendable usar esta por aquello de que las versiones anteriores tengan bugs 

recuerden descargar el fixpack que les corresponda

![[Pasted image 20241022150436.png]]

seleccionan el sistema en este caso Windows
despliegan y selecciona este caso la primera opción 

![[Pasted image 20241022150546.png]]

la primera opción si les pide conectar a una cuenta usen la que crearon para descargar db2 

![[Pasted image 20241022150643.png]]

y le dan en descargar para este caso pesa 1.35gb

![[Pasted image 20241022150822.png]]

una vez descargado ejecutan el archivo exe

les abrira una pantalla como esta![[Pasted image 20241022151435.png]]

busca una carpeta para extraer en mi caso cree una en descargas 
![[Pasted image 20241022151434.png]]
 y una vez  sabiendo en donde lo van a extraer le dan un unzip esperan que se extraiga todo y cierran la ventana
 les creara una carperta llamada universal
 ![[Pasted image 20241022151647.png]]
![[Pasted image 20241022151757.png]]
y busca el setup.exe y lo ejecutan

![[Pasted image 20241022151824.png]]

le damos en donde dice instalar un producto 
buscamos hasta encontra IBM Data Server Cliente 

![[Pasted image 20241022152259.png]]
le dan en instalar nuevo

![[Pasted image 20241022152434.png]]

le da síguete aceptan términos y condiciones una vez leídos xd
luego seleccionamos tipica y siguente


![[Pasted image 20241022152554.png]]

aca dejamos la opcion por defecto intarlar IMB data server.... y siguente
![[Pasted image 20241022152752.png]]

le dan en siguente

![[Pasted image 20241022152934.png]]
les aparece un cuadro como este solo acepten 
![[Pasted image 20241022153123.png]]


nos muestra lo que se va instalar revisamos que venta sporte de odbc  y le damos en finalizar
![[Pasted image 20241022153210.png]]
![[Pasted image 20241022153332.png]]
![[Pasted image 20241022153454.png]]


 ahora configuramos el ODBC 
vamos al buscador y escribimos `origenes de datos ODBC` en mi caso es de 64bits

![[Pasted image 20241022153806.png]]
![[Pasted image 20241022153908.png]]

nos vamos a la pestaña DNS de sistemas

![[Pasted image 20241022153942.png]]

y luego agregar

![[Pasted image 20241022154113.png]]

- si no hicimos la instalación anterior no nos aparecerá los los ODBC
- en este caso las dos opciones son validas 
- `IBM DB2 ODBC DRIVER`
- `IBM DB2 ODBC DRIVER -DB2COPY1`
- seleccionamos cualquiera
- pongan un nombre para identificar luego en añadir 
![[Pasted image 20241022154313.png]]

- descripción cualquier cosa que les sirva para ver para que sirve
- id de usuario el usuario en el que se conecta la base de datos y su respectiva contraseña 
![[Pasted image 20241022154743.png]]


ahora la siguente pestaña TCP/IP

![[Pasted image 20241022154938.png]]

- Nombre de la base en mi caso es `VMENDEZ`
- alias ponemos el mismo nombre de la base en mi caso VMENDEZ
- nombre del sistema principal en este caso es la` IP `de la maquina donde tenemos el db2
- y el puerto en mi caso es el `50001`
- si aparece marcada la opción la base de datos reside la desmarcamos
- le dan aceptar y aceptar 
![[Pasted image 20241022155258.png]]

cierran la ventana y vuelvan abrir y le dan en la pestaña DSN de sistema

![[Pasted image 20241022162137.png]]

y le dan configurar
![[Pasted image 20241022162232.png]]

prueben a ver si les conecta ingresando la contraseña y  pulsando el boton conectar
![[Pasted image 20241022162305.png]]

lo mismo con oracle

pero antes revisen si ya tienen 
![[Pasted image 20241022165007.png]]
en 

![[Pasted image 20241022165029.png]]

si no hagan esto
https://www.oracle.com/database/technologies/instant-client/downloads.html
antes de descargar cualquier cosa entren a sqlplus
ingresan y ejecuten lo siguente
````shell
select * from v$version;
````

![[Pasted image 20241022164121.png]]

en este caso es la 21
![[Pasted image 20241022164610.png]]

buscan ODBC package

![[Pasted image 20241022164639.png]]

descargan y descomprimen y ejecuten el archivo

![[Pasted image 20241022165145.png]]

si no les aparece aun intenten reiniciar la pc
volvemos a 
![[Pasted image 20241022165029.png]]

![[Pasted image 20241022165247.png]]

agregar selección cualquiera de las dos o la que les aparezca

![[Pasted image 20241022165323.png]]

RELLENAN LOS DATOS

- DATA SOURCE NAME EL NOMBRE DE LA CONECCION
- descripción algo para saber que es
- TNS service name el nombre de la base por defecto es `XE`
- user ID el usuario para conectar a la base puede ser `SYS, SYSTEM`, o el usuario que creamos en mi caso es `VMENDEZ`
![[Pasted image 20241022165909.png]]

le dan en Test connection
![[Pasted image 20241022170145.png]]
si todo esta bien le dan en ok
![[Pasted image 20241022170210.png]]
le dan en aceptar y ok 

## MS-ACCESS 

abren acces 
luego nueva base
![[Pasted image 20241022162453.png]]
escogen el nombre que ustedes quieran y en crear

![[Pasted image 20241022162522.png]]

se dirigen a la barra de navegación en el apartado datos externos

![[Pasted image 20241022162612.png]]

luego nuevo origen de datos > de otros orignes > base de datos ODBC

![[Pasted image 20241022162647.png]]
acá seleccionan la opción vincular al origen de datos creando una tabla vinculada y le dan aceptar 
![[Pasted image 20241022162839.png]]
se van a la pestaña origenes de datos de equipo

![[Pasted image 20241022162908.png]]
y buscan la la conexión que crearon seleccionan y aceptar
![[Pasted image 20241022162933.png]]

conectan con el usuario y contraseña de la base de datos y le dan bien
![[Pasted image 20241022163047.png]] 
les aparecera las tablas que tienen en la base de datos
y seleccionan las que quieran utilizar
![[Pasted image 20241022163125.png]]

como ejemplo usare estas 3 y aceptar 
![[Pasted image 20241022163254.png]]

seleccionan los campos que quieran que aparezcan en este caso todos y así con todas las tablas que seleccionaron 

![[Pasted image 20241022163333.png]]
después de esto ya tendrían vinculadas las tablas de db2  que escogieron para hacer un reporte en MS ACCESS
![[Pasted image 20241022163424.png]]
![[Pasted image 20241022163509.png]]


y lo mismo solo que para oracle 
![[Pasted image 20241022170401.png]]

![[Pasted image 20241022170432.png]]


