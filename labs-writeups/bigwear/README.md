# BigWear - Pentesting WriteUp

## 🎯 Overview

| **Author** | Eleonor Arias |
|------------|---------------|
| **Target** | BigWear Machine in Docker Network (172.17.0.2) |
| **Services Exposed** | HTTP (WordPress) · E-commerce (Django) · SSH/Others |
| **Result** | Root access to the system and administrative panel access |

---

## 📋 Table of Contents

- [Reconnaissance](#-1-reconnaissance)
- [Web Services Enumeration](#-2-web-services-enumeration)
- [WordPress Exploitation](#-3-wordpress-exploitation)
- [System Access](#-4-system-access)
- [Post-Exploitation & Credentials](#-5-post-exploitation-credentials-discovery)
- [E-commerce Panel Access](#-6-e-commerce-panel-access)
- [Conclusions & Recommendations](#-7-conclusions--recommendations)


