# Day 07 — Windows Users, Permissions & Services

**Course:** Cyber Security & Ethical Hacking Professional Program
**Module:** Computer & Operating System Fundamentals
**Day:** 07
**Topic:** Windows Users, Permissions & Services
**Level:** Beginner → Intermediate
**Recommended Duration:** 2–3 Hours

---

## 1. Learning Objectives

By the end of Day 07, students will understand:

* Windows users and user accounts
* Local users vs domain users
* Security Identifiers (SIDs)
* Windows groups
* Administrator vs standard users
* Permissions vs privileges
* Access tokens
* UAC and privilege elevation
* NTFS permissions
* Permission inheritance
* Explicit vs inherited permissions
* File/folder ownership
* Share permissions vs NTFS permissions
* Windows services
* Service accounts
* Service startup types
* Service dependencies
* How to audit users, permissions and services safely

> **Security Rule:** All practical exercises in this lesson must be performed only on your own Windows computer or an authorized training lab.

---

# 2. Why Users, Permissions & Services Matter in Cyber Security

A large part of Windows security is based on one simple question:

> **Who is allowed to do what?**

For example:

Suppose a computer has:

```text
C:\CompanyData
```

There may be:

```text
Administrator → Full Control
Teacher       → Modify
Student       → Read
Guest         → No Access
```

If permissions are configured incorrectly, a normal user might be able to access or modify information they should not.

Therefore, cyber security professionals need to understand:

```text
Users
   ↓
Groups
   ↓
Permissions
   ↓
Privileges
   ↓
Access Token
   ↓
Resources
```

---

# 3. Windows Identity

Windows needs to identify users and other security principals before deciding what they can access.

A **security principal** can include:

* User
* Group
* Computer account
* Service account

Example:

```text
Sumit
Student
Administrator
SYSTEM
```

Each security principal can have its own identity.

---

# 4. Local Users

A local user account exists on a particular Windows computer.

Example:

```text
PC-01
 ├── Administrator
 ├── Student
 ├── Teacher
 └── Guest
```

A local account is normally managed by that individual Windows computer.

### Example

If you create:

```text
student
```

on Computer A, that account does not automatically exist on Computer B.

---

# 5. Domain Users

In an organization, users may be centrally managed through a directory service such as **Active Directory**.

Example:

```text
Company Network
       │
       ▼
Domain Controller
       │
 ┌─────┼─────┐
 ▼     ▼     ▼
User1 User2 User3
```

Instead of creating and managing every employee separately on every PC, an organization can centrally manage identities and access.

We will study Active Directory in much greater depth later in the course.

---

# 6. Security Identifier — SID

Windows internally identifies security principals using a **Security Identifier (SID)**.

Example format:

```text
S-1-5-21-xxxxxxxxxx-xxxxxxxxxx-xxxxxxxxxx-1001
```

You normally should not depend on the username alone to identify a Windows security principal.

Why?

Because usernames can change.

For example:

```text
student
   ↓
new username
```

The underlying security identity is represented by its SID.

---

# 7. SID Structure — Basic Concept

A SID contains multiple components.

Simplified example:

```text
S-1-5-21-123456789-123456789-123456789-1001
│ │ │                         │
│ │ │                         └── Relative identifier
│ │ └──────────────────────────── Domain/Computer identifier
│ └────────────────────────────── Authority
└──────────────────────────────── SID identifier
```

You do **not** need to memorize the complete structure today.

The important concept is:

> Windows uses SIDs to uniquely identify security principals.

---

# 8. Finding Your Current User

Open PowerShell:

```powershell
whoami
```

Example:

```text
desktop-abc\sumit
```

This tells you the current user context.

You can also use:

```powershell
whoami /user
```

This displays the current user's SID.

Example:

```text
USER INFORMATION
----------------
User Name      SID
-------------- ----------------------------------------
desktop-abc\sumit S-1-5-21-...-1001
```

