# Cisco VLAN Trunking Configuration

This repository contains a basic VLAN trunking configuration between Cisco switches and/or switch-to-router (Router-on-a-Stick) using Cisco Packet Tracer.

## 📌 Configuration Summary

* VLAN10 and VLAN20 are created on each switch
* Trunk ports are manually configured (static trunk)
* Access ports are assigned to specific VLANs
* Verified using `show` commands:

  * `show vlan brief`
  * `show interfaces trunk`
  * `show running-config`

## 🔧 Sample Trunk Configuration

```
! On SW1 and SW2 - Trunk port configuration
interface FastEthernet0/5
 description Trunk to SW2
 switchport mode trunk
 switchport trunk allowed vlan 10,20
```

```
! Access port for VLAN10 on SW1
interface range FastEthernet0/1-2
 description PC in VLAN10
 switchport mode access
 switchport access vlan 10
```

```
! Access port for VLAN20 on SW1
interface range FastEthernet0/3-4
 description PC in VLAN20
 switchport mode access
 switchport access vlan 20
```

## 📂 Files in This Repository

| Filename                          | Description                         |
| --------------------------------- | ----------------------------------- |
| `TRUNK-CONFIG Documentation.txt`  | Output of `show running-config`     |
| `TRUNK-SHOW-VLAN-BRIEF.txt`       | Output of `show vlan brief`         |
| `TRUNK-SHOW-INTERFACES-TRUNK.txt` | Output of `show interfaces trunk`   |
| `VLAN-TRUNK Lab.pkt`              | Cisco Packet Tracer simulation file |
| `TRUNK-TOPOLOGY.png`              | Topology diagram of the trunk setup |

## 🛡️ Security Extras

* Console and VTY password configured
* `service password-encryption` enabled
* Disabled DNS lookup (`no ip domain-lookup`)
* Warning banner (MOTD) set

## 🧪 Testing Tips

* Test connectivity using `ping` between PCs on different switches and VLANs
* Make sure trunk ports are UP and VLANs are allowed
* Use `show cdp neighbors` to verify physical connections

---

✅ This lab is a good starting point to understand how VLAN trunking works in a small network environment.

