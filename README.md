# IT Support & Cybersecurity Portfolio — Sangay Thinley

Hands-on projects demonstrating practical experience in enterprise IT support, systems administration, SOC telemetry triage, AD security auditing, cloud threat hunting, vulnerability management, and digital forensics.

I hold an MSc in Cybersecurity from Leeds Beckett University and have previous experience in software development and technology-supported operations. This portfolio focuses on practical evidence: systems I configured, problems I investigated, controls I tested, and lessons learned.

---

## Featured Projects

| # | Project Name | Primary Tools & Focus Areas | Status |
|---|---|---|---|
| **01** | **[Enterprise Active Directory & Systems Security Lab](projects/01-enterprise-active-directory-systems-security/)** | Windows Server 2016, Active Directory, Kerberos, Debian, SSSD, PAM, Group Policy, access control, hardening | Completed |
| **02** | **[SOC Log Analysis & SIEM Triage with Splunk](01-soc-siem/)** | Splunk, Windows Event Viewer (EventCode 4625/4624), SPL Querying, Brute-Force Detection, GPO Lockout Policies | Completed |
| **03** | **[Sysmon Threat Detection & AD Telemetry](02-endpoint-identity/)** | Sysmon (Event ID 1), AD Authentication (Event ID 4769), Kerberoasting Triage, Script Block Logging, gMSA Hardening | Completed |
| **04** | **[NIDS Rule Engineering & Traffic Analysis](03-network-security/)** | Snort (`local.rules`), Zeek (`http.log`), PCAP Deep Packet Inspection, C2 Beaconing Detection, IPS Inline Drops | Completed |
| **05** | **[Active Directory Certificate Services (AD CS) Audit](04-enterprise-pki/)** | MMC Snap-ins, `Certify.exe`, ESC1/ESC2 Privilege Escalation, `ENROLLEE_SUPPLIES_SUBJECT` Vulnerability Analysis | Completed |
| **06** | **[Azure Incident Triage & KQL Threat Hunting](05-azure-security/)** | Microsoft Sentinel, KQL (SigninLogs / AzureActivity), Entra ID, Conditional Access Policies, FIDO2 MFA | Completed |
| **07** | **[Vulnerability Management & Web App Hardening](06-vulnerability-management/)** | Nessus/OpenVAS, Burp Suite (Repeater), OWASP Top 10 (SQLi/XSS), CVSS v3.1 / EPSS, ModSecurity WAF | Completed |
| **08** | **[Digital Forensics & Incident Response (DFIR)](07-forensics-hardening/)** | Autopsy, File Carving, Registry Hive Parsing, Linux `/var/log/auth.log` Forensics, Breach Timeline Analysis | Completed |
| -- | Microsoft Workplace Support Lab | Microsoft 365 / Entra ID / endpoint support | Planned |
| -- | Windows Service Desk Troubleshooting | Common L1 support scenarios and ticket documentation | Planned |
| -- | Network Troubleshooting Lab | TCP/IP, DNS, DHCP and connectivity diagnosis | Planned |
| -- | PowerShell for IT Support | Support-focused automation and diagnostics | Planned |

---

## Detailed TryHackMe Defensive Security Lab Projects

### 1. SOC Log Analysis & SIEM Triage with Splunk (`01-soc-siem/`)
* **Focus:** Splunk SPL queries, brute-force analysis, and alert lifecycle management.
* **Key Evidence:** Analyzed failed authentication spikes (`EventCode=4625`) from unauthenticated external IPs; structured automated triage and baseline queries.
* **Deliverables:** `room-notes.md`, `detection-analysis.md`, `lessons-learned.md`.

### 2. Sysmon Threat Detection & AD Telemetry (`02-endpoint-identity/`)
* **Focus:** Endpoint execution ancestry and Kerberos authentication abuse.
* **Key Evidence:** Analyzed living-off-the-land execution (Sysmon Event ID 1: `cmd.exe` $\rightarrow$ `powershell.exe`) and Kerberoasting ticket requests (`Event ID 4769` using RC4 cipher `0x17`).
* **Deliverables:** `windows-event-notes.md`, `identity-investigation.md`, `detection-and-hardening.md`.

### 3. NIDS Rule Engineering & Network Traffic Analysis (`03-network-security/`)
* **Focus:** Custom Snort signatures, PCAP analysis, and Zeek network telemetry.
* **Key Evidence:** Engineered custom Snort SID `1000001` for TCP SYN scan detection and inspected Zeek `http.log` for periodic command-and-control (C2) beaconing patterns.
* **Deliverables:** `network-analysis.md`, `web-security-finding.md`, `mitigation-matrix.md`.

### 4. Active Directory Certificate Services (AD CS) Security Audit (`04-enterprise-pki/`)
* **Focus:** Enterprise PKI auditing, template misconfiguration, and domain privilege escalation.
* **Key Evidence:** Verified vulnerable ESC1 certificate templates via `Certify.exe` where `ENROLLEE_SUPPLIES_SUBJECT` allowed low-privileged users to request certificates with arbitrary SAN values.
* **Deliverables:** `adcs-audit-report.md`, `pki-hardening-guidance.md`.

### 5. Azure Incident Triage & KQL Threat Hunting (`05-azure-security/`)
* **Focus:** Microsoft Sentinel, Kusto Query Language (KQL), and Entra ID identity governance.
* **Key Evidence:** Authored KQL queries across `SigninLogs` to detect impossible travel / brute-force patterns and configured Entra ID Conditional Access Policies to enforce MFA.
* **Deliverables:** `sentinel-kql-queries.md`, `incident-triage-report.md`, `cap-config.md`.

### 6. Vulnerability Management & Web App Hardening (`06-vulnerability-management/`)
* **Focus:** CVSS v3.1/EPSS scoring, web app vulnerability analysis, and dynamic defense.
* **Key Evidence:** Verified manual SQL injection vectors with Burp Suite Repeater, evaluated Nessus vulnerability reports, and verified 403 Forbidden blocking via ModSecurity WAF rules.
* **Deliverables:** `vulnerability-assessment-report.md`, `remediation-register.csv`, `waf-rules.md`.

### 7. Digital Forensics Analysis using Autopsy & Event Logs (`07-forensics-hardening/`)
* **Focus:** Forensic ingest pipelines, timeline reconstruction, and artifact extraction.
* **Key Evidence:** Processed forensic disk images in Autopsy, computed cryptographic hashes (MD5/SHA256), carved unallocated space, and parsed Linux `/var/log/auth.log` for sudo escalation.
* **Deliverables:** `dfir-case-report.md`, `timeline.csv`, `evidence-register.md`.

---

## Portfolio Approach
Each substantial project documents its objective, environment, implementation, troubleshooting, limitations, security considerations, evidence, and lessons learned.

> **Security Note:** Credentials, university identifiers, internal IP ranges, and other sensitive values are intentionally excluded or redacted.