---

# 9. Users vs Groups

A **user** represents an identity.

A **group** represents a collection of identities.

Example:

```text
Users
│
├── Sumit
├── Rahul
├── Priya
└── Aman
```

Instead of assigning permissions individually:

```text
Sumit → Read
Rahul → Read
Priya → Read
Aman  → Read
```

we can create:

```text
Students
│
├── Sumit
├── Rahul
├── Priya
└── Aman
```

Then assign:

```text
Students → Read
```

This is easier to manage.

---

# 10. Windows Groups

Some common Windows groups include:

| Group                           | General Purpose                                   |
| ------------------------------- | ------------------------------------------------- |
| Administrators                  | Administrative control                            |
| Users                           | Standard user access                              |
| Guests                          | Restricted guest access                           |
| Remote Desktop Users            | Permission to use Remote Desktop where configured |
| Backup Operators                | Specialized backup-related privileges             |
| Network Configuration Operators | Certain network configuration tasks               |

The exact groups available can vary depending on Windows edition and configuration.

---

# 11. Checking Local Users

On supported Windows editions, PowerShell provides:

```powershell
Get-LocalUser
```

Example:

```text
Name          Enabled
----          -------
Administrator False
Guest         False
Sumit         True
```

Students should **not enable or modify accounts during this exercise**.

The objective is observation.

---

# 12. Checking Local Groups

Use:

```powershell
Get-LocalGroup
```

To inspect members of a particular group:

```powershell
Get-LocalGroupMember -Group "Administrators"
```

Example:

```text
Name
----
DESKTOP-ABC\Administrator
DESKTOP-ABC\Sumit
```

This tells us which accounts have membership in that group.

---

# 13. Administrator vs Standard User

One of the most important concepts in Windows security is:

### Administrator

An administrator can perform many system-level operations.

Examples:

* Install software
* Change system configuration
* Manage users
* Configure security settings
* Modify protected system resources

### Standard User

A standard user has more restricted access.

For example:

```text
Standard User
      │
      ├── Use applications
      ├── Create personal files
      └── Perform normal tasks

      ✕
      ├── Cannot freely modify protected system areas
      └── Cannot freely perform administrative operations
```

---

# 14. Principle of Least Privilege

A fundamental security principle is:

> Give users only the permissions they actually need.

Example:

Suppose an employee only needs to read reports.

Bad configuration:

```text
Employee → Full Control
```

Better:

```text
Employee → Read
```

This reduces the potential impact of mistakes or compromised accounts.

---

# 15. Permissions vs Privileges

These terms are related but not identical.

### Permission

Controls access to a particular resource.

Example:

```text
File → Report.xlsx

User → Read
```

### Privilege

A system-level right granted to an account or security context.

For example, Windows has certain privileges that allow specific system operations.

Simplified:

```text
Permission
   ↓
"What can I do with this resource?"

Privilege
   ↓
"What system-level operation am I allowed to perform?"
```

This distinction becomes increasingly important later in security and privilege-management topics.

---

# 16. Access Token

When a user logs into Windows, Windows creates an **access token** representing the user's security context.

Conceptually:

```text
User Login
    ↓
Authentication
    ↓
Windows creates Access Token
    ↓
Contains identity/security information
    ↓
Application starts
    ↓
Application uses token
    ↓
Windows checks access
```

The token can contain information such as:

* User SID
* Group SIDs
* Privileges
* Security attributes

---

# 17. Authentication + Authorization

Remember the difference:

### Authentication

> Who are you?

Example:

```text
Username + Password
        ↓
Identity verified
```

### Authorization

> What are you allowed to access?

Example:

```text
User = Student

Student
   ↓
Read notes
   ↓
Allowed

Student
   ↓
Modify system configuration
   ↓
Not allowed
```

---

# 18. UAC — User Account Control

Windows uses **User Account Control (UAC)** to help prevent unauthorized administrative changes.

