# Day 08 — Windows System Administration & Security Controls

**Course:** Cyber Security & Ethical Hacking Professional Program
**Module:** Computer & Operating System Fundamentals
**Day:** 08
**Topic:** Windows System Administration & Security Controls
**Level:** Beginner → Intermediate
**Duration:** 2–3 Hours

---

## 1. Learning Objectives

By the end of Day 08, students should be able to:

* Understand basic Windows system administration.
* Identify important Windows security controls.
* Understand local system configuration.
* Manage users, groups, services, and system settings safely.
* Understand Windows Update and patch management.
* Understand Microsoft Defender and Firewall.
* Understand backups and recovery.
* Read basic system/security information.
* Build a basic Windows security checklist.
* Understand why misconfiguration can create security risks.

---

# 2. What is System Administration?

**System administration** means managing and maintaining computer systems so that they remain:

* Available
* Secure
* Stable
* Updated
* Properly configured
* Recoverable

A system administrator may manage:

```text
Users
   ↓
Operating System
   ↓
Applications
   ↓
Services
   ↓
Network
   ↓
Security Controls
   ↓
Backups
```

From a cybersecurity perspective, system administration is extremely important.

A security professional needs to understand **how a system is normally configured** before identifying abnormal or insecure behavior.

---

# 3. Windows Administration vs Windows Security

These two concepts are related but different.

| Windows Administration | Windows Security               |
| ---------------------- | ------------------------------ |
| Creating users         | Controlling user privileges    |
| Installing software    | Preventing malicious software  |
| Managing services      | Monitoring suspicious services |
| Configuring network    | Configuring firewall           |
| Installing updates     | Applying security patches      |
| Managing storage       | Protecting sensitive files     |
| Backups                | Disaster recovery              |
| System configuration   | Security hardening             |

A cybersecurity professional needs knowledge of both.

---

# 4. Windows Security Baseline

A **security baseline** is a set of recommended security configurations for a system.

For example:

```text
Windows Security Baseline

✓ Updated OS
✓ Strong authentication
✓ Standard user account
✓ Firewall enabled
✓ Antivirus enabled
✓ Important security logs enabled
✓ Unnecessary services reviewed
✓ Secure file permissions
✓ Regular backups
✓ Screen lock enabled
✓ Unnecessary software removed
```

The baseline gives us a reference point.

If something changes unexpectedly, we can investigate it.

---

# 5. System Configuration

Windows contains many configuration areas.

Important examples:

* System settings
* User accounts
* Network configuration
* Services
* Startup applications
* Firewall
* Security settings
* Windows Update
* Device configuration
* Storage
* Event logs

A security professional should know **where configuration information is stored and how to inspect it safely**.

---

# 6. Windows Update

Operating systems contain software components.

Sometimes vulnerabilities are discovered in these components.

A vendor may release a security update:

```text
Vulnerability discovered
        ↓
Security patch developed
        ↓
Windows Update released
        ↓
System updated
        ↓
Vulnerability mitigated
```

Therefore:

> **Patch management is an important part of cybersecurity.**

---

## Why Updates Matter

Updates may fix:

* Security vulnerabilities
* Bugs
* Stability problems
* Compatibility problems
* Driver problems

An outdated operating system may contain known vulnerabilities.

---

# 7. Checking Windows Update

Students can inspect Windows Update through:

**Settings → Windows Update**

PowerShell can also provide system information, depending on the Windows version and available modules.

For this course, students should first learn to **inspect** update status rather than attempting to manipulate update components.

---

# 8. Microsoft Defender

Microsoft Defender provides security features such as:

* Antivirus
* Malware detection
* Real-time protection
* Security monitoring
* Firewall integration
* Threat protection

Conceptually:

```text
Application/File
      ↓
Security Inspection
      ↓
Threat Detection
      ↓
┌───────────────┐
│ Safe          │
│ or            │
│ Suspicious    │
└───────────────┘
      ↓
Action / Alert
```

---

# 9. Real-Time Protection

Real-time protection continuously monitors activity.

For example:

