## Instalación de MySQL Workbench en Debian 12 GUI

### 1. Abrir la Terminal en Debian 12 GUI

Para comenzar, abre la terminal en tu sistema Debian 12.

### 2. Acceder como superusuario

Ejecuta el siguiente comando para obtener privilegios de superusuario:

```bash
su -
```

Introduce la contraseña cuando se solicite.

### 3. Actualizar repositorios del sistema

Ejecuta el siguiente comando para asegurarte de que los paquetes estén actualizados:

```bash
apt update
```

### 4. Instalar Snapd

Ejecuta el siguiente comando para instalar Snapd:

```bash
apt install snapd -y
```

![[Pasted image 20250222032524.png]]

### 5. Buscar MySQL Workbench en Snap

Ejecuta el siguiente comando para buscar MySQL Workbench:

```bash
snap search workbench | grep MySQL
```

![[Pasted image 20250222032628.png]]

Debe mostrar una línea similar a:

```bash
mysql-workbench-community 8.0.25 tonybolzan
```



### 6. Instalar MySQL Workbench

Ejecuta el siguiente comando para instalar MySQL Workbench:

```bash
snap install mysql-workbench-community
```

![[Pasted image 20250222032745.png]]
La descarga e instalación tomarán unos segundos. Espera hasta que aparezca el mensaje:

```bash
mysql-workbench-community 8.0.25 from tonybolzan installed
```

![[Pasted image 20250222034228.png]]

### 7. Salir del modo superusuario

Ejecuta el siguiente comando para salir del superusuario:

```bash
exit
```

### 8. Ejecutar MySQL Workbench

Para abrir MySQL Workbench, ejecuta el siguiente comando:

```bash
snap run mysql-workbench-community
```

Esto abrirá la aplicación MySQL Workbench en tu sistema Debian 12.

![[Pasted image 20250222035033.png]]