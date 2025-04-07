# VLAN 40 - 🧳 Guest Network

## Description
Guest access for temporary or personal devices with limited internet access.

## Subnet
`192.168.40.0/24`

## Devices
- Phones
- Laptops
- Tablets

## Rules Summary
| Action | Protocol | Source IP Range | Destination | Port | Description |
|--------|----------|------------------|-------------|------|-------------|
| ✅ Pass | IPv4 * | `192.168.40.0/24` | Internet | 80, 443 | Allow web access only |
| ❌ Block | IPv4 * | `192.168.40.0/24` | VLAN10, VLAN20, VLAN30 | Any | Block access to other VLANs |

## Notes
- Isolated by design. Great for parties or guests at home.

[[Homelab_Configurations]]
