# 📌Antes de la instalación
Necesitamos tener  al menos la  versión 11 de Java Development Kit (JDK) 
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

# Instalación de JDK 17 en Debian 12

## 1. Actualizar los repositorios

Abre la terminal y ejecuta:

```bash
sudo apt update && sudo apt upgrade -y
```

## 2. Instalar OpenJDK 17

Para instalar la versión de OpenJDK 17 (versión de código abierto de Java):

```bash
sudo apt install openjdk-17-jdk -y
```

![[Pasted image 20250219140941.png]]

## 3. Verificar la instalación

Comprueba que la instalación fue exitosa ejecutando:

```bash
java -version
```

Si ves una salida similar a esta, significa que Java 17 está instalado correctamente:

```plaintext
openjdk version "17.0.x" 202x-xx-xx
OpenJDK Runtime Environment (build 17.0.x+xx)
OpenJDK 64-Bit Server VM (build 17.0.x+xx, mixed mode)
```

![[Pasted image 20250219141142.png]]

---
# 📌 Instalación de SQL Developer 23 en Debian 12 (Bookworm)
# **1. Descargar SQL Developer 23**

SQL Developer no está en los repositorios de Debian, por lo que debes descargarlo manualmente desde el sitio oficial de Oracle:

1. Ve a la página de descargas de Oracle SQL Developer:
    
    - [Oracle SQL Developer Downloads](https://www.oracle.com/database/sqldeveloper/technologies/download/)
2. Descarga la versión `.zip` de **SQL Developer 23**.

![[Pasted image 20250219142116.png]]

![[Pasted image 20250219142702.png]]

## **2. Extraer el archivo**
Una vez descargado nos dirigimos a la carpeta de descargas y listamos para asegurarnos  que existe el  archivo 
```bash
cd Descargas/

ls
```

![[Pasted image 20250219144216.png]]

 extrae el archivo ejecutando:
```bash
unzip sqldeveloper-23.x.x-xxxxx.zip -d /opt/
```

>[!warning] 
>cambian `sqldeveloper-23.x.x-xxxxx.zip` por el nombre de su archivo

nos dirigimos a la carpeta opt y listamos nos aparecera la carpeta sql developer

```bash
cd /opt

ls
```

![[Pasted image 20250219145240.png]]

# (opcional)
#  **Ejecutar SQL Developer**

## **1. Crear un script de ejecución**

Para ejecutar **SQL Developer** :

```bash
sudo nano /usr/local/bin/sqldeveloper
```

### **Agregar el siguiente contenido al archivo:**

```bash
#!/bin/bash
/opt/sqldeveloper/sqldeveloper.sh
```

![[Pasted image 20250219150133.png]]

Guarda los cambios (`CTRL + X`, `S`, `ENTER`).

### **Guardar y dar permisos de ejecución:**

```bash
sudo chmod +x /usr/local/bin/sqldeveloper
```

---

## **Ejecutar SQL Developer**

Ahora puedes ejecutarlo desde la terminal con:

```bash
sqldeveloper
```

# **2. Crea un acceso directo como capa8**

abres tu gestor de archivos y te vas a la ruta de instalacion en mi caso es
`/opt/sqldeveloper/sqldeveloper/bin`

![[Pasted image 20250219150839.png]]

click derecho al archivo `sqldeveloper` crea un enlace  a escritorio
![[Pasted image 20250219151341.png]]

en dado caso que no les deje crear un enlace 


# **2. Crea un lanzador**

click derecho -> crear un lanzador

![[Pasted image 20250219151504.png]]

en tipo seleccionan aplicacion
nombre el nombre que le quieran poner
orden la ruta de la aplicacion es esta caso esta en `/opt/sqldeveloper/sqldeveloper/bin`
![[Pasted image 20250219151844.png]]

selecciona sqldeveloper y abrir

![[Pasted image 20250219151646.png]]

les creara un lanzador

![[Pasted image 20250219152058.png]]

🚀 ¡Sql developer está listo para usar en tu Debian 12! 🎯