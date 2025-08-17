<h1>Active Directory Lab</h1>

 ### [YouTube Demonstration](https://youtu.be/7eJexJVCqJo)

<h2>Overview</h2>
I designed and deployed a simulated small business IT environment using Windows Server 2022 and Windows 11 Enterprise. This project demonstrates my ability to configure and administer Active Directory Domain Services, manage users, groups, and organizational units (OUs), and apply Group Policy Objects (GPOs) for centralized security and configuration management.
<br />


<h2>Objectives</h2>

- <b>Deploy an Active Directory domain controller.</b> 
- <b>Simulate a small business organizational structure.</b>
- <b>Create and manage users, groups, and organizational units (OUs).</b>
- <b>Configure and apply Group Policy Objects (GPOs).</b>
- <b>Verify policy enforcement on a domain-joined client machine.</b>

<h2>Lab Environment</h2>

- <b>Hypervisor:</b> VirtualBox
- <b>Server OS:</b> Windows Server 2022 (Domain Controller)
- <b>Client OS:</b> Windows 11 Enterprise (Domain-joined workstation)

<p align="center">
<img src="https://i.imgur.com/DemjhgT.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>

<h2>Implementation</h2>

### Step 1 – Install Windows Server 2022 and Configure AD DS
- Installed Windows Server 2022 on a VM.
- Configured static IP addressing.
- Installed Active Directory Domain Services (AD DS) via Server Manager.
- Promoted server to a Domain Controller with domain name: LAB.local.

<img src="https://i.imgur.com/IXy4VjK.png"/>

### Step 2 – Create Organizational Units (OUs)
- Designed OUs to reflect a small company structure:
  - IT Department
  - HR Department
  - Sales Department
- Created sub-OUs for Users and Computers within each department.

<img src="https://i.imgur.com/8BrAlOw.png"/>

### Step 3 – Add Users and Groups
- Created sample users: jschroeder, jthomas, ebrown.
- Assigned users to security groups (e.g., Sales, IT Admins).
- Configured user properties (passwords, logon restrictions, etc.).

### Step 4 – Configure Group Policy Objects (GPOs)
- Created and linked GPOs for different OUs:
  - Password Policy: Minimum length, complexity, expiration.
  - Desktop Restrictions: Disable Control Panel for non-admins.
  - Login Banner: Display security/legal disclaimer at login.
  - Software Installation Policy: Automatic deployment of test software.

### Step 5 – Join Windows 11 Client to the Domain
- Installed Windows 11 Enterprise on VM.
- Joined workstation WS01 to LAB.local.
- Logged in using domain accounts.

### Step 6 – Test Group Policy Application
- Logged into Windows 11 with user accounts.
- Verified policies:
  - Login banner displayed.
  - Password rules enforced.
  - Control Panel disabled for HR and Sales OUs.

<h2>Conclusion</h2>
This project successfully simulated a small business Active Directory environment with centralized authentication, authorization, and policy enforcement. It demonstrates practical skills in Windows Server administration, domain management, and enterprise-level IT support.
<br />


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
