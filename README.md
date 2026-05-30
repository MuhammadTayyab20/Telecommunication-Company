<div align="center">

# 🏢 Telecommunication Company — Secure Enterprise Network

### *A scalable, secure, two-tier enterprise network with VLANs, OSPF, VoIP, Wi-Fi, a DMZ & an ASA firewall — built in Cisco Packet Tracer*

![Packet Tracer](https://img.shields.io/badge/Cisco%20Packet%20Tracer-8.2.2-1BA0D7?style=for-the-badge&logo=cisco&logoColor=white)
![Security](https://img.shields.io/badge/Focus-Network%20Security-D32F2F?style=for-the-badge)
![Firewall](https://img.shields.io/badge/Firewall-Cisco%20ASA%205506--X-512BD4?style=for-the-badge)
![Routing](https://img.shields.io/badge/Routing-OSPF-4CAF50?style=for-the-badge)
![Services](https://img.shields.io/badge/Services-VoIP%20%7C%20Wi--Fi%20%7C%20DHCP-FF9800?style=for-the-badge)

</div>

---

## 📖 Overview

This project redesigns a telecommunication company's outdated, flat network into a **modern, secure, and scalable enterprise infrastructure**, simulated in **Cisco Packet Tracer**. It uses a **two-tier hierarchical design** and segments traffic into **data, wireless, and voice** services — with centralized management, dynamic routing, a DMZ, and a hardened **Cisco ASA firewall** perimeter.

> 🎓 **Course:** System & Network Security &nbsp;·&nbsp; 🏫 Computer Engineering Dept, Bahria University (Karachi Campus)

---

## 🎯 Problem Statement

The company's existing network was **outdated, unoptimized, and lacked security controls**. Its flat design caused:

- 🐌 Performance bottlenecks and large broadcast domains
- 🔓 Exposure to cyber-attacks with no proper segmentation
- 🛠️ No centralized management, wireless control, or secure voice
- 📉 Poor scalability — risking inefficiency, security gaps, and downtime

The goal: build a **redesigned, future-ready network** that is fast, secure, and ready to scale.

---

## ✅ Implemented Solution

A scalable and secure infrastructure built around these pillars:

| Component | Purpose |
|-----------|---------|
| 🧱 **Two-tier hierarchical design** | Core + access layers for performance and scalability |
| 🧩 **VLAN segmentation** | Separate domains for **data**, **wireless**, and **voice** |
| 🔀 **Layer 3 core switch + OSPF** | Inter-VLAN routing via SVIs; OSPF for dynamic, scalable routing |
| 🔗 **EtherChannel (Port-channels)** | Bundled trunk links between core and access switches for bandwidth + redundancy |
| 📶 **Wireless LAN Controller (WLC-2504)** | Centrally manages enterprise Wi-Fi via lightweight access points |
| ☎️ **Voice Gateway + CME** | Handles VoIP using Call Manager Express; registers IP phones |
| 🌐 **Centralized DHCP** | AD server for data/wireless; voice gateway for IP phones |
| 🛡️ **Cisco ASA firewall + DMZ** | INSIDE / DMZ / OUTSIDE security zones, NAT, ACLs, and traffic inspection |
| ☁️ **Cloud + ISP edge** | SEACOM ISP uplink and an Azure-style cloud block |

---

## 🧠 Theory in Brief

- **VLANs** divide the network into smaller, isolated domains — less broadcast traffic, better performance and security.
- **Layer 3 inter-VLAN routing** (SVIs on the core switch) lets segments communicate, while **OSPF** handles reliable path selection and scalability.
- **EtherChannel** bundles multiple physical links into one logical trunk for higher throughput and failover.
- **DHCP** automates IP assignment and removes manual errors.
- A **WLC** centrally manages wireless for consistent security policies, roaming, and monitoring.
- **VoIP** converts voice into data packets for cost-effective communication, kept on a dedicated **voice VLAN**.
- A **firewall with a DMZ** separates public-facing servers from the internal network and provides NAT, ACLs, and zone-based security.

---


## 🧱 Network Design Details

### VLANs & Addressing

| VLAN | Purpose | Network | Gateway (SVI) |
|:----:|---------|---------|---------------|
| 50 | Data (wired/wireless users) | 192.168.10.0/24 | 192.168.10.1 |
| 60 | Servers / management | 10.20.0.0/16 | 10.20.0.1 |
| 101 | Voice (VoIP / IP phones) | 172.16.10.0/24 | 172.16.10.1 |

### Firewall Zones (Cisco ASA 5506-X)

| Zone | Security Level | Subnet |
|------|:--------------:|--------|
| INSIDE | 100 (trusted) | 10.30.30.0/30 |
| DMZ | 70 | 10.10.10.0/28 |
| OUTSIDE | 0 (untrusted) | 197.200.100.0/30 |

- **NAT:** dynamic PAT from INSIDE and DMZ out to the OUTSIDE interface.
- **Routing:** OSPF process 35 in area 0 across the core switch and ISP.
- **DMZ servers:** AD, ERP, Email, and File Storage.

---

## 🖥️ Device Inventory (high level)

| Category | Examples |
|----------|----------|
| Routers | SEACOM ISP, Cisco Voice Gateway (CME), Azure Cloud |
| Firewall | Cisco ASA 5506-X (perimeter) |
| Core / Access | 3650 multilayer core switch + 2960 access switches |
| Wireless | WLC-2504 + lightweight access points |
| Servers | AD, ERP, Email, File Storage (DMZ) |
| End devices | PCs, laptops, IP phones (7960), smartphones, printers |

---


## 🏁 Final Result

A secure, scalable, and fully operational enterprise network where **all services worked seamlessly**:

- ✅ Inter-VLAN routing via OSPF
- ✅ DHCP automation for data and voice
- ✅ IP phones registered and VoIP calls connected
- ✅ Wireless clients authenticated through the WLC
- ✅ NAT, ACLs, BPDU Guard, and PortFast actively protecting the network
- ✅ DMZ isolating public-facing servers from the internal LAN

The result is a **modernized, well-structured network ready for real-world deployment**.

---

## 💡 Applications

- 📡 Telecommunication headquarters and branch networks
- 🏫 University and hospital campus networks
- 🏢 Medium-scale enterprise environments
- ☎️ Corporate buildings needing Wi-Fi, VoIP, and centralized management
- 🧪 Training labs for network engineers
- 🔐 A secure testbed for evaluating future policies or configurations

