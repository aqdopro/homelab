
## Reference Table

|                 |     |     |     |     |     |     |     |     |
| --------------- |:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| **Number of IPs**  | 128 | 64  | 32  | 16  |  8  |  4  |  2  |  1  |
| **Subnet Mask** | 128 | 192 | 224 | 240 | 248 | 252 | 254 | 255 |
| **CIDR**        | /25 | /26 | /27 | /28 | /29 | /30 | /31 | /32 |

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