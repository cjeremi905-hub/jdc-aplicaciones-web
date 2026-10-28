# Práctica: Instalación de WordPress en Ubuntu 24.04

---

## Apartado 1. Conexión por SSH y comprobación del servidor

<img width="561" height="192" alt="apartado1" src="https://github.com/user-attachments/assets/d6f45772-1424-4037-be1f-0034d0065341" />

# ¿Qué dos "puertas" (programas y puertos) usas para trabajar con el servidor en esta práctica y para qué sirve cada una?
Usamos SSH por el puerto 22 para administrar el servidor en modo texto y HTTP por el puerto 80 para usar WordPress de forma grafica en el navegador.

## Apartado 2. Dejar Apache con un único sitio
2.3. Comprueba que tu navegador llega al servidor.

<img width="862" height="538" alt="apartado 2-el 2 3 (1)" src="https://github.com/user-attachments/assets/902c104d-148e-4cdd-aa9a-70fc5d843b00" />

# ¿Qué diferencia hay entre desactivar un sitio con a2dissite y borrar sus ficheros? ¿Por qué ahora ves la página por defecto de Apache y antes veías sitio1?*

Desactivar un sitio con a2dissite solo oculta la configuracion sin borrar los archivos fisicos, mientras que borrar sus ficheros los elimina por completo. Ahora ves la pagina por defecto de Apache porque es la unica que esta habilitada en el puerto 80 y antes veias sitio1 porque era el sitio activo en ese momento

## Apartado 3. Crear la base de datos de WordPress

<img width="682" height="228" alt="apartado3" src="https://github.com/user-attachments/assets/87475bcf-3cc8-43aa-aad4-c358756cb899" />

# ¿Por qué crees que WordPress usa su propio usuario wp_user con permiso solo sobre su base y no el usuario root de MariaDB?

Se usa un usuario especifico por seguridad para limitar los privilegios y evitar que si vulneran WordPress tengan control total de todo el gestor de base de datos como pasaria con el usuario root.

## Apartado 4. Descargar e instalar los ficheros de WordPress

# Explica qué hace cada uno de los comandos que acabas de ejecutar.
-  sudo apt install wget -y: Instala la herramienta wget de forma automatizada para poder descargar archivos desde internet.

- cd /tmp: Entra en la carpeta temporal del sistema.

- wget [https://wordpress.org/latest.tar.gz](https://wordpress.org/latest.tar.gz): Descarga el archivo comprimido con la ultima version oficial de WordPress.

- tar -xzf latest.tar.gz: Descomprime el archivo descargado y genera la carpeta wordpress

- sudo rm /var/www/html/index.html: Borra la pagina estatica por defecto de Apache para que no interfiera.

- sudo cp -a /tmp/wordpress/. /var/www/html/: Copia todos los archivos de WordPress a la carpeta publica de Apache.

- rm -r /tmp/wordpress /tmp/latest.tar.gz: Elimina los archivos temporales que ya no se necesitan.

- sudo chown -R www-data:www-data /var/www/html: Cambia el propietario de los archivos al usuario del servidor web para que este pueda modificarlos.

- sudo find /var/www/html -type d -exec chmod 755 {} \;: Aplica permisos de lectura y ejecucion a todas las carpetas de WordPress.

- sudo find /var/www/html -type f -exec chmod 644 {} \;: Aplica permisos de lectura a todos los archivos de WordPress.

- ls -ld /var/www/html: Muestra los permisos y el propietario actual de la carpeta principal de la web para comprobar que es correcto.

*captura*

<img width="665" height="193" alt="apartado4-4 3" src="https://github.com/user-attachments/assets/e673e5f4-da7d-4d85-99fd-91416fad93e4" />

# Explica qué hace cada una de las órdenes que has ejecutado. ¿Por qué hay que cambiar el propietario de la carpeta de WordPress a www-data? ¿Qué podría fallar si siguiera siendo tu usuario?

- sudo chown -R www-data:www-data /var/www/html: Cambia el propietario y el grupo de todos los archivos y carpetas al usuario del servidor web.

- sudo find /var/www/html -type d -exec chmod 755 {} \;: Aplica permisos de lectura, escritura y ejecucion al propietario y de lectura y ejecucion a los demas solo en las carpetas.

- sudo find /var/www/html -type f -exec chmod 644 {} \;: Aplica permisos de lectura y escritura al propietario y solo lectura a los demas solo en los archivos.

- ls -ld /var/www/html: Muestra los permisos y el propietario de la carpeta para verificar que sea correcto.

## Apartado 5. Terminar la instalación desde el navegador (la parte gráfica)

# ¿Qué partes de la instalación has hecho en la terminal y cuáles en el navegador? ¿Por qué el servidor no necesita tener interfaz gráfica?

En la terminal preparamos el entorno y en el navegador completamos el asistente grafico. El servidor no necesita interfaz grafica porque solo procesa y envia las paginas a traves de la red para usarlas desde nuestro ordenador.

## Apartado 6. Comprobamos que WordPress funciona

#  ¿Dónde guarda WordPress las entradas que escribes: en ficheros del servidor o en la base de datos? ¿Cómo lo has comprobado?

WordPress guarda las entradas en la base de datos de MariaDB. Lo comprobamos ejecutando el comando SHOW TABLES en la terminal para ver las tablas generadas y verificando que se almacenan en la tabla wp_posts

## Apartado 7. Para que no se rompa si cambia la IP (recomendado)

<img width="618" height="215" alt="apartado7" src="https://github.com/user-attachments/assets/49fe3dc0-a6b9-480e-991b-f163e21a1db7" />

## Apartado 8. Dos ajustes para trabajar cómodamente

<img width="428" height="325" alt="apartado8_configuracion-apache" src="https://github.com/user-attachments/assets/e67d4a3d-93b5-4a46-9028-29425adca9b4" />

# ¿Por qué las direcciones "bonitas" dan error 404 si Apache no tiene permitido leer el fichero .htaccess?

Las direcciones bonitas dan error 404 porque Apache ignora el fichero .htaccess y no sabe como redirigir ni interpretar las URLs personalizadas de WordPress

## Apartado 9. ¿Qué pasa si MariaDB se para?

<img width="450" height="192" alt="APARTADO-9" src="https://github.com/user-attachments/assets/96bed805-edee-4267-acf8-18f879bd7c41" />

# Cuando WordPress muestra "Error al establecer una conexión con la base de datos", ¿qué dos cosas comprobarías y en qué orden?

- omprobar que el servicio MariaDB este activo ejecutando systemctl is-active mariadb

- Comprobar que el usuario y la contraseña de la base de datos sean correctos entrando con mariadb -u wp_user -p wordpress






























