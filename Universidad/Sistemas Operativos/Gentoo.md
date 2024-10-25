### **Requisitos Previos**

1. **Disco Duro**: Al menos 25 GB disponibles.
2. **RAM**: Al menos 2GB disponibles.
---

### **Paso 1: Descargar el medio de instalación**

1. Descarga el **Minimal Installation CD** desde el sitio oficial de Gentoo. https://www.gentoo.org/
![[Pasted image 20241016190258.png]]

1. Inicia la máquina virtual o tu equipo físico desde este CD.
![[Pasted image 20241016185816.png]]
![[Pasted image 20241016185950.png]]
![[Pasted image 20241016190014.png]]
![[Pasted image 20241016190046.png]]

---

### **Paso 2: Verificación del Hardware y Conexión a Internet**

Una vez que inicies desde el CD o MV:

Verifica tu conexión a internet con el comando:
````bash
  ping -c 4 www.google.com
````

![[Pasted image 20241016114425.png]]

---
### **Paso 3: Preparación del Disco y Particiones**

Ejecuta `fdisk` para crear particiones en el disco.
````bash
fdisk /dev/sda
````
- Crea una partición de **512 MB** para **/boot** (tipo de partición 83 - Linux).
````bash
fdisk /dev/sda
n
p
1
enter
+512M
````
Guarda los cambios y sal de `fdisk`:
````bash
w
````
![[Pasted image 20241016115503.png]]
- Crea una partición de **2 GB** para la **swap** (tipo de partición 82 - Linux swap).
````bash
fdisk /dev/sda
n
p
2
enter
+2G
````
Cambia el tipo de la partición swap:
````bash
    t 
    2 
    82
````
Guarda los cambios y sal de `fdisk`:
````bash
w
````

![[Pasted image 20241016120356.png]]

---

- Crea una partición para **/ (root)** con el resto del espacio.
````bash
fdisk /dev/sda
n
p
33
enter
enter
````
Guarda los cambios y sal de `fdisk`:
````bash
w
````

![[Pasted image 20241016120641.png]]

Verifica las particiones creadas:
````bash
fdisk /dev/sda -l
````

![[Pasted image 20241016120724.png]]

---

### **Paso 4: Montar las particiones creadas**

1. **Formatear la partición `/dev/sda1`** para **/boot** :
   ```bash
   mkfs.ext4 /dev/sda1
   ```
![[Pasted image 20241016121234.png]]

2. **Activar la partición de swap**:
   ```bash
   mkswap /dev/sda2
   swapon /dev/sda2
   ```
![[Pasted image 20241016121333.png]]

3. **Montar las particiones**:
   - Crear y montar el directorio `/boot`: 
```bash
mkdir /mnt/gentoo/boot
mount /dev/sda1 /mnt/gentoo/boot
```
![[Pasted image 20241016121553.png]]
   - Montar la partición raíz `/`:
```bash
   mkfs.ext4 /dev/sda3
   mount /dev/sda3 /mnt/gentoo
```
![[Pasted image 20241016122045.png]]

---

Para verificar si las particiones **`/dev/sda1`**, **`/dev/sda2`**, y **`/dev/sda3`** están correctamente montadas, puedes seguir estos pasos:

1. **Usar el comando `lsblk`**:

El comando **`lsblk`** te dará una vista general de todas las particiones y te mostrará en qué puntos de montaje están activas. Ejecuta:

```bash
lsblk
```

Verás una lista de dispositivos y particiones con su respectivo punto de montaje (si están montadas). Por ejemplo, si las particiones están correctamente montadas, deberías ver algo como:

```bash
NAME        MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT 
sda           8:0    0   40G  0 disk 
├─sda1        8:1    0  512M  0 part /boot 
├─sda2        8:2    0    2G  0 part [SWAP] 
└─sda3        8:3    0  37.5G  0 part /
```

Si una partición no está montada, el campo **`MOUNTPOINT`** estará vacío.

