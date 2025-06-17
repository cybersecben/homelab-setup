# Seafile Setup

## Goal
Self-hosted file server for sharing and transfering files, basically a self-manged and self-hosted dropbox.

## Deployment

**Service Type:** LXC Container  
**Base OS:** Ubuntu 22.04  
**Installation Method:** [Seafile installation script](https://manual.seafile.com/12.0/setup/setup_ce_by_docker/#getting-started)

```bash
mkdir /opt/seafile
cd /opt/seafile

# Seafile CE 12.0
wget -O .env https://manual.seafile.com/12.0/repo/docker/ce/env
wget https://manual.seafile.com/12.0/repo/docker/seadoc.yml
wget https://manual.seafile.com/12.0/repo/docker/ce/seafile-server.yml
wget https://manual.seafile.com/12.0/repo/docker/caddy.yml

docker compose up -d
```

---

## Extra Considerations
- Docker instalation is required.
- File server only acessible inside network.

--- 

## Visual Dashboard
![imagen](https://github.com/user-attachments/assets/ade3af7c-0c51-47b4-8680-0ca446f5048a)
