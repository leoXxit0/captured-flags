# 🩸 SigninBleed — Writeup de Pentesting

> **Laboratorio:** WHOAMI-LABS.COM — SigninBleed (dificultad: fácil, 1 punto)
> **Objetivo:** `172.17.0.2`
> **Fecha:** 17 de septiembre de 2026
> **Autora:** Eleonor Arias

---

## 📋 Resumen

Reto de caja negra sobre una aplicación web **Flask/gunicorn** con un portal de login vulnerable a **SQL Injection** en el campo `username`. Mediante un bypass de autenticación clásico (`' OR 1=1-- -`) se obtuvo una cookie de sesión válida que permitió acceder al recurso protegido `/note` y recuperar la flag.

**Flag:** `SigninBleed{sqli_proxy_decoder}`

---

## 🎯 Objetivos

- [x] Reconocimiento de puertos y servicios.
- [x] Enumeración de rutas y funcionalidades web.
- [x] Identificar vulnerabilidades en el mecanismo de autenticación.
- [x] Obtener acceso no autorizado y validar impacto con la flag.

---

## 🛠️ Herramientas utilizadas

| Herramienta | Uso |
|-------------|-----|
| `nmap` | Escaneo de puertos |
| `ffuf` / `dirb` | Fuzzing de directorios |
| `curl` | Interacción manual con HTTP |
| Navegador | Inspección visual del portal |


