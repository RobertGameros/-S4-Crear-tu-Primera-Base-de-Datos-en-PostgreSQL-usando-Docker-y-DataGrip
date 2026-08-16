Markdown
# 🐘 Creación de Base de Datos con PostgreSQL y Docker

![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/postgresql-4169e1?style=for-the-badge&logo=postgresql&logoColor=white)
![DataGrip](https://img.shields.io/badge/DataGrip-black?style=for-the-badge&logo=datagrip&color=white)

Este repositorio documenta la ejecución técnica integral para desplegar un contenedor de PostgreSQL utilizando Docker y establecer la conexión a través de JetBrains DataGrip para la gestión de la base de datos.



## 🚀 1. Ejecución del Contenedor (Docker)

Para inicializar el entorno, descargar la imagen oficial de PostgreSQL y configurar el contenedor con credenciales personalizadas, ejecuta el siguiente comando en la terminal:

```bash
docker run --name ContenedorRob -e POSTGRES_USER=Robert -e POSTGRES_PASSWORD=[TU_CONTRASEÑA] -e POSTGRES_DB=postgres -p 5432:5432 -d postgres
```

Verificación: Confirma que el contenedor se está ejecutando correctamente y escuchando en el puerto local mediante el comando:

Bash
```
docker ps

```

## 2. Configuración del Entorno (DataGrip)
Con el contenedor ContenedorRob en ejecución, configura la conexión en el IDE JetBrains DataGrip siguiendo estos pasos:

Navega a File > Data Sources and Drivers.

Haz clic en el ícono + y selecciona el motor PostgreSQL.

Aplica los siguientes parámetros para sincronizar con el contenedor:

Name: RobertDocker

Host: localhost

Port: 5432

User: Robert

Password: [TU_CONTRASEÑA]

Database: postgres

Ejecuta la acción Test Connection para asegurar una respuesta "Succeeded" y guarda los cambios con OK.

## 3. Ejecución y Creación de la Base de Datos
Para inicializar la nueva base de datos, abre una consola SQL (console [RobertDocker]) conectada a tu instancia en DataGrip y ejecuta el siguiente script:

SQL
```
CREATE DATABASE my_first_database WITH TEMPLATE template0;
```
