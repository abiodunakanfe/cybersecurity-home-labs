# Cybersecurity Home Lab – SOC / Blue Team Focus

This repository documents my hands-on cybersecurity home lab designed to support
blue team and SOC-style monitoring, detection, and investigation activities.

The lab simulates an enterprise environment with network segmentation, Active Directory,
endpoint logging, and a dedicated attack network for controlled testing.

## Lab Architecture Overview
- Multi-LAN network segmented with pfSense
- Internal production network and isolated attack network
- Centralized endpoint telemetry using Sysmon and Splunk
- Windows Active Directory domain environment

## Network Segmentation
- Internal LAN: 10.0.1.0/24  
  Hosts Windows 11 endpoint, Windows Server (Domain Controller), and Metasploitable

- Attack LAN: 10.0.3.0/24  
  Hosts Kali Linux for attack simulation

pfSense enforces routing and traffic control between networks.

## Lab Environment
- VirtualBox
- pfSense
- Windows 11 (Endpoint with Sysmon + Splunk)
- Windows Server (Active Directory Domain Controller)
- Kali Linux
- Metasploitable 2

## Blue Team Skills Practiced
- Network segmentation and firewall architecture
- Active Directory administration and GPO management
- Endpoint telemetry collection with Sysmon
- Log ingestion and monitoring with Splunk
- Attack surface preparation for detection testing

## Labs
- [Lab 01: Virtualization Setup](lab-01-virtualization-setup/README.md)
- [Lab 02: pfSense Multi-LAN Network Architecture](lab-02-pfsense-multi-lan-architecture/README.md)
- [Lab 03: Windows Endpoint Logging with Sysmon and Splunk](lab-03-windows-endpoint-logging/README.md)
- [Lab 04: Active Directory Foundation and Policy Configuration](lab-04-active-directory-foundation/README.md)
- [Lab 05: Attack Surface Preparation](lab-05-attack-surface-preparation/README.md)
