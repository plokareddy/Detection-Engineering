# User Account Creation Detection 
## Objective 
The objective of this detection is to identify the creation of new local user accounts in Windows environment.I analyzed Windows Security Event ID 4720 to understand how account creation events are recorded and how they can be investigated from a SOC analyst's perspective.

## Attack Simulation
To simulate the activity, a new local user account named `attacker` has been created using Windows Local Users and Groups.This generated Windows Security Event ID 4720.

## Log Source 

- Log name : Windows Security Event Log
- Event ID : 4720
- Event description : A user acccount was created

## Event Analysis 
Event Id 4720 contains useful information for investigating newly created user accounts and that includes:
- Security ID
- Account name
- Account domain
- Creator account
- User Account Control(UAC) attributes
- Primary Group ID
- Time of action creation

## Investigation steps 
Below are the investigation steps when a new use account is detected.

1. Identify the newly created user account.
2. Verify which user created the account.
3. Review the time when the account was created.
4. Determine whether the account creation was authorized.
5. Check if the newly created account was added to any privileged groups.
6. Investigate whether the account was used for suspicious logon activity.

## False Positives
False positives could exist because user accounts may be created during normal administrative activities. Below are some possible false positives:

- IT administrators creating legitimate user accounts.
- New employee onboarding.
- Test accounts created for troubleshooting.
- Temporary accounts created for maintenance.


