# SOC Investigation: RDP Brute Force & File Integrity Monitoring (Wazuh SIEM)

# Objective
Investigate an RDP brute-force attack & confirm system compromise by correlating
Windows authentication logs & file integrity monitoring alerts using Wazuh SIEM.


# Lab Setup
Wazuh Manager, Indexer & Dashboard: Kali Linux
Victim Machine: Windows 10 (Wazuh Agent Installed)
Attacker Machine: Kali Linux
Attack Vector: RDP Brute Force


# Attack Simulation
Performed RDP brute-force attack against a Windows 10 machine user account.
Generated multiple failed login attempts followed by a successful login.
Modified an important file after successful login


# Detection & Analysis
Detected repeated Windows Event ID **4625** (Failed Logon).
Observed Windows Event ID **4624** indicating successful RDP login.
Identified the attacker source IP through log correlation in Wazuh.
File Integrity Monitoring alert detected: a file modification event after the successful RDP login.


# File Integrity Monitoring (FIM)
Detected unauthorized file modification after successful RDP access.
Confirmed attacker activity post-authentication.


# SOC Investigation Timeline

Time | Event 
T1 | Multiple 4625 failed RDP logon attempts 
T2 | 4624 successful RDP authentication
T3 | File Integrity Monitoring alert triggered
T4 | Incident confirmed as system compromise


# MITRE ATT&CK Mapping
T1110 – Brute Force
T1021.001 – Remote Services (RDP)
T1078 – Valid Accounts
T1565 – Data Manipulation  


# Outcome
Confirmed RDP brute-force attack.
Verified successful compromise using authentication logs.
Detected post-compromise file changes via FIM.
Documented incident in SOC-style investigation format.


# Tools Used
Wazuh SIEM
Windows Event Logs
Kali Linux
Windows
- Kali Linux
- Windows 10
