# Conditional Access & Cloud Governance Configuration

## Policy Recommendations
1. **Require Phishing-Resistant MFA:** Enforce FIDO2 security keys for all privilege administrative roles (`Global Administrator`, `User Administrator`).
2. **Privileged Identity Management (PIM):** Require Just-In-Time (JIT) activation with mandatory ticket reference and manager approval.
3. **Block Legacy Authentication:** Disable POP3, IMAP, and SMTP authentication protocols across all mailboxes.
