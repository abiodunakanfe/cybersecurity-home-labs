# Lab 04 – Active Directory Foundation and Policy Configuration

## Objective

Deploy and configure an Active Directory domain to support enterprise-style identity management, policy enforcement, and future attack and detection scenarios.

This lab focuses on **identity infrastructure readiness**, not exploitation.

---

## Why This Lab Matters

Most Windows-based attacks target identity.

Before testing:
- Credential abuse
- Privilege escalation
- Lateral movement

The directory service must be:
- Structured correctly
- Predictable
- Observable

This lab ensures Active Directory is intentionally designed, not left at default settings.

---

## Environment

- Server OS: Windows Server  
- Role: Domain Controller  
- Domain Services: Active Directory Domain Services (AD DS)  
- Client OS: Windows 11  
- Network: ECORP (`10.0.1.0/24`)  

---

## Domain Controller Deployment

### AD DS Installation

- Installed Active Directory Domain Services role
- Promoted the server to a Domain Controller
- Verified domain services were operational
- Confirmed DNS services were functioning correctly

---

## Active Directory Structure

### Organizational Units (OU)

Instead of using default containers, custom OUs were created to improve manageability and visibility.

**OU Structure**
- Users
- Groups
- Computers

This structure supports:
- Targeted Group Policy application
- Clear separation of objects
- Easier auditing and troubleshooting

---

## User and Group Management

- Created domain users for lab testing
- Created security groups to represent role-based access
- Assigned users to appropriate groups
- Verified group membership consistency

This setup enables future testing of:
- Privilege abuse
- Access control weaknesses
- Group-based policy impact

---

## Group Policy Configuration

### Policy Objective

Simulate real-world enterprise policy behavior while allowing controlled lab testing.

### Applied Group Policy

- Created a custom Group Policy Object (GPO)
- Applied the GPO at the OU level
- Configured the policy to allow specific lab users to bypass Microsoft Defender

This supports:
- Controlled attack testing
- Reduced interference during exploit simulation
- Clear policy-based behavior tracking

---

## Domain Join Validation

- Successfully joined the Windows 11 workstation to the domain
- Verified domain authentication
- Confirmed policy application using `gpresult` and system behavior
- Ensured domain users could log in successfully

---

## Validation and Testing

- Domain Controller services running as expected
- DNS resolution functional within the domain
- Group Policies applied correctly
- User authentication and authorization working as designed

---

## Key Observations

- Default Active Directory structures are insufficient for testing
- OU-based design improves policy control and visibility
- Group Policy changes significantly affect endpoint security posture
- Identity misconfiguration directly impacts detection reliability

---

## Outcome

A fully functional Active Directory environment with:
- Structured identity management
- Enforced policies
- Domain-joined endpoints

This directory service now supports:
- Attack simulation
- Identity-based detections
- Privilege abuse testing

---

## Next Steps

- Validate authentication and authorization logs in Splunk
- Simulate identity-based attacks
- Build detections around AD abuse techniques

---

## SOC Skills Demonstrated

- Active Directory administration
- Identity infrastructure design
- Group Policy management
- Blue Team operational thinking