```text
User opens a file
       ↓
Security software inspects activity
       ↓
Potential threat detected?
       ↓
     Yes ──→ Alert / Block / Quarantine
       │
      No
       ↓
Continue
```

Students should understand:

**Security software is a defense mechanism, not a replacement for secure configuration.**

---

# 10. Windows Firewall

A firewall controls network traffic according to configured rules.

Basic concept:

```text
Internet
   ↓
[ Windows Firewall ]
   ↓
Computer
```

The firewall can control:

* Incoming traffic
* Outgoing traffic
* Network profiles
* Application access
* Port-related rules

---

# 11. Windows Network Profiles

Windows commonly uses network profiles such as:

* Domain
* Private
* Public

A simplified security idea:

### Public Network

Usually more restrictive.

Examples:

* Airport Wi-Fi
* Cafe Wi-Fi
* Hotel Wi-Fi

### Private Network

Used for trusted networks such as a home network.

### Domain Network

Common in organizational environments.

---

# 12. Why Network Profiles Matter

Imagine this situation:

```text
Laptop
   ↓
Public Wi-Fi
   ↓
Firewall configured too openly
   ↓
Unnecessary network exposure
```

The system could have a larger attack surface.

Therefore:

> **Network configuration should match the trust level of the network.**

---

# 13. Startup Applications

Some applications automatically start when Windows boots.

Conceptually:

```text
Computer starts
      ↓
Windows loads
      ↓
Startup applications
      ↓
Background processes
      ↓
User desktop
```

Startup programs can be legitimate.

Examples:

* Antivirus
* Cloud synchronization
* Hardware utilities
* Communication software

But unnecessary startup programs can:

* Increase resource usage
* Increase attack surface
* Make troubleshooting harder

---

# 14. Inspecting Startup Applications

Students can use:

**Task Manager → Startup apps**

Check:

* Application name
* Publisher
* Startup impact
* Enabled/disabled status

### Security mindset

Do not assume:

> "Unknown = Malware"

Instead:

```text
Unknown application
        ↓
Identify publisher
        ↓
Identify file location
        ↓
Check whether expected
        ↓
Check digital signature
        ↓
Review security alerts/logs
        ↓
Investigate if necessary
```

This is an important professional habit.

---

# 15. Windows Services

We already introduced services on Day 07.

Today we look at them from an administration perspective.

A service can:

* Start automatically
* Run in the background
* Start manually
* Be disabled
* Depend on another service

Example:

```text
Windows
   │
   ├── Service A
   │
   ├── Service B
   │      └── Dependency → Service C
   │
   └── Service D
```

### Important

Never randomly disable Windows services during practice.

A service may be required for:

* Networking
* Audio
* Updates
* Security
* Login
* Hardware
* Other applications

---

# 16. Service Startup Types

A Windows service can have different startup configurations.

Common concepts include:

| Startup Type              | Meaning                         |
| ------------------------- | ------------------------------- |
| Automatic                 | Starts automatically            |
| Automatic (Delayed Start) | Starts automatically after boot |
| Manual                    | Starts when required            |
| Disabled                  | Cannot normally start           |

Security professionals should understand why a service exists before changing its configuration.

---

# 17. Windows Task Scheduler

Windows contains a **Task Scheduler**.

It allows Windows or applications to execute tasks based on triggers.

Example:

```text
Trigger
   ↓
Scheduled Task
   ↓
Program / Script
   ↓
Action
```

Possible triggers:

* System startup
* User logon
* Specific time
* Event occurrence

Task Scheduler is legitimate and widely used.

However, from a security perspective, unexpected scheduled tasks can deserve investigation because scheduled execution can also be abused.

---

# 18. Security Principle: Configuration vs Behavior

A very important cybersecurity concept:

> Configuration tells us how a system is supposed to behave.

> Logs and monitoring tell us how the system actually behaved.

Example:

```text
Configuration:
Firewall enabled

        +

Logs:
Unexpected connection attempts

        ↓

Investigation
```

Therefore, security professionals use both configuration and monitoring.

---

# 19. Windows Event Logs

