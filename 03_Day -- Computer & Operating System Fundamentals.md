# Day 03 — Computer & Operating System Fundamentals

**Course:** Cyber Security & Ethical Hacking Professional Program
**Day:** 03
**Module:** Cyber Security Fundamentals
**Topic:** Computer & Operating System Fundamentals
**Level:** Beginner

## Learning Objectives

By the end of Day 03, students should be able to:

* Understand how a computer system works at a high level.
* Understand CPU, RAM, storage, and input/output.
* Understand the difference between hardware and software.
* Understand what an operating system does.
* Understand processes, programs, and services.
* Understand users, accounts, and permissions.
* Understand why OS knowledge is important for cyber security.
* Identify basic security risks related to operating systems.

---

# 1. Why Should a Cyber Security Student Learn Computer Fundamentals?

Before learning ethical hacking, students need to understand the systems they are protecting or testing.

For example, if you want to secure a server, you should understand:

* How the server works.
* Which operating system it uses.
* Which processes are running.
* Which users have access.
* Which files exist.
* Which services are active.
* How applications communicate with the OS.

Therefore:

> **You cannot properly secure a system if you do not understand how the system works.**

---

# 2. What is a Computer?

A **computer** is an electronic system that receives data, processes it, stores it, and produces information.

A simplified model is:

```text
Input
  ↓
Processing
  ↓
Output
  ↓
Storage
```

Example:

When you type:

```text
10 + 20
```

the computer:

```text
Input → 10 + 20
          ↓
       CPU processes
          ↓
Output → 30
```

---

# 3. Hardware vs Software

A computer has two major components:

```text
Computer
   ├── Hardware
   └── Software
```

## Hardware

Physical components that you can touch.

Examples:

* CPU
* RAM
* SSD/HDD
* Keyboard
* Mouse
* Monitor
* Network card
* Motherboard

## Software

Programs and instructions that run on the hardware.

Examples:

* Windows
* Linux
* macOS
* Chrome
* VS Code
* Python
* Antivirus software

### Easy way to remember

> **Hardware = What you can physically touch**
> **Software = Instructions that run on the hardware**

---

# 4. Main Components of a Computer

The most important components for today's lesson are:

```text
CPU
RAM
Storage
Motherboard
GPU
Network Interface
Input/Output Devices
```

Let's understand each one.

---

# 5. CPU — Central Processing Unit

The **CPU** is responsible for executing instructions.

It performs calculations and controls many operations performed by software.

Think of the CPU as the computer's:

> **Instruction execution engine**

For example:

```text
Python Program
      ↓
Instructions
      ↓
CPU
      ↓
Results
```

---

# 6. CPU Cores

Modern CPUs generally have multiple cores.

For example:

```text
CPU
├── Core 1
├── Core 2
├── Core 3
└── Core 4
```

Multiple cores allow a system to perform multiple tasks concurrently.

However, the exact behavior depends on the operating system, applications, workload, and CPU architecture.

---

# 7. CPU and Cyber Security

Why does a security student care about the CPU?

Because security concepts involve:

* Processes
* Memory
* Instructions
* Privilege levels
* Virtualization
* Malware behavior
* Exploit mitigation
* System architecture

Later in the course, students will learn how applications interact with system resources.

---

# 8. RAM — Random Access Memory

**RAM** is temporary working memory used by the computer.

When programs are running, they use RAM.

Example:

```text
Open Chrome
     ↓
Program loaded into RAM
     ↓
CPU executes instructions
```

If you open:

* Browser
* VS Code
* Music player
* Python
* Multiple tabs

they consume memory.

---

# 9. RAM is Volatile

RAM is generally **volatile memory**.

This means its contents are lost when power is removed.

Example:

```text
Computer ON
   ↓
RAM contains active data
   ↓
Power OFF
   ↓
RAM contents disappear
```

This is different from persistent storage.

---

# 10. Storage

Storage keeps data even when the computer is powered off.

Examples:

* SSD
* HDD
* USB drive

Storage may contain:

