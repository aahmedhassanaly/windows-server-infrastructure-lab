# TASK 04 — DNS

## Objective

Configure and verify DNS services for the lab environment, including forward and reverse name resolution, DNS records, forwarding, and basic DNS troubleshooting.

## Environment

- Domain: `corp.contoso.local`
- DNS Server: `DC01`
- DNS Server IP: `10.10.10.33`
- Client/Test Machine: `CLIENT-1`

## What I Did

1. Verified that DNS is installed and running on `DC01`.

2. Verified the Active Directory forward lookup zone:
   - `corp.contoso.local`

3. Verified the `dc01` A record:
   - `dc01.corp.contoso.local`
   - `10.10.10.33`
<img width="1103" height="819" alt="image" src="https://github.com/user-attachments/assets/7fffab56-4536-486d-ac5b-003d30a6067d" />

4. Created a Reverse Lookup Zone:
   - `10.10.10.in-addr.arpa`

5. Created a PTR record:
   - `10.10.10.33`
   - `dc01.corp.contoso.local`
<img width="1093" height="788" alt="image" src="https://github.com/user-attachments/assets/98ddb9f2-b374-4aca-89eb-a5d86124066e" />

6. Tested forward DNS resolution from the client.

7. Tested reverse DNS resolution from the client.
<img width="654" height="431" alt="image" src="https://github.com/user-attachments/assets/14d7b450-7d28-4618-8d4f-1bba4236186d" />

8. Verified DNS forwarding for external names.

9. Used `nslookup` to verify DNS resolution and troubleshoot DNS problems.

## Forward DNS

Forward DNS resolves a hostname to an IP address.

Example:

```powershell
nslookup dc01.corp.contoso.local
