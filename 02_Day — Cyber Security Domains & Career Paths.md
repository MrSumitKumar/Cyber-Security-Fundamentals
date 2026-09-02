# Day 02 — Cyber Security Domains & Career Paths

**Course:** Cyber Security & Ethical Hacking Professional Program
**Day:** 02
**Module:** Cyber Security Fundamentals
**Topic:** Cyber Security Domains and Career Paths
**Level:** Beginner

## Learning Objectives

By the end of Day 02, students should be able to:

* Understand the major areas of cyber security.
* Differentiate Red Team, Blue Team, Purple Team, and related roles.
* Understand common cyber security job roles.
* Identify which career path matches their interests.
* Understand the skills required for different security careers.
* Create a basic roadmap for entering cyber security.

---

# 1. Cyber Security is a Large Field

Many beginners think:

> **Cyber Security = Ethical Hacking**

This is not correct.

Ethical hacking is only **one part** of cyber security.

Cyber security includes multiple domains such as:

```text
                    CYBER SECURITY
                          │
       ┌──────────────────┼──────────────────┐
       │                  │                  │
       ↓                  ↓                  ↓
    OFFENSIVE           DEFENSIVE         GOVERNANCE
    SECURITY             SECURITY          & RISK
       │                  │                  │
   Pentesting             SOC              GRC
   Red Team             Blue Team        Compliance
   AppSec               DFIR             Risk
       │                  │
       └──────────┬───────┘
                  ↓
             SECURITY
            ENGINEERING
                  │
        Cloud / IAM / Network
```

A student does **not** need to master everything at once.

The first goal is to understand what each area does.

---

# 2. Major Cyber Security Domains

Let's understand the most important domains.

---

## 2.1 Network Security

Network security focuses on protecting communication networks and network infrastructure.

Examples:

* Routers
* Switches
* Firewalls
* VPNs
* Servers
* Wireless networks
* Network traffic

### Example

Suppose a company has:

```text
Internet
   ↓
Firewall
   ↓
Router
   ↓
Switch
   ↓
Employee Computers
```

A network security professional helps protect this environment.

### Common skills

Students may eventually learn:

* TCP/IP
* DNS
* DHCP
* Routing
* Firewalls
* VPN
* Network monitoring
* Network segmentation
* IDS/IPS

---

# 3. Application Security

Application Security, or **AppSec**, focuses on making software applications secure.

Applications include:

* Websites
* Mobile apps
* APIs
* Desktop applications
* Enterprise software

Security professionals look for weaknesses in application design, development, configuration, and deployment.

### Example

A website contains:

```text
Login
   ↓
Application
   ↓
API
   ↓
Database
```

AppSec professionals ask:

* Is authentication secure?
* Is authorization implemented correctly?
* Is input validated?
* Is sensitive information protected?
* Are dependencies secure?

---

# 4. Web Application Security

Web security is a specialized area of application security focused on web applications.

Examples:

* E-commerce websites
* Banking portals
* Student portals
* SaaS applications
* Online dashboards

Students will later study common web security weaknesses and how to test them safely in authorized environments.

A major reference in this area is the **OWASP Top 10**.

---

# 5. Cloud Security

Modern organizations increasingly use cloud platforms.

Examples include:

* Virtual machines
* Cloud databases
* Object storage
* Containers
* Cloud networks
* Identity services

Cloud security focuses on protecting these environments.

### Important areas

```text
Cloud Security
     │
     ├── Identity
     ├── Access Control
     ├── Networking
     ├── Data Protection
     ├── Logging
     ├── Monitoring
     └── Configuration
```

A common problem in cloud environments is **misconfiguration**.

---

# 6. Endpoint Security

An endpoint is a device connected to a network.

Examples:

* Laptop
* Desktop
* Server
* Mobile device
* Workstation

Endpoint security protects these devices against threats.

Examples of security controls:

* Antivirus
* Endpoint Detection and Response
* Host firewall
* Device management
* Application control
* Security policies

---

# 7. Identity and Access Management

**Identity and Access Management**, commonly called **IAM**, controls who can access what.

The basic concept is:

```text
User
 ↓
Authentication
 ↓
Identity
 ↓
Authorization
 ↓
Resource
```

Example:

An employee may be allowed to access:

```text
Email       → YES
HR Portal   → YES
Payroll     → NO
Admin Panel → NO
```

IAM focuses on ensuring users receive appropriate access.

---

# 8. Security Operations Center — SOC

A **Security Operations Center**, or **SOC**, monitors an organization's environment for suspicious activity.

A simplified SOC workflow:

```text
Systems
   ↓
Logs
   ↓
SIEM / Security Tools
   ↓
Alerts
   ↓
SOC Analyst
   ↓
Investigation
   ↓
Response
```

