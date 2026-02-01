# Boss of the SOC V1 – Ransomware Incident (Cerber)

Splunk Investigations | SOC Case Study

##  Scenario Overview

In this case study, I acted as a SOC Analyst to investigate a critical ransomware incident. The incident targeted a high-value workstation, we8105desk, and subsequently spread to the corporate file server. My objective was to trace the infection from the initial web-based download through script execution to the final encryption of 663 documents across the network.

##  Investigation Highlights

Initial Access Identification: Traced the infection source to a drive-by download of a masqueraded file (mhtr.jpg) from a malicious domain via HTTP stream logs.

Execution Analysis: Leveraged Sysmon logs to identify the misuse of Windows script engines (wscript.exe) and localized the temporary execution script (121214.tmp).

Lateral Movement Tracking: Monitored outbound SMB (Port 445) traffic to identify the transition from local workstation compromise to remote server impact.

Data Impact Quantification: Used Splunk stats and dc (distinct count) functions to audit the exact number of encrypted PDF and TXT files, distinguishing between user data and system artifacts.

Process Forensics: Isolated the Parent Process ID (PPID 3968) to determine the origin of the malicious encryption routine.

##  Key Findings

Victim Workstation: we8105desk (192.168.250.100)

Target File Server: we3269srv (192.168.250.20)

Malicious Domain: solidaritedeproximite.org

Payload Execution: wscript.exe executing 121214.tmp

Total Data Impact: 406 local user TXT files and 257 remote PDF files (663 total).

Ransomware Variant: Cerber Ransomware.

##  Tools & Techniques

Splunk SIEM: Core platform for log aggregation and correlation across botsv1 data.

Sysmon (System Monitor): Used for deep process-level visibility and tracking Parent-Child process relationships.

Splunk Stream: Used for deep packet inspection and capturing wire-data metadata across the following protocols:

- stream:http: For payload delivery and web-based triggers.

- stream:smb: For tracking lateral movement and file share encryption.

- stream:dns: For identifying malicious domain lookups and DGA activity.

MITRE ATT&CK Mapping: Applied to categorize behaviors such as Command and Scripting Interpreter (T1059) and Data Encrypted for Impact (T1486).

