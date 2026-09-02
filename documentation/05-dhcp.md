TASK 05 — DHCP

Objective

Configure and verify the Windows DHCP Server for the lab environment.

The task covers DHCP installation, scope configuration, exclusions, reservations, scope options, leases, and basic troubleshooting.

Environment

Domain: corp.contoso.local

DHCP Server: DC01

DC01 IP: 10.10.10.33

Network: 10.10.10.0/26

Gateway: 10.10.10.1

DNS Server: 10.10.10.33

What I Did

Installed the DHCP Server role on DC01.

Authorized the DHCP Server in Active Directory.

Created an IPv4 DHCP scope:

Scope Name: Corp-LAN
Start IP:   10.10.10.40
End IP:     10.10.10.60
Subnet:     255.255.255.192 (/26)

Activated the DHCP scope.
<img width="1086" height="633" alt="image" src="https://github.com/user-attachments/assets/c267d36f-74e3-49d3-8078-f053084ee70f" />


Configured DHCP Scope Options:

003 Router
10.10.10.1

006 DNS Servers
10.10.10.33

015 DNS Domain Name
corp.contoso.local
<img width="1094" height="697" alt="image" src="https://github.com/user-attachments/assets/3d308964-fad7-4617-9422-4a10b0a45f06" />

Created an exclusion range:

10.10.10.58 - 10.10.10.59

This range is reserved for future infrastructure or static devices.

Created a DHCP reservation for a client device.

Verified the DHCP address pool and address leases.
<img width="1108" height="641" alt="image" src="https://github.com/user-attachments/assets/12b0f9f1-593c-4233-b89c-f92c413606fd" />

Verified the DHCP scope configuration using PowerShell.

DHCP Verification

The DHCP scope was verified using:

Get-DhcpServerv4Scope

Scope:

10.10.10.40 - 10.10.10.60

The configured DHCP options were verified using:

Get-DhcpServerv4OptionValue -ScopeId 10.10.10.0

Final configuration:

Router          10.10.10.1
DNS Server      10.10.10.33
DNS Domain      corp.contoso.local
Lease Duration  8 days

DHCP Lease

An address lease was observed in the DHCP server:

10.10.10.55

<img width="1084" height="634" alt="image" src="https://github.com/user-attachments/assets/cb420aa6-6514-4af6-8420-7d6ec50ee8b7" />

Troubleshooting Approach

For a DHCP problem, I would follow:

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

Useful commands include:

ipconfig /all
ipconfig /release
ipconfig /renew

On the DHCP server:

Get-DhcpServerv4Scope

Get-DhcpServerv4OptionValue -ScopeId 10.10.10.0
<img width="1273" height="612" alt="image" src="https://github.com/user-attachments/assets/d69017ec-831b-49a6-9843-bed9d6918c79" />
