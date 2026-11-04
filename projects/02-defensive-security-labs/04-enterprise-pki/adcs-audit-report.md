# Active Directory Certificate Services (AD CS) Audit Report

## Audit Scope
Evaluation of Active Directory Certificate Templates for privilege escalation risks (ESC1 / ESC2 vectors).

## Key Findings (ESC1 Vector Identification)
Using `Certify.exe find /vulnerable`, certificate template `UserAuthTemplate` was identified with critical misconfigurations:
1. **Client Authentication Enabled:** Allows Extended Key Usage (EKU) for Domain Authentication.
2. **`ENROLLEE_SUPPLIES_SUBJECT` Enabled:** Flag `CT_FLAG_ENROLLEE_SUPPLIES_SUBJECT` set in template properties.
3. **Broad Enrollment Rights:** `Authenticated Users` group granted Enrollment permissions.

## Exploitation Impact
An unprivileged domain user can request a certificate while supplying an arbitrary Subject Alternative Name (SAN) of a Domain Admin (e.g., `Administrator@corp.local`), allowing immediate domain compromise via PKINIT Kerberos authentication.
