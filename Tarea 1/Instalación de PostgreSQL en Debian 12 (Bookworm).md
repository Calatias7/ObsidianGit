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

# 📌 Instalación de PostgreSQL en Debian 12 (Bookworm)

## 1️⃣ Agregar el repositorio oficial de PostgreSQL

Ejecuta los siguientes comandos para agregar el repositorio y la clave GPG:

```bash
sudo apt update && sudo apt install -y curl ca-certificates gnupg

curl -fsS https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo gpg --dearmor -o /usr/share/keyrings/postgresql-keyring.gpg
```

>[!success] **¿Para qué sirve?**  
🔹 Esto es **importante** para asegurar que los paquetes provengan de fuentes legítimas y no hayan sido manipulados.

---
![[Pasted image 20250219052326.png]]
![[Pasted image 20250219053406.png]]

```
echo "deb [signed-by=/usr/share/keyrings/postgresql-keyring.gpg] http://apt.postgresql.org/pub/repos/apt bookworm-pgdg main" | sudo tee /etc/apt/sources.list.d/pgdg.list
```

>[!success] **¿Para qué sirve?**  
>El repositorio de PostgreSQL en **Debian predeterminado** no siempre contiene las versiones más recientes. Al agregar este repositorio, puedes instalar **versiones más actualizadas** de PostgreSQL.

![[Pasted image 20250219053803.png]]

Luego, actualiza la lista de paquetes:

```bash
sudo apt update
```
![[Pasted image 20250219053940.png]]


---

## 2️⃣ Instalar PostgreSQL

Para instalar PostgreSQL 16 (última versión estable), ejecuta:

```bash
sudo apt install -y postgresql postgresql-contrib
```

![[Pasted image 20250219054058.png]]

---

## 3️⃣ Verificar el estado del servicio

Después de la instalación, asegúrate de que el servicio está corriendo:

```bash
sudo systemctl status postgresql
```

![[Pasted image 20250219054236.png]]

Si no está activo, inícialo con:

```bash
sudo systemctl start postgresql
```

Habilítalo para que se inicie automáticamente al arrancar el sistema:

```bash
sudo systemctl enable postgresql
```

![[Pasted image 20250219054341.png]]

---

## 4️⃣ Acceder a PostgreSQL

PostgreSQL crea un usuario llamado `postgres` por defecto. Para acceder a la terminal de PostgreSQL, usa:

```bash
sudo -i -u postgres psql
```

![[Pasted image 20250219054453.png]]

Verifica la versión con:

```sql
SELECT version();
```

![[Pasted image 20250219054523.png]]


Para salir de la terminal de PostgreSQL, escribe:

```sql
\q
```

![[Pasted image 20250219054551.png]]

---

>[!info] **Notas**:
>- PostgreSQL se instala en la ruta `/var/lib/postgresql/`
>- Los archivos de configuración se encuentran en `/etc/postgresql/`
>-  Puedes gestionar los accesos y permisos mediante `pg_hba.conf`

🚀 ¡PostgreSQL está listo para usar en tu Debian 12! 🎯
