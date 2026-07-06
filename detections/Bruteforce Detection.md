# Bruteforce Detection 
## Objective 
The objective of this detection is to identify failed login attempts in Windows Security Event Logs that may indicate a brute force attack against a Windows user account. I analyzed Windows Security Event ID 4625 to understand how failed login attempts are recorded and how they can be investigated from a SOC analyst's perspective.

## Attack Simulation 
In order to simulate a BruteForce attack scenario,a local user account `attacker` has been created.Five incorrect password attempts were made before entering the correct password.This led in generating failed logon events that were recorded in the Windows Security Event logs.

## Log Source 
- Log name : Windows Security Event log
- Event ID : 4625
- Event description : An account failed to log on

## Event Analysis 
The Event ID 4625 which generated contains useful information for investigating the failed attempts based on:
- Account that failed to log on
- Logon type
- Failure reason
- Status codes
- Workstation source
- Time of the failed attempts

## Investigation Steps 
When multiple failed logon attempts are detected,below are the investigation phases:

1. The first step is identifying the user account that experienced the failed logon attempts.
2. Verify the logon type and understand how the authentication attempt was made.
3. Review the failure reason and the status codes to determine why the logon was failed.
4. Check the workstation source related with the failed authentication attempts.
5. Investigate whether successful logon as in this scenario Security Event ID 4624 has occurred after the failed attempts.
6. The last phase is to determine whether the acrivity was caused by a legitimate user or it is a potential brute force attack.

## False positives 
False positives could exist because multiple failed logon attempts do not always indicate a brute force attack. Below are some possible false positives:

- A user repeatedly trying an incorrect password.
- If the user forgets or recently changed password.
- If the credentials are expired.
- If scheduled tasks or services using / used outdated credentials
- Legitimate testing ot troubleshooting.

## Evidence
