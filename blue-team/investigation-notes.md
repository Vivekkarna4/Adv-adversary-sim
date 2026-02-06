# Investigation Notes

## Alert Triggered
- Rule: Suspicious PowerShell Execution
- Host: WIN10-CLIENT
- User: test-user

## Initial Findings
- Payload executed via user context
- PowerShell spawned with encoded commands

## Pivot Analysis
- Checked parent-child process tree
- Reviewed network connections
- Identified outbound C2 traffic

## Timeline Reconstruction
1. Initial execution
2. Persistence established
3. Credential access attempted
4. Lateral movement observed

## Conclusion
Confirmed adversary activity aligned with MITRE ATT&CK.
