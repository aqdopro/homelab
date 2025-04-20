
## Reference Table

|                 |     |     |     |     |     |     |     |     |
| --------------- |:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| **Number of IPs**  | 128 | 64  | 32  | 16  |  8  |  4  |  2  |  1  |
| **Subnet Mask** | 128 | 192 | 224 | 240 | 248 | 252 | 254 | 255 |
| **CIDR**        | /25 | /26 | /27 | /28 | /29 | /30 | /31 | /32 |

---

## 🧠 IP Address Classes Reference Table

| Class | Starting IP     | Ending IP       | Default Subnet Mask | CIDR  | Use Case                      |
|:-----:|------------------|------------------|----------------------|-------|-------------------------------|
| A     | 1.0.0.0          | 126.255.255.255  | 255.0.0.0            | /8    | Large networks (gov, ISPs)   |
| B     | 128.0.0.0        | 191.255.255.255  | 255.255.0.0          | /16   | Medium networks (universities, corps) |
| C     | 192.0.0.0        | 223.255.255.255  | 255.255.255.0        | /24   | Small networks (home, offices) |
| D     | 224.0.0.0        | 239.255.255.255  | *N/A*                | *N/A* | Multicast                     |
| E     | 240.0.0.0        | 255.255.255.255  | *N/A*                | *N/A* | Experimental / Reserved       |


### 🔍 Notes:
- **Class D** is used for **multicasting**, not typical host communication.
- **Class E** is reserved and not used in public networks.
- **Class A-C** are the ones you use when subnetting typical IPv4 networks.

---
## 🧠 Subnetting Breakdown Template

- **Given IP**: `192.168.1.0/24`
- **Subnet Mask**: `255.255.255.0`
- **CIDR Notation**: `/24`

---

### 📊 Subnet Details

| Field              | Value                |
|--------------------|----------------------|
| **Network ID**      | 192.168.1.0           |
| **Broadcast IP**    | 192.168.1.255         |
| **First Host IP**   | 192.168.1.1           |
| **Last Host IP**    | 192.168.1.254         |
| **Total IPs**       | 256 (254 usable hosts)|
| **Next Network**    | 192.168.2.0           |

---

### 🔣 Binary Representation

| Octet | Binary            |
|-------|-------------------|
| 192   | 11000000          |
| 168   | 10101000          |
| 1     | 00000001          |
| 0     | 00000000          |

---

### 🧪 Practice Problem Template

```
- Given IP Block: 
- Subnet Mask:
- Network ID:
- Broadcast IP:
- First Host IP:
- Last Host IP:
- Number of Hosts:
- Next Network:
```