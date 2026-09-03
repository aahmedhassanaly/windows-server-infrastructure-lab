TASK 07 — File Server & Permissions

Objective

Configure FS01 as a Windows File Server with department-based SMB shares and permissions.

Environment

Server: FS01

Domain: corp.contoso.local

IP: 10.10.10.28

Main folder: C:\Shares

Departments: IT, HR, Finance, Sales, Management

What I Did
<img width="1762" height="830" alt="image" src="https://github.com/user-attachments/assets/7b47ed14-832f-426c-a606-da64c2172c5b" />


Installed the File Server role.

Created department folders under C:\Shares.

Created SMB shares for all departments.
<img width="1839" height="965" alt="image" src="https://github.com/user-attachments/assets/a38032b6-f6fe-4d70-b9e0-d0abdc24cac5" />


Configured NTFS permissions using department security groups.

Configured Share Permissions.

Removed unnecessary Everyone and BUILTIN\Users access from the tested folders.

Enabled Access-Based Enumeration.

Permissions

IT

NTFS:
CORP\GG-IT → Modify
Administrators → Full Control
SYSTEM → Full Control

Share:
CORP\GG-IT → Change
Administrators → Full
<img width="985" height="610" alt="image" src="https://github.com/user-attachments/assets/751241c5-24d4-4c28-a4db-ab769b7b0440" /><img width="1054" height="692" alt="image" src="https://github.com/user-attachments/assets/d4d09920-ec7b-4113-8201-806bc66d5cec" />



HR

NTFS:
CORP\GG-HR → Modify
Administrators → Full Control
SYSTEM → Full Control

Share:
CORP\GG-HR → Change
Administrators → Full

Verification

Useful commands:

Get-SmbShare
Get-SmbShareAccess -Name IT
Get-Acl C:\Shares\HR
whoami /groups
Test-Path \\FS01\IT
Test-Path \\FS01\HR

Results:

CORP\GG-IT was present in Ahmed's logon token.

IT access was successful.
<img width="1737" height="864" alt="image" src="https://github.com/user-attachments/assets/b0ed8f98-16c2-4230-a0d6-ac14e1ba3a7a" />

HR access from the IT user was denied.
<img width="1604" height="807" alt="image" src="https://github.com/user-attachments/assets/60bed860-02ff-42ef-af86-9dc0aea6bdc5" />


Access-Based Enumeration was enabled on the department shares.

