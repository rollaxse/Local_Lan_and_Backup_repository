# GPO Settings 
1. Confirmed the employee workstation was successfully joined to the domain before applying any policies.

2. Created a new Group Policy Object (GPO) in Group Policy Management.

3. Linked the GPO to the appropriate Employees OU to ensure it applied only to employee users.

 4. Edited the GPO and configured restrictions under:

User Configuration
→ Policies
→ Administrative Templates
→ System
Enabled Prevent access to the command prompt

Enabled Prevent access to registry editing tools

Enabled Remove Run menu from Start Menu

5. Blocked Senitive Apps Using Dont Run specified Windows Applications
User Configuration
→ Policies
→ Administrative Templates
→ System
→ Don't run specified Windows applications
6.  Force A group Policy Refresh
gpupdate /force

7. Tested a confirmed that gpo applied
