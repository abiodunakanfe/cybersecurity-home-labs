# Lab 03 – Windows Endpoint Logging with Sysmon and Splunk

## Objective

Establish reliable Windows endpoint visibility by deploying Sysmon and validating log ingestion, parsing, and searchability in Splunk.

This lab focuses on **telemetry validation**, not alerting.

---

## Why This Lab Matters

In SOC operations, poor detections are often caused by:
- Missing endpoint logs
- Incorrect event coverage
- Unvalidated SIEM ingestion

This lab ensures that endpoint telemetry is:
- Generated correctly
- Collected consistently
- Searchable and usable for investigations

---

## Environment

- Endpoint OS: Windows 11  
- Logging Agent: Sysmon  
- SIEM: Splunk  
- Domain: Active Directory  
- Network: ECORP (`10.0.1.0/24`)  

---

## Sysmon Deployment

### Installation

- Installed Sysmon on the Windows 11 endpoint
- Applied a custom Sysmon configuration file
- Confirmed Sysmon service was running
- Verified events under:
  - **Applications and Services Logs**
  - **Microsoft**
  - **Windows**
  - **Sysmon**
  - **Operational**

---

### Sysmon Event IDs Enabled and Validated

| Event ID | Description |
|--------  |------------ |
| 1 | Process creation |
| 3 | Network connection |
| 5 | Process termination |
| 7 | Image loaded |
| 10 | Process access |
| 11 | File creation |
| 12 | Registry object added or deleted |
| 13 | Registry value set |
| 22 | DNS query |

These events provide sufficient visibility for:
- Initial access
- Execution
- Lateral movement
- Persistence indicators

---

## Splunk Configuration

- Installed Splunk on the Windows endpoint
- Configured ingestion of:
  - Sysmon Operational logs
  - Windows Security logs
- Verified correct sourcetype assignment:
  - `XmlWinEventLog:Microsoft-Windows-Sysmon/Operational`
- Confirmed time synchronization and indexing

---

## Telemetry Validation

### Process Creation (Sysmon Event ID 1)

**Purpose**
Validate visibility into command execution and application launches.

**SPL Query**
```spl
index=* sourcetype="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational"
EventCode=1
| table _time Computer User Image CommandLine ParentImage
