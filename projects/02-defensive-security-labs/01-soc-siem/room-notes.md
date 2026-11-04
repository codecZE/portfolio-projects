# Room Notes: SOC & SIEM Foundations

## Learning Outcomes & Concepts
- **SOC Alert Lifecycle:** Intake $\rightarrow$ Triage $\rightarrow$ Prioritization $\rightarrow$ Investigation $\rightarrow$ Containment & Remediation $\rightarrow$ Post-Incident Review.
- **Windows Security Telemetry:**
  - `EventCode=4624`: Successful account logon.
  - `EventCode=4625`: Failed account logon (SubStatus codes `0xc000006a` = Bad Password, `0xc000006e` = Unknown Username).
- **Splunk Processing:** Parsing raw syslog/XML events into indexed key-value fields for targeted query correlation using Search Processing Language (SPL).
