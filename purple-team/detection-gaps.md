# Detection Gaps Identified

## Overview
After executing the adversary attack chain and reviewing SIEM alerts,
multiple detection gaps and weaknesses were identified.

## Gap 1: Initial C2 Beaconing
- Observation: Encrypted outbound connections were logged but not flagged
- Impact: Attacker maintained active control without immediate alerting
- MITRE: T1071 – Application Layer Protocol

## Gap 2: Encoded PowerShell Execution
- Observation: PowerShell execution was detected, but encoded commands were not prioritized
- Impact: Malicious execution blended with legitimate administrative activity
- MITRE: T1059 – Command Execution

## Gap 3: Lateral Movement Correlation
- Observation: SMB-based remote execution events were logged independently
- Impact: No single alert correlated source and destination systems
- MITRE: T1021 – Remote Services

## Summary
These gaps indicated that while telemetry existed, detection logic
required tuning to identify attacker behavior more accurately.
