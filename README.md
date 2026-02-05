This is my first IT lab project: I built a fully documented multi-OS virtual environment with Kali Linux, Ubuntu, Windows 10/11, and Windows Server. In this lab, I showcase my skills in hands-on virtualization, domain and network setup, and system administration.

# MultiOS Virtual Lab

This is my first IT lab project. I built a fully documented multi-OS virtual environment with Kali Linux, Ubuntu, Windows 10/11, and Windows Server 2022. My goal was to set up a lab that allows me to practice and showcase skills in virtualization, system administration, networking, and domain management.

All virtual machines run on VMware Workstation and are stored on an external SSD for portability and performance.

---

## Project Goals

In this lab, I wanted to:

- Gain hands-on experience with virtualization and multi-OS deployment
- Build a Windows domain environment and integrate client machines
- Practice networking, system administration, and security configuration
- Document the lab setup in a professional, reproducible way

---

## VM Inventory & Configuration

| VM Name | OS | CPU | RAM | Disk | Network | Purpose |
|---------|----|-----|-----|------|---------|---------|
| Kali-2026.1-x64 | Linux (Debian 13.x) | 2 vCPUs | 4 GB | 60 GB | NAT | Penetration testing and security practice |
| Win10-22H2-Lab | Windows 10 | 2 vCPUs | 4–6 GB | 60 GB | NAT | Client machine for domain integration |
| Win11-23H2-Lab | Windows 11 | 2 vCPUs | 4–6 GB | 60 GB | NAT | Modern client OS testing |
| Server2022-Lab | Windows Server 2022 | 2 vCPUs | 4–6 GB | 80 GB | NAT/Host-only | Domain controller, DNS, DHCP |
| Ubuntu-24.04-Server | Linux | 1–2 vCPUs | 2–4 GB | 40 GB | NAT | Optional Linux client/server integration |

CPU and RAM allocations are set to allow multiple VMs to run simultaneously without overloading the host machine.

---

## Lab Architecture

- Host machine: Windows (or macOS/Linux) running VMware Workstation
- Virtual network:
  - NAT for internet access
  - Host-only for isolated internal lab network (optional)
- External SSD stores all VM virtual disks for portability
- I use snapshots to preserve clean states before making major changes

> Placeholder for diagram: `Docs/Network-Diagram.png`

---

## Installation Notes

- **Kali Linux:** installed using guided partitioning; GRUB bootloader installed; VMware Tools installed for smooth integration; hostname: KALI-LAB
- **Windows VMs:** default installation with admin accounts; Windows 10/11 clients configured to join the LAB.LOCAL domain after the server is set up; hostnames follow consistent naming conventions
- **Ubuntu:** optional Linux client/server integration
- Disks: growable virtual disks to save space on the external SSD
- CPU and RAM allocations are moderate to allow multiple VMs to run simultaneously

---

## Domain & Hostname Strategy

- Domain name: LAB.LOCAL
- Windows Server hostname: SRV2022
- Windows client hostnames: WIN10-CLIENT, WIN11-CLIENT
- Kali hostname: KALI-LAB (optional domain join)
- Fully qualified domain example: WIN10-CLIENT.LAB.LOCAL

Keeping hostnames and domains consistent ensures clarity and prevents conflicts.

---

## Security & Credentials

I document usernames, passwords, and hostnames internally in the Docs folder using placeholders. No sensitive personal data is included. Example:

