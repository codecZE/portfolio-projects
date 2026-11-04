# Enterprise Active Directory & Systems Security Lab

**Type:** Completed university practical project — Leeds Beckett University, Systems Security  
**Environment:** Windows Server 2016, Windows workstations, Debian GNU/Linux 12  
**Focus:** Centralised identity, access control, Linux/Windows integration, system hardening and network services

## Overview
This project implemented a centralised authentication and systems-security environment across five Windows and Linux systems. The objective was to reduce attack vectors and apply least privilege, secure defaults and defence in depth.

A Windows Server 2016 VM hosted Active Directory. Windows and Debian endpoints were integrated into the domain using Kerberos-based authentication and role-based access controls.

## What I implemented

### Centralised authentication
- Configured Microsoft Active Directory on Windows Server 2016.
- Joined Windows workstations to the domain.
- Joined Debian systems using `realmd` and `SSSD`.
- Configured GUI domain login through `GDM3`.
- Used PAM/NSS in Linux authentication/access configuration.
- Used Kerberos-backed domain authentication.

### User and group administration
- Created and managed domain users.
- Assigned users to staff, developer and administrator groups.
- Applied role-based access and least privilege.

### Security policies
- Configured Windows Group Policy controls.
- Applied password-complexity and account-lockout controls.
- Implemented login restrictions, including business-hours restrictions where required.
- Restricted administrative access for normal users.

### Linux security
- Hardened SSH configuration.
- Configured shared folders and Linux permissions.
- Applied AppArmor and Firejail sandboxing on the staff Linux workstation.
- Reviewed privileged access and security-relevant system configuration.

### Network/server services
- Worked with a Linux public-facing web-server role and restricted SSH administration.
- Installed/configured `vsftpd` for FTP.
- Installed/configured Samba/SMB file sharing.
- Tested services and documented integration problems rather than presenting partial implementations as successful.

## Troubleshooting and limitations

| Area | Result | Finding |
|---|---|---|
| Windows/Linux domain authentication | Implemented | Domain login was configured across Windows and Debian systems. |
| Linux automatic AD home-directory creation | Not working | PAM configuration was attempted, but expected automatic home-directory behaviour did not work reliably through GDM3. |
| FTP | Partially working | `vsftpd` was installed and anonymous access disabled, but passive-mode/AD-login behaviour was unreliable. |
| SMB/Samba | Partially working | Local Linux sharing worked, but consistent AD-user integration was not achieved. |
| MFA | Not implemented | MFA approaches were investigated but not completed within the lab constraints. |
| Advanced auditing/security controls | Partial | Basic hardening/firewall/sudo restrictions were applied, but the full intended audit-control set was not completed. |

Accurate reporting of unsuccessful configurations is part of this project: it distinguishes what was configured, what was verified, and what remained unresolved.

## Skills demonstrated
Active Directory Domain Services · Kerberos · IAM · Group Policy · `realmd` · SSSD · PAM/NSS · GDM3 · Linux permissions · SSH hardening · AppArmor · Firejail · FTP/vsftpd · Samba/SMB · least privilege · defence in depth

## Evidence to add
Before publishing original screenshots, sanitize them. Useful evidence includes:
1. Windows Server / AD overview
2. AD Users and Computers with sanitized/fake identities
3. Windows domain membership
4. Debian realm/SSSD integration
5. Successful Linux domain-user login
6. Group-based privilege/access test
7. Group Policy
8. Password/account-lockout test
9. Linux permissions/shared-folder test
10. SSH hardening
11. AppArmor/Firejail
12. FTP/Samba troubleshooting evidence clearly labelled partial/unresolved

## What I learned
The project gave me practical experience of centralised identity across heterogeneous Windows and Linux systems. It also demonstrated that identity integration depends on more than creating accounts: authentication protocols, PAM/NSS behaviour, permissions and individual services affect whether users can actually work.

The unresolved FTP, SMB and home-directory issues were useful troubleshooting exercises because they required separating successful domain authentication from service-specific integration problems.

## Relevance to IT support
This project gives me practical examples to discuss for user/group administration, domain-login troubleshooting, password/account policy, access/permission issues, Windows/Linux integration, service troubleshooting and documentation/escalation of unresolved issues.

## Next extension
I will rebuild a smaller personal version of the environment and create simulated service-desk tickets for password resets, account lockouts, disabled accounts, group/access requests, domain-login failures, DNS/connectivity problems and shared-folder permissions.

The personal extension will be documented separately so it is clearly distinguished from the original university project.