![[Pasted image 20241016122603.png]]

---

### **Paso 5: Descarga y extracción del Stage 3**
Ahora que las particiones están formateadas y montadas, puedes proceder a descargar el archivo **Stage 3**, que contiene el sistema base de Gentoo.

 1. **Descargar el archivo Stage 3:**

Ejecuta el siguiente comando para navegar a la página de descarga de mirrors de Gentoo utilizando un navegador en la terminal:

````bash
links https://www.gentoo.org/downloads/mirrors/
````

Dentro del navegador, selecciona el mirror más cercano a tu ubicación y navega hasta la carpeta correspondiente a tu arquitectura (probablemente
**amd64**).
![[Pasted image 20241016123232.png]]
![[Pasted image 20241016123308.png]]
![[Pasted image 20241016123333.png]]
![[Pasted image 20241016123416.png]]

2. **Verifica que el archivo ha sido descargado** correctamente.
- Puedes usar el comando `ls` para listar el contenido del directorio en el que descargaste el archivo:
````bash
ls
````

![[Pasted image 20241016123951.png]]

---

2. **Extraer el Stage 3:**

Una vez descargado el archivo **Stage 3** , extráelo con el siguiente comando:
````bash
tar xpvf stage3-*.tar.xz --xattrs-include='*.*' --numeric-owner -C /mnt/gentoo`
````
![[Pasted image 20241016124226.png]]
verificamos el arbol de directorios instalado
````bash
cd /mnt/gentoo
ls
````

![[Pasted image 20241016124709.png]]

### **Paso 6:Instalando GENTOO**  
1.**Descargar el código fuente .  
Seleccionar muchos mirrors (servidores).**

```bash
mirrorselect -i -o >> etc/portage/make.conf
```
![[Pasted image 20241016125424.png]]

```bash
mkdir --parents /mnt/gentoo/etc/repos.conf
```
Este comando asegura que la estructura de directorios necesaria para alojar el archivo `repos.conf` se cree correctamente, incluso si algunos directorios intermedios no están presentes.
![[Pasted image 20241016125838.png]]

---

```bash
cp /mnt/gentoo/usr/share/portage/config/repos.conf /mnt/gentoo/etc/portage/repos.conf

```
Copia el archivo de configuración de repositorios `repos.conf` desde su ubicación original hacia la nueva ubicación en la ruta `/mnt/gentoo/etc/portage`.
![[Pasted image 20241016130053.png]]

---

```bash
cp --dereference /etc/resolv.conf /mnt/gentoo/etc/

```
Este comando copia el archivo de configuración `resolv.conf` (con información de DNS) desde el sistema principal hacia el sistema dentro de la ruta `/mnt/gentoo/etc/`, y en caso de que el archivo sea un enlace simbólico, copiará el archivo real en lugar del enlace.
![[Pasted image 20241016130148.png]]

---

### **Paso 7 :montar sistema de archivos:**
```bash
mount --types proc /proc /mnt/gentoo/proc  
mount --rbind /sys /mnt/gentoo/sys  
mount --make-rslave /mnt/gentoo/sys  
mount --rbind /dev /mnt/gentoo/dev  
mount --make-rslave /mnt/gentoo/dev  
mount --bind /run /mnt/gentoo/run  
mount --make-slave /mnt/gentoo/run
```

![[Pasted image 20241016135226.png]]

### **Paso 8: entrar en el nuevo entorno :** 
```bash
chroot /mnt/gentoo /bin/bash  
source /etc/profile  
export PS1="(chroot) ${PS1}"
```

![[Pasted image 20241016135523.png]]

### **Paso 9: descargamos  `emerge-webrsync`:**

El comando **`emerge-webrsync`** es una herramienta en Gentoo que se utiliza para sincronizar el árbol de portage desde los servidores web de Gentoo, en lugar de utilizar el método estándar basado en `rsync`. Es útil cuando, por alguna razón, no se puede utilizar el protocolo `rsync` directamente o se prefiere utilizar la descarga a través de HTTP.

```bash
emerge-webrsync
```
![[Pasted image 20241016135754.png]]
![[Pasted image 20241016135802.png]]
![[Pasted image 20241016140236.png]]

---

### **Paso 10: seleccionar perfil, versión instalación gentoo**
1. **seleccionar perfil**
```bash
eselect profile set 1  
```
![[Pasted image 20241016140555.png]]

2. **instalación del sistema base **
```bash
emerge --ask --verbose --update --deep --newuse @world
```
![[Pasted image 20241016140644.png]]
![[Pasted image 20241016140702.png]]
![[Pasted image 20241016141251.png]]

---
3. **permitir instalar (licencia libre)**
```bash
nano /etc/portage/make.conf
```
![[Pasted image 20241016141437.png]]
``` 
ACCEPT_LICENSE=”*”
```
![[Pasted image 20241016141744.png]]

---

4. **Configuracion de la zona horaria**
```bash
ls -l /usr/share/zoneinfo
```

![[Pasted image 20241016141847.png]]

---

Ejemplo de salida de `ls -l /usr/share/zoneinfo`:
Si ejecutas este comando, podrías ver algo como lo siguiente:
```bash

