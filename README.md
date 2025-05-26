# Home Lab & Proxmox Setup

This repository documents the setup, configuration, and ongoing evolution of my personal home server — a place where I experiment with virtualization, system administration, and cybersecurity tools.

---

## Goals

- Learn by doing — documenting every step to solidify knowledge.
- Build a private ecosystem of services like media hosting and personal cloud.
- Explore cybersecurity tooling in a safe and isolated environment.
- Create a portfolio of practical experience to support my career in cybersecurity.

---

## Current Setup

**Hardware:**
- Mini PC (Proxmox Host)
- 128GB SSD (OS), 1TB SSD (Media), 480GB SSD (Storage)
- ISP provided router (working as bridged modem)
- Third party router (NAT, DHCP, DNS, IP Reservation)

**Hypervisor:**
- [Proxmox VE version]

**Virtual Machines & Containers:**
- `Jellyfin` – media server (LXC)
- `Adguard Home` - DNS and ad/tracker blocker
- `Ubuntu Server` – general-purpose testing

**Visual Dashboard**
![imagen](https://github.com/user-attachments/assets/35c376f4-94dd-4bb8-932c-fe59e1e637a6)

---

## Planned Services

- ✅ Jellyfin (deployed)
- ✅ AdGuard Home (deployed)
- ⏳ Personal cloud
- ⏳ Network monitoring tool 
- ⏳ Cyber defense/analysis tools 

---

## Structure of This Repo

- `proxmox/` – notes on system architecture, VM setup, backups.
- `services/` – configs and setup guides for hosted services.
- `notes/` – things I’ve learned, useful resources, and troubleshooting tips.

---
