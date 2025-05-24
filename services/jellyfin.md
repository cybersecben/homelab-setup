# Jellyfin Setup

## Goal
Self-hosted media server for streaming movies and TV shows.

## Deployment
- Type: LXC container
- Base: Debian template
- Install via official Jellyfin repo

## Storage
- Media mounted from 1TB SSD
- Shared with Jellyfin via bind mount

## Access
- Internal IP + port
- Reverse proxy TBD
