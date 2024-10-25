
descargan el sql developer

una vez descargado

se van a la carpeta zip o rar
 descomprimen
 ![[Pasted image 20241022142851.png]]
 buscan la aplicación y lo ejecutan
 ![[Pasted image 20241022142918.png]]
para conectar oracle es igual a como lo hacemos en el laboratorio

![[Pasted image 20241022143151.png]]

en name el nombre que quieran

tipo de base de datos solo les aparecera ORACLE

usuario con el usuario de la base de datos puede ser sys as sysdba, system as sysdba o el que creamos en mi caso es VMENDEZ

su respectiva contraseña

y dejan el host por defecto ya que el oracle lo tenemos en nuestra maquina
el puerto es 1521 de oracle si le cambiaron el puerto usen el puerto que tiene configurado
la base por defecto es xe

le dan en probar y si todo sale bien les conecta y ya tienen el oracle en el sql developer

## DB2 en sql developer

ahora para conectar el db2 en sql developer necesitamos hacer unas pequeñas configuraciones antes
se van al apartado donde dice herramientas

![[Pasted image 20241022143608.png]]

luego preferencias
![[Pasted image 20241022143648.png]]
luego en donde dice base de datos
![[Pasted image 20241022143718.png]]
expannden y en dnnde dice controladores de JDBC de terceros

![[Pasted image 20241022143749.png]]

le dan en el apartado donde dice agregar entrada
![[Pasted image 20241022143845.png]]
y buscan el jdbc de db2 en donde lo haya puesto

` db2jcc4.jar`

y lo añaden

![[Pasted image 20241022144004.png]]
 le dan aceptar y reinician la aplicación
ahora añaden una nueva conexion
![[Pasted image 20241022144114.png]]

en donde dice tipo de base de datos le dan en la flechita y seleccionan db2 que ya les tendria que aparecer
![[Pasted image 20241022144206.png]]

en el nombre el nombre que ustedes quieran 

en usuario es el usuario de la base de datos en mi caso es

`db2inst1` 

con su respectiva contraseña

en nombre de host la ip de su maquina virtual en donde esta el db2 instalado 
en mi caso era `192.168.1.3`

el puerto en usen el de db2 en mi caso era el  `50001`

base de datos el nombre de la base de datos en mi caso es VMENDEZ

y le dan en proobar y si todo lo hiciron bien les conectara recuerden tener el db2 inicializado

ya con eso tendrian el db2 y el oracle

![[Pasted image 20241022144712.png]]





