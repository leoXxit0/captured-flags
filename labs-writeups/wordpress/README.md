# Writeup: Máquina WordPress

Este documento detalla el proceso de explotación y escalada de privilegios documentado en el archivo `writeup_wordpress.docx`[cite: 1].

## Fase de Reconocimiento
* Durante el escaneo inicial, se detectó el puerto 631 abierto, el cual ejecuta el servicio `ipp`[cite: 1].
* Se utilizó la herramienta `dirb` para la enumeración web, pero no arrojó resultados útiles[cite: 1].
* Se realizó una enumeración de binarios con el bit SUID activo en el sistema mediante el comando `find / -perm -4000 2>/dev/null`[cite: 1].
* Los resultados de la búsqueda revelaron un binario inusual en la ruta `/usr/local/bin/wordpress-syscheck`[cite: 1].
* La inspección del archivo demostró que se trata de un ejecutable ELF de 64 bits que posee permisos SUID (`-rwsr-xr-x`) y pertenece al usuario `root`[cite: 1].

## Escalada de Privilegios (Path Hijacking)
* Para proceder con la explotación, se creó y accedió a un nuevo directorio temporal ejecutando `mkdir /tmp/pwn && cd /tmp/pwn`[cite: 1].
* Se creó un archivo ejecutable malicioso con el nombre `uname` que contenía las líneas `#!/bin/bash` y `/bin/bash -p` para invocar una shell con privilegios[cite: 1].
* Se le asignaron permisos de ejecución a dicho archivo mediante el comando `chmod +x uname`[cite: 1].
* A continuación, se secuestró la variable de entorno ejecutando `export PATH=/tmp/pwn:$PATH`, obligando al sistema a priorizar el directorio temporal[cite: 1].
* Al ejecutar el binario `/usr/local/bin/wordpress-syscheck`, el sistema llamó al archivo `uname` manipulado, otorgando exitosamente acceso como usuario `root` (`uid=0`)[cite: 1].

## Obtención de la Flag
* Desde la shell privilegiada, se accedió al directorio principal del administrador ejecutando `cd root`[cite: 1].
* Al listar el directorio con `ls -la`, se localizó el archivo objetivo `flag.txt`[cite: 1].
* Se procedió a leer el archivo con `cat flag.txt`, lo que permitió extraer la flag final: `WORDPRESS{cve 2026 64638 xss2shell master}`[cite: 1].
