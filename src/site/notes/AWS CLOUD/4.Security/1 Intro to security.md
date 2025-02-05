---
{"dg-publish":true,"permalink":"/AWS CLOUD/4.Security/1 Intro to security/","created":"2024-12-09T19:28:22.645+05:30"}
---


one short security - [aws security - last min rev](../aws%20security%20-%20last%20min%20rev.md)

> [!NOTE]
> NACL = subnet level 
> security group = instance level


## Types of firewall in EC2

In EC2, there are two main types of firewalls:
1. **Security Groups**: Act as virtual firewalls for EC2 instances to control inbound and outbound traffic. They are stateful, meaning if you allow inbound traffic, the response is automatically allowed.
    
2. **Network Access Control Lists (NACLs)**: Operate at the subnet level, controlling inbound and outbound traffic for all instances within a subnet. They are stateless, meaning responses must be explicitly allowed.

### Ransomware
**Ransomware** is a type of malicious software (malware) that encrypts a user's files or locks access to their system, demanding a ransom from the victim in exchange for the decryption key or to regain access. It often spreads through phishing emails, malicious attachments, or compromised websites.

## CIA triad
The **CIA Triad** represents three core principles of information security:

1. **Confidentiality**: Ensures data is only accessible to authorized users.
2. **Integrity**: Ensures data remains accurate and unaltered.
3. **Availability**: Ensures data and systems are accessible when needed.


![](/img/user/AWS CLOUD/4.Security/attachments/Pasted image 20241209194022.png)

## Types of threats

| Threat Name        | Description                                                                                         |
| ------------------ | --------------------------------------------------------------------------------------------------- |
| Malware            | Malicious software that disrupts or gains unauthorized access to computer systems.                  |
| Phishing           | Deceptive emails or websites tricking users into revealing sensitive information.                   |
| DoS/DDoS           | Overloading a system with traffic (DoS) or using multiple sources (DDoS) to render it inaccessible. |
| Man-in-the-Middle  | Interception of communication to eavesdrop, manipulate data, or impersonate parties.                |
| SQL Injection      | Exploiting web application vulnerabilities to gain unauthorized database access.                    |
| Zero-Day Exploit   | Attacks exploiting unknown software vulnerabilities before they are patched.                        |
| Insider Threat     | Misuse of access privileges by individuals within an organization.                                  |
| APT                | Sophisticated, prolonged attacks targeting high-value assets.                                       |
| Ransomware         | Encrypts files or locks systems, demanding ransom for decryption.                                   |
| Social Engineering | Psychological manipulation to deceive users into compromising security.                             |

## What , When , Who
1. **What (Security measures to implement - Security Controls)**:
    - What: Specific security measures or controls like encryption, firewalls, and access controls.
2. **When (When to implement security measures - Security Lifecycle)**:
    - When: Throughout the security lifecycle, from initial deployment to ongoing operations and updates.
3. **Who (Who is responsible for implementing security measures - Security Responsibilities)**:
    - Who: Assigned to administrators, DevOps teams, and security personnel, with clear roles and responsibilities for implementation and maintenance.



##  Security controls

![](/img/user/AWS CLOUD/3.Network/attachments/Pasted image 20241213230336.png)

- **Physical Controls**: Directly protect physical assets, like card readers for building access.
- **Administrative Controls**: Establish policies and procedures, such as requiring card swipes for access.
- **Technical Controls**: Use software or technology, like antivirus programs, to monitor and protect against threats.

![](/img/user/AWS CLOUD/3.Network/attachments/Pasted image 20241213230612.png)


### What is social engineering
Social engineering is a type of security threat where an attacker uses human interaction to manipulate a person into revealing sensitive information.

### What does cloud security strategy define
- what security measures to implemet (security controls)
- when to implement security measures (security lifecycle)
- who is responsible to implement security measures(security responsibility)

### In which phase of sec. lifecycle are security counter measures implemented
In the prevention phase of the secuity life cycle
