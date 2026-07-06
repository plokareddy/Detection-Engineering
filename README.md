# 🛡️ Detection Engineering 
## 1. Overview 
Detection engineering is a defensive cybersecurity practice that focuses on identifying suspicious and malicious activity using logs and system telemetry. In this project, I simulated common attacker techniques in a Windows environment and analyzed the resulting Windows Security Event Logs and Sysmon events. Each scenario is mapped to the MITRE ATT&CK framework, with corresponding detection logic, Sigma rules, and investigation procedures to demonstrate how SOC analysts can detect, investigate, and respond to potential threats.

## 2. Project Objectives
The project was designed to:
- Simulate common attacker techniques in a Windows environment.
- Analyze Windows Security Event Logs and Sysmon events.
- Build detection logic for different attack scenarios.
- Map detections to the MITRE ATT&CK framework.
- Create Sigma rules for each detection scenario.
- Document investigation procedures and identify potential false positives from a SOC analyst's perspective.

## 3. Lab Environment 
- Operating System : Windows 11 ARM64
- Virtualization : UTM
- Log source : Windows Security Event logs
- Telemetry : Sysmon
- Detection Framework : MITRE ATT&CK
- Detection rules : Sigma

## 4. Detection Scenarios 
This project consists of five detection scenarios which simulate common attacker activities.Each scenario includes event analysis, MITRE ATT&CK mapping, detection logic, sigma rules, investigation procedures and supporting evidence.

| Detection                        | Event ID          | MITRE ATT&CK            |
|----------------------------------|-------------------|-------------------------|
| Brute Force Detection            | 4625              | T1110                   |
| Reconnaissance Detection         | Sysmon Event ID 1 | T1033,T1082,T1016,<br>T1087,T1069.001 |
| User Account Creation            | 4720              | T1136                   |          
| Administrator Group <br> Modification | 4732              | T1098                   |
| Encoded Powershell Execution     | Sysmon Event ID 1 | T1059.001               |

## 5. Skills Applied 
- Detection Engineering
- Windows Event log Analysis
- Sysmon Monitoring
- MITRE ATT&CK Mapping
- Sigma Rule Development
- Security Event Analysis
- Threat Detection
- Blue Teams Operation
- Incident Investigation

## 6. Repository Structure
```text
Detection-Engineering-Lab/
│
├── README.md
├── detections/
├── sigma-rules/
└── screenshots/
```
