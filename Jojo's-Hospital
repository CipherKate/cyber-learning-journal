markdown
# JoJo’s Hospital Cybersecurity Incident Report

> **Location:** Lexington, Kentucky  
> **Date:** May–June 2024  
> **Reporting Analyst:** katesec

---

## 1. Executive Summary

On May 1, 2024, JoJo’s Hospital was targeted by a two-stage attack. First, the APT group **SharkFin7** executed a phishing campaign via a fake “Raisin Kane” promotion, delivered Cobalt Strike, performed internal reconnaissance, and exfiltrated sensitive network diagrams and credentials. They then sold access to the **LockByte** ransomware group, which deployed LockByte ransomware to encrypt 6 420 files across 321 hosts and demanded \$2 million within 72 hours—also threatening patients with SSN exposure unless each paid \$10 000.

---

## 2. Attack Overview

- **Phishing & Initial Access**  
  - Fake Google ad for “Raising Canes” → rainsinkanes.com  
  - Redirect chain (e.g. `raisinkanes.com?redirect=nothing-to-see-here.net`)  
  - Payloads delivered:  
    - `Raisin_Kane_Promo_Offer.docx` (SHA256: bd886046266b909a8ca5f19f16e5606baf73194a70632c81fdc44ef39ba29712)  
    - `Raisin_Kane_Free_Meal_Voucher.pdf`

- **Malware & C2**  
  - Dropped `cobaltstrike.exe` → connected to 93.238.22.122:50050

- **Discovery (Reconnaissance)**  
  - May 2, 2024 (RQJQ-MACHINE) ran:  
    - `systeminfo`  
    - `ipconfig /all`  
    - `netstat -an`  
    - `net user`  
  - May 3, 2024 ran:  
    - `net localgroup administrators`  
    - `net view`

- **Data Exfiltration (Stage 1)**  
  - Tool: `patient_data_exporter.exe`  
  - Archives created:  
    - `patient_data_1.zip` → `\\jojos-hospital-server\important_data\patient_records`  
    - `patient_data_2.zip` → `\\jojos-hospital-server\important_data\archive\patient-records`  
    - `patient_data_3.zip` → `\\jojos-hospital-server\important_data\old-patient-data`  
  - Sent to **secure-health-access.com** (203.0.113.1, 203.0.113.2)  
  - Deleted archives:  
    ```shell
    cmd.exe /c del C:\Users\andavis\Documents\patient_data_*.zip
    ```
  - 37 HTTP requests observed from exfiltration IPs

- **Lateral Movement & Reconnaissance (Stage 2)**  
  - May 14, 2024: Cobalt Strike beacon on AMFB-MACHINE (user: andavis)  
  - May 16, 2024:  
    - Downloaded `advanced-ip-scanner.exe`  
    - Exfiltrated `network_diagrams.pdf` and `credentials.txt`  
    - Compressed into `important_network_info.zip`  
    - Uploaded via `curl` to nothing-to-see-here.net

- **Ransomware Deployment**  
  - Deployed `spread_ransomware.exe` on `\\jojos-hospital.org\shared`  
  - Executed `lockbyte_ransomware.exe` on AMFB-MACHINE (14 process events)  
  - Encrypted 6 420 files across 321 hosts  
  - Ransom note:  
    - Filename: `We_Have_Your_Data_Pay_Up.txt`  
    - Path: `C:\Users\andavis\Documents\We_Have_Your_Data_Pay_Up.txt`  
    - SHA256: `7c348e95c8a8aeb8808f76434d73a92bbcb6b4586788365762b22624990b018`

---

## 3. Detailed Timeline

| Date & Time (UTC)       | Host           | Activity                                                       |
|-------------------------|----------------|--------------------------------------------------------------- |
| 2024-05-01 09:56:50     | RQJQ-MACHINE   | Downloaded `Raisin_Kane_Promo_Offer.docx` (SHA256: bd88…9712)  |
| 2024-05-01 09:59:12     | RQJQ-MACHINE   | Dropped & executed `cobaltstrike.exe`                         |
| 2024-05-02 14:39:36     | RQJQ-MACHINE   | Discovery: `systeminfo`                                        |
| 2024-05-02 14:40:18     | RQJQ-MACHINE   | Discovery: `ipconfig /all`                                     |
| 2024-05-02 14:41:05     | RQJQ-MACHINE   | Discovery: `netstat -an`                                       |
| 2024-05-02 14:42:30     | RQJQ-MACHINE   | Discovery: `net user`                                          |
| 2024-05-03 08:52:49     | RQJQ-MACHINE   | Discovery: `net localgroup administrators`                     |
| 2024-05-03 13:57:27     | RQJQ-MACHINE   | Discovery: `net view`                                          |
| 2024-05-14 12:24:45     | AMFB-MACHINE   | C2 beacon to 93.238.22.122:50050                               |
| 2024-05-16 10:00:05     | AMFB-MACHINE   | Downloaded `advanced-ip-scanner.exe`                           |
| 2024-05-16 11:00:38     | AMFB-MACHINE   | Exfiltrated `network_diagrams.pdf`                             |
| 2024-05-16 11:24:26     | AMFB-MACHINE   | Exfiltrated `credentials.txt`                                  |
| 2024-05-16 13:39:48     | AMFB-MACHINE   | Uploaded `important_network_info.zip` via `curl`               |
| 2024-05-20 00:00:00     | AMFB-MACHINE   | Searched hospital records page                                 |
| 2024-05-20 00:05:12     | AMFB-MACHINE   | Executed `patient_data_exporter.exe`                           |
| 2024-05-20 00:15:00     | AMFB-MACHINE   | Deleted ZIPs via `cmd.exe /c del …`                            |
| 2024-05-20 00:20:30     | AMFB-MACHINE   | Shared drive: `spread_ransomware.exe` deployed                 |
| 2024-05-20 00:25:00     | AMFB-MACHINE   | Executed `lockbyte_ransomware.exe`                             |

