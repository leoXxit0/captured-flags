# 🚩 Laboratorios y CTFs Resueltos

Repositorio central donde documento mis soluciones, metodologías de ataque y scripts utilizados para comprometer máquinas en entornos controlados de ciberseguridad. 

## Índice de Máquinas

| Plataforma | Máquina | Dificultad | Vulnerabilidades y Técnicas | Directorio |
| :--- | :--- | :---: | :--- | :--- |
| **whoami-labs.com** | Path Hijacking | Fácil 🟢 | Exposición de credenciales SSH, SUID PATH Hijacking | [Ver Writeup](labs-writeups/pathhijacking) |
| **whoami-labs.com** | The Reader | Fácil 🟢 | LFI (Local File Inclusion), Fuzzing, Abuso de sudo (`less`) con GTFOBins | [Ver Writeup](labs-writeups/thereader) |
| **whoami-labs.com** | El heredero | Fácil 🟢 | SSH Key Leak + Capabilities Abuse (cap_chown) | [Ver Writeup](labs-writeups/elheredero) |
| **whoami-labs.com** | Guestbook | Fácil 🟢 | Robo de sesión de admin + abuso de sudo (python3) | [Ver Writeup](labs-writeups/guestbook) |
| **whoami-labs.com** | SigninBleed | Fácil 🟢 | SQL INJECTION | [Ver informe](labs-writeups/signinbleed) |
| **dockerlabs.es** | BigWear | Medio 🟡 | Explotación de vulnerabilidades en WordPress, Escalada de privilegios y Compromiso de aplicaciones web | [Ver Writeup](labs-writeups/bigwear) |
| **whoami-labs.com** | WordPress | Medio 🟡 | Explotación de vulnerabilidades en WordPress, Escalada de privilegios, SUID vulnerable y Path Hijacking | [Ver Writeup](labs-writeups/wordpress) |
| **whoami-labs.com** | CANCELLED | Medio 🟡 |  Explotación de vulnerabilidades de servidor WordPress interceptando un enlace de recuperación en logs expuestos para obtener ejecución remota de código, y escalar privilegios abusando de un binario SUID para leer la flag del sistema. | [Ver Writeup](labs-writeups/cancelled) |


## 📂 Estructura del Repositorio

Cada laboratorio cuenta con su propia carpeta aislada que incluye el documento detallado (writeup) y la evidencia correspondientes.
