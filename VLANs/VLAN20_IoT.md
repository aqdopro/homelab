# VLAN 20 - 📱 IoT Network

## Description
Used for Internet of Things devices like smart plugs, thermostats, etc.

## Subnet
`192.168.20.0/24`

## Devices
- Smart plugs
- Smart displays
- IoT hubs

## Rules Summary
| Action | Protocol | Source IP Range | Destination | Port | Description |
|--------|----------|------------------|-------------|------|-------------|
| ✅ Pass | IPv4 * | `192.168.20.0/24` | Any | 80, 443 | Allow web access only |
| ❌ Block | IPv4 * | `192.168.20.0/24` | VLAN10, VLAN30, VLAN40 | Any | Block access to other VLANs |

## Notes
- Least trusted VLAN, internet-only access.
- Use pfBlockerNG for DNS filtering.

[[Homelab_Configurations]]
