Nos dirigimos a descargar jaspersoft 
https://www.jaspersoft.com/products/jaspersoft-community

![[Pasted image 20241023044048.png]]

seleccionamos el sistema operativo que usemos

![[Pasted image 20241023044111.png]]

Extraen y ejecutan el archivo .exe

![[Pasted image 20241026164751.png]]

para crear una conexion a una base  de datos usando el JDBC se van a la pestaña `Data Adapters` 
![[Pasted image 20241023044017.png]]
luega Create Data Adapter

![[Pasted image 20241023052605.png]]
seleccionan la `Opción Database JDBC Connection`


![[Pasted image 20241023052631.png]]

seleccionan el driver con la base que quieren conectarse  en este caso es Oracle

![[Pasted image 20241023052714.png]]

Rellenan los datos 
JDBC Url ponen la urls de su base de datos 
Username el usuario con el que se conectan a la base con su respectiva contraseña 

![[Pasted image 20241023052858.png]]

luego nos metemos en el apartado `Connection Properties`

![[Pasted image 20241023052841.png]]
aca seleccionamos el .jar de la base al cual nos conectaremos

![[Pasted image 20241023052916.png]]

![[Pasted image 20241023052936.png]]
luego de es le damos a test 
![[Pasted image 20241023052946.png]]
si todo esta bien nos conectara a la base
![[Pasted image 20241023053004.png]]

![[Pasted image 20241023053033.png]]
lo mismo para DB2

![[Pasted image 20241023053239.png]]

![[Pasted image 20241023053222.png]]
 para crear un nuevo reporte  seleccioamos nuevo y jasper Report
 
![[Pasted image 20241023054121.png]]

seleccionamos una platilla o una hoja en blanco 

![[Pasted image 20241023054152.png]]

seleccionamos la carpeta en donde se guardara nuestro reporte 
![[Pasted image 20241023054210.png]]
aca seleccionamos el adapatador que configuramos en este caso puede ser para Oracle o para DB2
![[Pasted image 20241023054302.png]]

![[Pasted image 20241023054247.png]]
se conectara y en table aparecerá las tablas que hemos hecho con el usario de la base de datos 
![[Pasted image 20241026174335.png]]

seleccionamos por medio de un Query las tablas que querramos usar para el reporte
![[Pasted image 20241026174324.png]]
seleccionamos  las columnas que queramos usar 
![[Pasted image 20241026174407.png]]

agregamos en nuestro entorno de trabajo

![[Pasted image 20241026180205.png]]

y visualizamos el reporte

![[Pasted image 20241026180310.png]]


