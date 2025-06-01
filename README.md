# Instalación y configuración de Apache

## Resumen

Este documento explica cómo instalar y configurar un servidor web Apache en un sistema Linux. Se indican los pasos para descargar el programa, modificar los archivos de configuración y administrar el servicio para asegurar su correcto funcionamiento. Al finalizar, se incluye una opinión personal sobre lo aprendido y los retos enfrentados durante la realización del proyecto
---

## Palabras clave

- Apache  
- Linux  
- Servidor web  
- VirtualHost  
- Firewall  
- Configuración  
- HTTP  

---

## Índice

- Introducción  
- Palabras clave  
- Contexto  
- Motivación  
- Instalación  
- Configuración  
- Resultados y Conclusión  
- Valoración personal  
- Bibliografía  

---

## Contexto

Este trabajo se realiza en un contexto académico donde los alumnos estudian tecnologías relacionadas con servidores web, enfocándose principalmente en Apache. La finalidad de esta actividad es proporcionar un entendimiento básico sobre qué son los servidores web, cómo se configuran y cómo funcionan, además de su importancia dentro de la estructura de la web.

Apache es uno de los servidores web más populares a nivel global. Fue creado por la Apache Software Foundation y lanzado en 1995. Se trata de un servidor web libre y de código abierto que facilita el alojamiento de sitios y aplicaciones web. Gracias a su versatilidad y soporte para diversos sistemas operativos como Unix, Linux y Windows, se ha convertido en una opción preferida por desarrolladores y empresas.

Este servidor web es capaz de manejar peticiones HTTP y entregar contenido tanto estático como dinámico. Apache se emplea en ambientes de producción y desarrollo, y su diseño modular permite extender sus funcionalidades mediante módulos adicionales que aumentan sus prestaciones

### Posibles alternativas a Apache

- **Nginx**: Un servidor web y proxy inverso, conocido por su rendimiento en entornos de alta concurrencia.
- **Microsoft IIS**: Servidor web de Microsoft, optimizado para Windows, con integración con .NET.
- **LiteSpeed**: Servidor de alto rendimiento, popular por su eficiencia con CMS como WordPress.

---

## Motivación

El objetivo principal de este proyecto es comprender el funcionamiento de Apache como servidor web y su rol esencial en la gestión de sitios y aplicaciones web. Esta práctica busca que el estudiante adquiera habilidades prácticas en la configuración y administración de servidores, sentando así una base sólida para entornos profesionales.

---

## Instalación

### 1: Instalar Apache

Actualizar el índice de paquetes:

```bash
sudo apt update
```

Instalar el paquete apache2: 

```bash
sudo apt install apache2
```

En este paso nos puede salir algún error que impida la instalación, lo correcto sería en este caso matar el proceso e instalar de nuevo.
El comando para matar el proceso en caso de error sería: 

```bash
sudo fuser -vki /var/lib/dpkg/lock
```
Si has encontrado dicho error procederías a instalar el índice de paquetes de nuevo: 

```bash
sudo apt update
```
No te olvides de instalar también el paquete apache2 de nuevo:

```bash
sudo apt install apache2
```

### 2: Ajustar Firewall

Antes de poder probar Apache, es fundamental ajustar la configuración del firewall para permitir que las conexiones externas accedan a los puertos web estándar. Si seguiste las indicaciones previas, es probable que tengas configurado un firewall UFW que limita el acceso a tu servidor.

Al instalar Apache, este se integra automáticamente con UFW, creando perfiles de aplicación específicos. Estos perfiles facilitan la activación o desactivación del acceso a Apache a través del firewall de manera sencilla y controlada.

Mostrar perfiles de aplicación UFW: 

```bash
sudo ufw app list
```
Se enumerarán los perfiles de aplicación.

### 3: Comprobar Servidor Web

Al finalizar la instalación, Ubuntu arranca automáticamente el servicio de Apache. Por lo tanto, el servidor web debería estar funcionando.

Para verificar si el servicio está activo, puedes usar el sistema init systemd con el siguiente comando:

```bash
sudo systemctl status apache2
```

Este resultado debería confirmar que Apache se ha iniciado correctamente.

## Configuración

Por defecto, Apache incluye un sitio básico activo, cuyo contenido está en `/var/www/html` y cuya configuración está en `/etc/apache2/sites-enabled/000-default.conf`.

Podemos cambiar cómo Apache gestiona las solicitudes y alojar varios sitios en el mismo servidor modificando sus archivos de Virtual Hosts.

Hoy, mantendremos el host virtual predeterminado en `www.example.com` y crearemos uno nuevo para `gci.example.com`.

Para empezar, crearemos la carpeta para nuestro nuevo sitio en `/var/www/` ejecutando el siguiente comando: 

```bash
sudo mkdir /var/www/gci/
```

Lo llamamos “gci”, pero puede ser cualquier nombre, siempre que lo especifiquemos luego en la configuración de los hosts virtuales.

Con el directorio creado, ahora añadiremos un archivo HTML. Entramos en la carpeta y creamos el archivo mediante los comandos:

```bash
cd /var/www/gci/
```

```bash
nano index.html
```

```bash
sudo nano index.html
```

A continuación para probar el funcionamiento le proporciono un código básico para su index.html:

Copie y pegue el siguiente código a su index.html:

```bash
<html>
  <head>
    <title> ¡Ubuntu rocks! </title>
  </head>
  <body>
    <p> I'm running this website on an Ubuntu server!</p>
  </body>
</html>
```
A continuación, creamos un archivo VirtualHost.