* Operating system
* Applications
* Documents
* Photos
* Databases
* Logs
* Configuration files

Example:

```text
SSD
├── Operating System
├── Applications
├── User Files
└── Logs
```

---

# 11. RAM vs Storage

This is a common beginner question.

| RAM                                          | Storage                       |
| -------------------------------------------- | ----------------------------- |
| Temporary working memory                     | Persistent storage            |
| Usually volatile                             | Non-volatile                  |
| Used by running programs                     | Stores files and programs     |
| Generally faster                             | Generally slower than RAM     |
| Contents normally disappear after power loss | Data remains after power loss |

### Simple analogy

Think of:

**RAM = Study table**

**Storage = Bookshelf**

You take the books you currently need from the bookshelf and place them on your study table.

---

# 12. Motherboard

The **motherboard** is the main circuit board that connects major components.

It provides communication pathways between components such as:

* CPU
* RAM
* Storage
* GPU
* Network devices
* Peripheral devices

Simplified:

```text
          CPU
           │
           │
RAM ─── Motherboard ─── Storage
           │
           ├── GPU
           │
           └── I/O Devices
```

---

# 13. Input Devices

Input devices allow users or systems to provide data to a computer.

Examples:

* Keyboard
* Mouse
* Microphone
* Camera
* Touchscreen

Example:

```text
Keyboard
    ↓
Computer
```

---

# 14. Output Devices

Output devices present information from the computer.

Examples:

* Monitor
* Printer
* Speakers
* Projector

Example:

```text
Computer
    ↓
Monitor
```

---

# 15. Network Interface

A computer needs a network interface to communicate over a network.

Examples:

* Ethernet adapter
* Wi-Fi adapter

It allows a system to communicate with:

* Other computers
* Servers
* Routers
* Internet services

This will become extremely important when we study networking.

---

# 16. What is Software?

Software is a collection of instructions that tells a computer what to do.

Two broad categories are:

```text
Software
├── System Software
└── Application Software
```

---

# 17. System Software

System software helps operate and manage the computer.

Examples:

* Operating systems
* Device drivers
* System utilities

The most important system software for today's lesson is the **Operating System**.

---

# 18. What is an Operating System?

An **Operating System**, or **OS**, is software that manages computer hardware and provides services for applications and users.

Common operating systems:

* Windows
* Linux
* macOS
* Android
* iOS

A simplified architecture:

```text
User
 ↓
Applications
 ↓
Operating System
 ↓
Hardware
```

---

# 19. Why Do We Need an Operating System?

Imagine running a computer without an operating system.

Every application would need to directly manage:

* CPU
* Memory
* Storage
* Keyboard
* Display
* Network devices

That would be extremely difficult.

The operating system provides an abstraction layer.

```text
Application
     ↓
Operating System
     ↓
Hardware
```

This makes it easier for applications to use system resources.

---

# 20. Major Responsibilities of an Operating System

An OS manages many resources.

Important responsibilities include:

### 1. Process Management

Manages running programs and processes.

### 2. Memory Management

Manages RAM and memory allocation.

### 3. File Management

Manages files and directories.

### 4. User Management

Manages users and accounts.

### 5. Device Management

Communicates with hardware devices.

### 6. Security

Provides mechanisms such as:

* Authentication
* Authorization
* Permissions
* Isolation
* Security policies

### 7. Networking

Provides network communication capabilities.

---

# 21. Kernel

The **kernel** is a central component of an operating system.

It manages interactions between software and hardware.

Simplified:

```text
Applications
     ↓
System Calls
     ↓
Kernel
     ↓
Hardware
```

The kernel has a highly privileged role.

This makes kernel security extremely important.

---

# 22. User Space vs Kernel Space

Operating systems generally separate applications from highly privileged system operations.

A simplified model:

```text
User Space
────────────────────
Applications
Browsers
Editors
Python Programs
────────────────────
Kernel Space
────────────────────
Operating System Kernel
────────────────────
Hardware
```

