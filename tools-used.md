# Tools Used – Wireshark Password Capture Lab

This document lists the tools, software, and configuration used in this lab.

---

## Tools & Software

| Tool | Description | Usage |
|------|-------------|--------|
| **Wireshark** | Network protocol analyzer | Used on Kali Linux to capture and analyze traffic between host and Windows VM |
| **Kali Linux** | Linux distro for offensive security | Ran Wireshark and performed packet inspection |
| **Windows 10 VM** | Target machine | Simulated a user login to send credentials over the network |
| **VirtualBox** | Virtualization platform | Hosted both Kali and Windows virtual machines |
| **VirtualBox Guest Additions** | Enables shared folders | Used to transfer screenshots and files to host system |
| **Shared Folder** | File sharing mechanism | Moved `.pcap` and screenshots from Kali to host machine |

---

## 🔧 Configuration Notes

- **Network Mode**: Both VMs used `Host-Only Adapter` (or same NAT network) to enable local communication.
- **Capture Interface**: Wireshark on Kali was set to listen on the correct interface (e.g., `eth0` or `enp0s3`) that bridges the two VMs.
- **Login Simulation**: User credentials were typed into the Windows VM's login form while Wireshark was capturing packets.

---

##  Output Files

- **Captured Credentials Screenshot**: `/screenshots/captured-password.png`
- **Login Page Screenshot**: `/screenshots/login-page.png`
- **PCAP File (Optional)**: `/pcaps/wireshark-login-capture.pcapng`

---

