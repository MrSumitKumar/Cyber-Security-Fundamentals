# Day 06 — Windows Operating System Fundamentals

**Course:** Cyber Security & Ethical Hacking Professional Program
**Day:** 06
**Module:** Computer & Operating System Fundamentals
**Topic:** Windows Operating System Fundamentals
**Level:** Beginner

## Learning Objectives

By the end of Day 06, students should be able to:

* Understand the basic architecture of Windows.
* Understand Windows users, groups, and privileges.
* Understand NTFS and file permissions.
* Understand Windows processes and services.
* Understand the Windows Registry.
* Understand Event Viewer and Windows logs.
* Understand UAC and administrator privileges.
* Understand Windows Defender Firewall at a basic level.
* Use basic PowerShell commands for system observation.
* Identify important Windows security concepts.

---

# 1. Introduction to Windows

**Windows** is a family of operating systems developed by Microsoft.

It is widely used in:

* Personal computers
* Business environments
* Enterprise networks
* Servers
* Educational institutions
* Organizations

For cyber security professionals, Windows is especially important because enterprise environments commonly contain Windows endpoints and servers.

---

# 2. Windows from a Security Perspective

A Windows computer can be viewed as:

```text
                 WINDOWS SYSTEM
                       │
       ┌───────────────┼────────────────┐
       ↓               ↓                ↓
     Users          Applications       Data
       │               │                │
       └───────────────┼────────────────┘
                       ↓
                 Windows OS
                       │
       ┌───────────────┼────────────────┐
       ↓               ↓                ↓
    Processes        Services        Security
       │                                │
       ↓                                ↓
     Kernel                       Authentication
                                      Permissions
                                      Logging
```

A security professional needs to understand each layer.

---

# 3. Windows Architecture

A simplified Windows architecture is:

```text
Applications
      ↓
User Mode
      ↓
Windows System Components
      ↓
Kernel Mode
      ↓
Hardware
```

Windows separates ordinary applications from highly privileged system components.

This separation helps improve system stability and security.

---

# 4. User Mode vs Kernel Mode

Two important concepts are:

### User Mode

Most normal applications run here.

Examples:

* Browser
* Text editor
* Office application
* Python application

### Kernel Mode

Highly privileged components operate here.

Examples include:

* Windows kernel
* Device drivers
* Low-level system components

Simplified:

```text
USER MODE
────────────────────────
Chrome
VS Code
Python
Applications
────────────────────────
KERNEL MODE
Windows Kernel
Drivers
Core System Components
────────────────────────
HARDWARE
```

A vulnerability in highly privileged components can potentially have greater security impact than a normal application vulnerability.

---

# 5. Windows Users

Windows uses user accounts to identify people or services interacting with the system.

Examples:

```text
Administrator
Student
Teacher
Guest
Service Account
```

Each account can have different permissions.

---

# 6. Local Account vs Microsoft Account

Windows systems can use different account arrangements.

### Local Account

An account managed primarily on the local computer.

### Microsoft Account

An account associated with Microsoft's online services and identity ecosystem.

Enterprise environments may also use organizational identity systems such as Active Directory or Microsoft Entra ID.

For today's lesson, focus on understanding the basic concept of user identity.

---

# 7. Administrator Account

An administrator account has elevated privileges.

It may be able to:

* Install software
* Change system configuration
* Manage users
* Modify protected files
* Configure security settings
* Manage services

Because administrative privileges are powerful, they should be used carefully.

---

# 8. Standard User

A standard user generally has fewer privileges.

For example, a standard user may:

* Run applications
* Create personal files
* Browse the internet
* Use approved software

but may not be allowed to perform certain system-level changes.

---

# 9. Principle of Least Privilege

From Day 03:

> **Users should receive only the permissions required for their work.**

Example:

```text
Student
   ↓
Needs:
Browser + VS Code
   ↓
Does NOT need:
System Administrator privileges
```

This reduces the potential impact if the account is compromised.

---