Important Windows logs include:

### Application

Application-related events.

### System

Operating-system and service-related events.

### Security

Security-related events such as authentication and auditing activity, depending on configured auditing.

Concept:

```text
System Activity
      ↓
Event
      ↓
Event Log
      ↓
Security Analyst
      ↓
Investigation
```

---

# 20. Backup and Recovery

Security is not only about preventing attacks.

It is also about recovering from incidents.

Example:

```text
Important Data
     ↓
Regular Backup
     ↓
Security Incident
     ↓
Data Damaged / Lost
     ↓
Recovery
```

A backup should ideally be:

* Regular
* Verified
* Protected
* Recoverable
* Appropriate for the importance of the data

---

# 21. 3-2-1 Backup Concept

A common backup strategy is the **3-2-1 rule**:

```text
3 copies of data
       ↓
2 different types of storage
       ↓
1 copy stored separately/off-site
```

Example:

```text
Original Data
     │
     ├── Computer
     ├── External Backup
     └── Separate/Cloud Backup
```

The exact implementation depends on the organization's requirements.

---

# 22. System Hardening

**Hardening** means reducing unnecessary security risks by improving system configuration.

Basic hardening examples:

* Remove unnecessary applications.
* Keep Windows updated.
* Use strong authentication.
* Use standard accounts for normal work.
* Enable firewall.
* Keep security protection enabled.
* Review unnecessary services.
* Review startup applications.
* Protect sensitive files.
* Enable appropriate logging.
* Maintain backups.

Concept:

```text
Default System
      ↓
Review
      ↓
Remove unnecessary exposure
      ↓
Apply security controls
      ↓
Hardened System
```

---

# 23. Attack Surface

The **attack surface** represents the possible points through which a system could be attacked or exposed.

Examples:

```text
Open network ports
Running services
Installed applications
User accounts
Remote access
Web applications
File shares
Network interfaces
External devices
```

More unnecessary exposure generally means more things that need to be secured.

---

# 24. Principle of Least Privilege

This principle should be repeated throughout the course.

> Give users and applications only the permissions they actually need.

Example:

```text
Normal Student
      ↓
Standard User
      ↓
Limited permissions
```

Instead of:

```text
Every User
      ↓
Administrator
      ↓
High privileges
```

The second approach can increase the impact of mistakes or compromised accounts.

---

# 25. Authentication + Authorization + Privilege

Students should now understand these three concepts clearly.

### Authentication

**Who are you?**

```text
Username + Password
       ↓
Identity Verification
```

### Authorization

**What are you allowed to access?**

```text
Authenticated User
       ↓
Permissions
       ↓
Allowed / Denied
```

### Privilege

**What powerful operations can your security token perform?**

These concepts are related but not identical.

---

# 26. Windows Security Architecture — Simplified

```text
                USER
                 │
                 ▼
          Authentication
                 │
                 ▼
          Access Token
                 │
       ┌─────────┴─────────┐
       ▼                   ▼
   Groups              Privileges
       │                   │
       └─────────┬─────────┘
                 ▼
           Authorization
                 │
                 ▼
       Resource Access
                 │
        ┌────────┴────────┐
        ▼                 ▼
      Allowed            Denied
```

This is one of the most important concepts of Windows security.

---

# 27. Practical Lab — Windows Security Administration Audit

**Lab environment:** Your own Windows computer or an authorized training machine.

Do not perform these exercises on someone else's computer.

---

## Task 1 — Identify Current User

Open PowerShell:

```powershell
whoami
```

Record:

* Username
* Computer name
* Domain/workgroup information if displayed

---

## Task 2 — Inspect Computer Information

```powershell
Get-ComputerInfo
```

Record important information such as:

* Windows version
* OS architecture
* Computer name
* Windows build

---

## Task 3 — Inspect Local Users

If available:

```powershell
Get-LocalUser
```

Record:

| Username | Enabled    | Description |
| -------- | ---------- | ----------- |
| User1    | True/False | ...         |
| User2    | True/False | ...         |

Do not change or delete any account.

---

