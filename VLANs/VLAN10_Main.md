# VLAN 10 - 🖥️ Main Network

## Description
This VLAN is used for primary trusted devices like workstations, servers, and admin systems.

## Subnet
`192.168.10.0/24`

## Devices
- Main PC
- Server nodes
- Admin devices

## Rules Summary
| Action | Protocol | Source IP Range | Destination | Port | Description |
|--------|----------|------------------|-------------|------|-------------|
| ✅ Pass | IPv4 * | `192.168.10.0/24` | Any | Any | Allow access to internet & internal services |
| ✅ Pass | IPv4 * | `192.168.10.0/24` | pfSense | 443 | Allow WebConfigurator |
| ❌ Block | IPv4 * | `192.168.10.0/24` | VLAN20, VLAN30, VLAN40 | Any | Block access to other VLANs |

## Notes
- This VLAN is the most trusted and has wider access across the homelab.

[[Homelab_Configurations]]
