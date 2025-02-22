# 📌 Antes de empezar
- entramos a nuestra maquina virtual con debia12 sin GUI
- entramos a nuestro usuario 
- entramos al super usuario
![[Pasted image 20250219050032.png]]

---

como buena practica digitamos

```shell
sudo apt update
```

>[!info] nota del editor
>`sudo apt update` actualizar la lista de paquetes disponibles en los repositorios del sistema. No instala ni actualiza paquetes, solo actualiza la información de los repositorios.


 esperamos que se actualice y luego ejecutamos 

```shell
sudo apt upgrade
```

>[!info] nota del editor
>`sudo apt upgrade` instala las versiones más recientes de los paquetes que ya están instalados en tu sistema, siempre que no requieran la eliminación de otros paquetes.

---

# 📌 Instalación de MySQL en Debian 12 (Bookworm)

## 1️⃣ Agregar el repositorio de MySQL

Ejecuta los siguientes comandos para descargar el paquete de configuración del repositorio de MySQL:

```bash
wget https://dev.mysql.com/get/mysql-apt-config_0.8.29-1_all.deb
```

![[Pasted image 20250219055939.png]]


Luego, instala el paquete con:

```bash
sudo dpkg -i mysql-apt-config_0.8.29-1_all.deb
```
![[Pasted image 20250219060219.png]]

les abrirá una ventana 

seleccionan la **primera opcion** y **enter**

![[Pasted image 20250219060058.png]]

seleccionan la **primera opción** y **enter**

![[Pasted image 20250219060118.png]]

seleccionan **Ok** y **enter**

![[Pasted image 20250219060144.png]]

Después, actualiza los repositorios:

```bash
sudo apt update
```

---

## 2️⃣ Instalar MySQL Server

Ejecuta el siguiente comando para instalar el servidor de MySQL:

```bash
sudo apt install -y mysql-server
```

![[Pasted image 20250219060359.png]]

📌 Durante la instalación, te pedirá que configures una contraseña para el usuario **root** de MySQL.

![[Pasted image 20250219060457.png]]

seleccionan la **primera opción** y **enter**

![[Pasted image 20250219060550.png]]


---

## 3️⃣ Verificar que MySQL está corriendo

Después de la instalación, verifica que el servicio esté activo con:

```bash
sudo systemctl status mysql
```

![[Pasted image 20250219060633.png]]


Si no está activo, inicia el servicio con:

```bash
sudo systemctl start mysql
```

Para que MySQL se inicie automáticamente al arrancar el sistema, usa:

```bash
sudo systemctl enable mysql
```

---

## 4️⃣ Acceder a MySQL

Para iniciar sesión en MySQL como **root**, usa:

```bash
sudo mysql -u root -p
```

![[Pasted image 20250219060804.png]]

📌 Introduce la contraseña que configuraste durante la instalación.

Verifica la versión con:

```sql
SELECT version();
```

![[Pasted image 20250219061001.png]]


Para salir de MySQL, usa:

```sql
EXIT;
```

![[Pasted image 20250219061053.png]]

---
>[!info]  **Notas**:
>- Los archivos de configuración de MySQL se encuentran en `/etc/mysql/`
>- La base de datos se almacena en `/var/lib/mysql/`
>- Para administrar usuarios y permisos, usa `mysql -u root -p` y los comandos `CREATE USER`, `GRANT`, `REVOKE`

🚀 ¡MySQL está listo para usar en tu Debian 12! 🎯