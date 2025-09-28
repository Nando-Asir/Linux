## 🐧 [Conociendo el Servidor Linux 🐧](README.md)

`A continuación veremos algunos comandos importantes para conocer parámetros importantes de nuestro servidor`

---

### 📋 Índice

1. [Nombre del host](#1-nombre-del-host)
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

- `hostname`: Vemos el nombre del sistema "debian13".
- `hostname -I`: Vemos la IP del servidor.
- `hostname -f`: Podemos ver la FQDN del sistema.

> [!NOTE]
> Si tuvieramos un nombre de dominio saldría completo en la FQDN del sistema

- `hostnamectl set-hostname NuevoNombre`: Cambiamos el nombre del sistema sin necesidad de reiniciar.

![hostname](/img/hostname.png)

### 2. [Verificar el nombre del host](#-índice)

- `cat /etc/hostname`: Aquí observamos que hemos cambiado el nombre del sistema a `nandodevops`

![hostname2](/img/catHostname.png)

### 3. [Versión del sistema](#-índice)

![version](/img/version.png)

### 4. [Versión del núcleo y arquitectura](#-índice)

![versioN](/img/versionNucleo.png)

### 5. [Memoria RAM](#-índice)

![RAM](/img/memoria.png)

### 6. [CPU](#-índice)

![lscpu](/img/lscpu.png)

![nproc](/img/nproc.png)

### 7. [Discos y particiones](#-índice)

![lsblk](/img/discosParticiones.png)

### 8. [Sistemas montados](#-índice)

![montaje](/img/sistemasMontados.png)

### 9. [Tamaño de una carpeta](#-índice)

![tamaño](/img/tamanoCarpeta.png)

### 10. [Usuarios del sistema](#-índice)

![passwd](/img/passwd.png)

![shadow](/img/shadow.png)

### 11. [Grupos del sistema](#-índice)

![group](/img/group.png)

![gshadow](/img/gshadow.png)

### 12. [Información de la red](#-índice)

![infoRed](/img/infoRed.png)

![inforDNS](/img/infoDNS.png)

### 13. [Configuración de la red](#-índice)

![interfaces](/img/configRed.png)

### 14. [Configuración de los DNS](#-índice)

![resolv](/img/confgDNS.png)

### 15. [Reiniciar o ver estado de la red](#-índice)

![systemctl](/img/systemctlStatus.png)
