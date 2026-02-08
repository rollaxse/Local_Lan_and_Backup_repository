# VirtualBox Setup
* The lab environment was built using Oracle VirtualBox as the virtualization platform. VirtualBox was downloaded and installed on the host system, and official Microsoft ISO images were used for all operating system installations.



<b>The following ISO files were used:</b>

`Win11_25H2_English_x64.iso` for the employee workstation

`SERVER_EVAL_x64FRE_en-us.iso` for the domain controller and backup server



* Each virtual machine was created using a manual setup process to better reflect a real-world deployment. During creation, the ISO file was mounted and set as the first boot device to allow the operating system installer to launch on initial startup.



During installation, the appropriate Windows editions were selected:

* Windows 11 Pro for the employee workstation

* Windows Server 2022 (Desktop Experience) for the domain controller and backup server



Each virtual machine was configured with two network adapters:

* One adapter attached to NAT, used for internet access during setup, updates, and software installation

* A second adapter configured as a host-only (private internal) network, used for internal communication between systems



This configuration allowed controlled internet access while keeping internal traffic isolated, supporting domain services, backup operations, and centralized management within the lab environment.
