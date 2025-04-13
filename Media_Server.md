# 🎬 Setup

This note covers the plan for setting up a Media Server in the homelab, capable of running both **Jellyfin** and **Plex**.

## 🧩 Use Case

- Stream media (movies, TV shows, music) to devices on the network and remotely
    
- Organize media libraries
    
- Support for 4K transcoding
    
- Access via web, mobile, smart TVs, etc.
    

## 🛠️ Planned Software

| Application | Purpose                  | Notes                                  |
| ----------- | ------------------------ | -------------------------------------- |
| Jellyfin    | Open-source media server | Privacy-focused, lightweight           |
| Plex        | Media server             | Broad client support, rich UI          |
| Overseerr   | Media request service    | Connects to Plex, allows user requests |

## 💽 Operating System

**TrueNAS SCALE**

- Linux-based for flexibility
    
- Supports Docker and Kubernetes
    
- Ideal for running multiple apps in containers
    

## 🧰 Features of TrueNAS SCALE

- ZFS storage support
    
- Docker and Kubernetes for app deployment
    
- Snapshot and replication support
    
- Web-based UI
    

## 📦 Services to Run

- Jellyfin (via Docker or TrueNAS App)
    
- Plex (via Docker or TrueNAS App)
    
- Overseerr (via Docker or TrueNAS App)
    
- Optional: Sonarr, Radarr, Prowlarr for automation
    

## 🔌Planned Hardware

### Ideal (for 4K transcoding and multiple users)

- CPU: Intel Xeon / Core i5, i7 (recent gen with Quick Sync) or AMD Ryzen with NVENC support
    
- RAM: 16GB or more
    
- Storage: 4+ bay NAS with ZFS support (e.g., 4x12TB drives)
    
- GPU: NVIDIA Quadro P2000 or better for hardware transcoding
    
- NIC: 2.5GbE or 10GbE for high-throughput streaming
    

## 🔗 Related Notes

- [[Homelab_Equipment]]
    
- [[VLAN50_Servers]]
    
- [[Homelab_Configurations]]
    
