# Cybersecurity Portfolio & Hands-On Security Lab Write-Ups

This project contains hands-on technical write-ups, incident triage documentation, network analysis logs, PKI audit findings, cloud security queries, and digital forensics case reports completed across TryHackMe defensive security modules and hands-on lab exercises.

## Repository Structure

```
.
├── 01-soc-siem/
│   ├── room-notes.md
│   ├── detection-analysis.md
│   ├── lessons-learned.md
│   └── screenshots/
│       └── README.md
├── 02-endpoint-identity/
│   ├── windows-event-notes.md
│   ├── identity-investigation.md
│   ├── detection-and-hardening.md
│   └── screenshots/
│       └── README.md
├── 03-network-security/
│   ├── network-analysis.md
│   ├── web-security-finding.md
│   ├── mitigation-matrix.md
│   └── screenshots/
│       └── README.md
├── 04-enterprise-pki/
│   ├── adcs-audit-report.md
│   ├── pki-hardening-guidance.md
│   └── screenshots/
│       └── README.md
├── 05-azure-security/
│   ├── sentinel-kql-queries.md
│   ├── incident-triage-report.md
│   ├── cap-config.md
│   └── screenshots/
│       └── README.md
├── 06-vulnerability-management/
│   ├── vulnerability-assessment-report.md
│   ├── remediation-register.csv
│   ├── waf-rules.md
│   └── screenshots/
│       └── README.md
└── 07-forensics-hardening/
    ├── dfir-case-report.md
    ├── timeline.csv
    ├── evidence-register.md
    └── screenshots/
        └── README.md
```

## Highlights & Focus Areas
- **SOC & SIEM Operations:** Splunk SPL queries for EventCode 4625 brute-force detection and triage.
- **Endpoint Telemetry:** Sysmon process tree anomaly detection (ID 1) and AD Kerberoasting triage (ID 4769).
- **Network Defense:** Custom Snort NIDS rule syntax (SID 1000001) for TCP SYN scan detection & Zeek packet analysis.
- **Active Directory PKI Audit:** AD CS ESC1 vulnerability identification and mitigation.
- **Azure Security:** KQL threat hunting on `SigninLogs` and `AzureActivity` with Sentinel & Entra ID policy setup.
- **Web Security & Vulnerability Management:** CVSS v3.1 scoring, OWASP Top 10 SQLi triage, ModSecurity WAF rules.
- **Digital Forensics:** Autopsy timeline parsing, unallocated space carving, and `/var/log/auth.log` escalation triage.
