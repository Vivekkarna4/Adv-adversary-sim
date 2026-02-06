# Detection Improvements Implemented

## Objective
Improve detection fidelity by addressing identified gaps using
behavior-based detection logic.

---

## Improvement 1: C2 Beaconing Detection
### Action Taken
- Implemented outbound network behavior detection
- Focused on repeated encrypted connections to uncommon destinations

### Result
- Reduced dwell time of attacker control

---

## Improvement 2: Encoded PowerShell Detection
### Action Taken
- Added detection for PowerShell with encoded command-line arguments
- Implemented parent-child process correlation

### Result
- Improved detection accuracy for fileless attacks

---

## Improvement 3: Lateral Movement Correlation
### Action Taken
- Correlated remote service creation with authentication logs
- Focused on internal east-west traffic patterns

### Result
- Faster identification of internal attacker spread

---

## Outcome
Detection logic became more behavior-focused and less dependent
on static indicators.
