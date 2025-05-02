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

## Step 1: Find column
1. **CIDR/Subnet** Mask map to each other
> Look for **CIDR** then find the **Subnet** that matches the column
> 
> In this case its 240

|               |                       |
| ------------- | --------------------- |
| Network ID    |                       |
| Broadcast IP  |                       |
| First Host IP |                       |
| Last Host IP  |                       |
| Next Network  |                       |
| # IP Address  |                       |
| CIDR/Subnet   | ==255.255.255.*240*== |

2. Locate Group Size
	Look at **Group Size** in that same column, start from 0 and add in increments of that number until its passed the target IP
> In this example .0 .16 .32 .48 .64 
> **Target IP** = 55 
---
## Step 2: Network ID
 Look for Number *before* target IP
> Network ID = .48

|               |                   |
| ------------- | ----------------- |
| Network ID    | ==10.1.1.**48**== |
| Broadcast IP  |                   |
| First Host IP |                   |
| Last Host IP  |                   |
| Next Network  |                   |
| # IP Address  |                   |
| CIDR/Subnet   | 255.255.255.240   |

---
## Step 3: Next Network
 Look for number *after* target IP
> Next Network = .64

|               |                   |
| ------------- | ----------------- |
| Network ID    | 10.1.1.48         |
| Broadcast IP  |                   |
| First Host IP |                   |
| Last Host IP  |                   |
| Next Network  | ==10.1.1.**64**== |
| # IP Address  |                   |
| CIDR/Subnet   | 255.255.255.240   |

---
## Step 4: Broadcast
 The IP address *before* Next Network
>Broadcast IP = .63

|               |                 |
| ------------- | --------------- |
| Network ID    | 10.1.1.48       |
| Broadcast IP  | ==10.1.1.*63*== |
| First Host IP |                 |
| Last Host IP  |                 |
| Next Network  | 10.1.1.**64**   |
| # IP Address  |                 |
| CIDR/Subnet   | 255.255.255.240 |

---
## Step 5: First Host & Last Host
**First** - The IP address *after* Network ID
**Last** - IP *before* Broadcast IP
>First Host = .49
>Last Host = .62

|               |                 |
| ------------- | --------------- |
| Network ID    | 10.1.1.48       |
| Broadcast IP  | 10.1.1.63       |
| First Host IP | ==10.1.1.*49*== |
| Last Host IP  | ==10.1.1.*62*== |
| Next Network  | 10.1.1.**64**   |
| # IP Address  |                 |
| CIDR/Subnet   | 255.255.255.240 |

---
## Step 6: # of IP addresses
The Group size
> Total IP = 16
> Usable IP = 14

|               |                 |
| ------------- | --------------- |
| Network ID    | 10.1.1.48       |
| Broadcast IP  | 10.1.1.63       |
| First Host IP | 10.1.1.49       |
| Last Host IP  | 10.1.1.62       |
| Next Network  | 10.1.1.64       |
| # IP Address  | ==16==          |
| CIDR/Subnet   | 255.255.255.240 |