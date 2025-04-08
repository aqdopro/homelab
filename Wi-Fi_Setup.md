# Wi-Fi Network Planning 🛜

This note outlines the planned Wi-Fi SSIDs, associated VLANs, and usage for future wireless network setup. Passwords will be set once an access point (AP) is installed.

## Overview

- Wi-Fi networks will be broadcasted using a Ubiquiti Access Point.
- Each SSID will be mapped to a specific VLAN in pfSense.
- Wi-Fi passwords and SSID broadcast will be configured in the UniFi Controller / Cloud Key.

## Planned Wi-Fi SSIDs and VLAN Assignments

| SSID Name | VLAN ID | Purpose         | Wi-Fi Password (to be set in AP) | Linked VLAN |
|-----------|---------|------------------|-----------------------------------| ----- |
| **MainNet**  | 10      | Trusted devices   | Set later in UniFi Controller     | [[VLAN10_Main]] |
| **IoTNet**   | 20      | Smart devices     | Set later in UniFi Controller     | [[VLAN20_IoT]] |
| **SecNet**   | 30      | Security devices  | Set later in UniFi Controller     | [[VLAN30_Security]] |
| **GuestNet** | 40      | Guest access      | Set later in UniFi Controller     | [[VLAN40_Guests]] |

---
## In the Meantime

 - [x] Pre-define VLANs in pfSense.
 - [x] Plan SSID names and which VLAN each SSID should map to.
 - [ ] Set up firewall rules for those VLANs.

---
## To Do Once AP Is Installed

- [ ] Install Ubiquiti Access Point
- [ ] Connect AP to VLAN trunk port on managed switch
- [ ] Log in to UniFi Controller / Cloud Key
- [ ] Create each SSID and map to correct VLAN
- [ ] Set strong Wi-Fi password per SSID
- [ ] Test VLAN isolation and firewall rules

---

**Backlinks:**
- [[Homelab_Configurations]]