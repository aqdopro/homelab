|            |     |     |     |     |     |     |     |     |
| ---------- | --- | --- | --- | --- | --- | --- | --- | --- |
| Group Size | 128 | 64  | 32  | 16  | 8   | 4   | 2   | 1   |
| Subnet     | 128 | 192 | 224 | 240 | 248 | 252 | 254 | 255 |
| CIDR       | /25 | /26 | /27 | /28 | /29 | /30 | /31 | /32 |

---

|               |                                        |
| ------------- | -------------------------------------- |
| Network ID    | First IP address in each Network       |
| Broadcast IP  | Last IP address in each Network        |
| First Host IP | IP address *after* the Network ID      |
| Last Host IP  | IP address *before* the Broadcast IP   |
| Next Network  | IP address *after* the Broadcast IP    |
| # IP Address  | Number of IP addresses in each Network |
| CIDR/Subnet   | Converting between CIDR/Subnet Mask    |

---

> Example: 10.1.1.55 /28

# Step 1: Find column
1. **CIDR/Subnet** Mask map to each other
> Look for **CIDR** then find the **Subnet** that matches the column
> 
> In this case its 240


2. Locate Group Size
	Look at **Group Size** in that same column, start from 0 and add in increments of that number until its passed the target IP
> In this example .0 .16 .32 .48 .64 
> **Target IP** = 55 

