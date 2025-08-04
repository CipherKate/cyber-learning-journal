# MITRE ATT&CK Cheat Sheet

A personal reference sheet for common adversary TTPs, organized by the MITRE ATT&CK framework.

> [MITRE ATT&CK Navigator](https://attack.mitre.org/)  
> TTP = Tactic → Technique → Procedure

---

## Tactics Overview (Initial Access → Impact)

| Tactic | Description |
|--------|-------------|
| Initial Access | How attackers gain entry (e.g., phishing, exploits) |
| Execution | Running malicious code |
| Persistence | Maintaining access over time |
| Privilege Escalation | Gaining higher-level permissions |
| Defense Evasion | Avoiding detection |
| Credential Access | Stealing usernames/passwords |
| Discovery | Learning about the environment |
| Lateral Movement | Moving through the network |
| Collection | Gathering data |
| Command and Control | Communicating with compromised systems |
| Exfiltration | Stealing data |
| Impact | Damaging, disrupting, or manipulating systems |

---

## Common Techniques by Phase

### Initial Access
- `T1566.001` – Spearphishing Attachment
- `T1190` – Exploit Public-Facing Application
- `T1078` – Valid Accounts

### Execution
- `T1059` – Command and Scripting Interpreter (PowerShell, Bash, etc.)
- `T1203` – Exploitation for Client Execution

### Defense Evasion
- `T1562.001` – Disable or Modify Tools (e.g., antivirus)
- `T1027` – Obfuscated Files or Information

### Credential Access
- `T1003.001` – LSASS Memory Dump
- `T1555.003` – Credentials from Web Browsers

### Lateral Movement
- `T1021.002` – SMB/Windows Admin Shares
- `T1075` – Remote Services

### ☠Impact
- `T1486` – Data Encrypted for Impact (Ransomware)
- `T1499` – Endpoint Denial of Service

---

## 🧪 Sample KC7 Application

| Incident | Technique Used | ATT&CK ID | Phase |
|---------|----------------|-----------|-------|
| Jojo’s Hospital | Phishing link in email | T1566.002 | Initial Access |
| Privileged Compromise | Token abuse | T1134.002 | Privilege Escalation |
| MFA Bypass | Exploit app password config | T1556.006 | Credential Access |

---

## 📚 Resources
- [MITRE ATT&CK Website](https://attack.mitre.org/)
- [Red Canary’s Atomic Red Team](https://atomicredteam.io/)
- [Sigma Rules Mapping](https://github.com/SigmaHQ/sigma)

---

_Last updated: August 2025_
