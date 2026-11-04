# Azure Cloud Incident Triage Report

## Incident Context
- **Alert Title:** Suspicious Role Assignment & Anomalous Cloud Logon.
- **Severity:** High.
- **MITRE Tactics:** T1098 (Account Manipulation), T1078 (Valid Accounts).

## Investigation Findings
- Analyst identified multiple failed logins from foreign locations followed by a successful login using single-factor authentication.
- Subsequent `AzureActivity` logs confirmed an Owner role assignment added to an external user account.

## Action Taken
- Revoked active user sessions via Entra ID portal.
- Removed unauthorized RBAC role assignment.
- Triggered mandatory password reset and enforced MFA registration.
