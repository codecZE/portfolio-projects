# Endpoint Detection & AD Hardening Strategy

## Recommendations
1. **Group Managed Service Accounts (gMSA):** Replace user-managed service accounts with gMSAs to automatically handle 128-character rotating passwords.
2. **PowerShell Logging:**
   - Enable Script Block Logging (Event ID 4104).
   - Enable Module Logging and Transcripts.
3. **Kerberos Encryption:** Enforce AES-128 / AES-256 encryption types domain-wide; disable RC4 support (`0x17`).
