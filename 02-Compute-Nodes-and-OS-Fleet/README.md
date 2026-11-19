# 02 — Multi-OS Compute Nodes & Endpoint Fleet

## Overview
This document details the hardware specifications, operating system architectures, and functional roles of the 4 endpoints deployed within my home-lab environment. All nodes are wired via unmanaged Ethernet switches, protected by an APC UPS battery backup system, and centrally managed via **Remmina**.

---

## Endpoint Asset Inventory

| Node ID | System / Chassis | Processor (CPU) | Operating System | Architecture | Primary Lab Role |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Node 01** | Custom-Built Desktop | Intel Core i5-4590 (Quad-Core) | Linux Mint 22.3 (Cinnamon) | 64-bit (x86_64) | Primary Linux workstation & Remmina central management console |
| **Node 02** | Custom-Built Desktop | Intel Core i5-4590 (Quad-Core) | Windows 11 Pro | 64-bit (x64) | Windows administrative endpoint, RDP host, & local policy/system testing |
| **Node 03** | Dell Inspiron 530 | Intel Pentium Dual-Core | Linux Mint 19.3 "Tricia" (Cinnamon) | 32-bit (x86) | Legacy hardware/OS compatibility testing, SSH/VNC endpoint, & lightweight network services |
| **Node 04** | Dell Latitude 2-in-1 | Intel Mobile Processor | Multi-OS / Portable Endpoint | 64-bit | Mobile endpoint testing, wireless AP roaming, & remote access verification |

---

## Key Technical Takeaways & IT Support Skills

* **Cross-Platform Administration:** Managing both **Windows 11 Pro** and **Linux Mint** environments simultaneously, including user permissions, local firewall rules, and package/update management.
* **Legacy Hardware Lifecycle Management:** Repurposing older 32-bit architecture (Dell Inspiron 530 with Intel Pentium Dual-Core) using lightweight Linux distributions to maintain usability and extend hardware ROI—a common requirement in budget-conscious IT environments.
* **Remote Protocol Configuration:**
  * Configured **RDP** (Remote Desktop Protocol) on Windows 11 Pro for seamless remote administration.
  * Configured **SSH** and **VNC** services across Linux Mint nodes for headless terminal and GUI access via **Remmina**.
* **Hardware Diagnostics & Custom Builds:** Assembled and maintained custom desktop builds (Intel Core i5-4590 platforms), ensuring thermal stability, proper BIOS/UEFI boot configuration, and reliable NIC connectivity.
