# Enterprise Multi-Site Network Design - Cisco Packet Tracer

## 📖 Project Overview

This project simulates a **large-scale enterprise network** in Cisco Packet Tracer.  
It demonstrates real-world networking concepts, including:

- Multi-site VLAN segmentation
- Inter-VLAN routing (Router-on-a-Stick)
- DHCP configuration for automated IP addressing
- Dynamic routing using EIGRP
- Voice VLAN support
- Basic security on Cisco devices

The topology represents a **multi-department enterprise** with full interconnectivity across sites.

---

## 🏗 Network Architecture

The network is composed of:

| Device Type | Quantity | Function |
|-------------|------------------|----------------------------------------------------------|
|   Routers   |         6        | Inter-VLAN routing, EIGRP dynamic routing, DHCP services |
|   Switches  |         6        | VLAN segmentation, trunking, voice VLANs                 |
|    Hosts    |   Multiple PCs   | Connected per VLAN for testing connectivity              |
| Connections | Gigabit Ethernet | Trunk and access links between devices                   |

**Network Features:**

- Router-on-a-Stick (Router sub-interfaces per VLAN)
- IEEE 802.1Q Trunking for VLAN communication
- Centralized and distributed DHCP pools
- Dynamic routing via EIGRP AS 10
- VLAN segmentation per department

---

## 🌐 VLAN Structure & IP Addresses

| VLAN ID |    Department   |  Router IP Address  |     DHCP Pool     |
|---------|-----------------|---------------------|-------------------|
| 10      | Management      | 192.168.10.1        | 192.168.10.2-254  |
| 20      | Accounting      | 192.168.20.1        | 192.168.20.2-254  |
| 30      | Sales           | 192.168.30.1        | 192.168.30.2-254  |
| 40      | HR              | 192.168.40.1        | 192.168.40.2-254  |
| 50      | Admin Right     | 192.168.50.1        | 192.168.50.2-254  |
| 60      | Admin Left      | 192.168.60.1        | 192.168.60.2-254  |
| 90      | Print           | 192.168.90.1-4      | 192.168.90.5-254  |
| 100     | CIO             | 192.168.100.1       | 192.168.100.2-254 |
| 110     | Management      | 192.168.110.1       | 192.168.110.2-254 |
| 120     | Accounting      | 192.168.120.1       | 192.168.120.2-254 |
| 130     | Sales           | 192.168.130.1       | 192.168.130.2-254 |
| 140     | HR              | 192.168.140.1       | 192.168.140.2-254 |

> **Note:** VLAN 90 exists in multiple sites with different IPs to avoid conflicts.

---

## 🔁 Routing Protocol

Dynamic routing is configured using:

- **EIGRP** (Enhanced Interior Gateway Routing Protocol)  
- **AS Number:** 10  
- All routers exchange routes dynamically, ensuring full connectivity between VLANs across all sites.

---

## 📡 Inter-VLAN Routing

Implemented with **Router-on-a-Stick**:

- Sub-interfaces configured per VLAN
- IEEE 802.1Q encapsulation
- Trunk links between routers and switches
- Each VLAN has its own IP subnet and DHCP pool

---

## 🖥 DHCP Configuration

Each router provides DHCP services for its local VLANs:

- Excludes the router’s IP (Gateway) from DHCP pool
- Configures default router (Gateway) and DNS server (8.8.8.8)
- Enables automated IP addressing for hosts
- Reduces manual configuration errors

---

## 🔐 Security Configuration

Basic security measures applied to all devices:

|  Device Type  | Security Feature                    |
|---------------|-------------------------------------|
| Router/Switch | Hostname configured                 |
| Router/Switch | Enable secret password set          |
| Router/Switch | Console password protection         |
| Router/Switch | Service password encryption enabled |

> These configurations protect access to Cisco IOS devices from unauthorized users.

---

## 📂 Devices Summary

### Routers
| Router Name | Connected VLANs |      WAN Links      |
|-------------|-----------------|---------------------|
| AMD_RW.0    | 100             | 10.0.0.0 / 11.0.0.0 |
| AMD_RW.1    | 90,110,120      | 10.0.0.0 / 14.0.0.0 |
| AMD_RW.2    | 10,20,90        | 11.0.0.0 / 12.0.0.0 |
| AMD_RW.3    | 130,140,90      | 14.0.0.0 / 15.0.0.0 |
| AMD_RW.4    | 30,40,90        | 12.0.0.0 / 13.0.0.0 |
| AMD_RW.5    | 50,60,90        | 13.0.0.0 / 15.0.0.0 |

### Switches
| Switch Name | Connected VLANs |   Special Config   |
|-------------|-----------------|--------------------|
| AMD_SW.0    | 90,110,120      | Trunk to router    |
| AMD_SW.1    | 10,20,90        | Voice VLAN enabled |
| AMD_SW.2    | 50,60,90        | Voice VLAN enabled |
| AMD_SW.3    | 130,140,90      | Voice VLAN enabled |
| AMD_SW.4    | 30,40,90        | Voice VLAN enabled |
| AMD_SW.6    | 100             | Voice VLAN enabled |

---

## 🛠 Technologies Used

- VLAN Segmentation  
- 802.1Q Trunking  
- Router-on-a-Stick  
- DHCP Server Configuration  
- EIGRP Dynamic Routing  
- Voice VLAN Support  
- Basic Cisco IOS Security  

---

## 🎯 Project Objectives

- Implement **scalable VLAN segmentation** across multiple sites  
- Enable **inter-site communication** via Router-on-a-Stick  
- Automate IP addressing using **DHCP**  
- Ensure **dynamic routing** between multiple routers  
- Simulate **enterprise-level network design**  
- Demonstrate **Voice VLAN configuration** for VoIP readiness  

---

## 📸 Topology Diagram

![Network Topology](network_topology.png)

---

## 🚀 Author

**Ahmed Alsayed**  
CCNA Student | Networking & Cybersecurity Enthusiast  

---

## 📂 Files Included

- `enterprise-network.pkt` → Cisco Packet Tracer file  
- `configs/` → All router & switch configurations as `.txt`  
- `network-diagram.png` → Topology diagram  
- `README.md` → Project documentation
