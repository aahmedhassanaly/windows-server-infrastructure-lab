# Windows Server Infrastructure Administration Lab

## Project Overview

This project is a practical Windows Server infrastructure lab designed to demonstrate real-world junior System Administrator and Infrastructure skills.

The lab focuses on building, configuring, securing, troubleshooting, and documenting a small company Windows environment.

The main goal is not to collect certifications or complete courses. The goal is to demonstrate practical administration skills through realistic implementation, verification, troubleshooting, and documentation.

AWS is used only as the hosting platform for the lab environment. The primary focus of the project is Windows Server infrastructure administration.

---

## Business Scenario

A small company requires a centralized Windows infrastructure environment for several departments:

* IT
* HR
* Finance
* Sales
* Management

The environment requires centralized identity management, DNS, DHCP, Group Policy, file sharing, access control, backup, and recovery.

The lab simulates the responsibilities of a Junior Windows/System Administrator managing this environment.

---

## Project Objectives

The project is designed to demonstrate practical experience with:

* Windows Server administration
* Active Directory Domain Services (AD DS)
* Domain Controllers
* Organizational Units (OUs)
* Users and Security Groups
* DNS
* DHCP
* Group Policy
* File Server administration
* NTFS and Share permissions
* PowerShell administration
* Windows troubleshooting
* Backup and restore using Veeam
* Basic Windows infrastructure security
* Technical documentation

---

## Architecture

The lab uses a small, realistic infrastructure consisting of:

| Server   | Role                      | IP Address  |
| -------- | ------------------------- | ----------- |
| DC01     | AD DS / DNS / DHCP        | 10.10.10.33 |
| FS01     | File Server               | 10.10.10.20 |
| VEEAM01  | Veeam Backup & Repository | 10.10.10.30 |
| CLIENT01 | Windows Client            | DHCP        |

### Domain

```text
Domain: corp.contoso.local
NetBIOS: CORP
```

### Network

```text
VPC: 10.10.10.0/24
Subnet: 10.10.10.0/26
Gateway: 10.10.10.1
```

---

## Infrastructure Components

### DC01

DC01 provides the core Windows infrastructure services:

* Active Directory Domain Services
* DNS
* DHCP
* Domain authentication
* Centralized identity management

### FS01

FS01 provides:

* Departmental file shares
* NTFS permissions
* Share permissions
* Group-based access control

### CLIENT01

CLIENT01 is used to test:

* Domain joining
* DNS resolution
* DHCP
* Group Policy
* User authentication
* File share access
* Permissions

### VEEAM01

VEEAM01 provides:

* Backup configuration
* Backup jobs
* Backup verification
* Restore testing

---

## Active Directory Structure

The domain will use an organized OU structure for users, groups, computers, and servers.

Planned departments:

```text
corp.contoso.local
│
├── Users
│   ├── IT
│   ├── HR
│   ├── Finance
│   ├── Sales
│   └── Management
│
├── Groups
│
├── Computers
│
└── Servers
```

---

## DNS

The DNS environment will demonstrate:

* Forward lookup
* Reverse lookup
* A records
* PTR records
* DNS forwarding
* Name resolution testing
* `nslookup`
* DNS troubleshooting

---

## DHCP

The DHCP environment will demonstrate:

* DHCP scope
* Address exclusions
* Reservations
* DHCP options
* DNS integration
* Lease management
* Client troubleshooting

---

## Group Policy

The lab will demonstrate practical Group Policy administration including:

* GPO creation
* GPO linking
* Password policies
* Account lockout policies
* Security policies
* User and computer policies
* Drive mapping
* Basic desktop/logon policies
* Security filtering
* GPO inheritance and precedence
* `gpupdate`
* `gpresult`
* GPO troubleshooting

---

## File Server

Departmental file shares will be created for:

* IT
* HR
* Finance
* Management

Access will be controlled using security groups and appropriate NTFS and Share permissions.

The project will specifically demonstrate the difference between:

```text
Share Permissions
        +
NTFS Permissions
        =
Effective Access
```

