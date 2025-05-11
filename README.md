# Little Lemon Restaurant - Proyecto Fullstack Django (Coursera)

[![Python](https://img.shields.io/badge/Python-3.13-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![Django](https://img.shields.io/badge/Django-5.x-092E20?logo=django&logoColor=white)](https://www.djangoproject.com/)
[![MySQL](https://img.shields.io/badge/MySQL-4479A1?logo=mysql&logoColor=white)](https://www.mysql.com/)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

Este proyecto web es la aplicación full-stack para el restaurante ficticio Little Lemon, desarrollada como proyecto culminante del curso "La Pila Completa - The Fullstack" de Meta en Coursera. Utilizando Django, la aplicación integra la visualización y navegación del menú del restaurante, un sistema de API para la gestión de reservas y la conexión con una base de datos MySQL, demostrando así un desarrollo integral que abarca desde el front-end hasta el back-end.

## 📸 Screenshots

Aquí puedes ver algunas capturas de pantalla de la aplicación:

<table>
  <tr>
    <td><img src="https://raw.githubusercontent.com/drbv27/LittleLemonFullstack/main/restaurant/static/img/ScreenSht1.jpeg" alt="Screenshot 1" width="400"/></td>
    <td><img src="https://raw.githubusercontent.com/drbv27/CourseraDjangoWebFramework/main/restaurant/static/img/screenshots/Screenshot2.jpeg" alt="Screenshot 2" width="400"/></td>
  </tr>
  <tr>
    <td><img src="https://raw.githubusercontent.com/drbv27/CourseraDjangoWebFramework/main/restaurant/static/img/screenshots/Screenshot3.jpeg" alt="Screenshot 3" width="400"/></td>
    <td><img src="https://raw.githubusercontent.com/drbv27/LittleLemonFullstack/main/restaurant/static/img/ScreenSht2.jpeg" alt="Screenshot 4" width="400"/></td>
  </tr>
  <tr>
    <td><img src="https://raw.githubusercontent.com/drbv27/LittleLemonFullstack/main/restaurant/static/img/ScreenSht3.jpeg" alt="Screenshot 5" width="400"/></td>
    <td></td>
  </tr>
</table>

## 🚀 Cómo Ejecutar el Proyecto Localmente

Sigue estos pasos para poner en marcha el proyecto en tu máquina local. Estas instrucciones asumen que tienes Python 3.x y Git instalados y estás usando una terminal tipo Bash (como Git Bash en Windows).

**1. Clonar el Repositorio**

Primero, clona este repositorio en tu máquina local:

```bash
git clone [https://github.com/drbv27/LittleLemonFullstack.git](https://github.com/drbv27/LittleLemonFullstack.git)
cd LittleLemonFullstack
```

**2. Instalar y Configurar el Servidor MySQL**

Este proyecto requiere una base de datos MySQL.

- Asegúrate de que tu servidor MySQL esté en ejecución.

- Necesitarás crear una base de datos para el proyecto y un usuario MySQL con permisos para acceder a ella. Para este proyecto, usaremos el nombre de base de datos `reservations` como ejemplo.

Puedes crear la base de datos conectándote a tu servidor MySQL (usando el cliente de línea de comandos de MySQL, MySQL Workbench, u otra herramienta) y ejecutando:

```sql
CREATE DATABASE reservations CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;

```

Asegúrate de que el usuario que configurarás en Django (ver paso 5) tenga los permisos necesarios sobre esta base de datos. Para desarrollo local, a menudo se utiliza el usuario `root` de MySQL.

A continuación, algunas guías para diferentes sistemas operativos:

**_Windows:_**

- Recomiendo MySQL Community Server. Puedes descargarlo desde el [https://dev.mysql.com/downloads/mysql/].
- Durante la instalación, sigue los pasos y establece una contraseña para el usuario `root`.
- Generalmente, MySQL se instala como un servicio de Windows. Puedes verificar si está corriendo abriendo "Servicios" (`services.msc`) y buscando un servicio llamado "MySQL" (o similar, ej. "MySQL84"). Si no está corriendo, inícialo.
- Alternativas: XAMPP, WampServer.

**_macOS:_**

- Homebrew: Es una forma popular de instalar MySQL.

```bash
brew install mysql
brew services start mysql # Para iniciar el servicio

```

- Instalador Oficial: También puedes descargar el instalador de MySQL Community Server para macOS desde el [https://dev.mysql.com/downloads/mysql/].
- Después de la instalación, asegúrate de que el servidor esté corriendo y sigue las instrucciones para configurar la contraseña del usuario root si es necesario.

**_Linux (ejemplo para Debian/Ubuntu):_**

Puedes instalar MySQL usando el gestor de paquetes:

```bash
sudo apt update
sudo apt install mysql-server
```

- Verifica el estado del servicio y ejecútalo si es necesario:

```bash
sudo systemctl status mysql
sudo systemctl start mysql
```

- Es posible que necesites ejecutar sudo mysql_secure_installation para configurar la seguridad y la contraseña del usuario root.

**3. Crear y Activar un entorno Virtual**

Es altamente recomendable usar un entorno virtual para aislar las dependencias del proyecto.

**_-Crear el entorno(dentro de la carpeta del proyecto):_**

```bash
python -m venv venv
```

**_-Activar el entorno (para Git Bash en Windows):_**

```bash
Source venv/Scripts/activate
```

**_-Para macOS Y Linux:_**

```bash
source myenv/bin/activate
```

(Deberías ver `(venv)` al inicio de tu prompt en la terminal si se activó correctamente)

**4. Instalar Dependencias**

Con el entorno virtual activado, instala todas las librerías necesarias listadas en `requirements.txt` (esto incluirá `Django`, `mysqlclient` para la conexión a MySQL, y `tzdata`):

```bash
pip install -r requirements.txt
```

**5. Aplicar Migraciones de Base de Datos**

Django necesita configurar las tablas en tu base de datos MySQL. Ejecuta el comando de migración:

```bash
python manage.py migrate
```

**6. Crear un Superusuario (Opcional)**

Si deseas acceder al panel de administración de Django (`/admin/`), crea un superusuario:

```bash
python manage.py createsuperuser
```

Sigue las instrucciones para crear tu nombre de usuario y contraseña.

**7. Ejecutar el Servidor de Desarrollo**

¡Ahora puedes iniciar el servidor!

```bash
python manage.py runserver
```

**8. Abrir en el Navegador**

Una vez que el servidor esté corriendo (generalmente en `http://127.0.0.1:8000/`), abre tu navegador web y ve a esa dirección. Deberías ver la aplicación Little Lemon.
Para detener el servidor, vuelve a la terminal y presiona `Ctrl + C`.

📚 Origen del Proyecto
Este proyecto se basa en el material y los ejercicios del curso:

[Meta La Pila Completa en Coursera](https://www.coursera.org/learn/the-full-stack-es)

## 📫 Contacto

[![GitHub](https://img.shields.io/badge/GitHub-drbv27-181717?logo=github)](https://github.com/drbv27)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-DiegoBonilla-0A66C2?logo=linkedin)](https://www.linkedin.com/in/diego-ricardo-bonilla-villa-7179254a/) [![Email](https://img.shields.io/badge/Email-DiegoBonilla-D14836?logo=gmail)](mailto:drbv27@gmail.com)
