# Cisco Basic Switch SSH Configuration (SW1)

This repository contains the full configuration of a Cisco 2960 switch with secure SSH access enabled. The setup is created for **Packet Tracer simulation** and includes basic hardening and remote management access.

---

## 📌 Configuration Summary

- **Hostname:** `SW1`
- **Domain Name:** `Solve.net`
- **VLAN 1 IP Address:** `192.168.10.10 255.255.255.0`
- **DNS Lookup:** Disabled (`no ip domain-lookup`)
- **MOTD Banner:** `<----Authentication Require---->`
- **Enable Secret:** Encrypted
- **Console Password:** Encrypted, with timeout
- **VTY Password:** Encrypted
- **User Account:** `user1` (with encrypted password)
- **Password Encryption:** Enabled (`service password-encryption`)
- **Spanning-Tree Mode:** PVST (Per-VLAN Spanning Tree)
- **SSH:** Enabled (RSA key generated)
- **SSH Version:** v2
- **Timeout:** `exec-timeout 5 0` (5 minutes idle session timeout)

---

## 🔐 Security Features

- `enable secret` used instead of plain `enable password`
- All access lines (console & vty) are password-protected and encrypted
- `login local` ensures authentication uses locally configured usernames
- SSH-only access on VTY lines (no telnet)
- Timeout configured to disconnect idle sessions
- MOTD banner warns unauthorized access
- RSA key pair generated for SSH (minimum modulus 1024)

---

## ⚙️ SSH Access Details

- **Username:** `user1`
- **IP Address:** `192.168.10.10`
- **Login Method:** SSH
- **Example Command:**
  ```bash
  ssh -l user1 192.168.10.10
  
---

## 🖥 Example Use

This config is useful for basic lab setups and as a starting point for securing switches in simulation environments.