For example:

```text
Application
     ↓
Requests administrative action
     ↓
UAC prompt
     ↓
User confirmation
     ↓
Elevation
```

A UAC prompt does not automatically mean that an application is malicious.

It means Windows is requesting confirmation for an operation that requires elevated privileges.

---

# 19. NTFS Permissions

Windows commonly uses the **NTFS** file system.

NTFS supports access control for files and folders.

Important permissions include:

| Permission     | Meaning                                       |
| -------------- | --------------------------------------------- |
| Read           | View file/folder information                  |
| Write          | Create or modify content                      |
| Read & Execute | Read and execute applicable files             |
| Modify         | Read, write, modify and delete                |
| Full Control   | Broad control including permission management |

---

# 20. Example of NTFS Permissions

Suppose we have:

```text
C:\MSK\Courses
```

Permissions might be:

```text
Administrator → Full Control
Teacher       → Modify
Student       → Read & Execute
Guest         → No Access
```

This creates an access model:

```text
                Courses
                   │
        ┌──────────┼──────────┐
        ▼          ▼          ▼
 Administrator   Teacher    Student
 Full Control     Modify      Read
```

---

# 21. Permission Inheritance

Permissions can be inherited from a parent folder.

Example:

```text
C:\MSK
   │
   └── Courses
        │
        ├── Python
        ├── Java
        └── Web
```

If `Courses` has permissions configured for inheritance, child folders may inherit those permissions.

Conceptually:

```text
Parent Folder
     │
     │ inherited permissions
     ▼
Child Folder
     │
     ▼
File
```

Inheritance reduces the need to configure every file individually.

---

# 22. Explicit vs Inherited Permissions

### Explicit Permission

Permission directly assigned to an object.

```text
File → Student → Read
```

### Inherited Permission

Permission received from a parent folder.

```text
Parent Folder
      ↓
Child Folder
      ↓
File
```

This distinction becomes very important when troubleshooting access problems.

---

# 23. Effective Access

A user may receive permissions through multiple groups.

Example:

```text
Sumit
 │
 ├── Students
 │      └── Read
 │
 └── Teachers
        └── Modify
```

The actual access available to the user depends on the complete security configuration.

Therefore, when investigating access problems, do not look only at:

```text
User → Permission
```

Also consider:

```text
User
 ↓
Groups
 ↓
Inherited permissions
 ↓
Explicit permissions
 ↓
Resource
```

---

# 24. File Ownership

Windows resources have an **owner**.

The owner can have special authority related to managing permissions.

Conceptually:

```text
Resource
   │
   ├── Owner
   ├── Permissions
   └── Access rules
```

Ownership and permission are not the same thing.

A person may have access to a file without being its owner.

---

# 25. NTFS Permissions vs Share Permissions

This becomes important when folders are shared over a network.

### NTFS permissions

Control access to the file system.

### Share permissions

Control access through a network share.

Simplified:

```text
Local Access
     ↓
NTFS permissions

Network Access
     ↓
Share permissions
        +
NTFS permissions
```

When accessing a shared folder over a network, both layers can matter.

---

# 26. Viewing File Permissions with `icacls`

Windows provides a command-line utility called:

```text
icacls
```

It can be used to view and manage file permissions.

For today's lab, we will only **inspect** permissions.

Example:

```powershell
icacls "C:\Users\Public"
```

You may see output similar to:

```text
C:\Users\Public
    BUILTIN\Users:(RX)
    BUILTIN\Administrators:(F)
    NT AUTHORITY\SYSTEM:(F)
```

The exact output depends on your Windows configuration.

---

# 27. Common `icacls` Permission Codes

Some common representations include:

| Code | Meaning        |
| ---- | -------------- |
| F    | Full Control   |
| M    | Modify         |
| RX   | Read & Execute |
| R    | Read           |
| W    | Write          |

These codes are useful when reading permission reports.

---

