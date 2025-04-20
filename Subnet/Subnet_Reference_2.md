# 🧠 Subnetting Reference Table

## 📊 Common Subnet Masks and CIDR Notation

| CIDR | Subnet Mask        | # of Subnets (Class C) | Hosts per Subnet | Block Size |
|------|--------------------|------------------------|------------------|------------|
| /24  | 255.255.255.0      | 1                      | 254              | 256        |
| /25  | 255.255.255.128    | 2                      | 126              | 128        |
| /26  | 255.255.255.192    | 4                      | 62               | 64         |
| /27  | 255.255.255.224    | 8                      | 30               | 32         |
| /28  | 255.255.255.240    | 16                     | 14               | 16         |
| /29  | 255.255.255.248    | 32                     | 6                | 8          |
| /30  | 255.255.255.252    | 64                     | 2                | 4          |
| /31  | 255.255.255.254    | N/A                    | 0 (point-to-point) | 2        |

---

## 🔢 Block Size Ranges Table

| CIDR | Block Size | Subnet Ranges                                  |
|------|------------|------------------------------------------------|
| /25  | 128        | 0–127, 128–255                                 |
| /26  | 64         | 0–63, 64–127, 128–191, 192–255                 |
| /27  | 32         | 0–31, 32–63, 64–95, 96–127, 128–159, 160–191, 192–223, 224–255 |
| /28  | 16         | 0–15, 16–31, 32–47, 48–63, 64–79, 80–95, 96–111, 112–127, 128–143, 144–159, 160–175, 176–191, 192–207, 208–223, 224–239, 240–255 |
| /29  | 8          | 0–7, 8–15, ..., 248–255                        |
| /30  | 4          | 0–3, 4–7, ..., 252–255                         |

> 💡 Tip: For /29 and /30, you can use spreadsheet formulas or scripts to generate full ranges.

---

## 🚀 Seven Second Subnetting Steps

1. **Find Block Size** from CIDR (/X)
2. **Determine Subnet Range** your IP falls in
3. **Network Address** = start of that range
4. **Broadcast Address** = end of that range
5. **First Usable IP** = Network + 1
6. **Last Usable IP** = Broadcast - 1

---