---

## 4. Indicators of Compromise (IOCs)

### 4.1 Files & Hashes

| File                                    | SHA256                                                          | Location / Host   |
|-----------------------------------------|-----------------------------------------------------------------|-------------------|
| We_Have_Your_Data_Pay_Up.txt            | 7c348e95c8a8aeb8808f76434d73a92bbcb6b4586788365762b22624990b018 | AMFB-MACHINE      |
| Raisin_Kane_Promo_Offer.docx            | bd886046266b909a8ca5f19f16e5606baf73194a70632c81fdc44ef39ba29712| RQJQ-MACHINE      |
| cobaltstrike.exe                        | *(hash redacted)*                                               | RQJQ-MACHINE      |
| advanced-ip-scanner.exe                 | *(hash redacted)*                                               | AMFB-MACHINE      |
| patient_data_1.zip / 2 / 3              | *(hashes redacted)*                                             | AMFB-MACHINE      |
| important_network_info.zip              | b373d6d9f3029598491a474374f067291a38350f9a92ff7bd3056f6c5bb88d88| AMFB-MACHINE      |
| spread_ransomware.exe                   | *(hash redacted)*                                               | Shared Drive      |
| lockbyte_ransomware.exe                 | *(hash redacted)*                                               | AMFB-MACHINE      |

### 4.2 Network & Domains

- **C2 Server:** 93.238.22.122:50050  
- **Exfil Domains:** secure-health-access.com → 203.0.113.1, 203.0.113.2  
- **Phishing Redirect:** rainsinkanes.com → nothing-to-see-here.net / totally-legit-domain.com  
- **HTTP Requests:** 37 connections from exfil IPs

---

## 5. MITRE ATT&CK Mapping

| Phase               | Technique ID | Technique Name                     |
|---------------------|--------------|------------------------------------|
| Initial Access      | T1566        | Phishing                           |
| Command & Control   | T1071        | Application Layer Protocol         |
| Discovery           | T1082 / T1049 / T1135 | System Information Discovery / Network Service Scanning / Network Share Discovery |
| Lateral Movement    | T1484        | Domain Policy Modification         |
| Collection          | T1005        | Data from Local System             |
| Exfiltration        | T1048        | Exfiltration Over Alternative Protocol|
| Impact (Ransomware) | T1486        | Data Encrypted for Impact          |

---

## 6. Impacted Assets

- **Total Hosts Affected:** 321  
- **Files Encrypted:** 6 420  
- **Users Compromised:**  
  - `evbrowne` (Eva Brown) on RQJQ-MACHINE  
  - `andavis` (Anthony Davis) on AMFB-MACHINE  

---

## 7. Remediation & Recommendations

1. **Containment**  
   - Isolate AMFB-MACHINE and RQJQ-MACHINE from network  
   - Block 93.238.22.122 at perimeter firewall  

2. **Eradication**  
   - Remove Cobalt Strike beacons and related payloads  
   - Scan shared drives for `spread_ransomware.exe`  

3. **Recovery**  
   - Restore from known-good backups  
   - Rotate all Service and Admin credentials  

4. **Hardening & Prevention**  
   - Enforce phishing awareness training  
   - Harden SMB and admin shares  
   - Deploy EDR rules to flag discovery tools  

---

## 8. Lessons Learned

1. **Phishing Vectors**  
   - Fake ads can bypass email filters. Validate URLs before clicking.  
2. **Security Monitoring**  
   - Alert on unusual use of native discovery tools (`systeminfo`, `net view`).  
3. **Access Resale**  
   - Segregate C2 detection and ransom remediation in incident plans.  
4. **Backup & Response**  
   - Regularly test restores. Be ready to rebuild encrypted hosts.  

---

## 9. References

- Internal EDR logs (May 2024)  
- DNS resolution records  
- Windows event logs (Security & Sysmon)  
- Network flow captures  

---
