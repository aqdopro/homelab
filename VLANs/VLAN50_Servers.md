# 🖥️ VLAN50 - Servers

**VLAN ID**: 50  
**Purpose**: Dedicated VLAN for home lab servers including NAS, media servers (e.g., Jellyfin/Plex), and other future server projects.  
**Subnet**: `10.1.50.0/24`  
**DHCP Range**: `10.1.50.100 - 10.1.50.200`

## 🔐 Firewall Rules

| Action   | Protocol | Source IP/Subnet | Destination        | Description                           |
| -------- | -------- | ---------------- | ------------------ | ------------------------------------- |
| ✅ Pass  | Any      | VLAN50 net       | WAN                | Allow internet access                 |
| ✅ Pass  | Any      | VLAN50 net       | VLAN10 net         | Allow access to main network          |
| ❌ Block | Any      | VLAN50 net       | VLAN20, 30, 40 net | Block access to IoT, Security, Guests |

## 🔧 Notes

- This VLAN is meant for devices like NAS, Jellyfin/Plex servers, backups, and docker containers.
    
- Static IPs are recommended for reliability.
    
- Can access VLAN10 (Main) for management/admin.
    

## 🔗 Backlinks

- [[Homelab_Configurations]]
    
- [[Homelab_Server]]