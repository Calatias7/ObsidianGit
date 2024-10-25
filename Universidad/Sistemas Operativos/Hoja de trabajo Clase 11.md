
1. **Cambiar tu clave de acceso actual y colocar una clave autorizada:**
     ```bash
     passwd
     ```
![[Pasted image 20241013121657.png]]

---
 
2. **Visualizar los permisos otorgados a los archivos y explicarlos:**
   ```bash
   ls -l /etc/passwd
   ls -l /etc/shadow
   ls -l /bin/login
   ls -l /bin/ls
   ls -l /etc/hosts
   ```
![[Pasted image 20241013122716.png]]
### Explicación de los permisos:
- el comando `ls -l /etc/passwd`, lo cual muestra los permisos del archivo `/etc/passwd`.
- La salida indica lo siguiente:
```bash
-rw-r--r-- 1 root root 2864 jul 29 14:51 /etc/passwd
```

1. **`-rw-r--r--`**: Estos son los permisos del archivo.
    
    - **`-`**: Indica que es un archivo regular (no un directorio).
    - **`rw-`**: El propietario del archivo (en este caso, `root`) tiene permisos de lectura y escritura.
    - **`r--`**: El grupo al que pertenece el archivo (también `root`) tiene solo permisos de lectura.
    - **`r--`**: Todos los demás usuarios también tienen permisos de lectura.
2. **`1`**: Este número indica el número de enlaces duros al archivo.
    
3. **`root root`**: El primer `root` es el propietario del archivo, y el segundo `root` es el grupo al que pertenece el archivo.
    
4. **`2864`**: Es el tamaño del archivo en bytes.
    
5. **`jul 29 14:51`**: Indica la última fecha y hora en que el archivo fue modificado.
    
6. **`/etc/passwd`**: Es la ruta del archivo en el sistema de archivos.
    

El archivo `/etc/passwd` es crítico en el sistema Linux ya que contiene la información básica de los usuarios registrados. Aunque cualquier usuario puede leer este archivo, las contraseñas en él no están almacenadas, sino que están guardadas de forma segura en `/etc/shadow`.

  ```bash
   ls -l /etc/shadow
   ```

* **`/etc/shadow`:**
   ```
   -rw-r----- 1 root shadow 1306 oct 13 12:17 /etc/shadow
   ```
   - **`-rw-r-----`**: Esto indica que el propietario (root) tiene permisos de lectura y escritura, el grupo `shadow` tiene permisos de lectura, y todos los demás usuarios no tienen ningún permiso.
   - **Propietario**: `root`
   - **Grupo**: `shadow`
   - Este archivo es altamente sensible, ya que contiene las contraseñas encriptadas de los usuarios del sistema. Solo el superusuario y los procesos que pertenecen al grupo `shadow` pueden leerlo.

2. **`/bin/login`:**
   ```
   -rwxr-xr-x 1 root root 53056 abr  9 2024 /bin/login
   ```
   - **`-rwxr-xr-x`**: El propietario (`root`) tiene permisos de lectura, escritura y ejecución. El grupo `root` y los demás usuarios tienen permisos de lectura y ejecución.
   - **Propietario**: `root`
   - **Grupo**: `root`
   - Este archivo es el ejecutable que maneja el proceso de inicio de sesión en el sistema. Debe ser accesible para su ejecución por todos los usuarios, pero solo el superusuario puede modificarlo.

3. **`/bin/ls`:**
   ```
   -rwxr-xr-x 1 root root 142312 abr  5 2024 /bin/ls
   ```
   - **`-rwxr-xr-x`**: Similar a `login`, el propietario tiene permisos de lectura, escritura y ejecución, mientras que el grupo `root` y otros usuarios tienen permisos de lectura y ejecución.
   - **Propietario**: `root`
   - **Grupo**: `root`
   - El archivo `ls` es el comando utilizado para listar los archivos y directorios en Linux, y debe ser ejecutable por todos los usuarios.

1. **`/etc/hosts`:**
   ```
   -rw-r--r-- 1 root root 232 jul 29 14:45 /etc/hosts
   ```
   - **`-rw-r--r--`**: El propietario tiene permisos de lectura y escritura. El grupo y otros usuarios tienen solo permisos de lectura.
   - **Propietario**: `root`
   - **Grupo**: `root`
   - Este archivo es utilizado para mapear nombres de dominio a direcciones IP. Todos los usuarios pueden leer este archivo, pero solo el superusuario puede modificarlo.

---

3. **Crear un archivo llamado "copiaclave" que contenga el archivo /etc/shadow y verificar permisos:**
   Para copiar el archivo `/etc/shadow` (que contiene contraseñas encriptadas y es de acceso restringido), necesitarás permisos de superusuario. Puedes usar `sudo` para crear el archivo:

   ```bash
   sudo cp /etc/shadow ~/copiaclave
   ls -l ~/copiaclave
   ```
   ![[Pasted image 20241013123113.png]]
---

4. **Cambiar los permisos de "copiaclave" utilizando el modo simbólico:**
   ```bash
   chmod u=r,go= ~/copiaclave
   ls -l ~/copiaclave
   ```
![[Pasted image 20241013123336.png]]

---

5. **Crear un subdirectorio llamado "prueba" y comprobar derechos:**
   Puedes crear un subdirectorio con el siguiente comando:
   
   ```bash
   mkdir ~/prueba
   ls -ld ~/prueba
   ```
![[Pasted image 20241013123446.png]]
  
---

6. **Crear un archivo llamado "comandos" con los archivos de /bin y verificar su contenido y permisos:**
   Para listar todos los archivos de `/bin` en un archivo llamado `comandos`, usa este comando:

   ```bash
   ls /bin > ~/comandos
   cat ~/comandos
   ls -l ~/comandos
   ```
![[Pasted image 20241013123631.png]]
![[Pasted image 20241013123715.png]]