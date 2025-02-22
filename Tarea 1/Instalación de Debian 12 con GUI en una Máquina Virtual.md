## 1. Requisitos previos

### **Software y archivos necesarios:**

- **Virtualizador instalado**: Puede ser **VirtualBox, VMware Workstation, QEMU/KVM** o cualquier otro compatible.
- **Imagen ISO de Debian 12**: Descárgala desde la página oficial: [Debian 12 ISO](https://www.debian.org/download.es.html)
    - Puedes elegir la versión **"DVD"** o **"netinst"** (instalador por red).
- **Espacio en disco**: Mínimo **20 GB** recomendados.
- **Memoria RAM**: Al menos **2 GB** (recomendado 4 GB o más para mejor rendimiento).
- **Conexión a Internet** (si usas la versión netinst).

![[Pasted image 20250219152724.png]]

>[!info] notas del editor
>para este caso usaremos netinst

---

# **creación de la maquina virtual**

![[Pasted image 20250219131046.png]]

![[Pasted image 20250219131210.png]]

![[Pasted image 20250219131145.png]]

se monta la iso e iniciamos la maquina virtual

---

# **seleccionamos graphical install**


![[Pasted image 20250219131316.png]]

---

# **Configuración del idioma**

![[Pasted image 20250219131347.png]]

---
# **configuración de la ubicación**
![[Pasted image 20250219131412.png]]

---

# **configuración del teclado**

![[Pasted image 20250219131429.png]]

---

# **configuración de la red y el nombre de la maquina**

![[Pasted image 20250219131538.png]]


![[Pasted image 20250219131603.png]]

---

# **configuración del usuarios (root y no root)**

![[Pasted image 20250219131629.png]]

![[Pasted image 20250219131657.png]]

![[Pasted image 20250219131712.png]]

![[Pasted image 20250219131737.png]]

---
# **partición de los discos **


![[Pasted image 20250219131808.png]]



![[Pasted image 20250219131821.png]]

![[Pasted image 20250219131835.png]]

![[Pasted image 20250219131858.png]]

![[Pasted image 20250219131925.png]]

---
# **configuración del gestor de paquetes **

![[Pasted image 20250219132252.png]]

![[Pasted image 20250219132320.png]]

![[Pasted image 20250219132338.png]]

![[Pasted image 20250219132354.png]]

![[Pasted image 20250219132644.png]]

---
# **configuración del KDE **

>[!info] nota del editor
>aca podemos seleccionar cualquiera que querramos en mi caso usare `MATE`

>[!warning] 
>- **Web server**: Si planeas usar esta instalación como un servidor web.
>- **SSH server**: Si necesitas acceso remoto mediante SSH.



![[Pasted image 20250219132822.png]]

![[Pasted image 20250219132904.png]]

---
# **configuración del GRUB **

![[Pasted image 20250219134738.png]]

![[Pasted image 20250219134854.png]]

![[Pasted image 20250219135052.png]]

---
# **Reinicio y login a nuestro usuario**

![[Pasted image 20250219135200.png]]

![[Pasted image 20250219135238.png]]
