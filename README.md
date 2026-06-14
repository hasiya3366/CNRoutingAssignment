# Advanced Routing Protocol Configuration Lab (CNRoutingAssignment)

**Coursework Module:** Computer Networks  
**Student Name:** Hasindu Indusara  
**Institution:** NSBM Green University  
**Implementation Date:** June 14, 2026  

---

## 📌 Project Overview
This repository contains the full Cisco Packet Tracer network implementations exploring three autonomous routing methods: Manual Static Routing, Routing Information Protocol Version 2 (RIPv2), and Enhanced Interior Gateway Routing Protocol (EIGRP). 

The underlying topology models a distributed regional campus network interconnecting three core hub locations—**ColomboNSBM**, **KandyNSBM**, and **GalleNSBM**—configured in a redundant triangular matrix loop.

---

## 📂 Repository Contents & Structure

This repository includes three standalone `.pkt` lab files representing each independent phase of network routing implementation alongside diagnostic report logs:

*   📂 `Static_Routing.pkt` - Network implementation utilizing manual static route mapping parameters.
*   📂 `RIP_Routing.pkt` - Dynamic network implementation using classless RIPv2 configuration boundaries.
*   📂 `EIGRP_Routing.pkt` - Advanced dynamic implementation using the hybrid Cisco DUAL algorithm engine.

---

## 🌐 Network Addressing Architecture

All devices in the independent network files are hardcoded using the following structured classless IP allocation matrix:

| Network Segment | Subnet / CIDR Block | Subnet Mask | Local Gateway Interface | Target Host IP |
| :--- | :--- | :--- | :--- | :--- |
| **Colombo LAN (Network A)** | 192.168.1.0/24 | 255.255.255.0 | GigabitEthernet0/0 (192.168.1.1) | PC1: 192.168.1.10 |
| **Kandy LAN (Network B)** | 192.168.2.0/24 | 255.255.255.0 | GigabitEthernet0/0 (192.168.2.1) | PC0: 192.168.2.10 |
| **Galle LAN (Network C)** | 192.168.3.0/24 | 255.255.255.0 | GigabitEthernet0/0 (192.168.3.1) | PC2: 192.168.3.10 |
| **Kandy to Galle Link** | 10.0.0.0/30 | 255.255.255.252 | Gig0/2 (Kandy) / Gig0/2 (Galle) | .1 (Kandy) / .2 (Galle) |
| **Colombo to Galle Link** | 11.0.0.0/30 | 255.255.255.252 | Gig0/2 (Col) / Gig0/1 (Galle) | .1 (Col) / .2 (Galle) |
| **Colombo to Kandy Link** | 12.0.0.0/30 | 255.255.255.252 | Gig0/1 (Col) / Gig0/1 (Kandy) | .1 (Col) / .2 (Kandy) |

---

## 🛠️ Verification & Diagnostic Testing

To verify the successful deployment of the standalone configurations inside Cisco Packet Tracer, execute the following instructional tasks:

### 1. Routing Table Analysis
Open any core router CLI tab, elevate your administrative execution mode (`enable`), and execute the routing table inspection check:
```text
Router# show ip route