Applications normally operate with fewer privileges than the kernel.

This separation helps limit the damage a normal application can cause.

---

# 23. What is a Program?

A **program** is a set of instructions designed to perform a task.

Examples:

* Calculator
* Web browser
* Text editor
* Python script

A program stored on disk is not necessarily actively executing.

---

# 24. What is a Process?

A **process** is an instance of a program that is currently executing.

Example:

```text
Program:
Chrome

When running:
Chrome Process
```

If you open multiple instances or components, the operating system may create multiple processes.

### Important distinction

> **Program = instructions**
> **Process = executing instance**

---

# 25. Program vs Process

| Program             | Process                     |
| ------------------- | --------------------------- |
| Stored instructions | Running instance            |
| Exists on storage   | Uses system resources       |
| Passive             | Active                      |
| Example: `app.exe`  | Running application process |

---

# 26. What is a Service?

A **service** is a background process or system component that provides a specific function.

Examples may include:

* Web server service
* Database service
* Logging service
* Network service

A server may have:

```text
Operating System
      ↓
Services
├── Web Server
├── Database
├── SSH
└── Logging
```

From a security perspective, unnecessary services can increase the attack surface.

---

# 27. What is an Account?

An operating system uses accounts to identify users.

Example:

```text
Computer
├── Administrator
├── Student
└── Guest
```

Different accounts can have different permissions.

---

# 28. Administrator vs Standard User

A standard user generally has limited privileges.

An administrator has much broader privileges.

Example:

```text
Standard User
 ├── Open applications
 ├── Create personal files
 └── Limited system changes

Administrator
 ├── Install software
 ├── Change system settings
 ├── Manage users
 └── Access protected resources
```

Exact permissions depend on the operating system and configuration.

---

# 29. Principle of Least Privilege

One of the most important security principles is:

> **Give users and applications only the permissions they actually need.**

Example:

An employee who only needs to read a document should not automatically receive permission to delete the entire database.

```text
Required Access
      ↓
Minimum Necessary Permission
```

This reduces potential damage if an account or application is compromised.

---

# 30. Authentication

Authentication answers:

> **Who are you?**

Common authentication factors include:

* Password
* PIN
* Security key
* Biometric
* One-time code

Example:

```text
Username
   +
Password
   ↓
Authentication
   ↓
Identity Verified
```

---

# 31. Authorization

Authorization answers:

> **What are you allowed to do?**

Example:

```text
User → Login
        ↓
   Authenticated
        ↓
   Check Permissions
        ↓
Read File → YES
Delete File → NO
```

Remember Day 01:

> **Authentication = Who are you?**
> **Authorization = What can you access/do?**

---

# 32. File System

An operating system needs a way to organize files.

This is handled by a **file system**.

Examples include:

* NTFS
* FAT32
* exFAT
* ext4
* APFS

A file system manages information such as:

* Files
* Directories
* Metadata
* Permissions
* Storage allocation

---

# 33. Files and Directories

A simple structure:

```text
Computer
│
└── Users
    │
    └── Student
        │
        ├── Documents
        ├── Downloads
        ├── Pictures
        └── Projects
```

Security professionals need to understand where important files and configurations are stored.

---

# 34. File Permissions

Permissions determine what users can do with files.

Common concepts include:

```text
Read
Write
Execute
```

For example:

```text
File: report.txt

Student → Read
Teacher → Read + Write
Administrator → Full Control
```

Incorrect permissions can create security vulnerabilities.

---

# 35. Windows vs Linux

Students will work with both Windows and Linux during the course.

| Windows                      | Linux                                            |
| ---------------------------- | ------------------------------------------------ |
| Common in business desktops  | Very common in servers and security environments |
| GUI-focused                  | Strong command-line environment                  |
| NTFS commonly used           | Multiple file systems available                  |
| PowerShell / Command Prompt  | Shells such as Bash                              |
| Active Directory widely used | Strong server/cloud presence                     |

Neither is universally "better."

Each has different use cases.

---

# 36. Why Linux is Important for Cyber Security

