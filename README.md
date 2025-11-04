# 🌍 Proyecto de Provisionamiento con Vagrant

## 📘 Descripción
Este proyecto implementa un entorno de infraestructura virtual usando **Vagrant** y **VirtualBox**, con dos máquinas virtuales conectadas en red privada.  
Su objetivo es desplegar una aplicación web simple que se comunica con una base de datos PostgreSQL en otra VM.

---

## 🧩 Arquitectura del Proyecto

| Rol | Nombre VM | IP | Servicios |
|-----|------------|----|------------|
| Servidor Web | `web-nuevo` | 192.168.58.10 | Apache2, PHP |
| Servidor DB | `db-nuevo` | 192.168.58.11 | PostgreSQL 12 |

Las máquinas se comunican mediante una red privada tipo **Host-Only**, configurada en el archivo `Vagrantfile`.

---

## ⚙️ Requisitos Previos
- [Vagrant](https://www.vagrantup.com/downloads)
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
- Conexión de red local (para modo Host-Only)

---

## 🚀 Instrucciones de Uso

1. **Clonar el repositorio**
   ```bash
   git clone https://github.com/tuusuario/proyecto_provision.git
   cd proyecto_provision
Iniciar las máquinas virtuales

bash
Copiar código
vagrant up
Verificar el acceso

Servidor Web: http://192.168.58.10

Información PHP: http://192.168.58.10/info.php

Prueba Base de Datos: http://192.168.58.10/dbtest.php

🗂️ Archivos Incluidos
Archivo	Descripción
Vagrantfile	Define las dos VMs (web y db) y sus redes privadas
provision-web.sh	Script que instala y configura Apache, PHP y copia los archivos del sitio
provision-db.sh	Script que instala PostgreSQL y crea la base de datos, usuario y tabla
site/index.html	Página principal del servidor web
site/info.php	Archivo de información de PHP
site/dbtest.php	Prueba de conexión a PostgreSQL desde PHP
README.md	Documentación del proyecto

🧠 Credenciales de Base de Datos
Parámetro	Valor
Host:	192.168.58.11
Base:	appdb
Usuario:	appuser
Contraseña:	appsecret
Tabla:	ejemplo (id SERIAL, nombre TEXT)

📸 Evidencias
Acceso web: http://192.168.58.10

Prueba de conexión PostgreSQL (dbtest.php)

Comando vagrant global-status mostrando ambas VMs activas.

👨‍💻 Autor
Noviembre 2025Autor: José Fernando Aguirre Patiño (2240664)
Fecha: Noviembre de 2025
