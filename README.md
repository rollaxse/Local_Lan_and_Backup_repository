# READ ME
<b>Overview</b>


This project simulates a small enterprise IT environment focused on user access control, backup management, and recovery validation. The lab environment consists of a domain-controlled employee workstation, a centralized backup server, and enforced security policies to reflect real-world IT support and incident response workflows. The primary objective was to restrict employee access during a suspected security incident and validate the ability to recover data from centralized backups.

<b>Project Scenario</b>


A fictional IT support ticket was submitted by an employee stating they were unable to access certain folders on their workstation. The issue was treated as a potential ransomware or unauthorized access incident. As part of the response, the employee account was restricted using Group Policy to prevent access to administrative tools, and backups were reviewed to ensure data could be restored if required.



This scenario mirrors common helpdesk and junior system administration responsibilities, including user account restriction, incident assessment, and recovery preparation.

<b>Restore & Validation</b>


Centralized backups of the employee workstation were created using Veeam and stored securely on a dedicated backup server. To validate the backup strategy, file-level restore testing was performed to confirm that employee data could be successfully recovered without granting the employee direct access to backup files.



The restore process confirmed that critical data could be restored quickly and reliably following a simulated security incident. This validation demonstrated the effectiveness of centralized backups, proper permission scoping, and recovery readiness within the environment.

<b>Outcome</b>


The lab successfully demonstrated a realistic enterprise-style backup and recovery workflow. Employee access was restricted using Group Policy, backups were securely stored on a separate server, and data restoration was validated without compromising security controls. This project highlights core IT skills related to access control, backup management, troubleshooting, and incident response.


