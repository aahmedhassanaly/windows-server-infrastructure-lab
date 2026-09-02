# TASK 03 — Active Directory

## Objective

Build and verify the Active Directory structure for the lab company, including organizational units, users, security groups, computer accounts, and domain membership.

## Environment

- Domain: `corp.contoso.local`
- NetBIOS name: `CORP`
- Domain Controller: `DC01`
- Client/Test machine: `CLIENT-1`
- AD DNS server: `10.10.10.33`

## What I Did

1. Created the main organizational units:
   - `Corp Users`
   - `Corp Computers`
   - `Groups`
   - `Servers`
   - 
<img width="935" height="664" alt="image" src="https://github.com/user-attachments/assets/06bc0612-535e-4353-bf95-4f6e63d66d0a" />

2. Created department OUs under `Corp Users`:
   - `IT`
   - `HR`
   - `Finance`
   - `Sales`
   - `Management`
   - 
<img width="932" height="599" alt="image" src="https://github.com/user-attachments/assets/105f31b1-030e-43fd-9929-793a12fa9630" />

3. Created domain users:
   - `ahmed.it`
   - `mohamed.it`
   - `sara.hr`
   - `omar.hr`
   - `ali.finance`
   - `mona.finance`
   - `khaled.sales`
   - `nada.sales`
   - `manager`
<img width="846" height="597" alt="image" src="https://github.com/user-attachments/assets/fdc30e79-400b-49da-9e3e-cefc2ce9bd3a" />

4. Created security groups:
   - `GG-IT`
   - `GG-HR`
   - `GG-Finance`
   - `GG-Sales`
   - `GG-Management`
<img width="1044" height="758" alt="image" src="https://github.com/user-attachments/assets/a5445b58-1476-48bd-92d1-09a94001a0c3" />

5. Added users to their department security groups.

6. Created and verified the `CLIENT-1` computer account.

7. Joined `CLIENT-1` to the `corp.contoso.local` domain.

8. Verified domain authentication using the `ahmed.it` account.
<img width="1189" height="888" alt="image" src="https://github.com/user-attachments/assets/fbccbb41-f4c7-460d-b590-b4a9626d4377" />



10. Verified that `ahmed.it` is a member of `CORP\GG-IT` using:

<img width="1090" height="810" alt="image" src="https://github.com/user-attachments/assets/ca23cf04-45e0-4a2d-a06c-1be62c080b8a" />


```cmd
whoami /groups