# 28. Task 4 — Inspect Local Groups

Run:

```powershell
Get-LocalGroup
```

Then inspect members of a group, for example:

```powershell
Get-LocalGroupMember -Group "Administrators"
```

Observe:

* Who has administrator membership?
* Are there unexpected accounts?
* Are there standard users?

Do **not** modify group membership.

---

# 29. Task 5 — Inspect File Permissions

Use a safe directory such as:

```powershell
icacls "C:\Users\Public"
```

Observe:

* Users
* Groups
* Permissions
* Inheritance indicators

Try another safe directory:

```powershell
icacls "$env:USERPROFILE\Documents"
```

The exact output will vary depending on Windows configuration.

---

# 30. Task 6 — Inspect Services

Run:

```powershell
Get-Service
```

You can inspect a specific service:

```powershell
Get-Service | Select-Object -First 20
```

Look for:

* Service name
* Status
* Display name

Do not stop, disable, or modify services.

---

# 31. Task 7 — Inspect Detailed Service Information

Run:

```powershell
Get-CimInstance Win32_Service |
Select-Object Name, State, StartMode, StartName |
Format-Table -AutoSize
```

This can show:

* Service name
* Current state
* Startup mode
* Account used to run the service

The `StartName` field is especially useful for understanding service accounts.

---

# 32. Task 8 — Check Network Configuration

Run:

```powershell
Get-NetIPConfiguration
```

Record:

* Network adapter
* IP address
* Gateway
* DNS information

Do not modify network configuration during this lab.

---

# 33. Task 9 — Check Active Connections

Run:

```powershell
Get-NetTCPConnection
```

You can inspect the state of connections.

Common states include:

* Listen
* Established
* TimeWait
* CloseWait

Remember:

> An open/listening port is not automatically a vulnerability.

You need context.

---

# 34. Task 10 — Inspect Windows Security

Open:

**Windows Security**

Review available sections such as:

* Virus & threat protection
* Firewall & network protection
* Account protection
* Device security
* App & browser control

Do not disable security features for experimentation.

---

# 35. Task 11 — Check Firewall Status

In PowerShell:

```powershell
Get-NetFirewallProfile
```

Observe:

* Domain profile
* Private profile
* Public profile
* Enabled/disabled status

Do not disable the firewall.

---

# 36. Task 12 — Check Event Viewer

Open:

```text
Win + R
```

Then:

```text
eventvwr.msc
```

Explore:

```text
Windows Logs
 ├── Application
 ├── Security
 ├── Setup
 └── System
```

Find several recent events.

Record:

* Date/time
* Log
* Event ID
* Source
* Level

Do not delete logs.

---

# 37. Mini Project — Windows Security Audit

Create a report titled:

## “Windows Security & Administration Baseline”

Include the following sections:

### 1. System Information

* Windows version
* Architecture
* Computer name

### 2. User Accounts

* Current account
* Other local accounts
* Enabled/disabled status

### 3. Administrators

* Members of Administrators group
* Whether administrator access appears necessary

### 4. File Permissions

* Public folder permissions
* Documents folder permissions
* Notes about inheritance

### 5. Services

Identify:

* 5 important services
* Their status
* Startup mode
* Service account

### 6. Network

Record:

* IP configuration
* Network profile
* Active connections

### 7. Security Controls

Check:

* Firewall
* Microsoft Defender
* Windows Update
* Account protection
* Device security

### 8. Logs

Record several relevant Event Viewer observations.

### 9. Recommendations

Give **5 security recommendations** based only on what you actually observed.

---

# 38. Important Professional Rule

Never write:

> “This computer is completely secure.”

A professional security assessment should instead say something like:

> “The assessment identified the following configuration observations and potential areas for improvement.”

Why?

Because security is not a binary state.

```text
Secure
  ↑
  │
Risk decreases
  │
  ↓
Less secure
```

Security is a continuous process.

---

# 39. Common Beginner Mistakes

### Mistake 1

Giving every user administrator access.

### Mistake 2

Disabling antivirus because it interferes with testing.

### Mistake 3

