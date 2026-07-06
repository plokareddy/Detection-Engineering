# Reconnaissance Detection
## Objective 
The objective of this detection is to identify reconnaissance activities performed using native Windows commands. I analyzed Sysmon Event ID 1 to understand how process creation events are recorded and how they can help identify an attacker's reconnaissance activities.

## Attack Simulation 
To simulate reconnaissance commands, native Windows commands including `whoami`, `systeminfo`, `ipconfig`, `net user`, and `net localgroup administrators` were executed. Each command generated a Sysmon Event ID 1 (Process Creation) event, which was later analyzed.

## Log Source 
- Log name : Microsoft-Windows-Sysmon/Operational
- Event ID : 1
- Event description : Process Creation

## Event Analysis
Sysmon Event ID 1 contains useful information that helps in investigating discovery activity based on:

- Process name
- Command line
- Parent process
- User account
- Process ID(PID)
- Process GUID
- Image path
- Time of execution

| Command    | Purpose         |
|------------|-----------------|
| whoami     | Prints the current logged-in user|
| systeminfo | Displays the operating system information |
| ipconfig   | Displays the network configuration |
| net user   | Lists the local user accounts
| net localgroup <br> administrators | Lists members of the administrators group |

## Investigation steps 
Below are the investigation phases when reconnaissance activity is detected.
1. The first step is identifying the user account that executed the command.
2. Review the process name and command line to determine what information has been requested.
3. Verifying the parent process that launched the command.
4. Check whether multiple reconnaissance commands were executed within a short period of time.
5. Determine whether the activity was performed by a legitimate administrator or a potential attacker.
6. Investigate whether the reconnaissance activity was followed by privilege escalation or other suspicious behavior.

## False Positives 
False positives could exist because these commands are commonly used by administrators and support teams. Some possible false positives include:

- System administrators performing routine maintenance.
- IT support troubleshooting a system.
- Security analysts conducting investigations.
- Automated administrative scripts.
- Legitimate users checking system information.

## Evidence 
