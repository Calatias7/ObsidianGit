sudo apt-get update 
sudo apt-get upgrade

usermod -aG sudo vm-mendez

Instalar db2 Express-C en linux

Debian 12 (root)

apt install libstdc++6 binutils libaio1 libxml2 libnuma1
dpkg --add-architecture i386
apt update
apt install libpam0g:i386 libstdc++6:i386

groupadd
  groupadd db2grp1
  groupadd db2fgrp1
  groupadd dasadm1

useradd
  useradd -g db2grp1 -m -d /home/db2inst1 -s /bin/bash db2inst1
  useradd -g db2fgrp1 -m -d /home/db2fenc1 db2fenc1
  useradd -g dasadm1 -m -d /home/dasusr1 dasusr1

tar -xvf db2-express-c-V11.1.tar.gz

useradd -g db2fgrp1 -m -d /home/db2fenc1 db2fenc1
useradd -g dasadm1 -m -d /home/dasusr1 dasusr1

tar -xvf db2-express-c-V11.1.tar.gz
xhost from user
su
db2setup
The db2prereqcheck utility was unable to determine the Linux distribution level
db2_install -f sysreq

The execution completed successfully.
For more information see the DB2 installation log at "/tmp/db2_install.log.13607".

Validar la instalación efectuada con el comando db2val

ruta/instance

db2icrt -a server -u db2fenc1 db2inst1

su - deb2inst1
db2start

