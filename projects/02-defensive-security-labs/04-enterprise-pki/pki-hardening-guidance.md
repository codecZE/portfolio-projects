# PKI & AD CS Hardening Guidance

## Remediation Steps
1. **Disable Enrollee Subject Specification:**
   - Uncheck "Supply in the request" on all templates providing Client Authentication.
2. **Restrict Access Control Lists (ACLs):**
   - Remove `Authenticated Users` from template enrollment permissions. Restrict to specific, audited security groups.
3. **Audit CA Settings:**
   - Run `certutil -setreg policy\EditFlags -EDITF_ATTRIBUTESUBJECTALTNAME2` to disable dangerous SAN overrides globally across the CA.
4. **Enable Auditing:** Enable Windows Event ID 4886 (Certificate Services requested) and Event ID 4887 (Certificate Services approved/issued).
