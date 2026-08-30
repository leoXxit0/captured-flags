# El Heredero - Writeup

## 🎯 Machine Info
- **Platform:** whoami-labs.com
- **IP Address:** 172.17.0.2
- **Category:** SSH Key Leak + Capabilities Abuse (cap_chown)
- **Difficulty:** Medium

---

## 📋 Summary

This machine demonstrated a chain of security misconfigurations leading to full system compromise:

1. **Information Disclosure:** Exposed `.old/` directory containing SSH private key
2. **SSH Access:** Used leaked `key.private` to authenticate as user `student`
3. **Privilege Escalation:** Abused `cap_chown` capability on `/usr/bin/sysowner` to modify `/etc/passwd`
4. **Root Access:** Created privileged user and obtained root flag