Linux is widely used in:

* Servers
* Cloud infrastructure
* Networking
* Containers
* Security tools
* Development environments

Security professionals often use Linux because of its:

* Command-line capabilities
* Automation
* Flexibility
* Open-source ecosystem
* Administrative tools

Later, we will study Linux in much greater detail.

---

# 37. Why Windows is Important for Cyber Security

Windows remains extremely important in enterprise environments.

Security professionals may need to understand:

* Windows users
* Services
* Event Logs
* PowerShell
* File permissions
* Group Policy
* Active Directory
* Endpoint security

This is why the course covers both Linux and Windows.

---

# 38. What is a Log?

A **log** is a record of events generated by a system, application, or service.

Examples:

```text
User Login
Application Error
Network Connection
Service Started
File Access
Security Alert
```

Example:

```text
10:30 AM → User logged in
10:35 AM → Application started
10:42 AM → Failed authentication attempt
```

Logs become extremely important in SOC and digital forensics.

---

# 39. Why Logs Matter in Cyber Security

Suppose an account was compromised.

Security analysts may examine logs to determine:

```text
Who logged in?
      ↓
When?
      ↓
From where?
      ↓
What happened afterward?
      ↓
Which systems were accessed?
```

Therefore:

> **Logs provide valuable evidence about system activity.**

---

# 40. Attack Surface

The **attack surface** is the collection of exposed points where an attacker could potentially interact with or attempt to compromise a system.

For example:

```text
Company Server
├── Web Application
├── API
├── SSH
├── Database
├── Network Services
└── User Accounts
```

Each unnecessary exposed service or weak configuration can potentially increase security risk.

---

# 41. Basic OS Security Principles

A secure operating system environment should generally follow principles such as:

### 1. Keep Software Updated

Security updates can fix known vulnerabilities.

### 2. Use Strong Authentication

Avoid weak and reused passwords.

### 3. Apply Least Privilege

Do not give unnecessary administrative access.

### 4. Disable Unnecessary Services

Reduce the attack surface.

### 5. Monitor Logs

Look for unusual activity.

### 6. Use Security Controls

Examples:

* Firewall
* Endpoint protection
* Access controls
* Encryption

### 7. Maintain Backups

Backups help with recovery after incidents.

---

# 42. Day 03 Practical Lab

Today should be a **safe local lab exercise**.

Students can inspect their own computer.

## Task 1 — Identify Your OS

Record:

```text
Operating System:
Version:
Architecture:
Computer Name:
```

Example:

```text
OS: Windows
Version: Windows 11
Architecture: 64-bit
```

---

## Task 2 — Identify Hardware

Find:

* CPU
* RAM
* Storage
* Network adapter

Create:

| Component       | Your System |
| --------------- | ----------- |
| CPU             | __________  |
| RAM             | __________  |
| Storage         | __________  |
| Network Adapter | __________  |

---

## Task 3 — Observe Running Processes

Open the system's process manager.

For example, on Windows you can use **Task Manager**.

Observe:

* Process name
* CPU usage
* Memory usage
* Number of processes

Do **not** terminate unfamiliar processes just for experimentation.

The objective today is observation.

---

## Task 4 — Identify Services

Find the services running on your operating system.

Record five services and write:

```text
Service Name
Purpose
Running / Stopped
```

---

## Task 5 — Explore User Accounts

Identify:

* Current username
* Account type
* Other local accounts, where appropriate

Do not change or delete accounts during this exercise.

---

# 43. Day 03 Mini Project

## "Know Your Computer"

Students should prepare a one-page system report.

### Required sections

```text
1. Operating System
2. CPU
3. RAM
4. Storage
5. Network Adapter
6. Current User
7. Five Running Processes
8. Five Services
9. File System
10. Three Security Recommendations
```

### Example security recommendations

```text
1. Keep OS updated.
2. Use a strong account password.
3. Avoid unnecessary administrator privileges.
```

---

# 44. Day 03 Assignment

### Question 1