# 10. Windows Groups

Windows can organize users into groups.

A group can be assigned permissions rather than configuring every user individually.

Conceptually:

```text
Students
 ├── Rahul
 ├── Priya
 └── Amit

Teachers
 ├── Neha
 └── Raj
```

Permissions can then be assigned according to the group's role.

---

# 11. NTFS

**NTFS** stands for:

> **New Technology File System**

It is a commonly used Windows file system.

NTFS provides features such as:

* File and folder permissions
* File metadata
* Access control
* Large-volume support
* File system security features

---

# 12. File and Folder Permissions

Windows uses access controls to determine who can perform actions on files and folders.

Common permissions include:

* Read
* Write
* Modify
* Execute
* Full Control

Example:

```text
Student
  ↓
Read → YES
Write → YES
Delete → NO

Administrator
  ↓
Full Control → YES
```

The exact effective permission depends on the user's identity, groups, inherited permissions, and other access-control rules.

---

# 13. Access Control

Access control answers:

> **Who can access this resource, and what can they do with it?**

Example:

```text
File: salaries.xlsx

HR Group
   ↓
Read + Modify

Students
   ↓
No Access
```

This is an important part of Windows security.

---

# 14. File Permissions vs Share Permissions

Windows network environments can involve different layers of permissions.

For example:

```text
Network Share Permission
          +
     NTFS Permission
          ↓
    Effective Access
```

Understanding how permissions interact is important for Windows security administration.

This will become more important when we study enterprise networks and Active Directory.

---

# 15. Windows Processes

As covered on Day 05, Windows runs programs as processes.

You can observe processes through:

**Task Manager**

Typical information includes:

* Process name
* PID
* CPU usage
* Memory usage
* User
* Network activity

Example:

```text
Process              PID
──────────────────────────
explorer.exe         1250
chrome.exe           2450
python.exe           3120
```

The exact PIDs change on every system.

---

# 16. Windows Services

A **Windows service** is a background component that provides a system or application function.

Examples may include services related to:

* Networking
* Updates
* Security
* Printing
* Databases
* Applications

Simplified:

```text
Windows
   ↓
Services
   ├── Networking
   ├── Security
   ├── Updates
   └── Applications
```

---

# 17. Why Services Matter in Cyber Security

Security professionals need to know:

* Which services are running?
* Why are they running?
* Which account runs them?
* Which network ports do they use?
* Are they necessary?
* Are they properly configured?

An unnecessary exposed service can increase the system's attack surface.

---

# 18. Windows Registry

The **Windows Registry** is a hierarchical database used by Windows and applications to store configuration information.

It contains information related to areas such as:

* System configuration
* User configuration
* Application settings
* Hardware configuration

Conceptually:

```text
Registry
│
├── System Settings
├── User Settings
├── Software Configuration
└── Hardware Information
```

---

# 19. Registry Hives

Common registry hives include:

* `HKEY_LOCAL_MACHINE` — system-wide configuration
* `HKEY_CURRENT_USER` — settings for the current user
* `HKEY_CLASSES_ROOT` — file associations and related information
* `HKEY_USERS` — information for user profiles
* `HKEY_CURRENT_CONFIG` — hardware configuration information

Students do not need to memorize all details today.

Focus on understanding:

> **The Registry is an important configuration database within Windows.**

---

# 20. Why the Registry Matters in Cyber Security

Security analysts may examine the Registry during:

* Incident response
* Digital forensics
* Malware investigations
* Configuration auditing

It may contain evidence about system configuration and user activity.

---

# 21. Windows Event Logs

Windows records many system and application events.

These records are called **Event Logs**.

Examples:

* Successful login
* Failed login
* Service changes
* Application errors
* Security events
* System events

Simplified:

```text
System Activity
      ↓
Event
      ↓
Windows Event Log
      ↓
Security Analyst
      ↓
Investigation
```

---

# 22. Event Viewer

**Event Viewer** is a Windows tool used to view event logs.

Important categories include:

