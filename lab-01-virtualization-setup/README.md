# Lab 01 – Virtual SOC Environment Setup

# Objective
Build a virtual SOC lab using VirtualBox with proper network segmentation, logging, and centralized visibility.

# Environment
- **Host OS:** Windows 11  
- **Hypervisor:** VirtualBox  
- **Firewall:** pfSense CE  
- **SIEM:** Splunk  
- **Endpoint Logging:** Sysmon  
- **Attack Platform:** Kali Linux  
- **Vulnerable Host:** Metasploitable2  
- **Directory Services:** Windows Server (AD DS)  

# Network Architecture
# LAN 1 – ECORP - Subnet: 10.0.1.0/24  
-Systems:
- Windows 11 (Sysmon + Splunk)
- Windows Server (Domain Controller)
- Metasploitable2

# LAN 2 – ATTACKLAN
Subnet: -10.0.3.0/24  
Systems: - Kali Linux

Firewall routing handled by **pfSense**.

# Why This Separation Exists
- Simulates real enterprise vs attacker boundary  
- Enables controlled attack paths  
- Allows realistic detection and monitoring scenarios  

# Key Configuration Steps
- Installed VirtualBox  
- Deployed pfSense with WAN and two LAN interfaces  
- Configured DHCP scopes:  
  - 10.0.1.11 – 10.0.1.245  
  - 10.0.3.11 – 10.0.3.245  
- Verified all hosts received correct IPs  
- Confirmed gateway and routing functionality  

# Validation
- All VMs received IPs from pfSense  
- Inter-LAN communication worked as designed  
- Internet access confirmed where required  
- Network isolation enforced correctly  

# Outcome
A stable, segmented SOC lab environment ready for:
- Attack simulation  
- Telemetry collection  
- Detection engineering  
<img width="1101" height="829" alt="virtualbox set up" src="https://github.com/user-attachments/assets/c43527a9-02f4-4c74-8bec-ef3447b09fc6" />
