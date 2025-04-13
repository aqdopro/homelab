# 🎬 Jellyfin / Plex

This note covers the setup, planning, and goals for a media server in my homelab using either **Jellyfin** or **Plex**.

## 📽️ Purpose

- Stream 1080p and 4K media across local network and remotely
- Organize movies, TV shows, anime, and personal videos
- Enable hardware-accelerated transcoding
- Share media to close family members with various devices

## 🧩 Software Options

| Platform | Notes |
|----------|-------|
| Jellyfin | Fully open-source, no subscriptions |
| Plex     | Mature ecosystem, some features require Plex Pass |

## 🧰 Planned Setup

- Host on: Baremetal
- Access: LAN, Tailscale or VPN for remote access
- Storage: Mounted NAS share 
- Monitoring: Netdata, Prometheus + Grafana

## 💾 Transcoding Hardware

- ✅ **Planned**: NVIDIA Quadro P2000  
  Great for 4K transcoding, widely supported by both Jellyfin and Plex

## 🔐 Access & Security

- [ ] Create read-only media share for Jellyfin/Plex
- [ ] Isolate network via VLAN (e.g., `Main` or dedicated `Media` VLAN)
- [ ] Limit guest access to media server only
- [ ] Optional: Enable HTTPS with reverse proxy (NGINX or Caddy)

## 📝 Tasks

- [ ] Install Jellyfin or Plex
- [ ] Configure media libraries
- [ ] Test transcoding and remote access
- [ ] Add monitoring and backup jobs

## 🔗 Related Notes

- [[Homelab_Server]]
- [[Homelab_Equipment]]
- [[Homelab_Configurations]]
- [[Homelab_Tools]]
