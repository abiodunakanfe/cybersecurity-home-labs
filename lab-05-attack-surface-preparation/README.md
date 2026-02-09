# Lab 05 – Attack Surface Preparation

## Objective

Prepare a controlled and observable attack surface by validating target exposure, network reachability, and logging coverage prior to executing attacks.

This lab marks the transition from **infrastructure setup** to **attack execution**.

---

## Why This Lab Matters

Attacks should never be executed blindly.

Before exploitation, a Blue Team must confirm:
- What systems are exposed
- What an attacker can reach
- What activity will be logged

This lab ensures that attacks generate **meaningful, detectable signals** rather than noise or blind spots.

---

## Environment Scope

### Attacker Environment
- OS: Kali Linux  
- Network: ATTACKLAN (`10.0.3.0/24`)

### Target Environment
- Windows 11 (Domain-joined)
- Windows Server (Domain Controller)
- Metasploitable2
- Network: ECORP (`10.0.1.0/24`)

---

## Network Reachability Validation

- Verified connectivity from ATTACKLAN to ECORP through pfSense
- Confirmed routing and firewall rules allow controlled access
- Ensured no unintended network isolation or overexposure

---

## Target Exposure Review

### Metasploitable2
- Confirmed system is reachable from ATTACKLAN
- No exploitation performed at this stage
- Used only connectivity and service discovery checks

### Windows Systems
- Confirmed systems are reachable where expected
- No attack tools executed
- Endpoint protections intentionally adjusted via Group Policy for lab testing

---

## Logging Coverage Validation

- Confirmed Sysmon is active on Windows endpoint
- Verified:
  - Process creation events
  - Network connection events
  - DNS query logging
- Validated Splunk ingestion prior to attack execution

---

## Attack Readiness Checklist

- Network paths validated
- Targets reachable
- Logging pipeline functional
- Identity infrastructure stable
- No exploitation executed prematurely

This checklist ensures that all future attacks can be:
- Observed
- Investigated
- Detected

---

## Key Observations

- Attack surface must be intentionally designed
- Overexposure reduces learning value
- Underexposure creates false confidence
- Logging validation is a prerequisite for exploitation

---

## Outcome

A controlled, observable attack surface ready for exploitation and detection testing.

This lab completes the **foundation phase** of the SOC home lab and enables safe transition into execution-level labs.

---

## Next Steps

- Execute reconnaissance from ATTACKLAN
- Perform exploitation against Metasploitable2
- Observe attacker behavior through validated telemetry
- Develop detection logic in Splunk

---

## SOC Skills Demonstrated

- Attack surface analysis
- Pre-attack validation
- Blue Team operational discipline
- Detection-first mindset
