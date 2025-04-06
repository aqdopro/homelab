# 🧠 Homelab Learning Journey

Welcome to my homelab documentation! This space is where I explore networking, security, and systems administration concepts using real hardware and virtual tools. The goal is to become confident in managing IT infrastructure while experimenting with best practices and modern technologies.

---

## 🏗️ Current Setup

- **Firewall**: pfSense running on a Lenovo M720q with VLAN segmentation and firewall rules.
- **Access Point**: Planning to add a Ubiquiti AP for reliable wireless networking.
- **Switch**: Will be adding a Ubiquiti 16-Port PoE switch to manage VLAN traffic and power devices.
- **Devices**: PC, IoT devices, future Unifi Cloud Key Gen2 and Doorbell, and servers.

---

## 📚 What I'm Learning

### 🔐 pfSense Firewall

- Configuring **LAN/WAN interfaces**
- Creating and managing **VLANs**
- Setting up **firewall rules** for network segmentation
- Enabling **SSH** and remote access for secure management
- DHCP and **static IP assignment** for better control
- Automated and manual **backup/restore** of configuration

### 🌐 Networking Concepts

- **VLANs** and subnetting for organizing traffic
- Differences between **TCP/UDP**, and **OSI vs TCP/IP** models
- Assigning VLANs on managed switches (e.g. Ubiquiti)
- Using **SFP modules** for future 1G/2.5G/10G network expansion
- **Network isolation** and segmentation for security

### 💡 Real-World Scenarios

- Isolating IoT and Guest networks from critical infrastructure
- Creating a **Security VLAN** for surveillance and smart devices
- Integrating servers into the Main VLAN with static IPs
- Using Unifi Controller app with Cloud Key + Doorbell across VLANs

---

## 🔒 VLAN and Firewall Strategy

| VLAN | Name      | Purpose                  | Rules Summary                            |
|------|-----------|--------------------------|------------------------------------------|
| 10   | 🖥 Main     | PCs, Workstations        | Full access, can reach other VLANs       |
| 20   | 📡 IoT      | Smart Home Devices       | Isolated, no access to other VLANs       |
| 30   | 🔐 Security | Cameras, Doorbell        | Fully isolated for critical protection   |
| 40   | 🧳 Guests   | Visitors and Phones      | Internet-only, no LAN/VLAN access        |

---

## 🛠️ Tools I'm Using

- **pfSense**: Open-source firewall/router OS
- **Markdown**: For documenting configs and notes
- **SSH**: For remote terminal management
- **Unifi App**: Wireless and IoT device control
- **Playit.gg** (planned): Secure remote access tunnels

---

## 🎯 Goals

- Build a **secure**, segmented home network
- Practice **real-world IT and sysadmin** tasks
- Deepen knowledge in **firewall and switch** management
- Prepare for **certifications** or **IT roles**
- Set up local services (Pi-hole, Plex, Minecraft servers)

---

Stay tuned! I’ll keep updating this as I grow my homelab and explore new topics. 🚀
