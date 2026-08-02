---
title: "Week 2 Worklog"
date: 2026-06-22
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---
### Week 2 Objectives

* Understand AWS VPC networking concepts: VPC CIDR block, public/private subnets, Internet Gateway, Route Tables, Security Groups, and Network ACLs.
* Set up an Endpoint Threat Detection Lab environment on Windows 10 / FLARE-VM.
* Install and configure Elastic Agent, Sysmon (with SwiftOnSecurity config), and Suricata IDS to collect multi-layered host and network telemetry.
* Execute 7 Endpoint attack simulation scenarios using Atomic Red Team mapped to MITRE ATT&CK techniques (PowerShell fileless, LSASS dumping, Run key persistence, Scheduled task, DLL injection, Network scan, C2 beaconing).
* Engineer custom KQL/EQL detection rules in Elastic SIEM, build a Python SOAR alerter (`elk_discord_alerter.py`) to dispatch Discord notifications, and complete 4 threat hunting reports.

### Tasks Carried Out This Week

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Mon | - Study AWS VPC networking: public/private subnets, Route Tables, Internet Gateway, Security Groups vs. Network ACLs.<br>- Design network segmentation and configure secure isolation rules for the attack simulation lab environment. | 06/22/2026 | 06/22/2026 | <https://000003.awsstudygroup.com><br><https://000092.awsstudygroup.com> |
| Tue | - Provision Windows 10 / FLARE-VM test workstation in the isolated lab environment.<br>- Install Sysmon with SwiftOnSecurity configuration (`sysmonconfig.xml`) to capture Event ID 1 (Process Creation), Event ID 10 (Process Access), and Event ID 13 (Registry Modification).<br>- Install Elastic Agent connected to Elastic SIEM Fleet and configure Suricata IDS for network packet inspection. | 06/23/2026 | 06/23/2026 | <https://000048.awsstudygroup.com><br><https://000062.awsstudygroup.com> |
| Wed | - Install Atomic Red Team framework on the Windows endpoint.<br>- Execute first 4 Endpoint Attack Scenarios:<br>&emsp;+ Scenario 1 (T1059.001): PowerShell Fileless Execution (Base64 encoded command).<br>&emsp;+ Scenario 2 (T1003.001): LSASS Memory Dump via `rundll32.exe` & `comsvcs.dll` (LOLBin abuse).<br>&emsp;+ Scenario 3 (T1547.001): Registry Run Key Persistence.<br>&emsp;+ Scenario 4 (T1053.005): Scheduled Task Persistence via `schtasks.exe`. | 06/24/2026 | 06/24/2026 | Atomic Red Team Docs<br><https://000044.awsstudygroup.com> |
| Thu | - Execute remaining 3 Endpoint Attack Scenarios:<br>&emsp;+ Scenario 5 (T1055.001): DLL Injection via `mavinject.exe`.<br>&emsp;+ Scenario 6 (T1046): Network Service Discovery & Port Scanning via Nmap/Suricata.<br>&emsp;+ Scenario 7 (T1071.001): C2 Beaconing with malicious HTTP User Agent.<br>- Develop Python SOAR utility (`elk_discord_alerter.py`) querying Elastic Security API to automate incident alerts with MITRE ATT&CK IDs to Discord webhooks. | 06/25/2026 | 06/25/2026 | <https://000066.awsstudygroup.com><br>Elastic Security API Docs |
| Fri | - Engineer, test, and tune 7 custom KQL/EQL detection rules in Elastic SIEM.<br>- Conduct 4 proactive Threat Hunting campaigns over historical telemetry:<br>&emsp;+ Hunt 1: LOLBin Abuse (`rundll32`, `mavinject`).<br>&emsp;+ Hunt 2: LSASS Reconnaissance (tuning exclusions for `svchost.exe` / `0x1410`).<br>&emsp;+ Hunt 3: Persistence Audit (creation and deletion lifecycles of Run keys / Scheduled tasks).<br>&emsp;+ Hunt 4: C2 Beaconing (adding Sysmon script egress rule).<br>- Author 4 comprehensive Threat Hunt Reports (`hunt1` - `hunt4`). | 06/26/2026 | 06/26/2026 | Elastic SIEM Detection Engine<br>MITRE ATT&CK Framework |

### Week 2 Achievements

* Mastered AWS VPC networking fundamentals, subnet architectures, route tables, and firewall access controls (Security Groups / NACLs).
* Successfully established an endpoint detection lab with Elastic Agent, Sysmon, and Suricata IDS collecting multi-layer telemetry.
* Simulated 7 real-world Endpoint attack scenarios aligned with MITRE ATT&CK using Atomic Red Team.
* Engineered high-fidelity custom KQL/EQL detection rules in Elastic SIEM and deployed a Python SOAR tool for real-time Discord alerting.
* Conducted 4 proactive Threat Hunting campaigns over historical logs, identifying detection gaps and tuning SIEM rules.
