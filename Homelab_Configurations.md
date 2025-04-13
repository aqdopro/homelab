# 🛠️ Homelab Configuration Overview

This note contains a structured overview of the VLANs, firewall rules, and key network configuration settings in the homelab.

## 🌐 VLAN Configuration

| VLAN ID | Name     | Purpose             | IP Range           | Notes                       |
| ------- | -------- | ------------------- | ------------------ | --------------------------- |
| 10      | Main     | Primary devices     | 192.168.10.100-200 | Full access to network      |
| 20      | IoT      | Smart devices       | 192.168.20.100-200 | Internet-only access        |
| 30      | Security | Cameras, Doorbell   | 192.168.30.100-200 | Limited cross-VLAN access   |
| 40      | Guest    | Guest Wi-Fi clients | 192.168.40.100-200 | No access to internal VLANs |
| 50      | Servers  | NAS, Media Servers  | 192.168.50.100-200 | VLAN for internal services  |

## 🔥 Firewall Rules Summary

| VLAN   | Source IP Range | Destination            | Action   | Description                        |
| ------ | --------------- | ---------------------- | -------- | ---------------------------------- |
| VLAN10 | 192.168.10.0/24 | Any                    | ✅ Pass  | Allow full access                  |
| VLAN20 | 192.168.20.0/24 | !192.168.10.0/24       | ✅ Pass  | Allow internet, block main         |
| VLAN20 | 192.168.20.0/24 | VLAN30, VLAN40         | ❌ Block | Block access to other VLANs        |
| VLAN30 | 192.168.30.0/24 | VLAN10, VLAN20         | ❌ Block | Block access to other VLANs        |
| VLAN40 | 192.168.40.0/24 | VLAN10, VLAN20, VLAN30 | ❌ Block | Guests blocked from internal VLANs |
| VLAN50 | 192.168.50.0/24 | VLAN10                 | ✅ Pass  | Servers can access main VLAN       |
| VLAN50 | 192.168.50.0/24 | VLAN20, VLAN30, VLAN40 | ❌ Block | Isolated from other VLANs          |

## 📁 Linked VLAN Notes

- [[VLAN10_Main]]
    
- [[VLAN20_IoT]]
    
- [[VLAN30_Security]]
    
- [[VLAN40_Guests]]
    
- [[VLAN50_Servers]]
    

## 🔧 Management Settings

- WebConfigurator accessible on VLAN10
    
- DHCP enabled for all VLANs
    
- VLAN interfaces created and assigned
    
- Basic firewall rules in place for segmentation and security
    

---

Back to [[Homelab_Configurations]]