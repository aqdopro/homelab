# 🛠️ Homelab Configurations

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