### Application

Events generated by applications.

### System

Operating system and system component events.

### Security

Security-related events, depending on auditing configuration.

### Other Logs

Additional logs may exist for specific Windows components and applications.

---

# 23. Successful vs Failed Login

Imagine an account has several failed login attempts:

```text
10:01 → Failed
10:02 → Failed
10:03 → Failed
10:04 → Failed
10:05 → Successful
```

A security analyst may investigate this pattern.

However:

> **Multiple failed logins do not automatically prove an attack.**

Context is required.

---

# 24. Windows Security Auditing

Windows can be configured to record various security-related activities.

Examples may include:

* Logon events
* Account changes
* Policy changes
* Object access
* Process-related events

The exact events available depend on Windows version and audit policy configuration.

---

# 25. User Account Control — UAC

**User Account Control (UAC)** is a Windows security feature that helps prevent unauthorized or accidental elevation of privileges.

When an application requests an administrative action, Windows may ask for confirmation.

Example:

```text
Application
    ↓
Requests Elevated Action
    ↓
UAC Prompt
    ↓
User Approval
    ↓
Elevated Operation
```

UAC helps reduce unnecessary privileged execution.

---

# 26. Why UAC Matters

Suppose a normal user opens a malicious application.

If everything automatically ran with administrator privileges, the potential impact could be greater.

UAC adds an additional boundary around administrative actions.

It is not a complete security solution by itself.

---

# 27. Windows Defender Firewall

Windows includes a built-in firewall capability.

A firewall controls network traffic according to configured rules.

Simplified:

```text
Internet
   ↓
Windows Firewall
   ↓
Windows Computer
```

Rules may control:

* Inbound traffic
* Outbound traffic
* Applications
* Ports
* Network profiles

---

# 28. Why Firewalls Matter

Suppose a computer has a service listening for network connections.

A firewall can help control who can reach that service.

Conceptually:

```text
Internet
   ↓
Firewall
   ↓
Allowed Traffic → Service
Blocked Traffic → ❌
```

Firewall configuration should follow the principle of allowing only required communication.

---

# 29. Windows Defender

Modern Windows systems include built-in security capabilities under **Microsoft Defender**.

These capabilities can help with:

* Malware protection
* Threat detection
* Endpoint security
* Firewall integration
* Security monitoring

Security professionals should understand both the protection mechanisms and the logs/alerts they generate.

---

# 30. PowerShell

**PowerShell** is Microsoft's command-line shell and scripting environment.

It is widely used for:

* System administration
* Automation
* Configuration
* Troubleshooting
* Security operations

Cyber security professionals frequently encounter PowerShell during investigations.

---

# 31. Basic PowerShell Commands

### Show current user

```powershell
whoami
```

### Show computer information

```powershell
Get-ComputerInfo
```

### List processes

```powershell
Get-Process
```

### List services

```powershell
Get-Service
```

### Show network configuration

```powershell
Get-NetIPConfiguration
```

### Show active network connections

```powershell
Get-NetTCPConnection
```

These commands are useful for **observing your own system**.

---

# 32. PowerShell vs Command Prompt

| PowerShell                                | Command Prompt                 |
| ----------------------------------------- | ------------------------------ |
| Modern shell and scripting environment    | Older command-line environment |
| Rich object-based pipeline                | Primarily text-based           |
| Powerful automation                       | Simpler command environment    |
| Strong system administration capabilities | Common legacy commands         |
| Widely used in enterprise environments    | Still available on Windows     |

Both can be useful, but PowerShell is particularly important for modern Windows administration and security.

---

# 33. Windows File System Navigation

PowerShell can be used to navigate files.

Example:

```powershell
Get-Location
```

Shows the current location.

```powershell
Get-ChildItem
```

Lists files and directories.

```powershell
Set-Location Documents
```

Moves into the Documents directory.

---

# 34. Windows Security Mindset

When analyzing a Windows computer, ask:

