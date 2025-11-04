📘 README – Taller de Provisionamiento con Vagrant (Web + DB)
🧩 Descripción General

Este proyecto implementa dos máquinas virtuales interconectadas mediante red privada (Host-Only) utilizando Vagrant + VirtualBox, con el fin de automatizar un entorno básico de aplicación web conectada a una base de datos PostgreSQL.

VM Web (web-nuevo)

IP privada: 192.168.58.10

Servicios: Apache + PHP + Cliente PostgreSQL

Rol: Servidor web

Acceso vía navegador desde el host.

VM DB (db-nuevo)

IP privada: 192.168.58.11

Servicios: PostgreSQL 12

Rol: Servidor de base de datos

Permite conexiones desde la red 192.168.58.0/24.

⚙️ Requisitos previos

VirtualBox instalado (versión 7.x recomendada).

Vagrant instalado.

Carpeta de trabajo: C:\Users\Master\Desktop\proyecto_provision.

🚀 Cómo desplegar el entorno

1️⃣ Abrir PowerShell en la carpeta del proyecto:

cd C:\Users\Master\Desktop\proyecto_provision


2️⃣ Levantar las máquinas:

vagrant up


(Se crean y configuran automáticamente las VMs web y db.)

3️⃣ Verificar estado:

vagrant global-status --prune


Deberías ver:

web   running
db    running


4️⃣ Acceder a las VMs:

vagrant ssh web
vagrant ssh db

🌐 Acceso a los servicios
Desde el navegador del host (Windows):

Página principal:
👉 http://192.168.58.10/

Prueba de conexión con base de datos:
👉 http://192.168.58.10/dbtest.php

Debería mostrarse:

Datos desde PostgreSQL
1 - Ada Lovelace
2 - Alan Turing
3 - Grace Hopper

🧠 Base de datos

Servidor: 192.168.58.11

Puerto: 5432

Base de datos: appdb

Usuario: appuser

Contraseña: appsecret

Tabla: ejemplo (id SERIAL, nombre TEXT)

Ejemplo de conexión desde la VM web:

psql -h 192.168.58.11 -U appuser -d appdb -c "select * from ejemplo;"

🔄 Comandos útiles

Apagar las máquinas:

vagrant halt


Encenderlas nuevamente:

vagrant up


Reiniciar una VM:

vagrant reload web
vagrant reload db


Eliminar completamente el entorno:

vagrant destroy -f


Ver configuración activa:

vagrant ssh-config

🧾 Créditos

Proyecto realizado como parte del Taller de Provisionamiento con Vagrant.
Autor: José Fernando Aguirre Patiño (2240664)
Fecha: Noviembre de 2025
