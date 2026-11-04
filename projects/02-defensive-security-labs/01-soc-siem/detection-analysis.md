# Detection Analysis: Brute-Force & Credential Stuffing Triage

## Context & Baseline
During routine monitoring, an anomaly was observed originating from IP `192.168.1.105` generating excessive failed authentication requests across multiple domain accounts within a short duration.

## Hypothesis
An external host is executing an automated password spray or targeted dictionary brute-force attack against domain accounts.

## SPL Search Queries
```spl
index=windows EventCode=4625 
| stats count by Source_IP, Target_AccountName, Failure_Reason 
| sort - count
```

## Evidence Artifacts
- **Event Viewer Details:**
```xml
<Event xmlns="http://schemas.microsoft.com/win/2004/08/events/event">
  <System>
    <Provider Name="Microsoft-Windows-Security-Auditing"/>
    <EventID>4625</EventID>
    <TimeCreated SystemTime="2026-03-30T08:15:22.1045218Z"/>
    <Computer>WORKSTATION01.corp.local</Computer>
  </System>
  <EventData>
    <Data Name="TargetUserName">administrator</Data>
    <Data Name="IpAddress">192.168.1.105</Data>
    <Data Name="Status">0xc000006d</Data>
    <Data Name="SubStatus">0xc000006a</Data>
  </EventData>
</Event>
```

## Verdict & Verdict Rationale
Confirmed Malicious Activity (Brute-force attack). Over 450 failure events recorded within 10 minutes targeting `administrator`, `jdoe`, and `svc_sql`.

## Recommended Actions
1. Block IP `192.168.1.105` at the perimeter firewall.
2. Enforce Group Policy Object (GPO) account lockout threshold (e.g., 5 invalid attempts = 30-minute lock).
3. Force password reset for target accounts exposed during the attack window.