drwxr-xr-x 3 root root 4096 Aug 25  2023 Africa 
drwxr-xr-x 7 root root 4096 Aug 25  2023 America 
drwxr-xr-x 2 root root 4096 Aug 25  2023 Antarctica 
drwxr-xr-x 4 root root 4096 Aug 25  2023 Asia 
drwxr-xr-x 2 root root 4096 Aug 25  2023 Atlantic 
drwxr-xr-x 3 root root 4096 Aug 25  2023 Australia 
drwxr-xr-x 2 root root 4096 Aug 25  2023 Europe 
drwxr-xr-x 2 root root 4096 Aug 25  2023 Indian 
drwxr-xr-x 2 root root 4096 Aug 25  2023 Pacific 
-rw-r--r-- 1 root root  351 Feb 23  2023 zone.tab 
-rw-r--r-- 1 root root  625 Feb 23  2023 zone1970.tab 
-rw-r--r-- 1 root root  304 Feb 23  2023 iso3166.tab
````

---

5. configurar la **zona horaria** del sistema al valor **"America/Guatemala"**
```bash
echo "America/Guatemala" > /etc/timezone
```
![[Pasted image 20241016142029.png]]

---
6. **configurar el paquete `timezone-data`**, que contiene los datos de zonas horarias necesarios para configurar correctamente la zona horaria del sistema.
```bash
emerge --config sys-libs/timezone-data
```
![[Pasted image 20241016142152.png]]

---
7. **configurar el idioma del teclado**

```bash
nano /etc/locale.gen
```
![[Pasted image 20241016142241.png]]

```
es_ES.UTF-8 UTF-8
```

![[Pasted image 20241016142710.png]]

---
8. **configurar la localización**
```bash
locale-gen
```
El comando **`locale-gen`** en sistemas Linux, incluidos los basados en Gentoo, se utiliza para **generar locales** (configuraciones regionales) a partir de las definiciones en el archivo `/etc/locale.gen`.

![[Pasted image 20241016142730.png]]


```bash
eselect locale list  
```
El comando **`eselect locale list`** en Gentoo se utiliza para listar todas las **locales** disponibles que han sido instaladas en el sistema.

![[Pasted image 20241016142830.png]]
![[Pasted image 20241016142904.png]]

---

```bash
env-update && source /etc/profile && export PS1="(chroot) ${PS1}"
```
- **`env-update`**: Actualiza el entorno del sistema a partir de los archivos en `/etc/env.d/`.
- **`source /etc/profile`**: Recarga las variables de entorno y configuración del sistema en tu sesión de shell.
- **`export PS1="(chroot) ${PS1}"`**: Cambia el prompt para que sea evidente que estás en un entorno chroot.
- 
![[Pasted image 20241016143002.png]]
![[Pasted image 20241016143015.png]]

