# Troubleshooting
Troubleshooting and Issues Encountered


During the setup and recovery process, multiple issues were encountered that required troubleshooting and corrective action. Below are the primary problems identified and the steps taken to resolve them.

<b>Windows Defender Firewall (Private vs Public Network)</b>


* One of the initial issues involved failed network communication between systems. The employee workstation was unable to ping or communicate with the domain controller due to the network profile being set incorrectly.



* By default, Windows Defender Firewall applies stricter rules when a network is marked as Public, which blocked ICMP traffic and internal communication.



<sub><b>Resolution:</b></sub>

1. The network connection was changed from `Public` to `Private`

2. IPv4 inbound communication was allowed

3. Firewall rules were adjusted to permit internal traffic



* Example PowerShell command used: 

`Set-NetConnectionProfile -InterfaceAlias "Ethernet1" -NetworkCategory Private`
After applying these changes, systems were able to successfully communicate within the domain.

<b>NTFS Permissions and Network Share Access</b>


Another issue involved access denial errors when attempting to access shared folders and restored data. These problems were related to NTFS permissions and share-level access control.



<sub><b>Resolution:</b></sub>

* Reviewed NTFS security permissions on shared folders

* Ensured proper inheritance was enabled

* Assigned ownership to the domain administrator

* Verified that appropriate domain users had read/write access



This ensured controlled access while maintaining centralized administrative oversight.

<b>Group Policy Object (GPO) Application Issues</b>


A Group Policy Object was created to enforce user and system restrictions; however, the policy initially failed to apply to the employee workstation.



Root Cause:

*The GPO was linked only to the user account

*The computer object was not included in the correct Organizational Unit (OU)



<sub><b>Resolution:</b></sub>

Verified correct OU placement

Ensured both the user and the machine were within the scope of the GPO

Forced a policy update using:

`Gpupdate /force`
After correction, the policy applied successfully.

