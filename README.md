# Active Directory Azure Lab

Azure-based Active Directory lab using Windows Server 2022. Covers Domain Controller setup, OUs, user creation, Group Policy, password resets, account disabling and deletion. Includes Microsoft Entra ID user and group management, directory role assignment, and Microsoft 365 Admin Center exploration.

## Software Used

- Microsoft Azure
- Windows Server 2022
- Active Directory Domain Services (AD DS)
- Group Policy Management
- Microsoft Entra ID
- Microsoft 365 Admin Center
- PowerShell

## Environments Used

- Windows Server 2022
- Azure Virtual Machine

## Lab Walkthrough

### Part 1: Azure VM Setup
1. A Windows Server 2022 virtual machine was provisioned on Microsoft Azure to serve as the Domain Controller for this lab.

![VM Overview](images/vm-overview.png)

2. A static private IP address of 10.0.4 was assigned to the network interface to ensure the Domain Controller always uses the same address on the network.

![Static IP](images/static-ip.png)

3. The virtual machine was accessed via Remote Desktop Protocol (RDP). Server Manager launched automatically on login confirming the server is live and ready for configuration.

![RDP Connection](images/rdp-connection.png)
### Part 2: Installing Active Directory
1. The Active Directory Domain Services role was added through Server Manager to enable the server to function as a Domain Controller.

![AD DS Role](images/adds-role.png)

2. The server was promoted to a Domain Controller and a new forest was created with the root domain name helpdesk.local.

![Domain Controller Promotion](images/dc-promotion.png)

3. Active Directory Users and Computers was opened from Server Manager confirming the domain helpdesk.local is installed and ready for configuration.

![ADUC](images/aduc-domain.png)
### Part 3: Organizational Units and Users
1. Organizational Units were created to mirror a real company structure, separating users by department and providing a dedicated location for disabled accounts.

![Organizational Units](images/organizational-units.png)

2. Test users were created across each Organizational Unit (HR, IT, Finance) to simulate a real company environment with employees across multiple departments.

![New User](images/new-user.png)
### Part 4: Help Desk Tasks

### Part 5: Group Policy

### Part 6: Entra ID

## Challenges and Takeaways