# 28. Windows Services

A **Windows service** is a background program designed to perform a system or application function.

Examples include services responsible for:

* Networking
* Updates
* Security
* Printing
* Logging
* Application functionality

Conceptually:

```text
Windows Starts
      ↓
Services Start
      ↓
Background Tasks
      ↓
Applications / System Functions
```

---

# 29. Service vs Normal Application

A normal application may be started directly by a user.

Example:

```text
Chrome
   ↓
User launches application
```

A service can operate in the background:

```text
Windows
   ↓
Service Manager
   ↓
Service
   ↓
Background operation
```

Some services can start automatically when Windows boots.

---

# 30. Service Startup Types

Services can have different startup configurations.

Common concepts include:

* Automatic
* Automatic (Delayed Start)
* Manual
* Disabled

Example:

```text
Automatic
   ↓
Starts automatically

Manual
   ↓
Starts when requested/triggered

Disabled
   ↓
Cannot normally start until configuration changes
```

**Do not change service startup settings during today's lab.**

---

# 31. Service Status

A service can have states such as:

```text
Running
Stopped
```

You can inspect services using PowerShell:

```powershell
Get-Service
```

To find a specific service:

```powershell
Get-Service | Where-Object {$_.Status -eq "Running"}
```

This is useful for observation and system administration.

---

# 32. Service Accounts

A service may run under a particular account/security context.

Common Windows service identities include:

* Local System
* Local Service
* Network Service
* Specific user account

This matters because the permissions available to the service depend partly on its security context.

---

# 33. Why Service Accounts Matter in Security

Imagine a service has excessive privileges.

Conceptually:

```text
Service
   ↓
Highly privileged account
   ↓
Large amount of system access
```

If that service were compromised, the consequences could potentially be much greater than if it used a restricted account.

Therefore:

> Services should operate with only the privileges they require.

This is another application of **least privilege**.

---

# 34. Viewing Detailed Service Information

You can use:

```powershell
Get-CimInstance Win32_Service
```

For a cleaner view:

```powershell
Get-CimInstance Win32_Service |
Select-Object Name, State, StartMode, StartName
```

You may see:

```text
Name       State    StartMode    StartName
----       -----    ---------    ---------
ServiceA   Running  Auto         LocalSystem
ServiceB   Stopped  Manual       LocalService
```

The actual services on your system will differ.

---

# 35. Service Dependencies

Some services depend on other services.

Example:

```text
Service A
   ↓
requires
   ↓
Service B
```

If Service B is unavailable, Service A may not function correctly.

You can inspect service relationships using Windows administration tools.

Understanding dependencies helps security professionals avoid making unsafe configuration changes.

---

# 36. Security Perspective of Services

When auditing a Windows computer, ask:

```text
Which services are running?
        ↓
Which services start automatically?
        ↓
Which accounts run them?
        ↓
What permissions do they have?
        ↓
Are they actually required?
        ↓
Are they properly maintained?
```

This is a defensive security mindset.

---

# 37. Practical Lab — Windows Access Control & Service Audit

## Lab Objective

Perform a basic security audit of your own Windows computer.

**Do not:**

* Disable services
* Stop critical services
* Modify permissions
* Change user privileges
* Disable Windows Defender
* Disable Windows Firewall
* Modify unknown accounts

Today is an **observation and analysis lab**.

---

## Task 1 — Identify Current User

Run:

```powershell
whoami
```

Then:

```powershell
whoami /user
```

Record:

```text
Username:
SID:
```

---

## Task 2 — List Local Users

Run:

```powershell
Get-LocalUser
```

Create a table:

| User          | Enabled | Notes |
| ------------- | ------- | ----- |
| Administrator |         |       |
| Guest         |         |       |
| Your User     |         |       |

Do not change anything.

---

## Task 3 — List Local Groups

Run:

```powershell
Get-LocalGroup
```

Record at least five groups.

Example:

