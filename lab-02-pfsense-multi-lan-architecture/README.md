# Lab 02: pfSense Multi-LAN Network Architecture

## Objective
Design and implement a segmented network architecture using pfSense to separate
internal systems from an attack network, supporting secure monitoring and detection
activities in a SOC-style lab environment.

## Environment
- VirtualBox
- pfSense
- Windows 11
- Windows Server (Active Directory Domain Controller)
- Kali Linux
- Metasploitable 2

## Network Design
The lab uses multiple LANs to enforce separation of trust zones.

- Internal LAN (Production): `10.0.1.0/24`
  - Windows 11 endpoint
  - Windows Server (Domain Controller)
  - Metasploitable 2

- Attack LAN: `10.0.3.0/24`
  - Kali Linux

pfSense is positioned as the routing and firewall device between all networks.

## IP Addressing
- Internal LAN DHCP range: `10.0.1.11 – 10.0.1.245`
- Attack LAN DHCP range: `10.0.3.11 – 10.0.3.245`

IP addresses were dynamically assigned and validated for all hosts.

## pfSense Configuration
- Configured multiple LAN interfaces
- Enabled DHCP services for each LAN
- Defined default routing via pfSense
- Ensured network isolation between internal and attack networks

Firewall rules were kept minimal at this stage to support controlled testing in later labs.

## Validation
- All VMs successfully obtained IP addresses from the correct LAN
- Internal hosts communicated through pfSense as expected
- Kali Linux was isolated to the attack LAN
- No direct host-to-host bridging occurred outside pfSense

## Outcome
A stable and segmented network architecture was successfully deployed, forming the
foundation for Active Directory services, endpoint logging, and future attack detection.

## Blue Team Takeaway
Network segmentation is critical for visibility and containment.
By isolating attack infrastructure from production systems, this design enables
realistic attack simulation while preserving controlled monitoring conditions.
