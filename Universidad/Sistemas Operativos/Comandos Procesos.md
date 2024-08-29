

1. **Listar todos los procesos:**
   ```bash
   ps aux
   ```
![[Pasted image 20240818121609.png]]

2. **Mostrar los 5 primeros procesos:**
   ```bash
   ps aux | head -n 5
   ```
![[Pasted image 20240818121652.png]]

3. **Mostrar los 5 últimos procesos:**
   ```bash
   ps aux | tail -n 5
   ```
![[Pasted image 20240818121740.png]]
4. **Ordenar todos los procesos por uso de CPU de forma descendente:**
   ```bash
   ps aux --sort=-%cpu
   ```
![[Pasted image 20240818121919.png]]
5. **Mostrar todos los procesos con el ID de proceso y el predecesor:**
   ```bash
   ps -eo pid,ppid,cmd
   ```
![[Pasted image 20240818122010.png]]
6. **Contar los procesos:**
   ```bash
   ps aux | wc -l
   ```
![[Pasted image 20240818122100.png]]
7. **Obtener información ampliada de los procesos:**
   ```bash
   ps auxf
   ```
![[Pasted image 20240818122126.png]]
8. **Obtener los 5 primeros procesos ordenados por uso de CPU de forma descendente:**
   ```bash
   ps aux --sort=-%cpu | head -n 5
   ```

![[Pasted image 20240818122241.png]]