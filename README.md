# Network Reconnaissance & Security Assessment

Security posture assessment of an isolated lab network using Kali Linux, Nmap and Wireshark.
Part of the Cyber Security Internship (Batch 2) Minor Project.

## Overview
- **Target:** Metasploitable 2 (192.168.56.102), an intentionally vulnerable VM
- **Attacker:** Kali Linux 2026.3 (192.168.56.101)
- **Network:** VirtualBox Host-Only, isolated (192.168.56.0/24)
- **Scope:** Identification and documentation only. No exploitation, no DoS.

## Tools
Kali Linux, Netdiscover, Nmap 7.99, Wireshark 4.6.6, VirtualBox, draw.io

## Methodology
| Step | Command | Purpose |
|---|---|---|
| 1 | `netdiscover -i eth1 -r 192.168.56.0/24` | ARP host discovery |
| 2 | `nmap -sn 192.168.56.0/24` | Ping sweep |
| 3 | `nmap 192.168.56.102` | Top 1,000 ports |
| 4 | `nmap -sS -p- 192.168.56.102` | All 65,535 ports |
| 5 | `nmap -sV 192.168.56.102` | Service and version detection |
| 6 | `sudo nmap -O 192.168.56.102` | OS fingerprinting |
| 7 | `nmap -sC --script vuln 192.168.56.102` | Vulnerability scripts |
| 8 | Wireshark on eth1 | Clear-text credential capture (Telnet/FTP) |

## Key
