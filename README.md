<h1>Active Directory Lab</h1>



<h2>Overview</h2>
I designed and deployed a simulated small company environment using Windows Server 2022 and Windows 11 Enterprise. This project demonstrates my ability to configure and administer Active Directory Domain Services, manage and create users, groups, and organizational units (OUs), and apply Group Policy Objects (GPOs) for enhanced security and policy enforcement.
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
<img src="https://i.imgur.com/K0eml58.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>

<h2>Implementation</h2>

### Windows Server 2022 Installation and Configuring AD DS
- Installed Windows Server 2022 on a VM.
- Configured static IP addressing.
- Set the loopback IP address of 127.0.0.1 as the preferred DNS server, since the Domain Controller also functions as a DNS server.
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
- Created and linked GPOs to different OUs using the Group Policy Management Editor:
   - Login Banner: Display security/legal disclaimer at login.
 <p align="center">
<img src="https://i.imgur.com/JspWT4l.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />

  - Password Policy: Minimum length, complexity, expiration.
    - Moved the new password policy GPO to be higher in link order than the default domain policy to override the default password policy.

<p align="center">
<img src="https://i.imgur.com/D2eoW0C.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />

  - Desktop Restrictions: Disable Control Panel for non-admins.
    - Denied the "Apply group policy" setting for domain and enterprise admins to ensure administrators can still access the control panel.
<p align="center">
<img src="https://i.imgur.com/RrMZjdi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />

### Joining Windows 11 Client to the Domain
- Installed Windows 11 Enterprise on a VM.
- Joined workstation WS01 to LAB.local.

<p align="center">
<img src="https://i.imgur.com/9qkfrF7.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />

- Logged in using domain account jschroeder.
<br />

<h2>Verifying Group Policy Application</h2>

- Logged into Windows 11 with user accounts.
- Verified policies:
  - Login banner displayed:

 <p align="center">
<img src="https://i.imgur.com/XRi218z.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />

  - Password rules enforced.
  - This message appears when attempting to create a new password that doesn't meet policy standards:

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

<h2>Skills Demonstrated</h2>

- <b>Hypervisor setup with VirtualBox.<b>
- <b>Windows OS installation.<b>
- <b>Active Directory Domain Services (AD DS) installation and configuration.<b>
- <b>User, group, and OU creation and configuration.<b>
- <b>Group Policy Object (GPO) creation and enforcement.<b>
- <b>Documentation of processes.<b>
<br />

<h2>Conclusion</h2>

In this project I demonstrated practical hands-on experience in Active Directory deployment and configuration. I gained experience in user and group creation, account management, OU structuring, and GPO enforcement. These skills are highly relevant for any systems administration and IT/desktop support roles.
