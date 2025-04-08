# 🌐 **WireGuard VPN Setup on pfSense** 🔐

## 📝 **Overview**
WireGuard is a modern, lightweight, and high-performance VPN protocol designed to be simpler and more secure than traditional options like OpenVPN. For your homelab, WireGuard provides a **fast** and **efficient** way to manage remote access without overloading your hardware. It integrates well with pfSense, especially for smaller setups like yours.

---

## 🔧 **Setup Guide**

### Step 1: Install WireGuard on pfSense 🚀
1. **Navigate to** `System > Package Manager > Available Packages`
2. Search for **WireGuard** and click **Install**
   - Refer to [**pfSense Packages**](link-to-pfsense-packages-note) for more details.

### Step 2: Create the WireGuard Interface 🌍
1. Go to `Interfaces > Assignments`
2. Click on **+ Add** to create a new interface for WireGuard
3. Select **WireGuard** as the interface type
4. Click **Save**

### Step 3: Configure WireGuard Settings 🔑
1. Go to `VPN > WireGuard`
2. Click **+ Add Tunnel**
3. Fill out the following details:
   - **Name**: (e.g., `HomeVPN`)
   - **Listen Port**: Default is `51820` (can be changed if necessary)
   - **Private Key**: Click to generate the key (or paste your own)
   - **Public Key**: Leave blank for now, it will be generated after the tunnel is saved
   - **Listen Address**: Use `0.0.0.0` to listen on all available IPs or specify a custom IP (e.g., `10.10.10.1/32`)
4. Click **Save** and **Apply Changes**

---

### Step 4: Add Peer Configurations 🖧
1. After saving the tunnel, click on the **Peers** tab
2. Click **+ Add Peer**
3. Fill out the following fields:
   - **Public Key**: Enter the peer's public key (from your remote device)
   - **Allowed IPs**: Enter the subnet of your home network or specific devices (e.g., `192.168.1.0/24`)
   - **Endpoint**: The remote device's IP address (e.g., `vpn.yourdomain.com:51820`)
4. Click **Save** and **Apply Changes**

### Step 5: Configure Firewall Rules 🚧
1. Go to `Firewall > Rules`
2. Select the interface `WireGuard`
3. Click **+ Add** to create a rule allowing traffic from the WireGuard network to the local network:
   - **Action**: Pass
   - **Interface**: WireGuard (or the VPN interface you created)
   - **Source**: Any
   - **Destination**: LAN (or the desired network)
4. Click **Save** and **Apply Changes**

   - Refer to the [**Firewall Rules Setup**](Homelab_Configurations) for a more detailed guide.

---

### Step 6: Set Up Remote Device (Client Configuration) 📱
1. Install the **WireGuard client** on your device (Windows, Linux, macOS, Android, iOS)
2. Create a new tunnel on the client and use the following settings:
   - **Private Key**: Generate the key on the client and paste it here
   - **Public Key**: This is the public key of your pfSense server (from Step 3)
   - **Allowed IPs**: `192.168.1.0/24` (or your home network range)
   - **Endpoint**: `vpn.yourdomain.com:51820` (or your pfSense external IP/domain)
   - **DNS Servers**: Optional, specify any DNS server (e.g., `1.1.1.1`)
3. Click **Activate** to connect the VPN

---

### Step 7: Verify the Connection ✅
1. Once connected, try to **ping** your pfSense LAN IP or any device on your home network from the remote device.
2. You can also check the **WireGuard status** in pfSense under `Status > WireGuard` to ensure everything is functioning properly.

---

## 🛠️ **Example Configuration**

| **Field**           | **Value**                     |
|---------------------|-------------------------------|
| **Tunnel Name**      | HomeVPN                       |
| **Listen Port**      | 51820                         |
| **Private Key**      | (Generated key)               |
| **Public Key (Peer)**| (Peer's public key)           |
| **Allowed IPs (Peer)** | 192.168.1.0/24               |
| **Endpoint**         | vpn.yourdomain.com:51820      |
| **Firewall Rule**    | Pass, Source: Any, Destination: LAN |

---

## 🗒️ **Notes**

- **Security**: 🔐 Make sure to use strong keys and properly configure firewall rules to restrict VPN access to only necessary devices.
- **Tailscale Integration**: 🌐 If you plan to use **Tailscale**, you can route WireGuard traffic over their network, making setup easier and more secure for remote access.
- **Backup**: 💾 Regularly back up your WireGuard configuration and pfSense setup to prevent data loss.

---

## 🔗 **Link to Other Notes**

- [WireGuard VPN Configuration - pfSense](VPN)
- [Firewall Rules Setup](Homelab_Configurations)
- [pfSense Package Setup](link-to-pfsense-package-note)

---

## 🌍 **Additional Considerations**
- **Firewall Performance**: WireGuard is known for its low overhead and better performance than older protocols like OpenVPN. Perfect for high-speed internet connections.
- **VPN Best Practices**: Ensure you're always using secure methods for key management and periodically rotating keys for optimal security.
