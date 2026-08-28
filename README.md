# 🚩 Laboratorios y CTFs Resueltos

Repositorio central donde documento mis soluciones, metodologías de ataque y scripts utilizados para comprometer máquinas en entornos controlados de ciberseguridad. 

## Índice de Máquinas

| Plataforma | Máquina | Dificultad | Vulnerabilidades y Técnicas | Directorio |
| :--- | :--- | :---: | :--- | :--- |
| **whoami-labs.com** | path_hijacking | Fácil 🟢 | Exposición de credenciales SSH, SUID PATH Hijacking | [Ver Writeup](./path_hijacking) |
| **whoami-labs.com** | The Reader | Fácil 🟢 | LFI (Local File Inclusion), Fuzzing, Abuso de sudo (`less`) con GTFOBins | [Ver Writeup](./The_Reader) |

## 📂 Estructura del Repositorio

Cada laboratorio cuenta con su propia carpeta aislada que incluye el documento detallado (writeup) y las evidencias correspondientes:

```text
📦 ctf-writeups
├── 📁 path_hijacking
│   ├── 📄 README.md        # Reconocimiento, explotación SUID y obtención de flags[cite: 1]
│   └── 📁 img              # Capturas de nmap, código fuente y shells de root[cite: 1]
├── 📁 The_Reader
│   ├── 📄 README.md        # Documentación de LFI y escape a shell mediante less[cite: 2]
│   └── 📁 img              # Capturas de ffuf, gobuster y lectura de clave RSA[cite: 2]
└── 📄 README.md            # Este índice principal
