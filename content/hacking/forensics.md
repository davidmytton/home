---
title: "Forensics"
date: 2023-01-03
modified: 2023-01-04
draft: false
summary: "Notes on digital forensics, office files, Powrshell, Packet capture, etc."
---

{{< hacking-disclaimer >}}

## Powershell

- [Often used for obfuscating scripts](https://www.cynet.com/attack-techniques-hands-on/powershell-obfuscation-demystified-series-chapter-2-concatenation-and-base64-encoding/).
- Use [PowerDecode](https://github.com/Malandrone/PowerDecode) (Windows only)
- [PSDecode](https://github.com/R3MRUM/PSDecode) (inside PowerShell)
- Can run scripts using [Any Run](https://app.any.run/)
- [Analyzing shell code](https://isc.sans.edu/diary/Analyzing+Encoded+Shellcode+with+scdbg/24134)

### On Kali

Need to find the `PSModule` path to be able to use [PSDecode](https://github.com/R3MRUM/PSDecode):

```shell
┌──(kali㉿kali)-[~/psd/PSDecode]
└─$ pwsh
┌──(kali㉿kali)-[/home/kali/psd/PSDecode]
└─PS> $Env:PSModulePath
/home/kali/.local/share/powershell/Modules:/usr/local/share/powershell/Modules:/opt/microsoft/powershell/7/Modules
┌──(kali㉿kali)-[~/psd/PSDecode]
└─$ mkdir /home/kali/.local/share/powershell/Modules/PSDecode
┌──(kali㉿kali)-[~/psd/PSDecode]
└─$ mv PSDecode.psm1 /home/kali/.local/share/powershell/Modules/PSDecode
┌──(kali㉿kali)-[/home/kali]
└─PS> PSDecode -dump -beautify -verbose fileToDecode.ps1
```

## Packet capture

- Wireshark GUI
- [tshark](https://tshark.dev/) CLI
  - `brew install --cask wireshark`
  - `tshark -r capture.pcap --export-objects http,http_objs`
- [A-Packets](https://apackets.com/upload) - Online pcap analysis

## Office docs

- Online file analysis tool: <https://hybrid-analysis.com/>
- Run the file through <https://any.run>
- [Analyzing Malicious Documents Cheat Sheet](https://zeltser.com/analyzing-malicious-documents/)
- For both `.docx` and `.doc` files, [oletools](https://github.com/decalage2/oletools)
  - `sudo -H pip install -U oletools`
- <https://inquest.net/blog/2020/03/18/Getting-Sneakier-Hidden-Sheets-Data-Connections-and-XLM-Macros>

### .doc or .xls

- Excel / Macro (XLS) deobfuscation - extracting macros from the file: [XLMMacroDeobfuscator](https://github.com/DissectMalware/XLMMacroDeobfuscator)

### .docx or .xlsx

- Used [OfficeDissector](https://github.com/grierforensics/officedissector) on a Ubuntu 20.04 GCP VM to export to JSON, then search for interesting strings.
  - Office file analysis (new format .docx only). Requires python2.

```python
import officedissector
doc = officedissector.doc.Document('file.docx')
doc_json = doc.to_json()
```
