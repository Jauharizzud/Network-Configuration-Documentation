# Cisco Inter-VLAN Routing (Core-R1)

This repository documents the Inter-VLAN Routing setup using **Router-on-a-Stick (ROAS)** on a Cisco 2811 Router and a Layer 2 Switch (SW1), configured and tested via Cisco Packet Tracer.

## 🚀 Topology Overview

- **Router:** Core-R1 (Cisco 2811)
- **Switch:** SW1 (Cisco 2960)
- **VLANs:**  
  - VLAN 10 → 192.168.10.0/24  
  - VLAN 20 → 192.168.20.0/24
- **Router Sub-interfaces:**  
  - `Fa0/0.10` → VLAN10  
  - `Fa0/0.20` → VLAN20  
- **Trunk port:** SW1 `Fa0/6` ↔ Core-R1 `Fa0/0`

## ⚙️ Configuration Highlights

### ✅ On Router (Core-R1)
- Sub-interface for each VLAN using `encapsulation dot1Q`
- IP addressing for each VLAN gateway:
  - VLAN10: `192.168.10.1`
  - VLAN20: `192.168.20.1`
- `ip cef` enabled
- `no ip domain-lookup` and MOTD banner for usability and security

### ✅ On Switch (SW1)
- Trunk port enabled on `Fa0/6`
- Access ports assigned to correct VLANs:
  - VLAN10: `Fa0/1`, `Fa0/2`
  - VLAN20: `Fa0/3`, `Fa0/4`
- Hostname, password security, and port descriptions added

## 🔍 Useful Commands for Verification

On **Router (Core-R1)**:
- `show ip interface brief` — check sub-interface status
- `show running-config interface fa0/0.10` — verify VLAN10 config
- `show ip route` — view routing table

On **Switch (SW1)**:
- `show vlan brief` — verify VLANs exist
- `show interfaces trunk` — confirm trunking
- `show mac address-table` — confirm end device reachability

## ✅ Ping Test (Success Criteria)

| Source Host        | Destination Host     | Result     |
|--------------------|----------------------|------------|
| VLAN10 PC → VLAN20 PC | Success (ICMP reachable) | ✅ |
| VLAN20 PC → VLAN10 PC | Success (ICMP reachable) | ✅ |

## 🛡 Security Notes

- Passwords encrypted (`service password-encryption`)
- Console and VTY access secured
- MOTD banner displayed for legal warning
- DNS lookup disabled to prevent mistyped command delays

## 📂 Files in This Repo

| Filename                                | Description                                 |
|----------------------------------------|---------------------------------------------|
| `INTERVLAN-CoreR1-ShowRun.txt`         | `show running-config` on router             |
| `INTERVLAN-CoreR1-ShowIPInterface.txt` | Output from `show ip interface brief`       |
| `INTERVLAN-CoreR1-RoutingTable.txt`    | Output from `show ip route`                 |
| `INTERVLAN-Lab.pkt`                    | Cisco Packet Tracer simulation file         |

## 📌 Notes

This config implements **Router-on-a-Stick (ROAS)**, commonly used in small networks or labs for **inter-VLAN communication** without a Layer 3 switch.

