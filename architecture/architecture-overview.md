# Architecture Overview

## Purpose of the Architecture
This project is designed to simulate a real-world enterprise cyber attack and evaluate detection and response capabilities using a Purple Team methodology. The architecture separates attacker, victim, and monitoring components to mirror professional security environments.

The design ensures:
- Isolation of malicious activity
- Centralized security monitoring
- Realistic adversary behavior
- SOC-style detection and investigation

---

## Network Design

The lab is deployed on a private virtual network using a NAT Network configuration. All virtual machines reside within the same isolated subnet, allowing controlled communication while preventing exposure to the host or external networks.

Subnet Example:
192.168.80.0/24

---

## Components and Roles

### Attacker Machine
- OS: Kali Linux
- Role: Red Team / Adversary
- Purpose:
  - Reconnaissance
  - Payload delivery
  - Command-and-Control us
---

### Victim Machines

#### Windows 10 Client
- Role: Initial access target
- Purpose:
  - Simulate end-user workstation
  - Execute adversary payload
  - Generate endpoint telemetry

#### Windows Server (Domain Controller)
- Role: High-value enterprise asset
- Purpose:
  - Active Directory services
  - Lateral movement target
  - Credential abuse detection

---

### Monitoring & SOC Machine

#### Ubuntu ELK Server
- Components:
  - Elasticsearch
  - Logstash
  - Kibana
- Purpose:
  - Centralized log ingestion
  - Detection engineering
  - Incident investigation
  - SOC dashboards

---

### Malware Analysis Machine

#### Malware Analysis VM
- Tool: Ghidra
- Purpose:
  - Static malware analysis
  - Behavioral understanding of payloads
  - Extraction of indicators
  - Detection improvement

---

## Log Flow and Detection Pipeline

Endpoint telemetry is generated on Windows and Linux systems using Sysmon and system logs. These logs are forwarded using Winlogbeat and Filebeat to Logstash, where they are processed and indexed into Elasticsearch. Kibana provides visualization, alerting, and investigation capabilities for the Blue Team.

---

## Security Design Principles

- Isolation: Attacker and malware never run on the SOC system
- Centralization: All telemetry flows to a single SIEM
- Visibility: High-fidelity endpoint logging using Sysmon
- Realism: Architecture mirrors small enterprise networks

---

## Architecture Outcome

This architecture enables full end-to-end adversary simulation, detection validation, malware analysis, and defense improvement through Purple Teaming, closely aligning with real-world security operations.
