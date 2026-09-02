# TASK 06 — Group Policy

## Objective

Configure and verify Group Policy in the `corp.contoso.local` domain.

The goal of this task was to practice:

- Creating and linking a GPO
- Applying user-based policies
- Configuring account lockout settings
- Mapping a network drive
- Verifying Group Policy application
- Basic Group Policy troubleshooting

---

## Environment

| Component | Details |
|---|---|
| Domain Controller | DC01 |
| Domain | corp.contoso.local |
| Test User | `CORP\ahmed.it` |
| User OU | `Corp Users\IT` |
| GPO | `GPO-IT-Desktop` |
| Test Machine | CLIENT-1 |

---

## 1. Created the GPO

I created a new Group Policy Object named:

```text
GPO-IT-Desktop
```

The GPO was linked to:

```text
Corp Users\IT
```

This allows the policy to apply to users located in the IT organizational unit.

---
<img width="938" height="658" alt="image" src="https://github.com/user-attachments/assets/f177a093-ee2d-4e75-9f99-99e6572e6162" />


## 2. Configured Desktop Policy

I configured a user desktop policy inside:

```text
User Configuration
→ Policies
→ Administrative Templates
→ Desktop
```

The policy was used to control the desktop environment for IT users.

---

## 3. Verified GPO Application

I logged in to CLIENT-1 using the domain account:

```text
CORP\ahmed.it
```

Then I checked the applied Group Policy Objects using:

```powershell
gpresult /r
```

The result showed:

```text
Applied Group Policy Objects
    GPO-IT-Desktop
```
<img width="988" height="731" alt="image" src="https://github.com/user-attachments/assets/09ed925f-f83a-43ab-8e75-23dc490f75d5" />

This confirmed that `GPO-IT-Desktop` was applied to the user.

The policy was applied from:

```text
DC01.corp.contoso.local
```

---

## 4. Account Lockout Policy

I configured the following account lockout settings:

| Setting | Value |
|---|---:|
| Account lockout threshold | 5 invalid attempts |
| Account lockout duration | 15 minutes |
| Reset account lockout counter after | 15 minutes |

The settings were configured under:

```text
Computer Configuration
→ Policies
→ Windows Settings
→ Security Settings
→ Account Policies
→ Account Lockout Policy
```

The configuration was completed successfully.

> Note: The Computer-side application of these settings was not separately verified with `gpresult /scope computer`.

---
<img width="1549" height="654" alt="image" src="https://github.com/user-attachments/assets/e20ec36d-41c9-47f1-9475-8c0468bb3d48" />

## 5. Drive Mapping

I configured a network drive mapping through Group Policy.

The purpose of the drive mapping is to provide IT users with access to the IT department file share.

The planned file server path is:

```text
\\FS01\IT
```

The actual file share will be configured in:

**TASK 06 — File Server & Permissions**

The drive mapping was configured as part of the Group Policy task.

---<img width="1384" height="682" alt="image" src="https://github.com/user-attachments/assets/1ab95a40-ab4e-4fd6-9c11-f39c19652873" />
<img width="1423" height="652" alt="image" src="https://github.com/user-attachments/assets/0b8aec28-5095-4d4b-a9c0-f148a495d023" />


## 6. Group Policy Verification

The following commands were used during the task.

To force a Group Policy update:


```powershell
gpupdate /force
```

To display the applied Group Policy Objects:

```powershell
gpresult /r
```

To generate a detailed HTML report:

```powershell
gpresult /h C:\Users\ahmed.it\Desktop\gpresult.html /f
```

These commands are useful for verifying whether a GPO was received and applied.

---