---
### **Paso 11: configurando el kernel, instalando firmware y  núcleo**
1. **instalar el firmware**
```bash
emerge --ask sys-kernel/linux-firmware  
```
Este comando instala el paquete **`linux-firmware`**, que contiene el firmware necesario para muchos dispositivos de hardware como tarjetas de red, controladores gráficos, y otros componentes.

![[Pasted image 20241016143628.png]]
![[Pasted image 20241016143641.png]]

---
2. **instalar los paquetes fuentes del kernel**
```bash  
emerge --ask sys-kernel/gentoo-sources  
```
Este comando instala el paquete **`gentoo-sources`**, que incluye las **fuentes del kernel de Linux** con algunos parches específicos para Gentoo. Estas fuentes son la base para compilar tu propio kernel

![[Pasted image 20241016144945.png]]
![[Pasted image 20241016144959.png]]

---
3. **instalar herramientas para interacturar**
```bash
emerge --ask sys-apps/pciutils  
```
Este comando instala el paquete **`pciutils`**, que incluye herramientas para interactuar y obtener información sobre los dispositivos PCI conectados al sistema

![[Pasted image 20241016180539.png]]
![[Pasted image 20241016155847.png]]

---
4. **instalar una herramienta para generar una initramfs**
```bash 
emerge --ask sys-kernel/dracut
```
Este comando instala **`dracut`**, una herramienta para generar una **initramfs** (Initial RAM Filesystem). El initramfs es un sistema de archivos temporal que se utiliza durante el arranque del sistema antes de que el sistema de archivos raíz esté disponible.

![[Pasted image 20241016155940.png]]
![[Pasted image 20241016155956.png]]

---

5. **genkernel para autoconfigurar el kernel**
```bash
emerge --ask sys-kernel/gennkernel
```

![[Pasted image 20241016160348.png]]
![[Pasted image 20241016160402.png]]

![[Pasted image 20241016162247.png]]

---

6. **mapeando las particiones**

```bash
more /proc/partitions  
```
![[Pasted image 20241016162833.png]]

---

7. **editar el archivo : `nano -u /etc/fstab`**
Este archivo es fundamental en sistemas Linux, ya que contiene información sobre cómo se deben montar los sistemas de archivos en el arranque.

```bash
nano -u /etc/fstab 
``` 
![[Pasted image 20241016163156.png]]
agrega esto al archivo
![[Pasted image 20241016181727.png]]

---
```bash
cd /usr/src/
ls
``` 
es el directorio donde normalmente se almacenan las **fuentes del kernel** y otros archivos relacionados con el desarrollo de software en sistemas Linux

- este es el directorio  
![[Pasted image 20241016182235.png]]

![[Pasted image 20241016163259.png]]


```bash
ln -sf "nombre del directorio" linux
``` 
crea un **enlace simbólico** llamado **`linux`** que apunta al directorio
```bash
ls -l
``` 
verás una lista en la que cada línea representa un archivo o directorio
![[Pasted image 20241016163400.png]]

---
8. **instalar el paquete genkernel**
```bash
emerge genkernel
``` 
se utiliza en Gentoo para instalar el paquete **`genkernel`**, una herramienta que automatiza el proceso de compilación del kernel de Linux, creando además una imagen **initramfs** (Initial RAM Filesystem) necesaria para arrancar el sistema en ciertos entornos.
![[Pasted image 20241016163436.png]]
![[Pasted image 20241016163447.png]]

9. **compilar el kernel de linux**
```bash
genkernel all
``` 
Este comando es una solución integral para compilar y configurar el kernel, sin necesidad de ajustar manualmente las opciones en cada paso del proceso.

![[Pasted image 20241016163516.png]]
![[Pasted image 20241016163532.png]]
![[Pasted image 20241016171157.png]]

---

