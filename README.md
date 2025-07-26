# Wireshark Password Capture Lab



## Overview

This lab demonstrates how plaintext login credentials can be captured over HTTP using Wireshark.  

A Windows VM submits a fake username and password to a Kali Linux-hosted insecure login page. Wireshark on Kali captures and reveals the credentials.



## Objectives

\- Understand risks of unencrypted login forms (HTTP)

\- Learn basic Wireshark capture and filtering techniques

\- Develop packet analysis skills applicable to SOC/Blue Team roles



## Tools Used

\- Kali Linux (Wireshark, Apache2)

\- Windows VM (Browser)



## MITRE ATT\&CK Mapping

\- T1040 - Network Sniffing

\- T1071.001 - Application Layer Protocol: Web Protocols



\## Repo Structure

\- `lab-instructions.md` – Step-by-step setup and analysis guide  

\- `screenshots/` – Wireshark capture and login screenshots  

\- `pcaps/` – Saved packet capture files  

\- `tools-used.md` – List of tools with descriptions  



---
##  Learning Outcomes

- Understand how attackers can sniff unencrypted traffic
- Learn to use Wireshark filters to isolate sensitive data
- Reinforce why encryption is critical in authentication

## ⚠️ Disclaimer

For educational use only.


Start with `lab-instructions.md` to reproduce the lab.



