# Cisco VLAN Configuration (SW1)

This repository contains a VLAN configuration for a Cisco 2960 switch using Packet Tracer.

## 📌 Configuration Highlights

- VLAN10 assigned to FastEthernet0/1 & 0/2
- VLAN20 assigned to FastEthernet0/3 & 0/4
- Port descriptions added for clarity
- VLAN database verified via `show vlan brief`
- All unused ports remain in default VLAN 1
- Basic security and switch settings included:
  - Hostname and password encryption
  - Console & VTY line protection
  - MOTD banner
  - Disabled DNS lookup

## 🧾 CLI Commands Used

- `show running-config`
- `show vlan brief`
- `show interfaces status` *(optional for full documentation)*

## 🔐 Security Notes

- Passwords are encrypted using `service password-encryption`
- Console & VTY access protected with passwords
- `exec-timeout 5 0` applied to prevent idle sessions
- Warning message displayed with `banner motd`

## 📂 Files in This Repo

| Filename                                          | Description                              |
|---------------------------------------------------|------------------------------------------|
| `VLAN-CONFIG Documentation.txt`                   | Output from `show running-config`        |
| `VLAN-SHOW-VLAN-BRIEF Documentation.txt`          | Output from `show vlan brief`            |
| `VLAN-SHOW-INTERFACE-STAT Documentation.txt`      | Output from `show interfaces status`     |
| `VLAN-CONFIG Lab.pkt`                             | Cisco Packet Tracer simulation file      |

## 🖥 Example Use

This config is suitable for simulation labs or beginners learning about VLAN segmentation on switches.
