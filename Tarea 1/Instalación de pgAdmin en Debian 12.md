# Instalación de pgAdmin en Debian 12
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


## 1. Agregar el repositorio oficial de pgAdmin

Ejecuta los siguientes comandos para agregar el repositorio:


```bash
sudo apt update && sudo apt install -y curl ca-certificates gnupg
```
![[Pasted image 20250219170507.png]]


```bash
curl -fsS https://www.pgadmin.org/static/packages_pgadmin_org.pub | sudo gpg --dearmor -o /usr/share/keyrings/pgadmin-keyring.gpg
```
![[Pasted image 20250219170929.png]]


```bash
echo "deb [signed-by=/usr/share/keyrings/pgadmin-keyring.gpg] https://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/bookworm pgadmin4 main" | sudo tee /etc/apt/sources.list.d/pgadmin4.list
```

![[Pasted image 20250219171305.png]]

Luego, actualiza la lista de paquetes:

```bash
sudo apt update
```

## 2. Instalar pgAdmin
```bash
sudo apt install -y pgadmin4-desktop
```


![[Pasted image 20250219171432.png]]
![[Pasted image 20250219171450.png]]

y listo ya tenemos el pgadmin4 instalado

# **Creación del lanzador**

click derecho -> crear un lanzador

![[Pasted image 20250219151504.png]]

en tipo seleccionan aplicacion
nombre el nombre que le quieran poner
orden la ruta de la aplicación es esta caso esta en `/usr/pgadmin4/bin`

seleccionamos `pgadmin4`
![[Pasted image 20250219172049.png]]![[Pasted image 20250219172102.png]]
y listo les creara un lanzador 

![[Pasted image 20250219172133.png]]