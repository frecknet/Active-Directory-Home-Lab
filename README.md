# 🛡️ Cybersecurity Home Lab: Week 1
Built an isolated Active Directory environment to practice offensive and desktop security fundamentals.

## 🕸️ Network Topology
![Lab Topology] Lab_Topology.png
*Architecture: VMware Workstation Pro using VMnet8 (NAT) for network isolation between the lab and my host machine.*

## 🔍 Nmap Enumeration (Day 4)
I performed an aggressive scan (`nmap -sS -sV -A`) from my Kali Linux machine against the Windows Server to map the attack surface.


| Target | IP Address | Role | Key Open Ports |
| :--- | :--- | :--- | :--- |
| **WinServer2022** | 192.168.107.128 | Domain Controller | 53, 88, 389, 445 |
| **Kali** | 192.168.107.129 | Attacker | N/A |

### Scan Evidence
![Nmap Results] nmap_1.png and nmap_2.png

## 🛠️ Hardening (Day 6)
I disabled **LLMNR** and **NetBIOS** on the Domain Controller via Group Policy. 
**The Result:** Subsequent Nmap scans confirmed these legacy services were no longer responding, effectively mitigating common local credential spoofing attacks (like Responder).
