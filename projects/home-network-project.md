# 🔧 Home Network Privacy Project

A practical network security overhaul to route all home internet traffic through a hardened VPN gateway and prepare for IoT segmentation.

---

## 🧭 Overview

This project documents the architecture and configuration of a home network designed for **privacy**, **control**, and **device isolation**. It leverages open-source tools, commercial-grade access points, and a VPN gateway for persistent outbound encryption.

---

## 🛠️ Architecture

**Connection Flow:**

1. **Bell GigaHub (Fiber ISP modem/router)** →  
2. **Protectli Vault running OPNsense** (VPN gateway + firewall) →  
3. **TP-Link TL-SG1005P PoE switch** →  
4. **Two TP-Link EAP225 Access Points (Omada-managed mesh Wi-Fi)**  
5. **Connected Devices** (personal computers, phones, smart devices, cameras, Alexa, etc.)

---

## 🔐 Privacy Enhancements

### ✅ VPN Gateway (OPNsense + Mullvad)
- Installed OPNsense on Protectli Vault
- Configured WireGuard VPN tunnel to Mullvad
- All outgoing traffic from LAN routes through Mullvad
- Kill-switch rules prevent fallback to clearnet if VPN drops

### ✅ DNS Leak Prevention
- Detected and resolved browser DNS leaks caused by "secure DNS" settings (e.g., Firefox/Chrome)
- Forced browser DNS resolution to use Mullvad DNS servers
- Confirmed clean VPN/DNS leak-free status using [dnsleaktest.com](https://dnsleaktest.com)

---

## 📶 Wi-Fi Coverage & Control

### TP-Link EAP225 Mesh Setup
- Installed two EAP225s at opposite ends of the house with Cat6 cabling to PoE switch
- Used Omada software controller to manage APs (hosted on PC)
- Full mesh Wi-Fi coverage across house and yard
- Stronger signal penetration, seamless roaming

---

## 🧱 Network Segmentation (Planned)

### Goal: Isolate IoT from personal devices using VLANs
- Current switch is **unmanaged** (TP-Link TL-SG1005P)
- Plan to replace with **managed PoE switch** to:
  - Create separate VLANs for smart devices (e.g. Alexa, chicken door, cameras)
  - Restrict IoT access to internet-only (no LAN discovery)
  - Improve network observability and control

---

## 🔎 Device Identification

### MAC Mapping Workflow
- Identified and labeled devices via DHCP leases in OPNsense and Omada controller
- Recorded MAC addresses, IPs, and device types in a centralized list
- Helps track rogue or unknown devices, and enforce rules

---

## ⚠️ Challenges Encountered

| Problem | Solution |
|--------|----------|
| EAP225s didn’t work with Bell GigaHub | Bypassed router using Protectli/OPNsense and local switch |
| DNS leak warnings in tests | Traced to browser-level secure DNS settings; disabled and re-routed properly |
| IoT identification overload | Manual MAC/IP identification, grouped by device type and function |

---

## 📌 Next Steps

- [ ] Install managed PoE switch to support VLAN tagging
- [ ] Implement Pi-hole + Unbound DNS resolver for local ad/tracker blocking
- [ ] Automate device tracking and notifications for unknown connections
- [ ] Document final firewall rule structure

---

## 🧠 Skills Demonstrated

- VPN tunneling (WireGuard on OPNsense)
- Firewall rule creation and kill-switch logic
- DNS configuration and leak detection
- Wi-Fi mesh deployment using enterprise-grade APs
- Home network documentation and device auditing

---

> _"Security is not a product, but a process."_  
> — Bruce Schneier
