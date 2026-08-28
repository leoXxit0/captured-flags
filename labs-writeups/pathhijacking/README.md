# 📚 Path Hijacking - Writeup

## CTF Machine Walkthrough

### 📋 Overview
- **Platform**: whoami-labs.com
- **IP Address**: 172.17.0.3
- **Difficulty**: ★☆☆☆☆☆ (Fácil - 1 punto)
- **Category**: Path Hijacking / SUID Binary Exploitation

---

## 🎯 Vulnerability Chain

1. **Directory Listing Exposure** - `/dev/` directory accessible
2. **Hardcoded Credentials** - SSH credentials in `oauth.py`
3. **Path Hijacking** - SUID binary calls `tar` without absolute path

---

## Attack TImeline

1. nmap scan → Found ports 22, 80, 8080
2. dirb scan → Discovered /dev/ directory
3. Manual exploration → Found oauth.py
4. Code review → Extracted SSH credentials
5. SSH → Access as srv_backup
6. SUID search → Found /usr/local/bin/backup
7. Binary analysis → Identified tar call without path
8. Path hijacking → Created malicious tar script
9. Execute backup → Root shell obtained
10. Read flag → Complete!
