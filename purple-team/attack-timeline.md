#  Purple Team Attack Timeline & Detection Validation

This document captures the **end-to-end adversary simulation** performed in the lab and the **corresponding detections observed in the ELK stack**.  
All activities are mapped to **MITRE ATT&CK techniques** and validated using **Sysmon, Beats, and ELK**.

---

## 1️ Detection Rules Implemented

Custom **behavior-based KQL detection rules** were developed and validated.

| Detection Rule File | ATT&CK Technique | Log Source | Result |
|--------------------|------------------|------------|--------|
| execution.kql | T1059 – Command Execution | Sysmon Event ID 1 |  Triggered |
| c2-beaconing.kql | T1071 – C2 Beaconing | Sysmon Event ID 3 |  Triggered |
| credential-dumping.kql | T1003 – Credential Dumping | Sysmon Event ID 10 |  Triggered |
| lateral-movement.kql | T1021 – Remote Services | Windows Security Logs |  Partial |
| persistence.kql | T1547 – Registry Persistence | Registry Logs |  Missed |

> Detection logic focused on **behavioral patterns** instead of static indicators like hashes or IPs.

---

## 2️ Attack Timeline

| Attack Step | Time (UTC) | Detection Log Source | Alert Triggered |
|------------|-----------|----------------------|-----------------|
| Initial Access (Payload Execution) | 2026-02-01 10:12:04 | Sysmon Event ID 1 | Yes |
| C2 Beacon Established | 2026-02-01 10:12:15 | Sysmon Event ID 3 | Yes |
| Command Execution | 2026-02-01 10:13:01 | PowerShell 4104 | Yes |
| Credential Dump Attempt | 2026-02-01 10:15:22 | Sysmon Event ID 10 | Yes |
| Lateral Movement Attempt | 2026-02-01 10:18:40 | Security Event Logs | Partial |
| Persistence Mechanism | 2026-02-01 10:20:05 | Registry Logs | No |

---

## 3️ Detection Validation Summary

###  Successful Detections
- Execution and C2 activity detected within seconds.
- Credential dumping and PowerShell abuse reliably detected.
- Sysmon + ELK provided deep endpoint visibility.

###  Partial Detection
- Lateral movement detected in logs but lacked high-confidence alerting.

###  Missed Detection
- Registry-based persistence required additional tuning.

---

## 4️ Key Observations

- Behavioral detections were more reliable than signature-based rules.
- ATT&CK-mapped detections improved traceability and reporting.
- Detection gaps helped identify areas for defensive improvement.

---

## 5️ Future Improvements

- Add correlation rules for persistence mechanisms.
- Improve AD enumeration detection.
- Enhance alert severity scoring based on attack phase.

---

##  Final Conclusion

**Behavior-based, ATT&CK-aligned detections significantly improved visibility across the attack lifecycle.  
Missed detections provided valuable insight for continuous defensive tuning, validating the Purple Team approach.**
