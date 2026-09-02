# TASK 05 — Group Policy

## Objective

Configure and verify Group Policy in the `corp.contoso.local` domain.

The task covers GPO creation and linking, password and account lockout policies, basic security settings, drive mapping, logon and desktop settings, security filtering, inheritance and precedence, and GPO troubleshooting.

## Environment

- Domain: `corp.contoso.local`
- Domain Controller: `DC01`
- Client/Test Machine: `CLIENT-1`
- Domain Controller IP: `10.10.10.33`
- Client/Test Machine IP: `10.10.10.50`

## Planned GPO Work

The following Group Policy configuration will be implemented and verified during this task:

1. Create and link a GPO.
2. Configure a password policy.
3. Configure an account lockout policy.
4. Configure basic security settings.
5. Configure a drive mapping policy.
6. Configure a desktop or logon setting.
7. Test security filtering.
8. Review GPO inheritance and precedence.
9. Apply policy changes using `gpupdate`.
10. Verify applied policies using `gpresult` and Group Policy Management.

## Group Policy Structure

The GPOs will be linked to the appropriate organizational units in the domain.

The main OUs used in this lab are:

- `Corp Users`
- `IT`
- `HR`
- `Finance`
- `Sales`
- `Management`
- `Corp Computers`
- `Groups`
- `Servers`

## Verification Commands

The following commands will be used to verify Group Policy on the client:

```powershell
gpupdate /force
```

```powershell
gpresult /r
```

A Group Policy report can also be generated when required:

```powershell
gpresult /h C:\Temp\gpresult.html
```

## Troubleshooting Approach

For a Group Policy problem, I would follow:

```text
Problem
   ↓
Collect Evidence
   ↓
Check Client Domain Membership
   ↓
Check DNS
   ↓
Check OU Location
   ↓
Check GPO Link
   ↓
Check Security Filtering
   ↓
Check Inheritance and Precedence
   ↓
Run gpupdate
   ↓
Check gpresult
   ↓
Verify the Result
```

## Common Checks

When a GPO does not apply, I will check:

- The client is joined to `corp.contoso.local`.
- The client uses `DC01` as its DNS server.
- The user or computer is in the correct OU.
- The GPO is linked to the correct OU.
- The GPO is enabled.
- Security filtering allows the target user or computer to apply the policy.
- No higher-precedence GPO overrides the setting.
- The policy was refreshed using `gpupdate /force`.
- The applied policy was verified using `gpresult /r`.

## Result

TASK 05 is currently **in progress**.

The configuration and verification results will be added after the practical Group Policy tasks are completed.

## Next Step

Configure the first GPO and verify that it applies to the intended target.