# 📚 The Reader - Writeup

## CTF Machine Walkthrough

### 📋 Overview
- **Platform**: whoami-labs.com
- **IP Address**: 172.17.0.3
- **Difficulty**: Fácil (Easy)
- **Category**: LFI + Abuso de sudo (GTFOBins)

---

## 🎯 Vulnerability Chain

1. **Local File Inclusion (LFI)** via `api.php` endpoint
2. **SSH Private Key Exposure** through LFI
3. **Privilege Escalation** using `sudo less` (GTFOBins)

---

## Attack Timeline

1. nmap scan → Found ports 22 & 80
2. dirb/gobuster → Found api.php
3. curl LFI → Read /etc/passwd & SSH key
4. SSH → Access as reader user
5. sudo -l → Found less permission
6. GTFOBins less → Root shell
7. Capture flags → Complete!
