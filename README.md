<h1>Active Directory Lab</h1>



<h2>Overview</h2>
I designed and deployed a simulated small business IT environment using Windows Server 2022 and Windows 11 Enterprise. This project demonstrates my ability to configure and administer Active Directory Domain Services, manage and create users, groups, and organizational units (OUs), and apply Group Policy Objects (GPOs) for security and policy enforcement.
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

### Windows Server 2022 Installation and Configuring AD DS
- Installed Windows Server 2022 on a VM.
- Configured static IP addressing.
- Used the loopback address of 127.0.0.1 as the preferred DNS server as the Domain Controller will also be acting as a DNS server.
<p align="center">
<img src="https://i.imgur.com/IifnSmX.png" height="35%" width="35%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />

### 
- Installed Active Directory Domain Services (AD DS) via Server Manager.
<p align="center">
<img src="https://i.imgur.com/oJJmX1l.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />

###
- Promoted server to a Domain Controller with domain name: "LAB.local".
<p align="center">
<img src="https://i.imgur.com/DsKZl3K.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />

### Creating Organizational Units (OUs)
- Designed OUs to reflect a small company structure:
  - IT Department
  - HR Department
  - Sales Department
- Created sub-OUs for Users and Computers within each department.

<p align="center">
<img src="https://i.imgur.com/8BrAlOw.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />

### Adding Users and Groups
- Created sample users: jschroeder, jthomas, ebrown.
- Created security groups for each department and assigned users to them.

<p align="center">
<img src="https://i.imgur.com/9u2EHjP.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>


### Configuring Group Policy Objects (GPOs)
- Created and linked GPOs for different OUs using the Group Policy Management Editor:
  - Password Policy: Minimum length, complexity, expiration.
  - Moved the new password policy GPO to be higher in link order than the default domain policy to override the default password policy.

<p align="center">
<img src="https://i.imgur.com/D2eoW0C.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />

  - Desktop Restrictions: Disable Control Panel for non-admins.
    - Checkmarked "Deny" to "Apply group policy" for domain and enterprise admins to ensure administrators can still access the control panel
<p align="center">
<img src="https://i.imgur.com/RrMZjdi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
 
   - Login Banner: Display security/legal disclaimer at login.
 <p align="center">
<img src="https://i.imgur.com/JspWT4l.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />

### Joining Windows 11 Client to the Domain
- Installed Windows 11 Enterprise on VM.
- Joined workstation WS01 to LAB.local.

<p align="center">
<img src="https://i.imgur.com/9qkfrF7.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />

- Logged in using domain account jschroeder.
<br />

<h2>Verifying Group Policy Application</h2>

- Logged into Windows 11 with user accounts.
- Verified policies:
  - Login banner displayed.

 <p align="center">
<img src="https://i.imgur.com/XRi218z.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />

  - Password rules enforced.
  - This message appears when attempting to create a new password that doesn't meet policy standards.

 <p align="center">
<img src="https://i.imgur.com/dFueSqh.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />

  - Control Panel disabled for every non-admin user.
  -  This notification appears when a standard user attempts to open the control panel:

 <p align="center">
<img src="https://i.imgur.com/SoDUo99.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />

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
