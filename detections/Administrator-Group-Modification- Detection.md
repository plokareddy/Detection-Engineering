# Administrator Group Modification Detection
## Objective 
The objective of this detection is to identify when a user account is added to a privileged local group in Windows. I analyzed Windows Security Event ID 4732 to understand how administrator group membership changes are recorded and how they can be investigated from a SOC analyst's perspective.

## Attack Simulation 
To simulate this activity, the local user account named `attacker` was added to the local `Administrators` group using Windows Local Users and Groups. 
This generated Windows Security Event ID 4732, which was analyzed later.

## Log Source 

- Log name : Windows Security Eveny log
- Event ID : 4732
- Event description : A member was added to a security-enabled local group

## Event Analysis 
Event ID 4732 contains useful information for investigating administrator group modifications, including:

- Security ID
- Member account
- Group name
- Group domain
- Subject account
- Subject Logon ID
- Time of the group modification

## Investigation Steps 
Below are the investigation steps when a user account is added to a privileged group.

1. Identify the user account that was added to the group.
2. Verify which account performed the group modification.
3. Review the name of the security-enabled local group.
4. Determine whether the group modification was authorized.
5. Check whether the newly added account performed any privileged activities.
6. Investigate whether additional group membership changes occurred.

## False Positives 
False positives could exist because administrator group modifications may occur during normal administrative activities. Below are some possible false positives:

- IT administrators assigning administrative privileges.
- User account maintenance.
- Temporary administrator access for troubleshooting.
- Authorized system configuration changes.

## Evidence 