SOC analysts may investigate:

* Suspicious login attempts
* Malware alerts
* Unusual network traffic
* Account compromise
* Endpoint alerts
* Data access anomalies

---

# 9. Digital Forensics

**Digital Forensics** involves examining digital evidence to understand what happened during an incident.

For example:

```text
Security Incident
       ↓
Evidence Collection
       ↓
Evidence Preservation
       ↓
Analysis
       ↓
Timeline
       ↓
Findings
       ↓
Report
```

Evidence may come from:

* Computers
* Servers
* Disk images
* Memory
* Logs
* Browsers
* Mobile devices
* Cloud environments

---

# 10. Incident Response

Incident Response is the process of responding to security incidents.

A simplified lifecycle:

```text
Preparation
    ↓
Detection
    ↓
Analysis
    ↓
Containment
    ↓
Eradication
    ↓
Recovery
    ↓
Lessons Learned
```

### Example

Suppose an employee's account is compromised.

The security team may:

1. Detect suspicious activity.
2. Investigate the account.
3. Contain the incident.
4. Reset credentials.
5. Investigate affected systems.
6. Restore normal operations.
7. Document what happened.
8. Improve security controls.

---

# 11. Malware Analysis

**Malware** means malicious software.

Examples include:

* Viruses
* Worms
* Trojans
* Ransomware
* Spyware
* Other malicious programs

Malware analysts study suspicious software in controlled environments.

They may try to determine:

* What the file does.
* Which systems it interacts with.
* What indicators it generates.
* How defenders can detect it.

---

# 12. Penetration Testing

Penetration testing, or **pentesting**, is authorized security testing.

A penetration tester attempts to identify and validate security weaknesses within an approved scope.

Typical areas include:

* Network infrastructure
* Web applications
* APIs
* Mobile applications
* Cloud environments
* Internal systems

The objective is:

> **Find security weaknesses before malicious attackers can exploit them.**

---

# 13. Red Team

A **Red Team** represents the offensive side of a security exercise.

The team simulates realistic attacker behavior under defined authorization and rules.

The objective is usually to test:

* Prevention
* Detection
* Response
* Security controls
* Organizational readiness

Red Team activities are broader than simply finding individual vulnerabilities.

---

# 14. Blue Team

The **Blue Team** represents the defensive side.

Blue Teams focus on:

* Monitoring
* Detection
* Investigation
* Prevention
* Incident response
* Hardening
* Threat hunting

Think:

```text
Red Team → Simulates Attack
Blue Team → Detects & Defends
```

---

# 15. Purple Team

Purple Team is not necessarily a completely separate team.

It represents collaboration between offensive and defensive security teams.

```text
       RED TEAM
          ↓
     Attack Simulation
          ↓
       BLUE TEAM
          ↓
     Detection Results
          ↓
       Improvements
          ↓
       Better Security
```

The purpose is to improve security by sharing lessons between offensive and defensive teams.

---

# 16. Security Engineering

Security engineering focuses on designing and implementing security controls.

Examples:

* Firewalls
* IAM systems
* Endpoint security
* Network segmentation
* Secure architectures
* Security monitoring
* Authentication systems

Security engineers often work closely with IT and software engineering teams.

---

# 17. Governance, Risk and Compliance — GRC

**GRC** stands for:

```text
G → Governance
R → Risk
C → Compliance
```

GRC focuses more on organizational security management than hands-on hacking.

### Governance

How an organization manages security.

### Risk

Understanding and managing security risks.

### Compliance

Ensuring the organization follows applicable requirements, policies, standards, or regulations.

---

# 18. Security Awareness

Humans are an important part of security.

Security awareness programs teach employees about:

* Phishing
* Password security
* Social engineering
* Data protection
* Safe browsing
* Device security
* Reporting suspicious activity

Even the strongest technical security controls can be undermined by unsafe human behavior.

---

# 19. Offensive vs Defensive Security

One of the most important distinctions for students:

| Offensive Security       | Defensive Security            |
| ------------------------ | ----------------------------- |
| Finds weaknesses         | Finds and responds to threats |
| Pentesting               | SOC                           |
| Red Team                 | Blue Team                     |
| Vulnerability assessment | Detection                     |
| Security testing         | Incident response             |
| Attack simulation        | Threat hunting                |

Both sides are important.

A strong security professional understands **how attacks work and how defenders detect and prevent them**.

---

# 20. Common Cyber Security Job Roles

Now let's look at actual career roles.

---

## 20.1 SOC Analyst

Main responsibility:

> Monitor and investigate security alerts.

Typical skills:

* Networking
* Windows
* Linux
* Logs
* SIEM
* Incident investigation
* Security fundamentals

Entry-level SOC roles are often a starting point for students entering defensive security.

---

# 21. Penetration Tester

Main responsibility:

> Perform authorized security assessments.

Skills include:

* Networking
* Linux
* Web security
* Vulnerability assessment
* Security testing
* Report writing

---

# 22. Security Engineer

Main responsibility:

> Design, implement, and maintain security controls.

Skills may include:

* Networking
* Operating systems
* Firewalls
* IAM
* Cloud
* Endpoint security
* Security architecture

---

# 23. Cloud Security Engineer

Focus:

> Secure cloud infrastructure and services.

Skills include:

* Cloud fundamentals
* IAM
* Networking
* Logging
* Security configurations
* Infrastructure security
* Automation

---

# 24. Incident Responder

Main responsibility:

> Investigate and respond to security incidents.

Skills:

* Incident response
* Logs
* Networking
* Endpoint security
* Forensics
* Threat intelligence

---

# 25. Digital Forensics Analyst

Main responsibility:

> Analyze digital evidence to understand security incidents.

Skills:

* Operating systems
* File systems
* Logs
* Evidence handling
* Forensic tools
* Investigation techniques

---

# 26. Malware Analyst

Main responsibility:

> Analyze suspicious or malicious software.

Skills may include:

* Operating systems
* Programming
* Assembly fundamentals
* Reverse engineering
* Debugging
* Malware behavior analysis

This is generally a more advanced specialization.

---

# 27. Application Security Engineer

Main responsibility:

> Help development teams build and maintain secure applications.

Skills include:

* Programming
* Web technologies
* APIs
* Secure coding
* Vulnerability assessment
* Threat modeling
* Application security testing

---

# 28. Security Architect

A Security Architect designs security solutions for organizations.

Example:

```text
Internet
   ↓
Firewall
   ↓
DMZ
   ↓
Application Layer
   ↓
Database
   ↓
Monitoring
```

They consider:

* Architecture
* Risk
* Identity
* Network security
* Cloud
* Data protection
* Security controls

This is generally a more experienced role.

---

# 29. Cyber Security Career Map

Students can visualize their career like this:

```text
                  CYBER SECURITY
                        │
       ┌────────────────┼────────────────┐
       ↓                ↓                ↓
   OFFENSIVE         DEFENSIVE          GRC
       │                │                │
   Pentester           SOC             Risk
   Red Team          Blue Team       Compliance
   AppSec           Incident Resp.   Governance
       │                │
       └────────┬───────┘
                ↓
        SECURITY ENGINEERING
                │
       ┌────────┼────────┐
       ↓        ↓        ↓
     Cloud     IAM     Network
    Security Security Security
```

---

# 30. Which Career Should a Beginner Choose?

There is no single "best" cyber security career.

The right path depends on your interests.

### If you enjoy hacking and finding weaknesses:

**Penetration Testing / Red Team**

### If you enjoy monitoring and investigation:

**SOC / Blue Team**

### If you enjoy programming:

**Application Security**

### If you enjoy cloud technology:

**Cloud Security**

### If you enjoy investigating incidents:

**Digital Forensics / Incident Response**

### If you enjoy analyzing malicious software:

**Malware Analysis**

### If you enjoy business, policies and risk:

**GRC**

### If you enjoy designing technical systems:

**Security Engineering / Security Architecture**

---

# 31. Skills Common to Almost Every Security Career

Regardless of specialization, students should build a strong foundation in:

```text
Networking
    +
Operating Systems
    +
Linux
    +
Windows
    +
Security Fundamentals
    +
Scripting
    +
Problem Solving
    +
Documentation
```

Later, specialization can be added.

---

# 32. The Cyber Security Skill Pyramid

A useful way to think about learning:

```text
             SPECIALIZATION
          /       |        \
       Cloud    Pentest     SOC
         |        |          |
         └────────┼──────────┘
                  ↓
          SECURITY KNOWLEDGE
                  ↓
        NETWORKING + SYSTEMS
                  ↓
          COMPUTER BASICS
```

### Important principle

Do not rush directly into advanced hacking tools.

First understand:

> **How computers and networks actually work.**

---

# 33. Tools Are Not the Same as Skills

A beginner may think:

> "If I learn many hacking tools, I will become a hacker."

Not necessarily.

For example, knowing how to run a security tool is less valuable than understanding:

* What the tool is doing.
* Why you are using it.
* What its output means.
* What the limitation is.
* How to validate the result.
* How to document the finding.
* How to fix the underlying issue.

### Remember

> **Tools change. Fundamentals remain valuable.**

---