Disabling the firewall unnecessarily.

### Mistake 4

Stopping unknown Windows services without understanding them.

### Mistake 5

Assuming every unknown process is malware.

### Mistake 6

Ignoring Windows updates.

### Mistake 7

Not maintaining backups.

### Mistake 8

Changing permissions without understanding inheritance.

### Mistake 9

Deleting logs.

### Mistake 10

Running security experiments on production systems.

---

# 40. Key Terminology

| Term                  | Meaning                                           |
| --------------------- | ------------------------------------------------- |
| System Administration | Managing and maintaining computer systems         |
| Hardening             | Reducing unnecessary security exposure            |
| Baseline              | Expected secure configuration                     |
| Patch                 | Software update that may fix bugs/security issues |
| Attack Surface        | Potential points of exposure                      |
| Firewall              | Controls network traffic                          |
| Antivirus             | Detects/protects against malicious software       |
| Backup                | Copy of data for recovery                         |
| Service               | Background Windows process/component              |
| Startup Application   | Program configured to start with Windows          |
| Task Scheduler        | Executes tasks based on triggers                  |
| Authentication        | Verifying identity                                |
| Authorization         | Determining allowed access                        |
| Privilege             | Ability to perform privileged operations          |
| Least Privilege       | Giving only necessary permissions                 |

---

# 41. Day 08 Assignment

### Theory

1. What is system administration?
2. What is system hardening?
3. What is a security baseline?
4. Why are Windows updates important?
5. What is the Windows Firewall?
6. What is Microsoft Defender?
7. What is attack surface?
8. Explain the 3-2-1 backup concept.
9. What is least privilege?
10. Differentiate authentication, authorization, and privilege.

### Practical

Perform a security audit on your own Windows computer and prepare:

```text
Windows Security Audit Report

1. System
2. Users
3. Groups
4. Permissions
5. Services
6. Network
7. Firewall
8. Defender
9. Event Logs
10. Backup
11. Security Recommendations
```

---

# 42. Quick Quiz

### Q1. What is hardening?

A. Installing games
B. Reducing unnecessary security exposure
C. Increasing CPU speed
D. Formatting Windows

**Answer: B**

---

### Q2. Which component controls network traffic?

A. Firewall
B. Calculator
C. Notepad
D. Paint

**Answer: A**

---

### Q3. What does least privilege mean?

A. Everyone gets administrator access
B. Users receive only the permissions they need
C. Nobody gets access
D. Passwords are removed

**Answer: B**

---

### Q4. Which tool can be used to inspect Windows services?

A. `Get-Service`
B. `Get-Weather`
C. `Get-Game`
D. `Get-Photo`

**Answer: A**

---

### Q5. What is a backup primarily used for?

A. Increasing RAM
B. Recovering data
C. Increasing internet speed
D. Changing the CPU

**Answer: B**

---

### Q6. Which tool opens Windows Event Viewer?

A. `eventvwr.msc`
B. `paint.exe`
C. `calc.exe`
D. `notepad.exe`

**Answer: A**

---

### Q7. Is an open network port automatically a vulnerability?

A. Yes, always
B. No, context is required

**Answer: B**

---

### Q8. What should you do before changing an unknown Windows service?

A. Immediately disable it
B. Understand what it does and its dependencies
C. Delete it
D. Kill the process

**Answer: B**

---

# 43. Day 08 Final Concept

Students should now understand the relationship:

```text
Windows System
      │
      ├── Users
      │
      ├── Groups
      │
      ├── Permissions
      │
      ├── Processes
      │
      ├── Services
      │
      ├── Network
      │
      ├── Firewall
      │
      ├── Defender
      │
      ├── Logs
      │
      ├── Updates
      │
      └── Backups
             │
             ▼
      Security Baseline
             │
             ▼
       System Hardening
             │
             ▼
      Continuous Monitoring
```

## 🎯 Day 08 Key Takeaway

> **A cybersecurity professional must first understand how a normal system is configured and administered. Security testing becomes much more meaningful when you can distinguish normal configuration and behavior from genuinely suspicious activity.**