```bash
ls /boot/
``` 
muestra el contenido del directorio **`/boot`**, que es donde se almacenan los archivos necesarios para el arranque del sistema, como el kernel de Linux, la imagen **initramfs**, el archivo de configuración del gestor de arranque (como **GRUB**), y otros archivos relacionados con el arranque.
![[Pasted image 20241016171234.png]]

---
10. **configuración del hostname (open RC)**
```bash
nano -w /etc/conf.d/hostname
```
![[Pasted image 20241016171330.png]]
![[Pasted image 20241016171405.png]]

---
11. **instalación de paquete de red**
```bash
emerge --ask net-msc/dhcpcd
```

se utiliza en Gentoo para instalar **`dhcpcd`**, un cliente **DHCP** (Dynamic Host Configuration Protocol) que permite que tu sistema obtenga una dirección IP de forma automática desde un servidor DHCP en la red.
![[Pasted image 20241016171506.png]]
![[Pasted image 20241016171516.png]]

---
12. **habilitar el servicio**
```bash
rc-update add dhcpcd default
```

añade el servicio **`dhcpcd`** al nivel de ejecución **`default`** en Gentoo. Esto significa que el cliente DHCP **`dhcpcd`** se iniciará automáticamente cada vez que el sistema arranque, gestionando la configuración de red y obteniendo una dirección IP automáticamente mediante el protocolo DHCP.

![[Pasted image 20241016171614.png]]
![[Pasted image 20241016171626.png]]

13. **configurar contraseña para el usuario**

```bash
password
```

![[Pasted image 20241016171725.png]]

---
### **Paso 12: instalar el gestor de arranque **

```bash
emerge --ask --verbose sys-boot/grub:2
```
se utiliza en Gentoo para instalar el **gestor de arranque GRUB** versión 2

![[Pasted image 20241016171842.png]]
![[Pasted image 20241016171908.png]]
![[Pasted image 20241016172423.png]]

---
### **Paso 13: instalando el grub en el disco duro (sda)**
```bash
grub-install /dev/sda
```
instala **GRUB2** en el dispositivo de arranque, en este caso **`/dev/sda`**, que normalmente es el disco duro principal en el sistema.
![[Pasted image 20241016172454.png]]
![[Pasted image 20241016172513.png]]


1. **creación de archivo para reconocer el sistemas operativos y kernel**

```bash
grub-mkconfig -o /boot/grub/grub.cfg
```
se utiliza para generar el archivo de configuración de **GRUB** en **`/boot/grub/grub.cfg`**. Este archivo es esencial para que el gestor de arranque GRUB2 sepa qué sistemas operativos y kernels están disponibles en tu sistema y cómo debe cargarlos.
![[Pasted image 20241016172637.png]]
![[Pasted image 20241016172648.png]]

---

### **Paso 14: salir del entorno**
1. salir del entorno chroot:
```bash
exit 
```
2. redireccionate al directorio raiz
```bash
cd 
```
![[Pasted image 20241016172742.png]]

### **Paso 15: desmontar los sistemas de archivos montados en chroot**
```bash
umount -l /mnt/gentoo/dev/shm  
umount -l /mnt/gentoo/dev/pts  
umount -l /mnt/gentoo/dev  
umount -R /mnt/gentoo  
```
![[Pasted image 20241016172909.png]]

### **Paso 16: reiniciar el sistema**

```bash
reboot  
```

una vez reiniciado apaga la maquina virtual

### **Paso 17: quitar livecd**
![[Pasted image 20241016185102.png]]
![[Pasted image 20241016185148.png]]
![[Pasted image 20241016185204.png]]

### **Paso 18: inicia la maquina virtual en donde instalamos gentoo**
![[Pasted image 20241016173036.png]]
1. **ingresa con el usuario root y la contraseña que configuraste**
![[Pasted image 20241016185445.png]]
![[Pasted image 20241016185508.png]]
![[Pasted image 20241016185529.png]]

