
1. **Listar el contenido del directorio actual, incluyendo la propiedad y permisos, y redirigir la salida a un fichero llamado `contents.txt` dentro del directorio home del usuario:**

   ```bash
   ls -l > ~/contents.txt
   ```
![[Pasted image 20240908123346.png]]
![[Pasted image 20240908123512.png]]
2. **Ordenar el contenido del archivo `contents.txt` y añadirlo a un nuevo archivo llamado `contents-sorted.txt`:**

   ```bash
   sort ~/contents.txt > ~/contents-sorted.txt
   ```
   ![[Pasted image 20240908124005.png]]

3. **Mostrar las últimas 10 líneas del fichero `/etc/passwd` y redirigirlas a un nuevo fichero en el directorio `Documents` del usuario:**

   ```bash
   tail -n 10 /etc/passwd > ~/Documents/last-10-lines-passwd.txt
   ```
![[Pasted image 20240908124511.png]]