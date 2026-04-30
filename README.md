# Active Directory Azure Lab

Azure-based Active Directory lab using Windows Server 2022. Covers Domain Controller setup, Organizational Units, user creation, Group Policy configuration, password resets, account disabling and deletion.

## Software Used

- Microsoft Azure
- Windows Server 2022
- Active Directory Domain Services (AD DS)
- Group Policy Management
- PowerShell

## Environments Used

- Windows Server 2022
- Azure Virtual Machine

## Lab Walkthrough

### Part 1: Azure VM Setup
- A Windows Server 2022 virtual machine was provisioned on Microsoft Azure to serve as the Domain Controller for this lab.

![VM Overview](images/vm-overview.png)

- A static private IP address of 10.0.4 was assigned to the network interface to ensure the Domain Controller always uses the same address on the network.

![Static IP](images/static-ip.png)

- The virtual machine was accessed via Remote Desktop Protocol (RDP). Server Manager launched automatically on login confirming the server is live and ready for configuration.

![RDP Connection](images/rdp-connection.png)
### Part 2: Installing Active Directory
- The Active Directory Domain Services role was added through Server Manager to enable the server to function as a Domain Controller.

![AD DS Role](images/adds-role.png)

- The server was promoted to a Domain Controller and a new forest was created with the root domain name helpdesk.local.

![Domain Controller Promotion](images/dc-promotion.png)

- Active Directory Users and Computers was opened from Server Manager confirming the domain helpdesk.local is installed and ready for configuration.

![ADUC](images/aduc-domain.png)
### Part 3: Organizational Units and Users
- Organizational Units (HR, IT , Finance) were created to mirror a real company structure, separating users by department and providing a dedicated location for disabled accounts.

![Organizational Units](images/organizational-units.png)

- Test users were created across each Organizational Unit (HR, IT, Finance) to simulate a real company environment with employees across multiple departments.

![New User](images/new-user.png)

- Users were added to their respective security groups to simulate real group membership management performed by help desk and IT administrators.

![Group Members](images/HR-SECURITY-GROUP.png)
![Group Members](images/IT-SECURITY-GROUP.png)

- Users were added to their respective security groups to simulate real group membership management performed by help desk and IT administrators.

![Group Members](images/HR-STAFF-MEMBERS.png)
![Group Members](images/IT-STAFF-MEMBERS.png)
### Part 4: Help Desk Tasks
   - Task 1 — Reset a Password
   - A password reset was performed on a user account, simulating one of the most common help desk tasks. The user was required to change their password on next login.

![Password Reset](images/password-reset.png)
![Password Reset](images/confirmation-for-password-change.png)

   - Task 2 — Disable a User Account
   - A user account was disabled to simulate an employee offboarding workflow. Disabling before deleting preserves audit logs and is standard IT practice.

![Disabled Account](images/disabled-account.png)
   - Task 3 — Unlock a Locked Out Account
   - A locked out user account was unlocked through the Account tab in Active Directory Users and Computers, simulating a common help desk request.

![Unlock Account](images/unlock-account.png)

   - Task 4 — Move a Disabled User to Disabled Accounts OU
   - The disabled user was moved to the Disabled Accounts Organizational Unit to keep the directory organized and clearly separate active from inactive accounts.

![Disabled Accounts OU](images/disabled-accounts-ou.png)
   - Task 5 — Delete a User
   - A user account was permanently deleted after being moved to the Disabled Accounts OU, following proper offboarding procedure before removal.

![Delete User](images/delete-user.png) 
### Part 5: Group Policy
- Open Group Policy Management
- Group Policy Management was opened from Server Manager to begin creating and linking Group Policy Objects to Organizational Units within the domain.

![Group Policy Management](images/gpo-console.png)

- Create a GPO for Account Lockout Policy
- An Account Lockout Policy was configured to lock user accounts after 5 failed login attempts, a standard security measure in enterprise environments.

![Account Lockout GPO](images/gpo-lockout.png)
### Part 6: Entra ID

## Challenges and Takeaways
