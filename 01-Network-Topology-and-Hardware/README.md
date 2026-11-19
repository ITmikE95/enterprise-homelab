# 01 — Physical Network Topology & Power Redundancy

## Overview
This document outlines the physical hardware layout, network connectivity path, and power protection infrastructure used in my multi-OS home-lab environment.

---

## Hardware Inventory
- **Primary WAN Gateway:** Ryoko 4G Wireless Router (AT&T Cellular SIM)
- **Wireless Bridge / Extender:** Securifi Almond Router (configured in Range Extender mode)
- **Switching & Wireless Distribution:** Unmanaged Ethernet Switches, Cat5e/Cat6 Ethernet cabling, and dedicated Wireless Access Point (AP)
- **Compute Nodes:** 4 physical computers running multi-OS environments
- **Power Protection:** APC Uninterruptible Power Supply (UPS) Battery Backup & Surge Protection

---

## Data & Power Flow

### 1. Network Connectivity Path
1. **Cellular WAN:** The Ryoko 4G router establishes external internet connectivity via an AT&T cellular data connection.
2. **Wireless-to-Wired Bridge:** The Securifi Almond router connects wirelessly to the Ryoko 4G gateway and bridges traffic to its physical LAN ports.
3. **Layer 2 Switching:** An Ethernet uplink connects the Almond extender to unmanaged Ethernet switches, distributing wired network access across all 4 lab machines and the dedicated Wireless Access Point.
4. **Centralized Management:** All 4 lab computers are accessed and administered from a primary workstation using **Remmina** (RDP/VNC/SSH).

### 2. Power Redundancy Architecture
- All 4 physical compute nodes are connected directly to an **APC UPS battery backup unit**.
- **Purpose:** Prevents abrupt shutdowns, operating system corruption, and loss of active lab configurations during utility power outages or voltage drops.

---

## Verification & Testing Notes
- Verified wired link lights and Layer 2 connectivity across all unmanaged switch ports.
- Confirmed stable local IP assignment and outbound internet routing through the cellular-to-wireless bridge.
- Verified uninterrupted workstation power during simulated AC disconnect testing on the APC UPS.
