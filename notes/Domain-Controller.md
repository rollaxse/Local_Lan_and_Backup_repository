# Domain Controller



The domain controller was deployed using Windows Server 2022 (Desktop Experience) to provide centralized authentication, user management, and policy enforcement. The configuration followed standard enterprise practices to ensure domain stability and allow consistent management of users and systems.



After logging into the server, initial configuration tasks were completed to prepare the system for domain services. The server was renamed to reflect its role as the domain controller and restarted to apply changes. This helps clearly identify infrastructure roles within the environment.



<sub><b>steps performed</b></sub>
1. Logged into the Windows Server VM

2. Renamed the server to reflect its domain controller role

3. Restarted the server to apply hostname changes

4. Verified network connectivity on the internal adapter

5. Active Directory Domain Services Installation

Server Manager


Active Directory Domain Services (AD DS) was installed using Server Manager. The role installation was completed using the Add Roles and Features wizard with a role-based installation on the local server. Required features were added automatically.



Once installation completed, the server was promoted to a domain controller. During this process, a new forest was created using a fictional company domain name to simulate an enterprise environment. DNS integration was enabled by default, and the server was restarted to complete the promotion.



<sub><b>Steps Performed</b></sub>
1. Opened Server Manager

2. Selected `Manage → Add Roles and Features`

3. Installed Active Directory Domain Services

4. Promoted the server to a domain controller

5. Created a new forest using a fictional domain name

6. Set the DSRM password

7. Restarted the server after promotion

8. Organizational Units and User Creation

Organizational Units


Organizational Units (OUs) were created to logically separate employee accounts and workstation objects. This structure supports clearer administration and allows targeted Group Policy enforcement.



Domain user accounts were created to represent fictional employees as part of a simulated onboarding process. These accounts were configured as standard users without administrative privileges.



<sub><b>Steps Performed</b></sub>
1. Opened `Active Directory Users and Computers`

2. Created Organizational Units for employees and workstations

3. Created domain user accounts for fictional employees

4. Verified users were members of Domain Users only

Network Configuration


The network for this lab was designed to separate external internet access from internal domain communication, similar to how a small enterprise environment is structured. Each virtual machine was configured with two network adapters: one for basic internet connectivity and one for a private internal network. Static IPv4 addressing was used on the internal LAN to ensure reliable communication between systems, including domain authentication and backup traffic. Windows Defender Firewall and network profile settings were adjusted to allow secure internal communication while minimizing unnecessary exposure

<sub><b>Steps Performed</b></sub>
1. Configured two network adapters on each virtual machine

2. NAT for internet connectivity

3. Host-only adapter for internal LAN communication

4. Assigned static IPv4 addresses on the internal network

5. Address range: `192.168.100.x`

6. Consistent subnet mask across all systems

7. Set the domain controller as the primary DNS server for the internal network

8. Changed the internal network connection profile to Private to allow domain traffic:

9. `Set-NetConnectionProfile -InterfaceAlias "Ethernet1" -NetworkCategory Private`

10. Adjusted Windows Defender Firewall to permit required inbound IPv4 communication on the private network

11. Verified connectivity and domain communication using ping tests and successful domain joins



Domain Join and Verification


Each employee workstation was joined to the domain using domain administrator credentials. After joining the domain, systems were restarted and tested to ensure proper authentication and profile creation.



Successful login using domain credentials confirmed that domain services were functioning correctly.



<sub><b>Steps Performed</b></sub>
1. Logged into each workstation using a local account

2. Verified DNS pointed to the domain controller

3. Joined the workstation to the domain

4. Restarted the workstation

5. Logged in using domain user credentials to verify functionality

Validation


The domain configuration was validated by confirming successful authentication, proper workstation registration in Active Directory, and the ability to apply Group Policy Objects.



This setup enabled centralized control, enforced user restrictions, and supported realistic testing of security policies and recovery workflows.
