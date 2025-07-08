# Fortinet-Basic-Deployment
## This lab simulates a Fortinet firewall deployment in a multi-segment network environment. The architecture includes core components such as a Network Operations Center (NOC), Local Area Network (LAN), Demilitarized Zone (DMZ), and Wide Area Network (WAN), with access to the Internet through a NAT gateway. This topology is ideal for testing policies, routing, segmentation, and firewall security functions.
=================================
🌐 Network Segments & Components
## Segment Subnet  Devices Connectivity
NOC 192.168.1.0/24  MGMT PC Connected via eth1 to mgmt switch
LAN - VLAN 100  192.168.100.0/24    Admin PC    Connected via eth1 to SW_User on e0/1
LAN - VLAN 200  192.168.200.0/24    Marketing PC    Connected via eth1 to SW_User on e0/2
DMZ 192.168.201.0/24    Web Server  Connected via e0/1 to SW_DMZ
WAN 171.1.1.0/24    Fortinet Firewall   Connected via port1 (WAN interface)
NAT Gateway 100.1.1.0/24    NAT Device  Connected to Internet
=================================
🔐 Fortinet Firewall Configuration Outline
1. Interface Setup
port1 → WAN (171.1.1.x)

port2 → LAN (SW_User, handling VLAN 100 & 200)

port4 → DMZ (SW_DMZ)

mgmt → Management access (192.168.1.x)

2. VLAN Creation
Create VLAN interfaces on port2:

VLAN 100: Admin

VLAN 200: Marketing

3. Policy Rules
LAN ➜ DMZ: Allow HTTP/HTTPS from Admin/Marketing to Web Server

LAN ➜ WAN: Allow internal access to external resources

DMZ ➜ WAN: Allow outbound traffic with restrictions

NOC ➜ All: Permit full access for management and testing

4. Security Profiles
Apply Antivirus, Web Filtering, and IPS profiles as appropriate.

Use SSL Inspection for outbound connections, if supported in lab.

5. NAT & Routing
Configure NAT on outbound policies from LAN and DMZ to WAN.

Setup static routes for Internet access through NAT Gateway.
====================================
🧪 Lab Use Cases
✅ Validate inter-VLAN routing and segmentation

✅ Simulate DMZ services and expose public-facing web server

✅ Test NAT and firewall policies under various access conditions

✅ Implement and assess security profiles in controlled scenarios



