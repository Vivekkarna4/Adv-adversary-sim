## Active Directory Attack Path Analysis

### Objective
Analyze AD relationships to identify misconfigurations that enable privilege escalation.

### Key Findings
- Excessive group memberships  
- Weak delegation controls  
- Misconfigured service accounts  

### Privilege Escalation Paths
Examples:
- User → Local Admin → Domain Admin  
- Kerberoasting targets  
- Unconstrained delegation abuse  

### Security Impact
These paths demonstrate how low-privileged access can lead to full domain compromise.

### Defensive Value
Findings are mapped to detection rules and mitigation strategies.
