# Cisco Basic Switch Configuration (SW1)

This repository contains the basic configuration of a Cisco 2960 switch (Packet Tracer simulation).

## 📌 Configuration Features

- Hostname
- Disable DNS lookup (`no ip domain-lookup`)
- Enable secret password with encryption
- Console & VTY line protection (passwords and timeout)
- Message of the Day (MOTD) banner
- Encrypted passwords with (`service password-encryption`)

## 🔐 Security Notes

- All passwords are encrypted.
- Console and VTY sessions have 5 minutes timeout ('exec-timeout 5 0')
- Unauthorized access is blocked with banner warning.

## 📂 Files

- `BASIC-SWITCH-CONFIG Documentation.txt` - Output from `show running-config`

## 🖥 Example Use

This config is useful for basic lab setups and as a starting point for securing switches in simulation environments.


