# Windows Server Infrastructure Lab

* Active Directory
* DNS
* DHCP
* Group Policy
* File Server
* NTFS and SMB permissions
* Access-Based Enumeration
* DFS Namespace
* Basic troubleshooting

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/46a1c150-af91-4ca6-a8f0-023a2a674c15" />

---

## Business Scenario

The company has five departments:

* IT
* HR
* Finance
* Sales
* Management

The environment provides centralized user management, network services, Group Policy, and department file shares.

---

## Environment

| System   | Role                        |  IP Address |
| -------- | --------------------------- | ----------: |
| DC01     | AD DS / DNS / DHCP          | 10.10.10.33 |
| FS01     | File Server / DFS Namespace | 10.10.10.28 |
| CLIENT01 | Domain-joined test system   | 10.10.10.50 |

### Domain

```
Domain: corp.contoso.local
NetBIOS: CORP
```

### Network

```
VPC: 10.10.10.0/24
Subnet: 10.10.10.0/26
Gateway: 10.10.10.1
```

> CLIENT01 uses a Windows Server image and was used as a test system for domain, DNS, GPO, and file access.

---

# Tasks Completed

## TASK 01 — DC01 Preparation

Configured DC01 as the main Windows Server.

Implemented:

* Windows Server
* AD DS
* Domain Controller
* DNS
* Global Catalog
* Basic service verification

---

## TASK 02 — Active Directory

Implemented:

* Domain users
* Security groups
* Organizational Units
* Department structure
* Domain computer management
* Domain joining

Example groups:

```
GG-IT
GG-HR
GG-Finance
GG-Sales
GG-Management
```

---

## TASK 03 — DNS

Implemented and tested:

* Forward lookup zone
* Reverse lookup zone
* A records
* PTR records
* DNS forwarding
* `nslookup`
* SRV record verification

---

## TASK 04 — DHCP

Configured:

* DHCP scope
* Address exclusions
* DHCP options
* DNS server
* Default gateway
* Domain name
* Lease management

Example:

```
Range: 10.10.10.40 - 10.10.10.60
DNS:   10.10.10.33
GW:    10.10.10.1
```

---

## TASK 05 — Group Policy

Implemented and tested:

* GPO creation
* GPO linking
* Desktop policy
* Account lockout policy
* Drive mapping
* GPO verification
* `gpupdate`
* `gpresult`

Example:

```
GPO-IT-Desktop
```

---

## TASK 06 — File Server & Permissions

Configured FS01 as a Windows File Server.

Department shares:

```
IT
HR
Finance
Sales
Management
```

Implemented:

* SMB shares
* NTFS permissions
* Share permissions
* Group-based access
* Access-Based Enumeration
* DFS Namespace

DFS Namespace:

```
\\corp.contoso.local\Shares
```

Access was tested from CLIENT01 using domain users.

Example:

```
Test-Path \\FS01\IT
Test-Path \\FS01\HR
```

---

# Troubleshooting

Troubleshooting was performed during the lab for areas such as:

* DNS
* Domain connectivity
* Group Policy
* SMB access
* NTFS permissions
* Share permissions
* Windows services

The troubleshooting method used was:

```
Problem
   ↓
Evidence
   ↓
Test
   ↓
Fix
   ↓
Verify
```

---

# Security

The lab demonstrates basic security practices:

* Group-based permissions
* Least-privilege access
* NTFS permissions
* SMB permissions
* Domain authentication
* Controlled network access

---

# Technologies Used

| Technology       | Purpose                    |
| ---------------- | -------------------------- |
| Windows Server   | Server infrastructure      |
| Active Directory | User and domain management |
| DNS              | Name resolution            |
| DHCP             | Network configuration      |
| Group Policy     | Centralized configuration  |
| SMB              | File sharing               |
| NTFS             | File permissions           |
| DFS Namespace    | File namespace             |
| PowerShell       | Administration             |
| AWS EC2          | Lab hosting                |

---

# Project Structure

```
windows-server-infrastructure-lab/
│
├── README.md
│
└── documentation/
    ├── 01-DC01 Preparation.md
    ├── 02-domain-controller-promotion.md
    ├── 03-active-directory.md
    ├── 04-dns.md
    ├── 05-dhcp.md
    ├── 06-group-policy.md
    └── 07-file-server-permissions-medium.md
```

---

# Project Result

The project demonstrates a small Windows domain environment with:

```
Active Directory
      +
DNS
      +
DHCP
      +
Group Policy
      +
File Server
      +
Permissions
      +
DFS Namespace
```

The main focus is practical administration, verification, troubleshooting, and documentation.
