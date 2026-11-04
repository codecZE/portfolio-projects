# Windows & Active Directory Security Notes

## Core Event IDs
- **Sysmon Event ID 1:** Process Creation (captures ParentImage, Image, CommandLine, User, Hashes).
- **Sysmon Event ID 3:** Network Connection.
- **Sysmon Event ID 16:** Sysmon configuration change.
- **AD Security Event ID 4769:** A Kerberos service ticket was requested.

## Attack Vectors
- **Living Off The Land (LotL):** Utilizing native binaries (`cmd.exe`, `powershell.exe`, `mshta.exe`) to evade signature-based antivirus.
- **Kerberoasting (T1558.003):** Requesting TGS tickets for SPNs encrypted with RC4 (`0x17`) to crack service passwords offline.