```text
Administrators
Users
Guests
Remote Desktop Users
Backup Operators
```

---

## Task 4 — Inspect Administrators Group

Run:

```powershell
Get-LocalGroupMember -Group "Administrators"
```

Answer:

1. How many members are present?
2. Is your current account a member?
3. Are there accounts you do not recognize?

**Do not remove or modify any account.**

---

# 38. Task 5 — Check File Permissions

Run:

```powershell
icacls "C:\Users\Public"
```

Record:

```text
Users:
Administrators:
SYSTEM:
Other entries:
```

Then explain:

> Which accounts/groups have broad permissions?

---

# 39. Task 6 — Inspect Services

Run:

```powershell
Get-Service
```

Then:

```powershell
Get-Service | Where-Object {$_.Status -eq "Running"}
```

Answer:

* Approximately how many services are running?
* Why might Windows need background services?
* Why should you avoid disabling an unknown service?

---

# 40. Task 7 — Analyze Service Accounts

Run:

```powershell
Get-CimInstance Win32_Service |
Select-Object Name, State, StartMode, StartName
```

Select **5 services** and record:

| Service   | State | Startup | Service Account |
| --------- | ----- | ------- | --------------- |
| Service 1 |       |         |                 |
| Service 2 |       |         |                 |
| Service 3 |       |         |                 |
| Service 4 |       |         |                 |
| Service 5 |       |         |                 |

---

# 41. Task 8 — Compare Permissions and Privileges

Create this scenario:

```text
User: Student

Group:
Students

File:
PythonNotes.txt

Permission:
Read
```

Now answer:

### Question

Can the student necessarily:

```text
Read the file?       → ?
Modify the file?     → ?
Delete the file?     → ?
Change permissions?  → ?
```

Explain each answer based on permissions.

---

# 42. Mini Project

## Windows Access Control & Service Audit

Prepare a small security report for your own computer.

### Section 1 — User

```text
Current User:
SID:
```

### Section 2 — Local Accounts

```text
Total users:
Enabled users:
Disabled users:
```

### Section 3 — Administrators

```text
Administrators group members:
```

### Section 4 — File Permissions

Analyze:

```text
C:\Users\Public
```

### Section 5 — Services

Select five services and record:

```text
Service
Status
Startup Type
Service Account
```

### Section 6 — Security Recommendations

Write at least five recommendations.

Example:

```text
1. Use standard accounts for normal activities.
2. Apply least privilege.
3. Review administrator membership periodically.
4. Avoid unnecessary services.
5. Keep Windows security controls enabled.
```

---

# 43. Assignment

### Short Answer Questions

1. What is a Windows user account?
2. What is a security principal?
3. What is a SID?
4. What is the difference between a user and a group?
5. What is the principle of least privilege?
6. What is the difference between permission and privilege?
7. What is an access token?
8. What is NTFS?
9. What is permission inheritance?
10. What is the difference between explicit and inherited permissions?
11. What is file ownership?
12. What is a Windows service?
13. What is a service account?
14. Why can highly privileged services create security risk?
15. What is the difference between authentication and authorization?

---

# 44. Practical Assignment

Run the following commands on your own system:

```powershell
whoami
```

```powershell
whoami /user
```

```powershell
Get-LocalUser
```

```powershell
Get-LocalGroup
```

```powershell
Get-LocalGroupMember -Group "Administrators"
```

```powershell
icacls "C:\Users\Public"
```

```powershell
Get-Service
```

```powershell
Get-CimInstance Win32_Service |
Select-Object Name, State, StartMode, StartName
```

Create a report titled:

> **Windows Users, Permissions & Services Security Audit**

---

# 45. Quick Quiz

### Q1. What uniquely identifies a Windows security principal?

A. IP address
B. SID
C. MAC address
D. Hostname

**Answer: B**

---

### Q2. Which principle says users should receive only required access?