```text
Who are the users?
       ↓
Which groups are they members of?
       ↓
Which processes are running?
       ↓
Which services are active?
       ↓
Which ports/services are exposed?
       ↓
Which files have sensitive permissions?
       ↓
What do the logs show?
       ↓
What security controls are enabled?
```

This is the beginning of Windows security analysis.

---

# 35. Day 06 Practical Lab

**Perform these activities only on your own Windows computer or an authorized lab.**

## Task 1 — Identify Your User

Open PowerShell:

```powershell
whoami
```

Record the result.

---

## Task 2 — System Information

Run:

```powershell
Get-ComputerInfo
```

Find:

* Windows version
* OS architecture
* Computer name
* Manufacturer
* System type

---

## Task 3 — Process Analysis

Run:

```powershell
Get-Process
```

Identify five familiar processes.

Create:

| Process | PID | CPU | Memory |
| ------- | --: | --: | -----: |
|         |     |     |        |
|         |     |     |        |
|         |     |     |        |
|         |     |     |        |
|         |     |     |        |

---

# 36. Task 4 — Service Analysis

Run:

```powershell
Get-Service
```

Choose five services.

Record:

| Service | Status | Purpose |
| ------- | ------ | ------- |
|         |        |         |
|         |        |         |
|         |        |         |
|         |        |         |
|         |        |         |

Do not stop or disable services during today's exercise.

---

# 37. Task 5 — Network Configuration

Run:

```powershell
Get-NetIPConfiguration
```

Identify:

* Network adapter
* IPv4 address
* Gateway
* DNS information

Do not publish your private network information publicly.

---

# 38. Task 6 — Active Network Connections

Run:

```powershell
Get-NetTCPConnection
```

Observe:

* Local address
* Local port
* Remote address
* Remote port
* Connection state

Do not attempt to connect to or probe unknown external systems.

The purpose is simply to understand what your own system is doing.

---

# 39. Task 7 — Event Viewer

Open:

**Event Viewer**

Explore:

```text
Windows Logs
├── Application
├── Security
├── Setup
└── System
```

Find several recent events and record:

* Date/time
* Event source
* Event ID
* Level
* Short description

Do not modify or delete logs.

---

# 40. Task 8 — Windows Firewall

Open Windows Security / Windows Defender Firewall settings.

Identify:

* Whether firewall protection is enabled.
* Which network profiles are active.
* Where firewall configuration can be viewed.

Do not disable the firewall for experimentation.

---

# 41. Day 06 Mini Project

## "Windows Security Baseline"

Create a basic security report for your own Windows system.

### Section 1 — System

```text
Computer Name:
Windows Version:
Architecture:
```

### Section 2 — Users

```text
Current User:
Account Type:
```

### Section 3 — Processes

List five processes.

### Section 4 — Services

List five services.

### Section 5 — Network

Record your network adapter and configuration at a high level.

### Section 6 — Logs

Document three interesting but normal events.

### Section 7 — Security Controls

Identify:

* Firewall
* Microsoft Defender
* UAC
* Updates

### Section 8 — Recommendations

Give five security recommendations.

---

# 42. Day 06 Assignment

### Q1.

What is the difference between User Mode and Kernel Mode?

### Q2.

What is NTFS?

### Q3.

What is a Windows service?

### Q4.

What is the Windows Registry?

### Q5.

What is Event Viewer?

### Q6.

Why are Windows Event Logs important for cyber security?

### Q7.

What is UAC?

### Q8.

What is the purpose of Windows Firewall?

### Q9.

What is PowerShell?

### Q10.

Why is least privilege important in Windows?

---

# 43. Day 06 Quick Quiz

### Q1. Which operating system component operates with highly privileged access?

A. Kernel
B. Browser
C. Notepad
D. Calculator

**Answer: A**

---

### Q2. NTFS is:

A. A Windows file system
B. A network protocol
C. A programming language
D. An antivirus

**Answer: A**

---

### Q3. Which tool is commonly used to view Windows Event Logs?

