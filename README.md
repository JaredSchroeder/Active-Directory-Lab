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

### Windows Server 2022 Installation and Configuring AD DS
- Installed Windows Server 2022 on a VM.
- Configured static IP addressing. I used the loopback address of 127.0.0.1 as the preferred DNS server as our Domain Controller will also be acting as a DNS server.
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
