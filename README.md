# Advanced Adversary Simulation Lab (Purple Team Capstone)

## Overview

This project implements an **enterprise-grade adversary simulation lab** using a **Purple Team methodology**, combining both **offensive (Red Team)** and **defensive (Blue Team)** perspectives.

A complete **attack lifecycle** was executed and monitored — from **initial access** to **command-and-control (C2)**, **credential dumping**, **Active Directory enumeration**, **persistence**, and **lateral movement** — with all activities mapped to **MITRE ATT&CK** techniques.

The primary objective of this lab is to **validate real-world detection capabilities** using SIEM telemetry, correlation rules, and alerting, simulating how a modern SOC detects and responds to advanced threats.

---

## Objectives

- Simulate realistic adversary behavior in a controlled enterprise lab
- Execute full attack chain mapped to MITRE ATT&CK
- Validate detection logic using SIEM telemetry
- Correlate attacker activity with alerts and risk scoring
- Demonstrate Purple Team collaboration between attack simulation and defense validation

---

## Attack Lifecycle Simulated

| Phase | Description |
|------|------------|
| Initial Access | Payload execution and beacon establishment |
| Command & Control | Sliver C2 beaconing and communication |
| Credential Dumping | LSASS memory access and credential extraction |
| AD Enumeration | Domain mapping using SharpHound |
| Persistence | Registry and scheduled task techniques |
| Lateral Movement | Credential reuse and internal host access |

---

## Detection & Monitoring Architecture

- **Endpoint Telemetry**  
  - Sysmon for process, network, and memory activity  
  - Windows Event Logs for authentication and privilege activity  

- **Log Collection**  
  - Winlogbeat for forwarding logs to SIEM  

- **SIEM Stack**  
  - Elasticsearch for log indexing and search  
  - Logstash for parsing and enrichment  
  - Kibana for visualization, dashboards, and alerting  

- **Detection Logic**
  - Custom correlation rules
  - MITRE ATT&CK technique mapping
  - Alert severity and risk scoring

---

## Tools & Technologies Used

### Red Team / Adversary Simulation
- Kali Linux
- Sliver C2
- SharpHound
- BloodHound

### Blue Team / Detection
- Sysmon
- Winlogbeat
- Elasticsearch
- Logstash
- Kibana

### Frameworks & Standards
- MITRE ATT&CK

---

## Key Outcomes

- Successful simulation of advanced adversary behavior
- Real-time detection of:
  - C2 beaconing
  - Credential dumping attempts
  - Suspicious PowerShell activity
  - Active Directory reconnaissance
- Demonstrated effectiveness of SIEM-based threat detection
- Clear mapping between attacker actions and defensive alerts

---

## Learning Highlights

- Hands-on Purple Team methodology
- Deep understanding of attacker TTPs
- Practical SOC detection engineering
- MITRE ATT&CK-driven threat modeling
- Enterprise-style log correlation and alerting

---

## Disclaimer

⚠️ **Legal & Ethical Notice**

This project was conducted **strictly within a controlled lab environment** for **educational and research purposes only**.  
No systems were accessed without authorization.  
The techniques demonstrated should only be used for **defensive security testing, learning, and detection validation**.

---

## Author

**Vivek Karna**  
Purple Team | Network Security | SIEM | Adversary Simulation

---

