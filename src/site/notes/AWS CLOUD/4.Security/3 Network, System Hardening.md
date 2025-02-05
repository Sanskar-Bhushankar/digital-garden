---
{"dg-publish":true,"permalink":"/AWS CLOUD/4.Security/3 Network, System Hardening/","created":"2024-12-11T18:43:25.178+05:30"}
---

one short security - [aws security - last min rev](../aws%20security%20-%20last%20min%20rev.md)

> [!NOTE]
> NACL works at subnet level
> security groups works at ec2 level
> 
# Network Hardening
## Q1. What is difference between AWS systems manager, cloud watch ,cloud trail ?

| **Feature**          | **AWS Systems Manager**                                      | **Amazon CloudWatch**                                  | **AWS CloudTrail**                             |
| -------------------- | ------------------------------------------------------------ | ------------------------------------------------------ | ---------------------------------------------- |
| **Purpose**          | Manage and configure AWS resources securely.                 | Monitor resource performance and logs.                 | Audit and log API calls and account activity.  |
| **Focus**            | Operational management (inventory, patching, secure access). | Metrics, alarms, logs, dashboards for monitoring.      | Governance, compliance, and security auditing. |
| **Use Cases**        | Inventory, patching, automation, secure EC2 access.          | Monitor CPU, memory, application logs, and set alerts. | Track API calls, detect unauthorized changes.  |
| **Scope**            | Instance-level management (EC2 and hybrid resources).        | Resource performance and health metrics.               | Logs activity for AWS account actions.         |
| **Data Tracked**     | Instance configuration, patches, applications.               | Performance metrics, system logs, custom metrics.      | API calls, user actions, and resource changes. |
| **Integration**      | Patch Manager, Session Manager, Run Command.                 | Alarms, SNS, Lambda, dashboards.                       | S3, CloudWatch Logs, EventBridge.              |
| **Retention**        | Depends on configuration (for inventory and logs).           | Configurable for logs and metrics.                     | 90 days default for event history, extendable. |
| **Example Use Case** | Automatically patch EC2 instances.                           | Monitor EC2 instance CPU usage.                        | Identify who deleted an S3 bucket.             |

---
- **Network Hardening**: Layered security to prevent unauthorized access, misuse, and data breaches.
- **Two Main Areas**:
    - **Network Discovery Hardening** – Prevent attackers from mapping networks.
    - **Network Architecture Hardening** – Secure networks through design.

#### **Network Discovery Threats & Prevention**

- **Threats**:
    - **Network Mapping** (ping, traceroute, Nmap) – Reveals topology.
    - **Port Scanning** (Nmap) – Identifies open ports & services.
    - **Traffic Sniffing** (Wireshark) – Captures unencrypted data.
- **Prevention**:
    - Disable **ICMP, SNMP**, and promiscuous mode.
    - Use **switches over hubs**.
    - Encrypt sensitive data.
    - Monitor for suspicious activity (unknown IPs, sequential scans).
    - Limit remote admin access & use **AAA policies**.
    - **AWS:** Use **Amazon Inspector** for vulnerability detection.

#### **Network Architecture Hardening**

- **Firewalls** (Filter traffic based on IPs, ports, protocols)
    - Deny all by default; log exceptions.
    - **AWS:** Security Groups (stateful), Network ACLs (stateless).
- **Intrusion Prevention Systems (IPS)** – Blocks malicious activity.
    - **AWS:** AWS Network Firewall for VPCs.
- **Network Segmentation (Subnetting)**
    - Improves security & performance using **CIDR notation**.
    - **ACLs** act as stateless firewalls at the subnet level.

#### **AWS Security Layers**

- **Security Groups** – Instance-level, stateful.
- **Network ACLs** – Subnet-level, stateless.
- **Combined** for a layered security approach in VPCs.

#### **Key Takeaways**

- Prevent threats (network mapping, port scanning, sniffing).
- Use firewalls, IPS, segmentation, and AAA policies.
- AWS security: Security Groups (stateful) + Network ACLs (stateless).

# System Hardening

- **Goal**: Reduce vulnerabilities to protect systems from attacks.
- **Key Areas**:
    - **Authentication, Authorization, Accounting (AAA)** for access control.
    - **Physical Security**: Restricted access, surveillance, biometrics.
    - **Security Baselines**: Define expected system state for anomaly detection.
    - **Patching**: Regular updates to fix vulnerabilities (**AWS Patch Manager**).

#### **Hardening Methods**

