# Jellyfin Setup

## Goal
Self-hosted media server for streaming movies and TV shows.

## Deployment

**Service Type:** LXC Container  
**Base OS:** Ubuntu 22 template  
**Installation Method:** [Jellyfin installation script](https://jellyfin.org/docs/general/installation/linux)

```bash
curl https://repo.jellyfin.org/install-debuntu.sh | sudo bash
```

---

## Extra Considerations
- Media mounted from 1TB SSD, shared with Jellyfin via bind mount
- Access done through Internal IP + port
- Hardware acceleration enabled for faster transcoding

--- 

## Visual Dashboard
![imagen](https://github.com/user-attachments/assets/7569971a-f7f0-4f17-9b59-faef309789c4)
