# 📌 Antes de empezar
- entramos a nuestra maquina virtual con debia12 con GUI
- entramos a la terminal 
- entramos al super usuario

![[Pasted image 20250219140348.png]]

![[Pasted image 20250219140430.png]]

como buena practica digitamos

```shell
sudo apt update
```

 esperamos que se actualice y luego ejecutamos 

```shell
sudo apt upgrade
```

>[!info] nota del editor
>para la instalacion lo haremos por comandos en la terminal por que no somos capa 8

---

# Instalación de SQuirreL SQL

## 1. Descargar SQuirreL SQL

Puedes descargar la última versión desde la página oficial o usar `wget` en la terminal:

```bash
wget https://sourceforge.net/projects/squirrel-sql/files/latest/download -O squirrel-sql-installer.jar
```

![[Pasted image 20250219162532.png]]
![[Pasted image 20250219162606.png]]

## 2. Instalar Java (si no lo tienes)

SQuirreL SQL requiere **Java 17 o superior**. Asegúrate de tenerlo instalado:

```bash
java -version
```

![[Pasted image 20250219162729.png]]

Si no tienes Java, instálalo con:

```bash
sudo apt install openjdk-17-jdk -y
```

## 3. Instalar SQuirreL SQL

Ejecuta el instalador con:

```bash
java -jar squirrel-sql-installer.jar
```

![[Pasted image 20250219162803.png]]


![[Pasted image 20250219162818.png]]

# **Elegimos la ruta de instalación**
en este caso la dejare por defecto en  `/usr/local/squirrel-sql-snapshot-20250216_2134`

![[Pasted image 20250219162906.png]]

# **Elegimos los plugin que necesitemos**

>[!info] nota del editor
>aca elegi el db2, oracle, postgres y el paquete de idioma español

>[!success] **¿Para qué sirve?**  
>**SQL Parametrisation**
>**SQL Replace**
>**SQL Validator**
>Estos plugins pueden mejorar la experiencia de desarrollo en SQuirreL SQL al ofrecer herramientas para optimizar y validar consultas antes de ejecutarlas.


![[Pasted image 20250219163014.png]]

![[Pasted image 20250219163046.png]]

# **finalizacion de la instalacion**

![[Pasted image 20250219163118.png]]

>[!info] notas del editor
>seleccione la casilla `Create additional shortcuts on the desktop`
>para crear un acceso directo en el escritorio

listo con esto nos abra finalizado la instalacion y la creacion un acceso directo en el escritorio

![[Pasted image 20250219163613.png]]
## 4. Ejecutar SQuirreL SQL(opcional)

En un dado caso no, nos genera un acceso directo en el escritorio crearemos un lanzador
click derecho -> crear un lanzador

![[Pasted image 20250219151504.png]]

en tipo seleccionan aplicación
nombre el nombre que le quieran poner
orden la ruta de la aplicación es esta caso esta en `/usr/local/squirrel-sql-snapshot-20250216_2134`

![[Pasted image 20250219164143.png]]

seleccionamos el archivo `squirrel-sql.sh`

![[Pasted image 20250219164131.png]]

nos crea el lanzador

![[Pasted image 20250219164310.png]]