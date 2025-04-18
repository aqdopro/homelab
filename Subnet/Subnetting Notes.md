## 🧠 Subnetting Practice Guide

This note is a guide to practicing subnetting and understanding key IP address calculations.

---

### 📘 What You Should Know

- **Binary**, **Hexadecimal**, and **Decimal** conversions
    
- **Subnet Masks** and **CIDR Notation**
    
- Identifying key values from a subnet
    

---

### 🔢 Common Subnet Information

When given an IP address and CIDR (e.g., `192.168.1.0/26`), calculate:

|Field|Description|
|---|---|
|**Network ID**|First address of the subnet|
|**Broadcast IP**|Last address of the subnet|
|**First Host IP**|First usable IP address in the subnet|
|**Last Host IP**|Last usable IP address in the subnet|
|**Next Network**|Starting address of the next subnet|
|**IP Addresses**|Total number of addresses in the subnet|
|**CIDR/Subnet**|Notation that determines the size of the subnet|

---

### 🧮 How to Calculate (Simplified)

1. **Subnet Mask**: Determine from CIDR (e.g., `/26` → `255.255.255.192`)
    
2. **Block Size**: `256 - last octet of subnet mask` (e.g., `256 - 192 = 64`)
    
3. **Network ID**: Start of the block (e.g., `192.168.1.0`)
    
4. **Broadcast IP**: Last IP in the range (e.g., `192.168.1.63`)
    
5. **First Host IP**: One after Network ID (e.g., `192.168.1.1`)
    
6. **Last Host IP**: One before Broadcast IP (e.g., `192.168.1.62`)
    
7. **Next Network**: Start of the next block (e.g., `192.168.1.64`)
    

---

### 🧪 Example: `192.168.1.0/26`

|Field|Value|
|---|---|
|Network ID|`192.168.1.0`|
|First Host IP|`192.168.1.1`|
|Last Host IP|`192.168.1.62`|
|Broadcast IP|`192.168.1.63`|
|Next Network|`192.168.1.64`|
|Total IPs|`64`|
|CIDR/Subnet|`/26` = `255.255.255.192`|

---

### 🔁 Practice

Try calculating these:
[[Subnet_Reference]]

- `10.0.0.0/24`

	- Subnet Mask:
	- Network ID:
	- Broadcast IP:
	- First Host IP:
	- Last Host IP:
	- Number of Hosts:
	- Next Network:

- `172.16.5.128/25`
    
- `192.168.10.64/27`
    