- Turn off unnecessary services.
- Apply security updates regularly.
- Use **group policies** for system control.
- Implement **firewalls, encryption, and least privilege access**.
- **AWS Security Tools**:
    - **AWS Trusted Advisor** – Best practice recommendations.
    - **Amazon GuardDuty** – Threat detection.
    - **AWS Shield** – DDoS protection.
    - **AWS CloudTrail** – Tracks user activity & API usage.

#### **Server & Application Hardening**

- **Servers**: Secure file systems, restrict access, encrypt data.
- **Applications**: Use firewalls, antivirus, encryption, and password policies.
- **Mobile Device Management (MDM)**: Control mobile security (**AWS SSM, AWS Config**).
#### **Key Takeaways**

- Balance **security and usability**.
- Establish **security baselines**.
- Regular **patching & monitoring** is critical.
- Use **AWS security services** for enhanced protection.

---
# notebooklm summarized data (EXTRA THEORY)

## Network hardening
**Core Concepts**

- **Network Hardening** is a layered security approach focused on prevention. It aims to protect networks from unauthorised access, misuse, modification, or destruction, maintaining network usability and data integrity. It combines policies, procedures, and hardware/software solutions.
- **Two Main Areas of Network Hardening:**
    - **Network discovery hardening**: Preventing attackers from mapping the network.
    - **Network architecture security hardening**: Improving network security through design.
- **Network Security Threats** are attempts to compromise a network. They typically begin with reconnaissance to discover network information and exploit vulnerabilities.
    - Key discovery threats: **Network mapping, port scanning, and traffic sniffing**.

**Network Discovery Threats & Prevention**

- **Network Mapping:** Exposes the network topology, including devices and hosts, using tools like **ping, traceroute, and Nmap**.
- **Port Scanning:** Reveals available protocols and services by scanning ports. **Nmap** is a common port scanning tool.
- **Traffic Sniffing:** Captures data passing through the network, including unencrypted data. Tools like **Wireshark** are used.
- **Preventing Network Discovery:**
    - **Restrict or disable network discovery protocols** such as **ICMP** and **SNMP**.
    - **Disable promiscuous mode** on NICs.
    - Use **switches** instead of **hubs**.
    - **Encrypt sensitive data**.
    - In AWS, use **Amazon Inspector** to discover network exposure vulnerabilities.
    - Monitor for suspicious activities like unknown IP addresses and sequential port scans.
    - Limit remote administration access.
    - Implement **AAA (authentication, authorization, and accounting)** policies.

**Network Architecture Hardening**

- **Goal:** Enhance security through network design improvements.
- **Methods**:
    - **Adding Security Components:**
        - **Network Firewalls:** Filter traffic based on rules (source/destination IPs, ports, protocols).
            - Best practices: Deny all traffic by default, log exceptions, place firewalls close to traffic sources. Firewalls create network zones with different security levels.
        - In AWS, **security groups** act as instance-level firewalls with allow rules. Security groups are **stateful**.
        - **Intrusion Prevention Systems (IPS):** Actively protect against threats by monitoring traffic and blocking malicious activity. Uses techniques such as anomaly and signature based detection.
        - **AWS Network Firewall** provides IPS features for VPCs.
    - **Network Segmentation (Subnetting):** Dividing a large network into smaller, logical subnets.
        - Uses **CIDR notation** to define IP ranges.
        - Improves manageability and performance.
        - **Network Access Control Lists (ACLs):** Act as stateless firewalls at the subnet level in AWS, controlling traffic based on rules.

**AWS Specifics**

- **Security groups** provide instance-level protection and are stateful.
- **Network ACLs** provide subnet-level protection and are stateless.
- Together, Security groups and Network ACLs create a layered approach to security in a VPC.

**Key Takeaways**

- Network hardening is crucial for preventing network attacks.
- Key threats include network mapping, port scanning, and traffic sniffing.
- Effective techniques include disabling discovery protocols, limiting remote access, using firewalls, segmenting networks, and implementing AAA policies.
- In AWS, VPC security groups and network ACLs act as firewalls.

By implementing these techniques, networks can be made significantly more robust against both internal and external threats.

---
## System hardening

**Core Concept: Systems Hardening**

- **Systems hardening** is the process of securing computing systems to protect them from attacks.
- It involves reducing the number of running services and using tools to make systems more secure.
- The goal is to make systems as "hack-proof" as possible.
- A balance must be struck between security and productivity. Overly strict security measures can make systems difficult to use.

**Systems Hardening in the Security Lifecycle**

- Systems hardening is a **preventative measure**.
- The security lifecycle includes **prevention, detection, response, and analysis**.
- Systems hardening is the first line of defence.

**Key Security Facets**

