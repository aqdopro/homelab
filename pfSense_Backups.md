# 💾 pfSense Backups

## 🔄 Overview
This note outlines methods to **back up pfSense configurations** both manually and automatically. Keeping backups is critical to quickly restore your firewall settings in case of failure or changes.

Backlink: [[Homelab_Configurations]]

---

## 🧰 Manual Backup

### 🗂️ Exporting Config
1. Navigate to: `Diagnostics > Backup & Restore`
2. Select:
   - **Backup Area**: "All" (or specific section)
   - Check `Encrypt the configuration file` (recommended)
3. Click `Download Configuration`

### 🔐 Encryption
- Use a **strong password**
- Keep it stored securely (e.g., password manager or secure USB)

---

## ☁️ Automatic Config Backup (ACB)

### 🔧 Setup
1. Go to: `Services > Auto Config Backup`
2. Enable **Auto Config Backup**
3. Sign in or register for a **Netgate account**
4. Enable encryption and set a secure password

### 🔁 How It Works
- Backups are **stored in Netgate cloud**
- Saves config automatically when changes are made

> ⚠️ Note: ACB is free for Netgate devices. For custom hardware, registration is required but still free.

---

## 🛠️ Backup Storage Tips
- Store copies:
  - Locally on external drives
  - Encrypted cloud storage (e.g., Google Drive, Dropbox)
  - Internal NAS or home server
- Set calendar reminders to periodically back up if not using ACB

---

## 🧪 Restore Process
1. Navigate to: `Diagnostics > Backup & Restore`
2. Upload configuration file
3. pfSense will **reboot automatically**

> ✅ Be sure the backup matches the same pfSense version and hardware configuration.

---

## 🧷 Extra Tips
- Name your backup files clearly:  
  `pfsense-config_YYYY-MM-DD_location.xml`
- Document your VLANs, interfaces, firewall rules in Obsidian (see [[Firewall_Rules]], [[VLANs]])
- Store config snapshots **before and after** major changes

---

## 🔗 Related Notes
- [[Homelab_Configurations]]
- [[Ubiquiti_Setup]]
