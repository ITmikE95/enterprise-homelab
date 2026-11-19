# 03 — Troubleshooting Logs & Root-Cause Analysis (RCA)

This document records real-world technical challenges encountered while building, networking, and administering my multi-OS home-lab environment, along with the diagnostic steps and resolutions executed.

---

## Incident Log #001: Legacy 32-Bit OS Deployment & Network/Remote Access Integration (Dell Inspiron 530)

### 1. Problem Statement
Integrating a legacy **Dell Inspiron 530** (Intel Pentium Dual-Core, 32-bit architecture) into a modern 2026 multi-OS lab network alongside 64-bit Windows 11 Pro and Linux Mint 22.3 workstations. Due to the age of the hardware and deprecation of standard 32-bit software support, automated installation and standard network/remote-access configurations failed out of the box.

### 2. Symptoms & Technical Bottlenecks
- **OS & Architecture Constraints:** Modern 64-bit operating systems were incompatible with the legacy hardware, requiring a lightweight 32-bit OS (**Linux Mint 19.3 "Tricia" 32-bit**) capable of running reliably in 2026.
- **Package & Dependency Deprecation:** Standard one-click package installations and modern repository sources failed or threw dependency errors due to end-of-life (EOL) 32-bit support timelines.
- **Network & Remote Bridging Failures:** Establishing cross-machine communication and remote management (**Remmina** via SSH/VNC) between the legacy Inspiron 530 and modern 64-bit nodes required manual service installation, protocol alignment, and network configuration.

### 3. Diagnostic & Resolution Steps
1. **Legacy OS Selection & Deployment:** Audited hardware limits and deployed **Linux Mint 19.3 (32-bit)** to balance modern desktop usability with low CPU/RAM overhead.
2. **Manual Package & Repository Remediation:** Bypassed broken automated installers by manually resolving software dependencies, verifying network interface configurations, and installing required remote-access daemons (SSH/VNC) individually via terminal.
3. **Network & Firewall Alignment:**
   - Verified static/DHCP IP assignment through the unmanaged Ethernet switch and Securifi Almond wireless bridge.
   - Configured local firewall rules (`ufw`) and remote desktop service permissions to allow inbound administrative connections from the primary **Remmina** management console.
4. **End-to-End Verification:** Tested and confirmed stable terminal (SSH) and graphical (VNC) remote sessions from the primary 64-bit Linux Mint 22.3 workstation without packet loss or session drops.

### 4. Key Takeaways & Skills Applied
- **Persistence & Root-Cause Troubleshooting:** Diagnosed multi-layered compatibility issues over an extended testing cycle rather than abandoning legacy hardware.
- **Linux CLI & Manual Dependency Management:** Gained hands-on experience installing and configuring services manually when automated GUI tools fail.
- **Cross-Generation Interoperability:** Successfully bridged legacy 32-bit x86 systems with modern 64-bit Windows 11 and Linux endpoints on a unified LAN.
