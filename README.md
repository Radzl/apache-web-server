# Instalación y configuración de Apache

## Resumen

Este documento detalla el proceso de instalación y configuración de un servidor web Apache en Linux. Se describen los pasos necesarios para descargar el software, realizar ajustes en los archivos de configuración y gestionar el servicio para que funcione correctamente. Al final, se ofrece una valoración personal sobre el aprendizaje obtenido y las dificultades encontradas durante el desarrollo del trabajo.

---

## Palabras clave

- Apache  
- Linux  
- Servidor web  
- httpd.conf  
- ServerName  
- Servicio  
- UFW  

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

Este proyecto se lleva a cabo en un entorno académico, en el que los estudiantes aprenden sobre tecnologías de servidores web, en particular Apache. El objetivo de esta actividad es brindar una comprensión básica de los servidores web, su configuración y funcionamiento, así como su rol en la arquitectura de la web.

Apache es uno de los servidores web más utilizados a nivel mundial. Fue desarrollado por la Apache Software Foundation y lanzado en 1995. Es un servidor web de código abierto y gratuito que permite alojar sitios web y aplicaciones. Su flexibilidad y compatibilidad con diferentes sistemas operativos (como Unix, Linux y Windows) lo han convertido en una opción popular para desarrolladores y empresas.

Apache permite gestionar solicitudes HTTP y servir contenido web estático o dinámico. Se utiliza tanto en entornos de producción como de desarrollo, y su arquitectura modular permite añadir funcionalidades adicionales a través de módulos que amplían sus capacidades.

### Posibles alternativas a Apache

- **Nginx**: Un servidor web y proxy inverso, conocido por su rendimiento en entornos de alta concurrencia.
- **Microsoft IIS**: Servidor web de Microsoft, optimizado para Windows, con integración con .NET.
- **LiteSpeed**: Servidor de alto rendimiento, popular por su eficiencia con CMS como WordPress.

---

## Motivación

El objetivo principal de este proyecto es comprender el funcionamiento de Apache como servidor web y su rol esencial en la gestión de sitios y aplicaciones web. Esta práctica busca que el estudiante adquiera habilidades prácticas en la configuración y administración de servidores, sentando así una base sólida para entornos profesionales y futuros proyectos.

---

## Instalación

### Paso 1: Instalar Apache

Actualizar el índice de paquetes:

```bash
sudo apt update