Explain the difference between:

**RAM vs Storage**

### Question 2

Explain:

**Program vs Process**

### Question 3

What is the role of an operating system?

### Question 4

Explain:

**Authentication vs Authorization**

### Question 5

What is the principle of least privilege?

### Question 6

Why are logs important to a cyber security professional?

### Question 7

Why should a security professional understand both Windows and Linux?

---

# 45. Day 03 Quick Quiz

### Q1. Which component executes instructions?

A. SSD
B. CPU
C. Keyboard
D. Monitor

**Answer: B**

---

### Q2. Which memory is normally volatile?

A. SSD
B. HDD
C. RAM
D. USB storage

**Answer: C**

---

### Q3. What manages hardware and provides services to applications?

A. Operating System
B. Keyboard
C. Monitor
D. Database

**Answer: A**

---

### Q4. What is a process?

A. A file stored on disk
B. A running instance of a program
C. A hardware component
D. A network cable

**Answer: B**

---

### Q5. Authentication answers:

A. What can you access?
B. Who are you?
C. What is your IP?
D. Which CPU do you have?

**Answer: B**

---

### Q6. Authorization answers:

A. Who are you?
B. What are you allowed to access?
C. What is your password?
D. What is your operating system?

**Answer: B**

---

### Q7. Which principle recommends giving only necessary permissions?

A. Defense in Depth
B. Least Privilege
C. Availability
D. Redundancy

**Answer: B**

---

### Q8. Why are logs useful?

A. They increase screen brightness
B. They record system and application events
C. They replace RAM
D. They install operating systems

**Answer: B**

---

# 46. Day 03 Important Terminology

| Term            | Meaning                                                  |
| --------------- | -------------------------------------------------------- |
| CPU             | Executes instructions                                    |
| RAM             | Temporary working memory                                 |
| Storage         | Persistent data storage                                  |
| OS              | Manages hardware and provides system services            |
| Kernel          | Core privileged component of an OS                       |
| Program         | Set of instructions                                      |
| Process         | Running instance of a program                            |
| Service         | Background component providing a function                |
| User            | Identity/account interacting with a system               |
| Permission      | Defines allowed actions                                  |
| Authentication  | Verifies identity                                        |
| Authorization   | Determines permitted access/actions                      |
| File System     | Organizes and manages stored data                        |
| Log             | Record of system/application events                      |
| Attack Surface  | Potentially exposed points for interaction or compromise |
| Least Privilege | Give only required permissions                           |

---

# 47. Day 03 Key Takeaways

Students should remember:

1. A computer consists of hardware and software.
2. The CPU executes instructions.
3. RAM provides temporary working memory.
4. Storage retains data persistently.
5. The operating system manages hardware and system resources.
6. The kernel is a highly privileged core component of the OS.
7. A program is different from a running process.
8. Services provide background functionality.
9. Users and permissions control access to resources.
10. Authentication verifies identity.
11. Authorization determines permitted access/actions.
12. Least privilege reduces unnecessary access.
13. Windows and Linux are both important to security professionals.
14. Logs are valuable for monitoring and investigation.
15. Unnecessary exposed services can increase the attack surface.

---

# 48. Day 03 Final Concept

The complete picture is:

```text
                 USER
                   ↓
             APPLICATION
                   ↓
                PROCESS
                   ↓
           OPERATING SYSTEM
                   ↓
                KERNEL
                   ↓
        ┌──────────┼──────────┐
        ↓          ↓          ↓
       CPU        RAM       STORAGE
        │          │          │
        └──────────┼──────────┘
                   ↓
              NETWORK / I/O
```

From a **cyber security perspective**, every layer matters.

A security professional should continuously ask:

> **Who can access this system?**
> **What can they access?**
> **Which processes are running?**
> **Which services are exposed?**
> **What permissions exist?**
> **What events are being logged?**
> **What could go wrong if one component is compromised?**

That mindset will become the foundation for the networking, Linux, ethical hacking, SOC, penetration testing, and security engineering modules that follow.