- A comprehensive hardening solution considers:
    - **Authentication:** Verifying the user's identity.
    - **Authorization:** Confirming a user has permission to access a resource.
    - **Accounting:** Gathering usage information for auditing and billing.

**Physical Security**

- Physical security is essential to systems hardening.
- This includes:
    - Restricting access to facilities.
    - Designing buildings to withstand disasters.
    - Using measures such as surveillance, alarms, security guards, and biometric identification.

**Types of Systems to Harden**

- Various systems can be hardened, including:
    - Desktops.
    - Servers.
    - Mobile phones.
    - Applications.
- Hardening eliminates or reduces attacks by patching vulnerabilities, turning off non-essential services, configuring security controls and deactivating unused network ports.
- **Server hardening** focuses on securing server data, ports, components and permissions using advanced security measures at the hardware, firmware and software layers.
- **Software application hardening** concentrates on securing applications running on a server.

**Security Baselines**

- A **baseline** defines the expected state of a system, providing a starting point for securing it.
- It allows for quick detection of anomalies and is updated to reflect changes.
- Without a baseline, it's difficult to identify security deviations.
- Baselines can be derived from system documentation.

**How to Harden Systems**

- Common ways to harden systems:
    - **Turn off unnecessary services**: Reduces attack opportunities.
    - **Control operations through group policies**: Centralises configuration and management of systems.
    - **Regularly apply patches and updates**: Protects against malware and exploits.
- Systems are not pre-hardened by default.
- Activating only necessary services reduces the risk of an attacker compromising a vulnerability.

**Patching**

- A **patch** fixes weaknesses, performance issues, and improves security.
- Patches can be for firmware, OS, applications or other software.
- Patches come as updates or service packs.
- **Patch Manager**, a feature of AWS Systems Manager, automates patching.

**Systems Hardening Recommendations**

- **Client systems:** Turn on antivirus and firewalls, run fewer applications, apply updates, control downloads, and limit removable media.
- **Server systems:** Restrict physical access, use dedicated roles, secure file systems, use encryption and PKI, apply updates and monitor the environment.

**Software Application Hardening**

- Involves updating security measures for standard and third party applications.
- Examples: Using application firewalls, antivirus software, data encryption and password management.
- Using CPUs that support Intel Software Guard Extensions (SGX) can enhance security by creating memory enclaves to protect sensitive information.
- AWS offers best practices that include security groups, AWS IAM, least privilege and access control lists.

**Server Hardening (Specific Examples)**

- **FTP server:** Deactivate anonymous mode, use IP filtering, and maintain quotas.
- **Directory services server:** Implement strong authentication, monitor events, and activate permission restrictions.
- **DHCP server:** Activate port security, monitor, and isolate roles.
- **DNS server:** Use DNSSEC with trusted servers and fix writable cache problems to protect against pharming.
- **SFTP (Secure File Transfer Protocol)** is preferable to FTP because it is secure.

**Mobile Device Management (MDM)**

- MDM solutions are used to secure and control mobile devices.
- MDM is especially important when companies allow BYOD (bring your own device).
- AWS offers services equivalent to MDM solutions such as AWS System Manager and AWS Config.

**Training and Education**

- Training and education are effective defenses against social engineering and phishing attacks.
- Employees must be trained on policies, and policies must be enforced.
- Consequences for noncompliance are important.
- Social engineering attempts to bypass security controls by deceiving individuals.

**Systems Hardening Tools (AWS)**

- AWS provides tools to help harden systems.
- Key tools:
    - **AWS Trusted Advisor:** Provides recommendations based on best practices.
    - **Amazon GuardDuty:** A threat detection service that monitors AWS accounts for malicious activity.
    - **AWS Shield**: A managed DDoS protection service
    - **AWS CloudTrail:** Tracks user activity and API usage for auditing and security monitoring.
- **Amazon GuardDuty** uses threat intelligence feeds and machine learning to identify unusual or unauthorised activity.
- GuardDuty monitors data sources such as VPC Flow Logs, CloudTrail logs and DNS logs.
- It also provides additional data points to help identify the source of the activity.

**Checkpoint Questions**

- Common ways to harden systems: Turn off unnecessary services, implement corporate policies, and apply security updates.
- The purpose of patching is to repair vulnerabilities discovered after software release.
- **Amazon GuardDuty** uses threat intelligence feeds to identify unexpected activity.

**Key Takeaways**

- The goal of systems hardening is to **reduce vulnerabilities** to minimise security risks.
- Effective techniques include establishing security baselines, turning off unnecessary services, and applying patches regularly.
- **Systems hardening must balance restrictions with usability**.

