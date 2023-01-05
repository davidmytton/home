---
title: "Windows"
date: 2023-01-03
modified: 2023-01-04
draft: false
summary: "Notes on hacking Windows."
groupByYear: false
showTableOfContents: true
cascade:
  showDate: false
  showDateUpdated: true
  showAuthor: false
  showBreadcrumbs: true
---

{{< hacking-disclaimer >}}

## Commands

### General

Get Windows version:

```powershell
Get-WmiObject -Class win32_OperatingSystem | select Version,BuildNumber
```

Walk through all files in the C drive, one screen at a time:

```bash
tree c:\ /f | more
```

List all subdirectories contents within another subdir:

```powershell
Get-ChildItem -Path C:\Users\Administrator\Downloads -Recurse
```

List permissions of a specific directory. See the [icacls](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/icacls) [reference](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/icacls) for output including other options like grant:

```bash
icacls c:\windows
```

List running services:

```powershell
Get-Service | ? {$_.Status -eq "Running"}
Get-Service | ? {$_.Status -eq "Running"} | fl # shows extra info
```

Manage a service named wuauserv. sdshow output is in [SDDL](https://docs.microsoft.com/en-us/windows/win32/secauthz/security-descriptor-definition-language-for-conditional-aces-):

```bash
sc qc wuauserv # query
sc stop wuauserv # stop (needs elevated privs)
sc sdshow wuauserv # view service perms
```

Show service permissions:

```powershell
Get-ACL -Path HKLM:\System\CurrentControlSet\Services\wuauserv | Format-List
```

Enable WSL:

```powershell
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
```

Query registry key:

```powershell
reg query HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Run
```

AD get user attributes/privs ([ref](https://docs.microsoft.com/en-us/windows/win32/ad/user-object-attributes)):

```powershell
Get-ADUser -Identity htb-student # specific user
whoami /priv # current user
```

AD list domain admins:

```powershell
Get-ADGroup -Identity "Domain Admins" -Properties * | select DistinguishedName,GroupCategory,GroupScope,Name,Members
```

### NTLM Hash Cracking

Use [[Responder]] to get the NTLM hash then crack it with John.

```bash
echo "Administrator::RESPONDER:81c52155620d80d0:47825D3134646498212FAB22A2AD671A:0101000000000000804556E0679ED8014716E858CCE2CFFA00000000020008003800510058004E0001001E00570049004E002D0043005A0030004A00360039004D004F004B0046004D0004003400570049004E002D0043005A0030004A00360039004D004F004B0046004D002E003800510058004E002E004C004F00430041004C00030014003800510058004E002E004C004F00430041004C00050014003800510058004E002E004C004F00430041004C0007000800804556E0679ED801060004000200000008003000300000000000000001000000002000006324F7C1510A87EC0E2018FD19F16F33670CCF4EAA7FE82ECAF9D8C3B518653C0A001000000000000000000000000000000000000900200063006900660073002F00310030002E00310030002E00310034002E00330036000000000000000000" > hash.txt
john -w=/usr/share/wordlists/rockyou.txt hash.txt
```

## Notes

### General links

- RDP from Linux using `rdesktop`
- [Critical Windows services](https://docs.microsoft.com/en-us/windows/win32/rstmgr/critical-system-services)
- [General Windows components](https://en.wikipedia.org/wiki/List_of_Microsoft_Windows_components#Services)
- [SysInternals](https://docs.microsoft.com/en-us/sysinternals/) can be accessed from Explorer or Command prompt.

### Authentication

- Part of workgroup = auth via local Windows database.
- Part of a domain = auth via Active Directory.

### LFI

- [LFI Payloads](https://github.com/carlospolop/Auto_Wordlists/blob/main/wordlists/file_inclusion_windows.txt) e.g. `../../../../../../../../windows/system32/drivers/etc/hosts`

### WinRM Session

`evil-winrm -i $IP -u administrator -p password`

## Other pages
