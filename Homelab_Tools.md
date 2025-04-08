# 🛠️ **Homelab Tools** 🖥️

This note contains an overview of the tools and equipment used in the **Homelab** environment. It includes network devices, software, and configurations for seamless operations.

---

## 🔌 **Network Devices**
### **Firewall**
- **Device**: pfSense Firewall 🚀
  - **Purpose**: Main network security, routing, and management device.
  - **Features**:
    - Supports VLANs and multiple subnets 🌐
    - WireGuard VPN support 🔑
    - Advanced firewall rules configuration 🔒
  - [[Homelab_Configurations]]

### **Switch**
- **Device**: Ubiquiti 16-Port PoE Switch 🌉
  - **Purpose**: Manage devices via VLANs, power over Ethernet for APs and other devices.
  - **Features**:
    - 16 PoE ports for devices like APs, cameras 🎥
    - VLAN support for segmented network traffic 🖧

---

## 💻 **Software Tools**
### **pfSense**
- **Version**: Latest stable release 🛡️
- **Purpose**: Core router/firewall for Homelab.
- **Tools Integrated**:
  - VLAN Configuration 🏗️
  - VPN Setup (WireGuard) 🌐
  - Traffic monitoring 📊
  - Package support (e.g., pfBlockerNG) 🔒

### **WireGuard VPN**
- **Purpose**: Secure remote access to the Homelab via VPN 🔑
- **Use Case**: For external network access to pfSense and remote monitoring 🔍
- [[VPN]]

---

## 🏠 **Wi-Fi & Access Points**
### **Ubiquiti AP (To be purchased)** 📶
- **Purpose**: Expand Wi-Fi coverage for devices on the network.
- **Use Case**: Ideal for devices such as the 3D printer and other IoT devices.
- **To be configured**: Once the device is added to the network, ensure proper VLAN settings for Wi-Fi isolation.

### **Wi-Fi Security** 🔐
- **Purpose**: Ensure secure connections by setting up WPA2 or WPA3 encryption on the Wi-Fi network.
- **VLAN Assignment**: Depending on the device type, assign to either IoT or Guest VLAN for proper isolation.
- [Backlinked Note: Wi-Fi Security Setup]

---

## 🖨️ **3D Printer**
### **3D Printer Setup** 🖨️
- **Purpose**: Add 3D printer to the network for remote printing management.
- **Network Configuration**:
  - Assign to **VLAN 20 (IoT)** or **VLAN 40 (Guests)** depending on security needs.
  - Ensure the 3D printer has access to the internet for updates and management, but is isolated from the core network.

---

## 🛡️ **Security Tools**
### **pfBlockerNG** 🧰
- **Purpose**: Block unwanted traffic and malicious domains.
- **Use Case**: Install for network-wide ad blocking and threat filtering.

---

## 🗂️ **Configuration Notes**
### **VLAN Configuration** 🌐
- **VLANs**: Set up multiple VLANs (e.g., Main, IoT, Guests, etc.) for network segmentation.
- **Use Case**: Ensure proper segmentation of traffic to enhance security and improve network performance.
- [Backlinked Note: VLAN Setup]

### **Firewall Rules** 🔐
- **Purpose**: Set up firewall rules for each VLAN to ensure security and access control.
- **Use Case**: Block access between VLANs as needed to isolate IoT or guest devices from the main network.
- [[Homelab_Configurations]]
