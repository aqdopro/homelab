# 🔄 Turn pfSense into Main Router
- ## 📌 Overview
  This note documents how to transition pfSense from a lab firewall to the **primary router** in a home network, replacing the existing ISP or consumer-grade router.
- ## 🛠️ Prerequisites
- pfSense installed and accessible
- At least 2 network interfaces (WAN + LAN)
- Modem or ONT from ISP
  id:: 67f8ddbc-1714-451f-83d0-ca2714d158aa
- VLANs already configured (optional but recommended)
- [[Homelab_Configurations]]
  
  ---
- ## 🌐 Step 1: Configure WAN Interface
- Go to `Interfaces > WAN`
- Set to:
	- **DHCP** (most ISPs)
	- **PPPoE / Static IP** (if required by ISP)
- Connect pfSense WAN port directly to **ISP modem**
- If using a combo modem/router:
	- Set to **Bridge Mode** to avoid double NAT
	  
	  ---
- ## 🖧 Step 2: Configure LAN and VLANs
- LAN interface will serve as the **gateway** for devices
- VLAN interfaces should be assigned and enabled
- Go to:
	- `Interfaces > Assignments > VLANs`
	- Set descriptions (e.g., `Main`, `IoT`, `Security`, `Guest`)
- Example:
  
  | VLAN | Description | Interface |
  | ------ | ------------- | ----------- |
  | 10   | Main        | igb1.10   |
  | 20   | IoT         | igb1.20   |
  | 30   | Security    | igb1.30   |
  | 40   | Guest       | igb1.40   |
  
  ---
- ## 📦 Step 3: Enable DHCP & DNS
- Go to `Services > DHCP Server`
	- Enable per VLAN/LAN
	- Assign range for each VLAN
- pfSense acts as **DNS Resolver**
	- Can use internal or external DNS servers
	- Optionally configure **DNSBL** or **pfBlockerNG**
	  
	  ---
- ## 🔐 Step 4: Set Up Firewall Rules
  Create firewall rules for each VLAN:
  
  | VLAN     | Allow Internet | Block Inter-VLAN | Notes                    |
  |----------|----------------|------------------|--------------------------|
  | Main     | ✅              | ❌                | Can access pfSense admin |
  | IoT      | ✅              | ✅                | Internet only            |
  | Security | ✅              | ✅                | Only camera/cloud key    |
  | Guest    | ✅              | ✅                | Internet only            |
  
  See [[Homelab_Configurations]] for full table.
  
  ---
- ## 📶 Step 5: Replace Old Router
- Power off old router
- Option 1: Retire it completely
- Option 2: Convert to **Access Point only**
	- Disable DHCP
	- Assign static IP in pfSense LAN subnet
	- Use LAN port (not WAN) for uplink
	  
	  ---
- ## 🧰 Optional Configs
- Dynamic DNS: `Services > Dynamic DNS`
- Port Forwarding: `Firewall > NAT > Port Forward`
- UPnP (for gaming): `Services > UPnP`
- Backups: [[pfSense_Backups]]
  
  ---
- ## 🔍 Verification Checklist
- [ ] WAN gets public IP
- [ ] LAN clients can access Internet
- [ ] DHCP ranges working
- [ ] VLANs are tagged and routed
- [ ] WebGUI is reachable
- [ ] Old router DHCP is off (if kept)
  
  ---
- ## 🔗 Related Notes
- [[Homelab_Configurations]]
- [[pfSense_Backups]]
- [[Ubiquiti_Setup]]