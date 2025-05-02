# 🌐 Subnetting Practice Notes
|                |                                        |
| -------------- | -------------------------------------- |
| Network ID     | First IP address in each Sub-Network   |
| Broadcast IP   | Last IP address in each Sub-Network    |
| First Host IP  | IP address **after** the Network ID    |
| Last Host IP   | IP address **before** the Broadcast IP |
| Next Network   | IP addess **after** the Broadcast IP   |
| # IP Addresses | Number of IP addesses in Sub-Network   |
| CIDR / Subnet  | Converting between CIDR/Subnet Mask    |

[[Subnet_Practice]]

---

## 📘 IPv4 Basics

- An IPv4 address has **32 bits**: `xxx.xxx.xxx.xxx`
- It is divided into:
  - **Network portion**
  - **Host portion**
- Example: `192.168.1.0/24`
  - `/24` means 24 bits are for the **network**
  - Remaining **8 bits** are for **hosts**

---

## 🧮 Subnetting Steps

### 1️⃣ Determine Number of Subnets Needed
> ✏️ Formula: `2^n ≥ number_of_subnets`

- To get **4 subnets**, solve: `2^n ≥ 4`
- Result: `n = 2` (you need to borrow 2 bits)

---

### 2️⃣ New Subnet Mask

- Starting with: `/24` = `255.255.255.0`
- Borrow 2 bits → `/26` = `255.255.255.192`

---

### 3️⃣ Calculate Subnet Ranges

Each `/26` block has:
- `2^6 = 64` addresses per subnet
- `64 - 2 = 62` usable host addresses (subtract network and broadcast)

📊 Subnets:
| Subnet # | Network Address | First Host     | Last Host      | Broadcast Address |
|:--------:| --------------- | -------------- | -------------- | ----------------- |
|    1     | 192.168.10.0    | 192.168.10.1   | 192.168.10.62  | 192.168.10.63     |
|    2     | 192.168.10.64   | 192.168.10.65  | 192.168.10.126 | 192.168.10.127    |
|    3     | 192.168.10.128  | 192.168.10.129 | 192.168.10.190 | 192.168.10.191    |
|    4     | 192.168.10.192  | 192.168.10.193 | 192.168.10.254 | 192.168.10.255    |

---

## 🧠 Tips to Remember

- 🧩 Borrow bits from the host portion to make more subnets.
- 🧮 Number of usable hosts = `2^host_bits - 2`
- 🚫 Network and Broadcast addresses are **not** usable for hosts.
- 🧾 Keep subnet sizes as powers of two (8, 16, 32, 64...)

---

## 📝 Practice Challenge

> Given: `10.0.0.0/16`  
> Divide into **8 subnets**.

1. How many bits do you need to borrow?
2. What is the new subnet mask?
3. How many addresses per subnet?
4. What are the first two subnet ranges?

---
