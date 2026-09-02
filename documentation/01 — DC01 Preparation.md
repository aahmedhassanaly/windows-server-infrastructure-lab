## TASK 01 — DC01 Preparation

### Objective

Prepare the first Windows Server in the lab as the foundation for the Windows infrastructure environment and install the Active Directory Domain Services (AD DS) role.

### Environment

| Item             | Configuration       |
| ---------------- | ------------------- |
| Server Name      | DC01                |
| Operating System | Windows Server 2022 |
| Platform         | AWS EC2             |
| Private IP       | 10.10.10.33         |
| Subnet           | 10.10.10.0/26       |
| Gateway          | 10.10.10.1          |
| Initial DNS      | 10.10.10.2          |

### Implementation

The following preparation steps were completed:

1. Created the Windows Server 2022 instance.
2. Verified the server hostname as `DC01`.
3. Verified the server's private IP configuration.
4. Verified the default gateway.
5. Verified the initial DNS configuration.
6. Installed the **Active Directory Domain Services (AD DS)** role.
7. Installed the required AD DS management tools.
8. Verified the successful installation of the AD DS role.

### Verification

The server was verified successfully with:

* Hostname: `DC01`
* Private IP: `10.10.10.33`
* Gateway: `10.10.10.1`
* AD DS: Installed
* AD DS Management Tools: Installed

At the end of this task, DC01 was prepared for Domain Controller promotion.

### Troubleshooting

No major troubleshooting issue was encountered during the AD DS role installation.

The installation completed successfully.

### Evidence

The following screenshot will be used as evidence for this task:

<img width="1909" height="1016" alt="image" src="https://github.com/user-attachments/assets/74ce8a40-5615-4174-a982-0549223cedb3" />


The screenshot demonstrates that the **Active Directory Domain Services** role has been successfully installed on DC01.

### Result

DC01 is successfully prepared for the next stage of the lab.

### Next Task

**TASK 02 — Promote DC01 to Domain Controller**
