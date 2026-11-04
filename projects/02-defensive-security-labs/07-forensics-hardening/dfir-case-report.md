# Digital Forensics & Incident Response (DFIR) Case Report

## Executive Summary
Forensic analysis was conducted on a compromised workstation image to determine initial access, privilege escalation, and lateral movement activities following a suspected perimeter breach.

## Methodology
1. **Evidence Ingestion:** Image ingested into Autopsy; calculated cryptographic hashes (`MD5: 8743b73db7e01e23...`).
2. **Artifact Carving:** Extracted deleted payloads from unallocated space.
3. **Log Parsing:** Examined Windows Registry hives (`SAM`, `SYSTEM`) and Linux `/var/log/auth.log` files.

## Incident Kill Chain Findings
1. **Initial Access:** Execution of malicious attachment via user profile.
2. **Persistence:** Scheduled task added targeting system boot.
3. **Privilege Escalation:** Sudo privilege abuse parsed from Linux auth logs (`sudo su` execution without proper clearance).
