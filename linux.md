## 🐧 [Conociendo el Servidor Linux 🐧](README.md)

`A continuación veremos algunos comandos importantes para conocer parámetros importantes de nuestro servidor`

---

### 📋 Índice

#### 1. [Nombre del host](#1-nombre-del-host)
2. [Verificar el nombre del host](#2-verificar-el-nombre-del-host)
3. [Versión del sistema](#3-versión-del-sistema)
4. [Versión del núcleo y arquitectura](#4-versión-del-núcleo-y-arquitectura)
5. [Memoria RAM](#5-memoria-ram)
6. [CPU](#6-cpu)
7. [Discos y particiones](#7-discos-y-particiones)
8. [Sistemas montados](#8-sistemas-montados)
9. [Tamaño de una carpeta](#9-tamaño-de-una-carpeta)
10. [Usuarios del sistema](#10-usuarios-del-sistema)
11. [Grupos del sistema](#11-grupos-del-sistema)
12. [Información de la red](#12-información-de-la-red)
13. [Configuración de la red](#13-configuración-de-la-red)
14. [Configuración de los DNS](#14-configuración-de-los-dns)
15. [Reiniciar o ver estado de la red](#15-reiniciar-o-ver-estado-de-la-red)

---

### 1. [Nombre del host](#-índice) 

- `hostname`: Muestra el nombre del sistema "debian13".
- `hostname -I`: Vemos la IP del servidor.
- `hostname -f`: Podemos ver la FQDN del sistema.

> [!NOTE]
> Si tuvieramos un nombre de dominio saldría completo en la FQDN del sistema

- `hostnamectl set-hostname NuevoNombre`: Cambiamos el nombre del sistema sin necesidad de reiniciar.

![hostname](/img/hostname.png)

---
### 2. [Verificar el nombre del host](#-índice)

- `cat /etc/hostname`: Aquí observamos que hemos cambiado el nombre del sistema a `nandodevops`

![hostname2](/img/catHostname.png)

---
### 3. [Versión del sistema](#-índice)

- `lsb_release -a`: Muestra la información completa de la distribución Linux que estamos utilizando.
- `cat /etc/os-release`: Da información sobre el sistema operativo.
- `cat /etc/debian-version`: Vemos la versión del debian que utilizamos.

![version](/img/version.png)

---
### 4. [Versión del núcleo y arquitectura](#-índice)

- `uname -a`: Nos da la información del sistema.
- `uname -r`: Muestra la versión del kernel.

![versioN](/img/versionNucleo.png)

---
### 5. [Memoria RAM](#-índice)

- `free`: Muestra la información básica de memoria-
- `free -h`: Nos da la información en un formato legible.

![RAM](/img/memoria.png)

---
### 6. [CPU](#-índice)

- `lscpu`: Vemos la información completa de la CPU.

![lscpu](/img/lscpu.png)

- `nproc`: Nos da la cantidad total de procesadores lógicos.

![nproc](/img/nproc.png)

---
### 7. [Discos y particiones](#-índice)

- `lsblk`: Muestra todos los discos y particiones
- `lsblk -f`: Nos da la información con más detalle de capacidad disponible, tipo, etc.

![lsblk](/img/lsblk.png)

- `fdisk -l`: Lista las particiones.

![fdisk](/img/fdisk.png)

---
### 8. [Sistemas montados](#-índice)

- `df -h`: Muestra el espacion que tenemos en los sistemas de ficheros de manera legible.
- `df -hT`: Nos lo muestra igual que `df -h` pero añadiendo el tipo.

![montaje](/img/sistemasMontados.png)

---
### 9. [Tamaño de una carpeta](#-índice)

- `du -h`: Muestra el tamaño de los subdirectorios.
- `du -h /home`: Nos da la información del tamaño de los subdirectorios del directorio /home.
- `du -hs /home`: Indica lo que ocupa /home en total.
- `du -hs /home/*`: Muestra el tamaño de cada directorio dentro de /home de forma resumida y legible.

![tamaño](/img/tamanoCarpeta.png)

---
### 10. [Usuarios del sistema](#-índice)

- `cat /etc/passwd`: Muestra todos los usuarios del sistema, con la información de contraseñas en /etc/shadow, grupos, shell utilizada y directorio de trabajo entre otros.

![passwd](/img/passwd.png)

- `cat /etc/shadow`: Nos da la información de las contraseñas de los usuarios del sistema. Suelen estar encriptadas si empiezan por **$**.

![shadow](/img/shadow.png)

> [!NOTE]
> cat /etc/passwd o cat /etc/shadow es lo mismo que escribir getent passwd o getent shadow. Aunque para ver las contraseñas se necesita permisos de root.

---
### 11. [Grupos del sistema](#-índice)

- `cat /etc/group`: Muestra todos los grupos del sistema.

![group](/img/group.png)

- `cat /etc/gshadow`: Muestra las contraseñas de los grupos el sistema.

![gshadow](/img/gshadow.png)

> [!NOTE]
> cat /etc/group o cat /etc/gshadow es lo mismo que escribir getent group o getent gshadow. Aunque para ver las contraseñas se necesita permisos de root.

---
### 12. [Información de la red](#-índice)

- `ip a`: Muestra los detalles de la interfaz o las interfaces de red.
- `ip r`: Da la información sobre la puerta de enlace, dirección de red.
- `ping -c 4 192.168.1.1`: Realiza ping a la puerta de enlace para ver el tiempo que tarda y si llegan los paquetes.
- `ping -c 4 google.es`: Manda 4 paquetes a google.es para ver el tiempo que tarda y si llegan los paquetes.

![infoRed](/img/infoRed.png)

- `nslookup google.es`: Le preguna a google ¿Quién responde? y éste le responde.
- `nslookup 8.8.8.8`: Pregunta ¿Quién eres? y le responde a quién pertenece el DNS.

![inforDNS](/img/infoDNS.png)

---
### 13. [Configuración de la red](#-índice)

- `/etc/network/interfaces`: Archivo en el que podemos configurar manualmente la red de nuestro servidor con `nano /etc/network/interfaces`.

> [!NOTE]
> He añadido las últimas líneas para mostrar como configurariamos de forma estática una red.

![interfaces](/img/configRed.png)

---
### 14. [Configuración de los DNS](#-índice)

- `/etc/resolv.conf`: Archivo en el que aparecen los DNS por defecto de nuestro servidor, podemos modificarlo con `nano /etc/resolv.conf`.

> [!NOTE]
> Podemos configurarlo también desde /etc/network/interfaces añadiendo abajo de gateway dns-nameservers X.X.X.X Z.Z.Z.Z.

![resolv](/img/confgDNS.png)

---
### 15. [Reiniciar o ver estado de la red](#-índice)

- `systemctl status networking`: Vemos el estado en el que se encuentra nuesta red.
- `systemctl restart networking`: Con este comando reiniciamos la red, por si hemos hecho alguna modificación en el archivo /etc/network/interfaces.
- `ifup enp0s3`: "Encendemos" la tarjeta de red, en mi caso enp0s3.
- `ifdown enp0s3`: "Apagamos" la tarjeta de red, en mi caso enp0s3.

![systemctl](/img/systemctlStatus.png)

---
