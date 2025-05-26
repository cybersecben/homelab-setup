# AdGuard Home Setup

## Overview

AdGuard Home is a network-wide tracker and ad blocker. It functions as a DNS server that filters out unwanted content before it reaches your devices.

---

## Goal

- Block ads, trackers, and malicious domains across all devices on the network.
- Improve network performance and privacy.
- Gain visibility into DNS queries and client activity.

---

## Deployment

**Service Type:** LXC Container  
**Base OS:** Debian template  
**Installation Method:** [AdGuard Home installation script](https://github.com/AdguardTeam/AdGuardHome)

```bash
curl -s -S -L https://raw.githubusercontent.com/AdguardTeam/AdGuardHome/master/scripts/install.sh | sh -s -- -v
```

---

## Visual Dashboard
![imagen](https://github.com/user-attachments/assets/71d50aeb-d260-4c46-bff3-bc38faa1ae58)
