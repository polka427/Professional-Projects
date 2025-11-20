# Threat Model

This threat model identifies realistic security threats, vulnerabilities, risks, and recommended controls for a small company environment.

## Method
The analysis uses a simple threat based approach.

## Threat Analysis

| Threat | Vulnerability | Risk | Impact | Controls Implemented |
|--------|---------------|-------|---------|------------------------|
| Phishing attack | User clicks malicious link | Credential theft | Loss of confidentiality | MFA, email filtering, user awareness training |
| Malware infection | Unpatched systems | System compromise | Data loss, downtime | Automatic updates, antivirus, restricted admin rights |
| Unauthorized access | Weak passwords | Account compromise | Data tampering | Password policy, MFA, logging |
| Network intrusion | Open ports on servers | Lateral movement | Service interruption | Firewall rules, segmentation |
| Data loss | No backups | Permanent loss of data | High | Cloud backups, offline backups |
| WiFi attack | Weak router password | Eavesdropping | Breach of confidentiality | WPA3, strong key, network segmentation |
| Insider misuse | Excess permissions | Data manipulation | Medium | Least privilege, auditing |

## Summary
The main risks to confidentiality are phishing and wireless insecurity. The main risks to integrity are insider misuse and privilege escalation. The main risks to availability are malware, misconfigurations, and unpatched systems.