A. Defense in Depth
B. Least Privilege
C. Availability
D. Redundancy

**Answer: B**

---

### Q3. Which permission provides the broadest control?

A. Read
B. Write
C. Read & Execute
D. Full Control

**Answer: D**

---

### Q4. What does UAC help control?

A. CPU temperature
B. Administrative elevation
C. Internet speed
D. Disk formatting only

**Answer: B**

---

### Q5. What is a Windows service?

A. A background system/application component
B. A physical hardware device
C. A user password
D. A file extension

**Answer: A**

---

### Q6. What command displays local users?

A. `Get-Service`
B. `Get-Process`
C. `Get-LocalUser`
D. `Get-ComputerInfo`

**Answer: C**

---

### Q7. What command can be used to inspect Windows file permissions?

A. `ping`
B. `icacls`
C. `ipconfig`
D. `tracert`

**Answer: B**

---

### Q8. What is authentication?

A. Determining what a user can access
B. Verifying identity
C. Encrypting a file
D. Starting a service

**Answer: B**

---

### Q9. What is authorization?

A. Verifying identity
B. Determining permitted access
C. Installing Windows
D. Creating a SID

**Answer: B**

---

### Q10. Why are service accounts important?

A. They determine the security context under which services operate
B. They increase internet speed
C. They replace RAM
D. They control monitor resolution

**Answer: A**

---

# 46. Important Terminology

| Term            | Meaning                                                    |
| --------------- | ---------------------------------------------------------- |
| User            | An identity used to access a computer/system               |
| Group           | Collection of users/security principals                    |
| SID             | Security Identifier                                        |
| Permission      | Access rule for a resource                                 |
| Privilege       | System-level right                                         |
| Access Token    | Security context used by processes                         |
| UAC             | User Account Control                                       |
| NTFS            | Windows file system with security features                 |
| Inheritance     | Permissions passed from parent to child                    |
| Owner           | Security principal associated with ownership of a resource |
| Service         | Background system/application component                    |
| Service Account | Identity under which a service runs                        |
| Least Privilege | Giving only required access                                |

---

# 47. Important Security Concepts to Remember

The following chain is extremely important:

```text
USER
  ↓
GROUP MEMBERSHIP
  ↓
SECURITY IDENTIFIER (SID)
  ↓
ACCESS TOKEN
  ↓
PERMISSIONS + PRIVILEGES
  ↓
RESOURCE
  ↓
ACCESS DECISION
```

For services:

```text
WINDOWS
   ↓
SERVICE
   ↓
SERVICE ACCOUNT
   ↓
SECURITY CONTEXT
   ↓
PERMISSIONS / PRIVILEGES
   ↓
SYSTEM RESOURCE
```

---

# 48. Day 07 Final Concept

A Windows security professional should think like this:

```text
                    WINDOWS SECURITY
                           │
        ┌──────────────────┼──────────────────┐
        ▼                  ▼                  ▼
      USERS              GROUPS            SERVICES
        │                  │                  │
        ▼                  ▼                  ▼
       SID           Membership         Service Account
        │                  │                  │
        └──────────┬───────┴──────────┬───────┘
                   ▼                  ▼
             ACCESS TOKEN        SECURITY CONTEXT
                   │                  │
                   └────────┬─────────┘
                            ▼
                    PERMISSIONS
                            │
                            ▼
                       RESOURCE
                            │
                            ▼
                     ACCESS DECISION
```

### The core principle:

> **Cyber security is not only about detecting attacks. It is also about controlling who can access what, under which security context, and with which level of privilege.**

By the end of Day 07, students should be comfortable inspecting **Windows users, groups, SIDs, permissions, access control and services** without making potentially dangerous system changes.

**Next: Day 08 — Windows System Administration & Security Controls**, covering system configuration, administrative tools, Windows security settings, system information, task management, storage, networking configuration, updates, Defender, Firewall and creating a basic Windows security baseline.