---

## PowerShell & Windows Administration

PowerShell will be used where it provides practical administrative value.

Examples include:

* User administration
* Group administration
* Service management
* Network verification
* Windows administration
* Troubleshooting
* System information gathering

---

## Backup & Recovery

Veeam will be used to demonstrate a realistic backup and recovery workflow.

The process will include:

1. Configure backup infrastructure
2. Create backup jobs
3. Run backups
4. Verify backup status
5. Introduce a controlled data-loss scenario
6. Restore the required data
7. Verify the restored data

The goal is to demonstrate that a backup is useful only when the restore process is actually tested.

---

## Troubleshooting

Troubleshooting is a major part of this project.

The lab will intentionally introduce realistic failures involving areas such as:

* DNS
* DHCP
* Active Directory
* Group Policy
* File permissions
* Network connectivity
* Backup and restore

The troubleshooting methodology used throughout the project is:

```text
Problem
   ↓
Evidence
   ↓
Hypothesis
   ↓
Test
   ↓
Fix
   ↓
Verify
   ↓
Document
```

---

## Security

The lab will demonstrate basic infrastructure security practices including:

* Least-privilege access
* Group-based permissions
* Secure administrative practices
* Controlled network access
* Appropriate file permissions
* Backup protection
* Avoiding unnecessary public exposure

---

## Project Structure

```text
windows-server-infrastructure-lab/
│
├── README.md
│
├── architecture/
│   ├── architecture.md
│   ├── network.md
│   └── ip-plan.md
│
├── active-directory/
│
├── dns/
│
├── dhcp/
│
├── group-policy/
│
├── file-server/
│
├── powershell/
│
├── troubleshooting/
│
├── veeam/
│
└── screenshots/
```

Each major task will contain its own documentation and evidence.

---

## Skills Demonstrated

The project will be evaluated based on practical ability rather than course completion.

| Skill                         | Status      |
| ----------------------------- | ----------- |
| Windows Server Administration | In Progress |
| Active Directory              | In Progress |
| DNS                           | Planned     |
| DHCP                          | Planned     |
| Group Policy                  | Planned     |
| File Server                   | Planned     |
| NTFS / Share Permissions      | Planned     |
| PowerShell                    | Planned     |
| Troubleshooting               | Planned     |
| Veeam Backup & Restore        | Planned     |

Final skill levels will be evaluated after completing the practical assessment.

---

## Project Approach

Every major task follows:

```text
Understand
   ↓
Configure
   ↓
Verify
   ↓
Troubleshoot
   ↓
Explain
   ↓
Document
   ↓
Demonstrate
```

The objective is to build skills that can be demonstrated during a technical interview and applied in a real IT environment.

---

## Scope

### Included

* Windows Server
* Active Directory
* DNS
* DHCP
* Group Policy
* File Server
* Permissions
* PowerShell
* Troubleshooting
* Veeam Backup & Restore

### Intentionally Excluded

The project does not focus on:

* Kubernetes
* Advanced DevOps
* Advanced cybersecurity
* Complex enterprise architecture
* Clustering / High Availability
* VMware integration
* Advanced cloud architecture
* Unnecessary enterprise technologies

The scope is intentionally limited to skills relevant to a junior Windows/System Administration role.

---

## Project Status

**Status:** In Progress

Current phase:

```text
Foundation → Active Directory
```

Current task:

```text
TASK 02 — Promote DC01 to Domain Controller
```

---

## Final Assessment

After completing the lab, a practical assessment will be performed covering:

* Active Directory
* DNS
* DHCP
* Group Policy
* File Server
* Permissions
* PowerShell
* Backup and Restore
* Troubleshooting

The final assessment will determine the actual skill level for each area using a 0–5 scale:

```text
0 — No knowledge
1 — Basic awareness
2 — Understand concepts
3 — Can implement
4 — Can troubleshoot
5 — Job-ready
```

The project will not be considered complete based only on successful configuration. The ability to troubleshoot, explain, verify, and document the environment is required.
