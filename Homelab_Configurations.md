# 🛠️ Homelab Configurations

# Homelab Network Configuration Overview

## VLAN Configuration Table

| VLAN ID | Name          | Devices (Example)                      | Firewall Rules Applied                | Notes                          |
|---------|---------------|----------------------------------------|---------------------------------------|--------------------------------|
| VLAN10  | 🖥️ Main Network | Main PC, Server nodes, Admin devices   | Allow internet access, Block other VLANs | Primary trusted network         |
| VLAN20  | 📱 IoT Network | Smart plugs, IoT hubs, Smart displays  | Allow web access, Block access to other VLANs | IoT devices, limited access    |
| VLAN30  | 🛡️ Security Network | UniFi Protect Doorbell, Security cameras | Allow cloud connectivity, Block other VLANs | Security-focused devices        |
| VLAN40  | 🧳 Guest Network | Phones, Laptops, Tablets               | Allow web access, Block access to other VLANs | Isolated for guest use         |

---

## Detailed Firewall Rules Summary

| VLAN ID | Rule Description | Action | Source | Destination  | Port(s)         | Protocol |
|---------|------------------|--------|--------|--------------|-----------------|----------|
| VLAN10  | Allow Internet Access | ✅ Pass | Local Network (VLAN10) | Any         | Any             | IPv4     |
| VLAN10  | Allow Access to pfSense WebConfigurator | ✅ Pass | Local Network (VLAN10) | pfSense (443) | 443             | IPv4     |
| VLAN10  | Block Access to VLAN20, VLAN30, VLAN40 | ❌ Block | Local Network (VLAN10) | VLAN20, VLAN30, VLAN40 | Any     | IPv4     |
| VLAN20  | Allow Web Access Only | ✅ Pass | Local Network (VLAN20) | Any         | 80, 443         | IPv4     |
| VLAN20  | Block Access to VLAN10, VLAN30, VLAN40 | ❌ Block | Local Network (VLAN20) | VLAN10, VLAN30, VLAN40 | Any     | IPv4     |
| VLAN30  | Allow Cloud Connectivity | ✅ Pass | Local Network (VLAN30) | Internet     | 443             | IPv4     |
| VLAN30  | Block Access to VLAN10, VLAN20, VLAN40 | ❌ Block | Local Network (VLAN30) | VLAN10, VLAN20, VLAN40 | Any     | IPv4     |
| VLAN40  | Allow Web Access Only | ✅ Pass | Local Network (VLAN40) | Any         | 80, 443         | IPv4     |
| VLAN40  | Block Access to VLAN10, VLAN20, VLAN30 | ❌ Block | Local Network (VLAN40) | VLAN10, VLAN20, VLAN30 | Any     | IPv4     |

---

## 🔧 pfSense Setup
- WAN: DHCP from main router
- LAN: Custom static IP
- VLANs:
  - VLAN10: Main
  - VLAN20: IoT
  - VLAN30: Security
  - VLAN40: Guests

## 🔐 Firewall Rules
See individual VLAN notes:
- [[VLAN10_Main]]
- [[VLAN20_IoT]]
- [[VLAN30_Security]]
- [[VLAN40_Guests]]

## 🌐 Network Segmentation
- Block inter-VLAN access between IoT, Guests, and Security
- Allow Main VLAN to access all VLANs
- DNSBL configured with pfBlockerNG

## 📦 DHCP & Static
- Servers and security devices use static IPs
- DHCP ranges restricted to prevent IP conflicts
