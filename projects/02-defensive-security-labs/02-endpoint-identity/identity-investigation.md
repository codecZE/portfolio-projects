# Identity & Threat Detection Investigation

## Process Anomaly Investigation (Sysmon Event ID 1)
- **Parent Process:** `C:\Windows\System32\cmd.exe`
- **Child Process:** `C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe`
- **CommandLine:** `powershell.exe -NoP -NonI -W Hidden -Exec Bypass -enc [Base64 Payload]`
- **Analysis:** Obfuscated PowerShell execution launched from interactive command shell, indicating potential reverse shell payload launch.

## AD Telemetry Investigation (Kerberoasting - Event ID 4769)
- **Target Service Name:** `MSSQLSvc/sqlserver01.corp.local:1433`
- **Ticket Options:** `0x40810000`
- **Ticket Encryption Type:** `0x17` (RC4-HMAC)
- **Client IP:** `10.0.1.45`
- **Analysis:** Request for weak RC4 ticket on domain service account, characteristic of Kerberoasting ticket extraction.
