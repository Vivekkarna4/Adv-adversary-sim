# Virtualization Setup

## Hypervisor
- VMware

## Network Configuration
- Network Mode: NAT Network
- Subnet: 192.168.80.0/24
- Purpose:
  - VM-to-VM communication
  - Internet access for updates
  - Isolation from host LAN

## Virtual Machines
| VM | Role | IP |
|---|---|---|
| Kali Linux | Attacker (Red Team) | 192.168.80.159 |
| Windows 10 | Client Endpoint | 192.168.10.142 |
| Windows Server | AD / DC | 192.168.80.164 |
| Ubuntu | ELK SIEM | 192.168.80.130 |
| Malware VM | Ghidra Analysis | Isolated |

## Security Considerations
- No bridging to host network
- Malware executed only inside lab
- Analysis VM has no internet access
