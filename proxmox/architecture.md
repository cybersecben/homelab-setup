# Proxmox Architecture

## Hardware
- Mini PC host
- 128GB SSD – OS (Proxmox)
- 1TB SSD 
- 480GB SSD 

## Virtualization
- Proxmox VE running with:
  - 1 Ubuntu Server
  - 1 LXC Jellyfin container
  - 1 LXC Adguard container

## Network
- Bridged networking ISP router
- Own router handles DHCP
- Adguard handles DNS
