# Cheat-Sheet – Core Acronyms & Ports

## A. Core Abbreviations (ISC2 CC & TryHackMe)

| Abbrev. | Stands for | 5-second meaning |
|---------|------------|------------------|
| **CIA triad** | Confidentiality, Integrity, Availability | Core security goals. |
| **AAA** | Authentication, Authorization, Accounting | Who are you, what can you do, and logging it. |
| **ACL** | Access Control List | Permission rules on files / firewalls. |
| **RBAC / DAC / MAC** | Role- / Discretionary- / Mandatory Access Control | The three classic models. |
| **IDS / IPS** | Intrusion Detection / Prevention System | IDS monitors; IPS actively blocks attacks. |
| **SOC** | Security Operations Center | 24 × 7 team watching alerts. |
| **SIEM** | Security Info & Event Management | Log-collection + alerting tool (Splunk, QRadar). |
| **CVE / CVSS** | Common Vulnerabilities & Exposures / Common Vulnerability Scoring System | ID number & severity score for a known flaw. |
| **TLS / SSL** | Transport Layer Security / Secure Sockets Layer | Protocol that makes HTTPS secure. |
| **PKI** | Public Key Infrastructure | Certificate system behind TLS & e-mail signing. |

---

## B. Must-know “number” questions

| Number  | What it usually points to                        |
|---------|--------------------------------------------------|
| **7**   | OSI layers (1 Physical … 7 Application)          |
| **20 / 21** | FTP Data / Control ports                       |
| **22**  | SSH (Secure Shell)                               |
| **23**  | Telnet (insecure)                                |
| **25**  | SMTP (e-mail out)                                |
| **53**  | DNS (Domain Name System)                         |
| **80 / 443** | HTTP / HTTPS                                  |
| **110 / 143** | POP3 / IMAP (legacy mail retrieval)          |
| **3389** | RDP (Remote Desktop Protocol)                   |
| **128 / 192 / 256** | Common AES encryption key sizes         |
