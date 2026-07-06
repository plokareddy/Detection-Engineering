# Encoded Powershell Execution Detection 
## Objective 
The objective of this detection is to identify the execution of Base64-encoded Powershell commands in Windows.I analyzed Sysmon Event ID 1 to understand how encoded PowerShell commands are recorded and how they can be investigated from a SOC analyst's perspective.

## Attack Simulation 
To simulate this activity, a Base64-encoded PowerShell command was executed using the `EncodedCommand` parameter. This generated a Sysmon Event ID 1 (Process Creation) event, which was later analyzed.

## Log Source 

- Log name  : Microsoft-Windows-Sysmon/Operational
- Event ID  : 1
- Event description : Process Creation

## Event Analysis
Sysmon Event ID 1 contains useful information for investigating encoded PowerShell execution, including:

- Process name
- Command line
- Parent process
- User account
- Process ID (PID)
- Process GUID
- Image path
- Time of execution

## Investigation Steps
Below are the investigation steps when encoded PowerShell execution is detected.

1. Identify the user account that executed the PowerShell command.
2. Review the command line to determine whether the `-EncodedCommand` parameter was used.
3. Verify the parent process that launched PowerShell.
4. Determine whether the encoded command was expected or suspicious.
5. Investigate any additional PowerShell activity that occurred around the same time.
6. Check whether the encoded command was followed by any malicious activity.

## False Positives 
False positives could exist because PowerShell is commonly used for administration and automation. Below are some possible false positives:

- System administrators running PowerShell scripts.
- Automated maintenance scripts.
- Software installation or update processes.
- Security testing performed by administrators.