# 34. Recommended Learning Order

For this 18-month program, students should follow this progression:

```text
Computer Fundamentals
        ↓
Networking
        ↓
Linux + Windows
        ↓
Python + Bash
        ↓
Security Fundamentals
        ↓
Ethical Hacking
        ↓
Network Security
        ↓
Web Security
        ↓
API Security
        ↓
Active Directory
        ↓
SOC / Blue Team
        ↓
Forensics
        ↓
Malware Analysis
        ↓
Cloud Security
        ↓
Advanced Pentesting
        ↓
Security Engineering
        ↓
Capstone
```

This prevents students from trying to learn advanced topics without the necessary foundation.

---

# 35. Day 02 Practical Activity

## Activity: Find Your Security Career Path

Create the following table:

| Question                            | Your Answer |
| ----------------------------------- | ----------- |
| Do I enjoy networking?              | Yes / No    |
| Do I enjoy Linux?                   | Yes / No    |
| Do I enjoy programming?             | Yes / No    |
| Do I enjoy finding vulnerabilities? | Yes / No    |
| Do I enjoy investigating incidents? | Yes / No    |
| Do I enjoy analyzing logs?          | Yes / No    |
| Do I enjoy cloud technology?        | Yes / No    |
| Do I enjoy digital investigation?   | Yes / No    |
| Do I enjoy business/risk?           | Yes / No    |

Then select your **top 2 areas of interest**.

Example:

```text
My interests:

1. Penetration Testing
2. Web Application Security
```

Do not worry if your choice changes later.

---

# 36. Day 02 Assignment

### Assignment 1

Explain the difference between:

1. Red Team
2. Blue Team
3. Purple Team

### Assignment 2

Explain the difference between:

**SOC Analyst vs Penetration Tester**

### Assignment 3

Choose **three cyber security career roles** and write:

* What they do
* Skills required
* Tools/technologies they may use
* What type of person may enjoy the role

### Assignment 4

Create your personal career map:

```text
My Current Knowledge
        ↓
Skills I Need
        ↓
Security Domain I Like
        ↓
Target Job Role
        ↓
Skills Required
        ↓
Projects I Need
```

---

# 37. Day 02 Quick Quiz

### Q1. What does SOC stand for?

A. Security Operations Center
B. System Operating Computer
C. Security Online Control
D. System Operations Cloud

**Answer: A**

---

### Q2. Which team primarily focuses on defense?

A. Red Team
B. Blue Team
C. Black Team
D. Attack Team

**Answer: B**

---

### Q3. Which role commonly investigates security alerts?

A. SOC Analyst
B. UI Designer
C. Database Administrator
D. Graphic Designer

**Answer: A**

---

### Q4. What does GRC stand for?

A. Governance, Risk and Compliance
B. General Risk Control
C. Global Resource Center
D. Governance, Recovery and Cloud

**Answer: A**

---

### Q5. Which area focuses on authorized security testing?

A. Penetration Testing
B. Accounting
C. Graphic Design
D. Data Entry

**Answer: A**

---

### Q6. What is the main purpose of Purple Team activities?

A. Replace the SOC
B. Combine offensive and defensive learning
C. Build websites
D. Manage payroll

**Answer: B**

---

# 38. Day 02 Key Takeaways

Students should remember these points:

1. **Cyber Security is much larger than ethical hacking.**
2. Network Security protects network infrastructure.
3. Application Security protects software.
4. Cloud Security protects cloud environments.
5. SOC teams monitor and investigate security events.
6. Red Teams simulate authorized attacks.
7. Blue Teams defend systems.
8. Purple Team activities improve collaboration between offensive and defensive teams.
9. Digital Forensics investigates digital evidence.
10. Incident Response handles security incidents.
11. GRC focuses on governance, risk, and compliance.
12. Security Engineering focuses on designing and implementing security controls.
13. Different cyber security careers require different skills.
14. Strong fundamentals are more important than memorizing tools.
15. **Authorization is essential whenever security testing is performed.**

## Day 02 Final Concept

```text
                CYBER SECURITY
                       │
       ┌───────────────┼────────────────┐
       ↓               ↓                ↓
    ATTACK            DEFEND           MANAGE
       │               │                │
   Pentesting          SOC              GRC
   Red Team            IR               Risk
   AppSec              DFIR             Compliance
       │               │
       └───────────────┼────────────────┘
                       ↓
              SECURITY ENGINEERING
                       ↓
                SECURE SYSTEMS
```

**Tomorrow's foundation:** Day 03 should move into **Computer & Operating System Fundamentals**, starting with how computers, CPUs, RAM, storage, processes, users, and operating systems work—before students begin deeper hands-on security work.
