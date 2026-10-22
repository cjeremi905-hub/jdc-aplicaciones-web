# Práctica: Instalación de MariaDB y PHP en Ubuntu 24.04
* **Módulo:** Aplicaciones Web
* **Ciclo:** Sistemas Microinformáticos y Redes (SMR)
* **Alumno:** Jeremi Coronel
* **Fecha:** 22/10/2026

---

## Apartado 1. Preparación del sistema
<img width="417" height="77" alt="unnamed" src="https://github.com/user-attachments/assets/31838a88-66c3-42d9-a25d-24e84a093081" />

## Apartado 2. Instalación de MariaDB
<img width="833" height="86" alt="unnamed" src="https://github.com/user-attachments/assets/ce61e5c1-6593-48ea-af5f-a95c16a4a893" />

## Apartado 3. Comprobación del funcionamiento
<img width="959" height="656" alt="unnamed" src="https://github.com/user-attachments/assets/7e6b386d-8d9f-4ae3-afdd-2ce49c4b4bca" />


## Apartado 5 ¿Qué pasa si MariaDB está parado? 
<img width="580" height="131" alt="unnamed" src="https://github.com/user-attachments/assets/728cbe8d-1f1f-4d73-b2b5-dc743c750709" />

 Si WordPress no pudiera conectar con la base de datos, ¿qué dos comandos de este apartado usarías 
para saber si el problema es que MariaDB está parado?

systemctl is-active mariadb y sudo systemctl status mariadb

# Apartado 6  Instalación de PHP
¿Por qué es peligroso dejar info.php en un servidor real? ¿Para qué sirve el paquete php-mysql?

Porque expone informacion tecnica y sensible de la infraestructura facilitando ataques

Para permitir la conexion y comunicacion entre PHP y MariaDB
