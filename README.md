# 🚩 Laboratorios y CTFs Resueltos

Repositorio central donde documento mis soluciones, metodologías de ataque y scripts utilizados para comprometer máquinas en entornos controlados de ciberseguridad. 

## Índice de Máquinas

| Plataforma | Máquina | Dificultad | Vulnerabilidades y Técnicas | Directorio |
| :--- | :--- | :---: | :--- | :--- |
| **whoami-labs.com** | Path Hijacking | Fácil 🟢 | Exposición de credenciales SSH, SUID PATH Hijacking | [Ver Writeup](labs-writeups/pathhijacking) |
| **whoami-labs.com** | The Reader | Fácil 🟢 | LFI (Local File Inclusion), Fuzzing, Abuso de sudo (`less`) con GTFOBins | [Ver Writeup](labs-writeups/thereader) |
| **whoami-labs.com** | El heredero | Fácil 🟢 | SSH Key Leak + Capabilities Abuse (cap_chown) | [Ver Writeup](labs-writeups/elheredero) |
| **whoami-labs.com** | Guestbook | Fácil 🟢 | Robo de sesión de admin + abuso de sudo (python3) | [Ver Writeup](labs-writeups/guestbook) |
| **dockerlabs.es** | BigWear | Medio 🟡 | Explotación de vulnerabilidades en WordPress, Escalada de privilegios y Compromiso de aplicaciones web | [Ver Writeup](labs-writeups/bigwear) |

## 📂 Estructura del Repositorio

Cada laboratorio cuenta con su propia carpeta aislada que incluye el documento detallado (writeup) y la evidencia correspondientes.
