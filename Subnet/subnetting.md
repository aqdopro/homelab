
# 🧠 Human-Friendly Subnetting (Magic Number Method)

## 📘 What is It?

A shortcut method to quickly calculate subnets without deep binary math.

Useful for:
- Network address
- Broadcast address
- Usable IPs
- Subnet ranges

---

## 🔢 Step 1: Know Your "Magic Numbers"

| CIDR | Subnet Mask        | Block Size (Magic #) |
|------|---------------------|-----------------------|
| /24  | 255.255.255.0       | 256                   |
| /25  | 255.255.255.128     | 128                   |
| /26  | 255.255.255.192     | 64                    |
| /27  | 255.255.255.224     | 32                    |
| /28  | 255.255.255.240     | 16                    |
| /29  | 255.255.255.248     | 8                     |
| /30  | 255.255.255.252     | 4                     |

🧮 Magic Number Formula:
```
Block Size = 256 - (last octet of subnet mask)
```

---

## 🚀 Step 2: Use It!

### Example:
**IP Address:** `192.168.1.0/26`

- Subnet Mask: 255.255.255.192
- Magic Number: `256 - 192 = 64`
- Subnet jumps: every 64 in the last octet

```
📊 Subnet Ranges:
192.168.1.0     → Network
192.168.1.1     → First usable
192.168.1.62    → Last usable
192.168.1.63    → Broadcast

192.168.1.64    → Next subnet
...
```

---

## 📝 Fast Steps to Subnet

1. ✏️ Get the subnet mask (CIDR format)
2. 🔍 Find the magic number: `256 - subnet mask's last octet`
3. ➕ Increment the subnet using that number
4. 📐 First IP = subnet + 1
5. 📛 Broadcast = next subnet - 1
6. ✅ Usable hosts = IPs between network and broadcast

---

## 🧪 Quick Practice

**Given:** `192.168.10.0/27`

- Subnet Mask: 255.255.255.224
- Magic Number: `256 - 224 = 32`

🎯 Subnets:
- 192.168.10.0 → 192.168.10.31 (broadcast)
- 192.168.10.32 → 192.168.10.63
- 192.168.10.64 → 192.168.10.95
- And so on...

---

## 🔁 Pro Tip

Memorize this cheat:

| CIDR | Hosts | Magic # |
|------|--------|----------|
| /30  | 2      | 4        |
| /29  | 6      | 8        |
| /28  | 14     | 16       |
| /27  | 30     | 32       |
| /26  | 62     | 64       |
| /25  | 126    | 128      |
| /24  | 254    | 256      |

💡 Hosts = `2^host_bits - 2`

---
