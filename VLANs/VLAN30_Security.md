# VLAN 30 - 🛡️ Security Network

## Description
Dedicated to security devices like cameras, doorbells, and UniFi controllers.

## Subnet
`10.1.30.0/24`

## Devices
- UniFi Protect Doorbell
- Cloud Key Gen2
- Security cameras

## Rules Summary
| Action   | Protocol | Source IP Range | Destination            | Port | Description              |
| -------- | -------- | --------------- | ---------------------- | ---- | ------------------------ |
| ✅ Pass  | IPv4 *   | `10.1.30.0/24`  | Internet               | 443  | Allow cloud connectivity |
| ❌ Block | IPv4 *   | `10.1.30.0/24`  | VLAN10, VLAN20, VLAN40 | Any  | Block inter-VLAN access  |

## Notes
- Consider static IPs for monitoring devices.

[[Homelab_Configurations]]
