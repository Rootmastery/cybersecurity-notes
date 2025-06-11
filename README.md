# 🛡️ Cybersecurity Learning Journal

Welcome to my cybersecurity learning repository. This is a living document of my journey into the world of cybersecurity, digital forensics, and ethical hacking. Here you'll find notes, lab writeups, study resources, and personal projects as I build hands-on skills and deepen my technical knowledge.

---

## 📚 Learning Paths & Progress

### 🔐 TryHackMe
- [x] Pre-Security
- [ ] Cyber Security 101
- [ ] Junior Penetration Tester
- Notes: [`tryhackmenotes.md`](./tryhackme/tryhackmenotes.md)

### 📜 CompTIA Security+ Prep
- [ ] Network Security
- [ ] Threats & Vulnerabilities
- [ ] Risk Management

---

#### 🔧 Home Network Privacy Project
**Description:** Redesigned my home network to route all traffic through a VPN gateway and prepare for IoT segmentation.

**Key Components:**
- **ISP:** Bell GigaHub with fiber connection.
- **VPN Gateway:** Protectli Vault running OPNsense, configured to route all traffic through Mullvad VPN.
- **Network Architecture:**
  - OPNsense box connected directly to Bell router.
  - POE switch downstream feeding internal devices.
  - Two TP-Link EAP225 access points providing Wi-Fi via mesh setup.
- **DNS Privacy:** Resolved DNS leaks caused by browser-level "secure DNS" features; forced compliance with Mullvad's DNS.
- **IoT Segmentation:** (In progress) Planning VLAN-based separation of smart home devices (e.g. Alexa, smart plugs, Wi-Fi chicken door) from personal computing devices.

**Challenges Overcome:**
- Initial incompatibility between access points and Bell router.
- DNS leak troubleshooting due to conflicting secure DNS settings.
- Manual setup of controller software for Omada APs.

**Next Steps:**
- Replace unmanaged POE switch with managed one to support VLANs.
- Set up Pi-hole and Unbound for local DNS filtering.
- Map MAC addresses to known devices for clarity and control.

**Skills Applied:** Network architecture, VPN configuration, firewall rules, secure DNS, Wi-Fi mesh setup, troubleshooting, documentation.
---

## 🚧 Ongoing Goals
- Stay consistent with daily learning
- Document labs clearly
- Complete TryHackMe JPT path
- Earn CompTIA Security+

---

## 🧠 Why This Repo?
This repo is a combination of:
- 🧾 Structured notes for revision
- 💡 Practical write-ups for hands-on labs
- 🛠️ A portfolio of applied skills and learning history

---

## 📬 Contact
I’m open to collaboration, feedback, or networking.  
You can reach me at: `me@email.com`

---

> _"Amateurs practice until they get it right. Professionals practice until they can’t get it wrong."_  
> — Author Unknown
