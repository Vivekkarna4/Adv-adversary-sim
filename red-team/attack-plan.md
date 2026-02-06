# Adversary Attack Plan

## Objective
The objective of this adversary simulation is to emulate a realistic attacker
gaining initial access to an enterprise network, establishing command-and-control,
escalating privileges, moving laterally, and exfiltrating sensitive data.

## Adversary Profile
- Type: Advanced persistent-style adversary
- Motivation: Data access and domain compromise
- Access Level: External attacker

## Target Environment
- Windows 10 client (initial access)
- Windows Server (Active Directory)
- Centralized SIEM (ELK) monitoring

## Tools Used
- Sliver C2 framework
- Nmap for reconnaissance
- Native Windows utilities (LOLBins)
- SMB-based lateral movement techniques

## Engagement Scope
- No destructive activity
- No real data exfiltration
- Simulation-only payloads
