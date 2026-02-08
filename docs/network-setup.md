# Network Setup
To allow the virtual machines to communicate properly, each system was configured with two network adapters. The first adapter used NAT to provide internet access and was used for basic connectivity such as downloading updates and required software during setup.



The second network adapter connected each virtual machine to a private internal network. IPv4 settings were manually configured on this internal network, and static IP addresses in the 192.168.100.x range were assigned to ensure consistent communication between the domain controller, employee workstation, and backup server.



Windows Defender Firewall was adjusted to allow required inbound IPv4 traffic on the internal network so that domain services, file access, and backup operations could function correctly. The internal network connection was also set to Private, which enabled trusted communication and network discovery between systems while maintaining appropriate security settings.



This dual-network setup allowed internet access through NAT while keeping internal traffic isolated on a private LAN, following basic networking and security practices commonly used in small office environments.
