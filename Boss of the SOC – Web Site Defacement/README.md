Boss of the SOC V1 – Web Site Defacement

Splunk Investigations | SOC Case Study

🧪 Scenario Overview

In this hands-on lab, I assumed the role of Alice Bluebird, a newly hired SOC analyst at Wayne Enterprises. The first assignment was to investigate a potential website defacement reported by the Gotham City Police Department (GCPD). The website in question, imreallynotbatman.com
, hosted on Wayne Enterprises' infrastructure, appeared to have been compromised. The task was to determine the legitimacy of the defacement and reconstruct the attack timeline using Splunk.

🔍 Investigation Highlights

Initial Compromise Detection: Identified the first signs of compromise through HTTP request logs, pinpointing the attack vector.

Brute Force Attack Analysis: Analyzed login attempts to uncover the attacker's methods and tools.

Malware Identification: Detected and analyzed a malicious executable uploaded during the attack.

Timeline Reconstruction: Built a comprehensive timeline of events leading up to and following the defacement.

Indicator of Compromise (IOC) Extraction: Extracted IOCs, including IP addresses, domain names, and file hashes, to aid in further threat analysis.

📊 Key Findings

Defacement File: poisonivy-is-coming-for-you-batman.jpeg

Malicious IP Address: 23.22.63.114, 40.80.148.42

Uploaded Executable: 3791.exe

MD5 Hash of Executable: aae3f5a29935e6abcc2c2754d12a9af0

Brute Force Password Guess: batman

🛠 Tools & Techniques

Splunk SIEM: Utilized for log aggregation, search, and visualization.

VirusTotal: Used to analyze file hashes and detect known malware.

MITRE ATT&CK Framework: Applied for mapping adversary tactics and techniques.
