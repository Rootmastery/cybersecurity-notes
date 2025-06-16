# 🔧 Home Network Privacy Project

A practical network security overhaul focused on privacy, control, and segmentation—routing all traffic through a hardened VPN gateway and preparing for secure IoT isolation.

---

## 🧭 Overview

This project documents the architecture and configuration of a modern home network designed for:

- DNS-level ad/tracker blocking  
- Outbound VPN tunneling  
- IoT segmentation via VLANs  
- Device identification and observability  

The stack integrates open-source tools (OPNsense, Pi-hole), commercial-grade Wi-Fi infrastructure (TP-Link Omada), and a Protectli firewall appliance.

---

## 🛠️ Architecture

**Connection Flow:**  
`Bell GigaHub (Fiber ISP modem)` →  
`Protectli Vault (OPNsense + Mullvad VPN Gateway)` →  
`TP-Link SG2008P (Managed PoE Switch)` →  
• Two TP-Link EAP225s (Omada-managed mesh Wi-Fi)  
• Hardwired clients (PC, cameras, Omada controller)  
• Wireless clients (phones, Alexa, smart devices, etc.)

**Controller Setup:**

- Dedicated full-time Omada Software Controller  
- Nearly 50 devices assigned static IPs and custom hostnames  
- Devices categorized by type for easier management and rule enforcement  

---

## 🔐 Privacy Enhancements

### ✅ VPN Gateway (OPNsense + Mullvad)

- WireGuard tunnel to Mullvad VPN
- All LAN traffic routes through VPN (default deny rules + kill switch)
- Selective routing via aliases allows exceptions (e.g., Alexa, casting devices)

### ✅ DNS Leak Prevention

- Disabled DoH/DoT in Firefox and Chrome
- OPNsense enforces DNS resolution via Mullvad's servers
- Verified using [dnsleaktest.com](https://www.dnsleaktest.com) and similar tools

---

## 📶 Wi-Fi Coverage & Control

### TP-Link EAP225 Mesh Setup

- Dual EAP225s wired with Cat6 to the managed PoE switch
- Omada software controller manages AP configuration and monitoring
- Seamless mesh Wi-Fi throughout home and yard
- Optimized roaming and signal tuning using Omada controller tools

---

## 🧱 Network Segmentation (In Progress)

**Goal:** Isolate untrusted IoT devices from LAN

- Upgraded to managed PoE switch (SG2008P)
- VLANs planned to separate:
  - IoT devices (e.g., smart lights, Alexa, chicken door, cameras)  
  - Trusted personal devices  
  - Guest network  
- Inter-VLAN routing to be restricted with OPNsense firewall rules

---

## 🔎 Device Identification

### MAC Mapping Workflow

- Cross-referenced DHCP leases in OPNsense and Omada
- Static IPs assigned to known devices
- All devices logged in centralized list (MAC, IP, hostname, type)
- Enables rogue detection and precise rule enforcement

---

## ⚠️ Challenges Encountered

| Problem                               | Solution                                                                 |
|--------------------------------------|--------------------------------------------------------------------------|
| EAP225s failed behind Bell GigaHub   | Inserted Protectli VPN gateway with local switch; bypassed Bell router   |
| DNS leak detection                   | Traced to browser DoH; forced DNS resolution through VPN tunnel          |
| IoT device sprawl                    | Manual MAC mapping, grouped and labeled by type                          |
| VPN broke Alexa/smart device access  | Implemented selective routing via aliases in OPNsense                    |

---

## 📌 Next Steps

- [ ] Complete VLAN tagging across switch and wireless network  
- [ ] Deploy Pi-hole + Unbound as internal DNS with ad/tracker filtering  
- [ ] Set up automatic alerts for new/unknown MAC addresses  
- [ ] Finalize and document OPNsense firewall rule structure  
- [ ] Expand traffic visibility using Zenarmor deep packet inspection  

---

## 🧠 Skills Demonstrated

- VPN tunneling (WireGuard on OPNsense)  
- Firewall rule design and kill-switch logic  
- Secure DNS setup and leak prevention  
- Enterprise Wi-Fi deployment and mesh optimization  
- Static DHCP management and MAC-based device auditing  
- Network documentation and architecture planning  

> "Security is not a product, but a process."  
> — *Bruce Schneier*
