# TASK 05 — DHCP

## Objective

Configure and verify the Windows DHCP Server for the lab environment.

The task covers DHCP installation, scope configuration, exclusions, reservations, scope options, leases, and basic troubleshooting.

## Environment

Domain: corp.contoso.local

DHCP Server: DC01

DC01 IP: 10.10.10.33

Network: 10.10.10.0/26

Gateway: 10.10.10.1

DNS Server: 10.10.10.33

## What I Did

Installed the DHCP Server role on DC01.

Authorized the DHCP Server in Active Directory.

Created an IPv4 DHCP scope:

Scope Name: Corp-LAN
Start IP:   10.10.10.40
End IP:     10.10.10.60
Subnet:     255.255.255.192 (/26)

Activated the DHCP scope.

Configured DHCP Scope Options:

003 Router
10.10.10.1

006 DNS Servers
10.10.10.33

015 DNS Domain Name
corp.contoso.local

Created an exclusion range:

10.10.10.58 - 10.10.10.59

This range is reserved for future infrastructure or static devices.

Created a DHCP reservation for a client device.

Verified the DHCP address pool and address leases.

Verified the DHCP scope configuration using PowerShell.

## DHCP Verification

The DHCP scope was verified using:

```powershell
Get-DhcpServerv4Scope
```

Scope:

```text
10.10.10.40 - 10.10.10.60
```

The configured DHCP options were verified using:

```powershell
Get-DhcpServerv4OptionValue -ScopeId 10.10.10.0
```

Final configuration:

```text
Router          10.10.10.1
DNS Server      10.10.10.33
DNS Domain      corp.contoso.local
Lease Duration  8 days
```

## DHCP Lease

An address lease was observed in the DHCP server:

```text
10.10.10.55
```

## AWS Environment Note

The lab is hosted on AWS.

The EC2 network interface receives its DHCP configuration from the AWS VPC DHCP service.

During testing, CLIENT-1 showed:

```text
DHCP Server: 10.10.10.1
```

This means the EC2 network interface was using the AWS DHCP service rather than the Windows DHCP server.

Therefore, the Windows DHCP configuration was verified on the server, but the EC2 network interface was not used as proof that Windows DHCP distributed the client IP.

This is an important limitation of the lab environment.

## Troubleshooting Approach

For a DHCP problem, I would follow:

```text
Problem
   ↓
Collect Evidence
   ↓
Check IP Configuration
   ↓
Check DHCP Server
   ↓
Check Scope
   ↓
Check Scope Options
   ↓
Check Leases
   ↓
Test Connectivity
   ↓
Verify the Result
```

Useful commands include:

```powershell
ipconfig /all
ipconfig /release
ipconfig /renew
```

On the DHCP server:

```powershell
Get-DhcpServerv4Scope
```

```powershell
Get-DhcpServerv4OptionValue -ScopeId 10.10.10.0
```

## Result

TASK 05 is complete at the practical configuration level.

Current DHCP skill level:

**3/5 — Can implement**

The lab verified:

- DHCP Server installation
- DHCP authorization
- Scope creation
- IP range configuration
- Scope activation
- Scope options
- DHCP exclusions
- DHCP reservations
- DHCP leases
- PowerShell verification
- Basic DHCP troubleshooting

## Next Task

TASK 06 — Group Policy