A. Event Viewer
B. Paint
C. Calculator
D. Notepad

**Answer: A**

---

### Q4. What does UAC help control?

A. Administrative privilege elevation
B. Screen brightness
C. Internet speed
D. File compression

**Answer: A**

---

### Q5. Which command lists processes in PowerShell?

A. `Get-Process`
B. `Get-Files`
C. `Show-CPU`
D. `List-System`

**Answer: A**

---

### Q6. Which command lists Windows services?

A. `Get-Service`
B. `Get-Network`
C. `Get-Users`
D. `Show-Service`

**Answer: A**

---

### Q7. What is the primary purpose of a firewall?

A. Control network traffic
B. Increase RAM
C. Edit documents
D. Create users automatically

**Answer: A**

---

### Q8. What does `whoami` generally show?

A. Current user identity
B. CPU temperature
C. IP routing table
D. Disk capacity

**Answer: A**

---

# 44. Important Terminology

| Term            | Meaning                                                |
| --------------- | ------------------------------------------------------ |
| Windows         | Microsoft operating system family                      |
| User Mode       | Lower-privilege execution environment for applications |
| Kernel Mode     | Highly privileged execution environment                |
| Administrator   | Account with elevated privileges                       |
| Standard User   | Account with more limited privileges                   |
| Group           | Collection of user/security identities                 |
| NTFS            | Common Windows file system                             |
| Permission      | Allowed action on a resource                           |
| Registry        | Windows configuration database                         |
| Service         | Background system/application component                |
| Event Log       | Record of system/application/security events           |
| Event Viewer    | Tool for viewing Windows event logs                    |
| UAC             | User Account Control                                   |
| Firewall        | Controls network traffic                               |
| PowerShell      | Windows shell and scripting environment                |
| Defender        | Microsoft's built-in security capabilities             |
| Least Privilege | Providing only required permissions                    |

---

# 45. Day 06 Key Takeaways

Students should remember:

1. Windows is an important operating system for cyber security professionals.
2. Windows separates User Mode and Kernel Mode.
3. Users and groups control identity and access.
4. Administrator privileges should be used carefully.
5. NTFS provides important file-system capabilities and access controls.
6. Services run background functionality.
7. The Registry stores important system and application configuration.
8. Event Logs provide valuable information about system activity.
9. Event Viewer helps analysts inspect Windows events.
10. UAC adds a protection boundary around administrative actions.
11. Windows Firewall controls network traffic according to configured rules.
12. Microsoft Defender provides built-in security capabilities.
13. PowerShell is an important Windows administration and security tool.
14. Security analysts should understand processes, services, users, permissions, and logs together.
15. **A Windows security professional should be able to inspect a system before attempting to secure or investigate it.**

---

# 46. Day 06 Final Concept

Think of a Windows computer like this:

```text
                    WINDOWS
                       │
          ┌────────────┼────────────┐
          ↓            ↓            ↓
        USERS       PROCESSES     FILES
          │            │            │
          ↓            ↓            ↓
       GROUPS       SERVICES      NTFS
          │            │            │
          └────────────┼────────────┘
                       ↓
                  SECURITY
                       │
       ┌───────────────┼───────────────┐
       ↓               ↓               ↓
      UAC           FIREWALL          DEFENDER
       │               │               │
       └───────────────┼───────────────┘
                       ↓
                    LOGS
                       ↓
                 EVENT VIEWER
                       ↓
                 SECURITY ANALYST
```

### Security Analyst Mindset

When you sit in front of a Windows machine, don't immediately think:

> **"Which hacking tool should I run?"**

Instead think:

> **Who is using this system?**
> **What processes are running?**
> **Which services are active?**
> **What permissions exist?**
> **What network connections exist?**
> **What security controls are enabled?**
> **What do the logs tell us?**

That approach builds the foundation required for **Day 07 — Windows Users, Permissions & Services**, where students will go deeper into accounts, groups, privileges, NTFS permissions, service accounts, and Windows access control.
