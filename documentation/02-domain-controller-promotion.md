# TASK 02 — Domain Controller Promotion

## Objective

Promote DC01 to a Domain Controller and create the Active Directory domain.

## Environment

| Item             | Value               |
| ---------------- | ------------------- |
| Server           | DC01                |
| Operating System | Windows Server 2022 |
| Domain           | corp.contoso.local  |
| NetBIOS Name     | CORP                |

## What I Did

1. Opened **Server Manager**.
2. Selected **Promote this server to a domain controller**.
3. Selected **Add a new forest**.
4. Created the domain:

```text
corp.contoso.local
```

5. Enabled **DNS Server**.
6. Enabled **Global Catalog**.
7. Disabled **Read-Only Domain Controller (RODC)**.
8. Set the **DSRM password**.
9. Checked the prerequisites.
10. Started the installation.
11. DC01 restarted after the installation.

## Verification

After the restart, I checked:

* **Active Directory Users and Computers**
* **DNS Manager**
* The domain `corp.contoso.local`
* DC01 as the Domain Controller

The domain was available and DC01 was working as a Domain Controller.

## Troubleshooting

No major problem occurred during this task.

The Domain Controller promotion completed successfully.

## Result

DC01 is now the first Domain Controller in the `corp.contoso.local` domain.

The server is ready for the next Active Directory configuration tasks.
<img width="1913" height="1058" alt="image" src="https://github.com/user-attachments/assets/49722c25-e422-4e1f-9432-883759fe6150" />


## Next Task

**TASK 03 — Active Directory and DNS Verification**
