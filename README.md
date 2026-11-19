# enterprise-homelab
Documentation, network diagrams, and troubleshooting logs for my multi-OS IT support home lab.
# Enterprise Home-Lab Infrastructure & Troubleshooting Documentation

This repository documents the architecture, configuration, and troubleshooting logs for my physical multi-OS home-lab network. The environment simulates a remote branch office utilizing cellular WAN failover/connectivity, wireless bridging, wired Layer 2 switching, and centralized remote administration.

---

## Network Architecture & Topology

```text
[ AT&T Cellular Network (4G LTE) ]
               │
               ▼
[ Ryoko 4G Wireless Router ]  <-- Primary WAN Gateway (Cellular SIM)
               │
      (( 2.4GHz Wi-Fi Bridge ))
               │
               ▼
[ Almond Securifi Router ]    <-- Configured in Wireless Range Extender / Bridge Mode
               │
       ( Ethernet Uplink )
               │
               ▼
[ Unmanaged Ethernet Switch(es) ] <-- Layer 2 Wired Distribution
   │       │       │       │
   ▼       ▼       ▼       ▼
[Node 1] [Node 2] [Node 3] [Node 4]  <-- Multi-OS Lab Workstations / Servers
                                         (Managed centrally via Remmina RDP/VNC/SSH)
```

---

## Hardware & Software Stack

### Networking & Connectivity
- **WAN Gateway:** Ryoko 4G Portable Wi-Fi Router (AT&T Cellular SIM)
- **Wireless Bridge / Extender:** Securifi Almond Touchscreen Router (configured primarily in Range Extender mode to bridge wireless WAN to wired LAN)
- **Switching & Distribution:** Unmanaged Gigabit Ethernet Switches + Cat5e/Cat6 structured cabling + Dedicated Wireless Access Point (AP)

### Compute & Remote Management
- **Lab Nodes:** 4 physical computers running multi-OS environments (Windows / Linux)
- **Remote Administration:** **Remmina** Remote Desktop Client (utilizing RDP, VNC, and SSH protocols for headless management across all lab machines)
### Power Redundancy & Physical Protection
- **Uninterruptible Power Supply (UPS):** APC Battery Backup & Surge Protection System supporting all 4 physical compute nodes and core networking equipment to prevent abrupt shutdowns, OS corruption, and data loss during utility power fluctuations.

---


## Repository Directory

- **[`01-Network-Topology-and-Hardware/`](./01-Network-Topology-and-Hardware)** — Physical cabling layout, cellular-to-bridge WAN setup, unmanaged switches, and APC UPS power redundancy.
- **[`02-Compute-Nodes-and-OS-Fleet/`](./02-Compute-Nodes-and-OS-Fleet)** — Hardware asset inventory and OS architecture across all 4 physical machines (Windows 11 Pro, Linux Mint 64-bit, legacy Linux Mint 32-bit, and Dell Latitude).
- **[`03-Troubleshooting-Logs/`](./03-Troubleshooting-Logs)** — Root-cause analysis (RCA) logs documenting legacy 32-bit OS integration, manual dependency resolution, and Remmina remote access setup.

---

## Key Skills Demonstrated
- **Layer 1 & Layer 2 Networking:** Structured Ethernet cabling, unmanaged switch uplinks, and wireless-to-wired bridging.
- **IP Addressing & Gateway Management:** Managing DHCP scopes across cellular routers, range extenders, and access points.
- **Remote Desktop & Systems Support:** Configuring headless remote access via Remmina, managing local firewall rules, and administering multi-OS endpoints.
- **Technical Documentation:** Writing clear Standard Operating Procedures (SOPs) and root-cause troubleshooting logs.
- **Power Continuity & Hardware Protection:** Implemented an APC UPS battery backup architecture to safeguard lab workstations against brownouts, surges, and unexpected power failures, ensuring data integrity and graceful shutdown capabilities.
