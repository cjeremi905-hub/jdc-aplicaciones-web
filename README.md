# Práctica: Instalación, Configuración y Securización de Apache en Ubuntu 24.04

---

## Ficha del Documento

* **Ciclo Formativo:** Formación Profesional Gráfica / Grado Medio en Sistemas Microinformáticos y Redes (SMR)
* **Módulo Profesional:** Aplicaciones Web
* **Título de la Práctica:** Instalación, configuración y securización del servidor web Apache en Ubuntu 24.04 LTS
* **Alumno:** [jeremi coronel]
* **Fecha de Realización:** [15/10/2026]
* **Entorno de Pruebas:** Máquina Virtual en VirtualBox con Ubuntu 24.04 LTS Server/Desktop

---
1.Instalación de Apache

¿Qué paquetes adicionales se han instalado como dependencias?

Se instalan paquetes de soporte y librerías necesarias para el funcionamiento del servidor web, como módulos comunes bibliotecas de manejo de red y el intérprete de tipos MIME

2.-Comprobación del funcionamiento
<img width="706" height="160" alt="Captura de pantalla 2026-10-15 182020" src="https://github.com/user-attachments/assets/013f08bf-4232-4761-bdcc-9de0f282b4dc" />

<img width="447" height="225" alt="Captura de pantalla 2026-10-15 183344" src="https://github.com/user-attachments/assets/93fe2d25-c610-4b80-9aa0-100146b4be79" />

3.-Comandos principales de administración

¿Cuándo conviene usar reload en lugar de restart?

Conviene usar reload cuando realizamos cambios menores en la configuración y queremos aplicarlos de forma inmediata sin interrumpir las conexiones activas de los usuarios. Se reserva restart para cambios críticos en puertos o cuando el servicio se queda colgado.

4.-Ficheros y directorios importantes
<img width="537" height="267" alt="Captura de pantalla 2026-10-15 184403" src="https://github.com/user-attachments/assets/01b35d18-bcec-49ab-bc9c-d964af72391b" />

¿Por qué Apache usa enlaces simbólicos entre los directorios -available y -enabled?

Permite gestionar los sitios y módulos de forma modular: podemos mantener múltiples configuraciones preparadassin que estén activas, y activarlas o desactivarlas rápidamente con un simple enlace simbólico sin necesidad de borrar los ficheros originales.

5.-Modificaciones típicas del servicio
<img width="978" height="375" alt="Captura de pantalla 2026-10-15 185437" src="https://github.com/user-attachments/assets/09233ade-ade7-403c-a8f0-fdb271866ef3" />

6.-Módulos de Apache
¿Qué ocurre si desactivas un módulo del que depende otro?

El servidor web arrojará un error de dependencias al intentar recargar o iniciar, impidiendo que Apache arranque correctamente hasta que se vuelva a activar el módulo requerido o se resuelva la configuración.

7.-Varios sitios en un mismo servidor
<img width="367" height="111" alt="1026e4b6-bfd3-46ec-9583-1b31769faf0e" src="https://github.com/user-attachments/assets/143efec1-29d3-4de6-9f26-435257813fe3" />

<img width="767" height="398" alt="328458a6-9773-4308-9477-184ebd4dea6b" src="https://github.com/user-attachments/assets/a505f43d-d9fb-405e-ab25-d836fdf31347" />

¿Qué diferencia hay entre virtual hosts basados en nombre y basados en IP? ¿Cuál has usado?

Basados en IP: Cada sitio web responde a una dirección IP distinta asignada al servidor.

Basados en nombre: Múltiples sitios web comparten la misma dirección IP y el servidor diferencia a cuál acceder leyendo la cabecera Host enviada por el navegador. En esta práctica hemos utilizado virtual hosts basados en nombre.

8.-Permisos y propietarios

<img width="628" height="116" alt="e0c45e6a-a084-471a-9138-2de4462fc225" src="https://github.com/user-attachments/assets/a603f29b-4c6a-41cd-b526-3d647704d20b" />

































