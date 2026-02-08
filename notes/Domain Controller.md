# Domain Controller
Domain Controller Setup and Domain Configuration


The domain controller was deployed using Windows Server 2022 (Desktop Experience) to provide centralized authentication, user management, and policy enforcement. The configuration followed standard enterprise practices to ensure domain stability and allow consistent management of users and systems.



After logging into the server, initial configuration tasks were completed to prepare the system for domain services. The server was renamed to reflect its role as the domain controller and restarted to apply changes. This helps clearly identify infrastructure roles within the environment.



<sub><b>steps performed</b></sub>
1. Logged into the Windows Server VM

2. Renamed the server to reflect its domain controller role

3. Restarted the server to apply hostname changes

4. Verified network connectivity on the internal adapter

5. Active Directory Domain Services Installation


Active Directory Domain Services (AD DS) was installed using Server Manager. The role installation was completed using the Add Roles and Features wizard with a role-based installation on the local server. Required features were added automatically.



Once installation completed, the server was promoted to a domain controller. During this process, a new forest was created using a fictional company domain name to simulate an enterprise environment. DNS integration was enabled by default, and the server was restarted to complete the promotion.



Steps Performed
Opened Server Manager

Selected Manage → Add Roles and Features

Installed Active Directory Domain Services

Promoted the server to a domain controller

Created a new forest using a fictional domain name

Set the DSRM password

Restarted the server after promotion

Organizational Units and User Creation


Organizational Units (OUs) were created to logically separate employee accounts and workstation objects. This structure supports clearer administration and allows targeted Group Policy enforcement.



Domain user accounts were created to represent fictional employees as part of a simulated onboarding process. These accounts were configured as standard users without administrative privileges.



<sub><b>Steps Performed</b></sub>
Opened Active Directory Users and Computers

Created Organizational Units for employees and workstations

Created domain user accounts for fictional employees

Verified users were members of Domain Users only

# Network Configuration

The network for this lab was designed to separate external internet access from internal domain communication, similar to how a small enterprise environment is structured. Each virtual machine was configured with two network adapters: one for basic internet connectivity and one for a private internal network. Static IPv4 addressing was used on the internal LAN to ensure reliable communication between systems, including domain authentication and backup traffic. Windows Defender Firewall and network profile settings were adjusted to allow secure internal communication while minimizing unnecessary exposure

Steps Performed
Configured two network adapters on each virtual machine

NAT for internet connectivity

Host-only adapter for internal LAN communication

Assigned static IPv4 addresses on the internal network

Address range: 192.168.100.x

Consistent subnet mask across all systems

Set the domain controller as the primary DNS server for the internal network

Changed the internal network connection profile to Private to allow domain traffic:

Set-NetConnectionProfile -InterfaceAlias "Ethernet1" -NetworkCategory Private
Adjusted Windows Defender Firewall to permit required inbound IPv4 communication on the private network

Verified connectivity and domain communication using ping tests and successful domain joins



Domain Join and Verification


Each employee workstation was joined to the domain using domain administrator credentials. After joining the domain, systems were restarted and tested to ensure proper authentication and profile creation.



Successful login using domain credentials confirmed that domain services were functioning correctly.



Steps Performed
Logged into each workstation using a local account

Verified DNS pointed to the domain controller

Joined the workstation to the domain

Restarted the workstation

Logged in using domain user credentials to verify functionality

Validation


The domain configuration was validated by confirming successful authentication, proper workstation registration in Active Directory, and the ability to apply Group Policy Objects.



This setup enabled centralized control, enforced user restrictions, and supported realistic testing of security policies and recovery workflows.
