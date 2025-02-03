---
{"dg-publish":true,"permalink":"/aws-cloud/aws-security-last-min-rev/","title":"aws security - last min rev","tags":["aws-security-oneshot","aws","security"],"created":"2025-02-02T16:32:08.884+05:30"}
---



> [!AWS SECURITY]
> **AWS ACM:** A service to manage certificates for AWS services, simplifying their use and renewal.
> 
> **AWS Identity Management Services:**
> 1. **AWS SSO:** Centralizes SSO access to AWS accounts.
> 2. **Amazon Cognito:** Manages user authentication for apps.
> 3. **AWS IAM:** Controls access to AWS resources using policies.
> 
>  IAM is free and global, not region-specific.



## Types of firewall in EC2

In EC2, there are two main types of firewalls:

1. **Security Groups**: Act as virtual firewalls for EC2 instances to control inbound and outbound traffic. They are stateful, meaning if you allow inbound traffic, the response is automatically allowed.
2. **Network Access Control Lists (NACLs)**: Operate at the subnet level, controlling inbound and outbound traffic for all instances within a subnet. They are stateless, meaning responses must be explicitly allowed.

---
## Prevention in security Lifecycle

![](app://8d5af57fa78ee23374e97ae12e4d75bd89bc/C:/Users/omkar/OneDrive/Documents/Sanskar/AWS%20CLOUD/4.Security/attachments/Pasted%20image%2020241211173920.png?1733918960686)

---
### AWS System Manager Inventory Function ss

![](app://8d5af57fa78ee23374e97ae12e4d75bd89bc/C:/Users/omkar/OneDrive/Documents/Sanskar/AWS%20CLOUD/4.Security/attachments/Pasted%20image%2020241211180756.png?1733920676371)

The AWS Systems Manager inventory function offers centralized management, detailed instance inventory, automation for tasks like software and patch management, enhanced security through up-to-date instance information, and operational insights for improved efficiency within AWS environments.

---
## Types of prevention measures (Onion layers)

![](app://8d5af57fa78ee23374e97ae12e4d75bd89bc/C:/Users/omkar/OneDrive/Documents/Sanskar/AWS%20CLOUD/4.Security/attachments/Pasted%20image%2020241211184141.png?1733922701395)

---
## OSI MODEL

- Layers: Physical
- Data link
- Network, 
- Transport, 
- Session, 
- Presentation, 
- Application.

---
### WHICH THREE TASKS ARE PERFORMED AT THE PREVENTION PHASE OF SECURITY LIFE CYCLE

- Identify assets to be protected
- Assess  asset vulnerability
- implement countermeasures

---
# Network Hardening
- **Prevents** unauthorized access, misuse, and data breaches.
- **Two Types**:
    - **Discovery Hardening** – Blocks network mapping.
    - **Architecture Hardening** – Secures design.
#### **Threats & Prevention**

- **Network Mapping** (ping, traceroute, Nmap) – **Disable ICMP, SNMP**.
- **Port Scanning** (Nmap) – **Monitor & limit access**.
- **Traffic Sniffing** (Wireshark) – **Encrypt data, use switches**.
- **AWS:** Use **Amazon Inspector** for vulnerabilities.
#### **Architecture Hardening**

- **Firewalls** – Deny all by default.
- **IPS** – Blocks threats (**AWS Network Firewall**).
- **Segmentation** – Uses **CIDR & ACLs** for subnet security.
#### **AWS Security**

- **Security Groups** – Instance-level, **stateful**.
- **Network ACLs** – Subnet-level, **stateless**.
- **Layered** security for VPCs.

🔹 **Focus**: Block threats, encrypt data, limit access, monitor traffic.
1. **AWS Systems Manager**: Focused on managing and automating tasks on AWS resources (e.g., patching, inventory, secure shell access).
2. **Amazon CloudWatch**: Provides real-time monitoring of AWS resources and applications (e.g., performance metrics and logs).
3. **AWS CloudTrail**: Tracks all API and console actions in AWS for auditing and compliance.

**Key Difference**:
- Systems Manager = Manage resources.
- CloudWatch = Monitor resources.
- CloudTrail = Track actions on resources.

---
# System hardening

- **Goal**: Secure systems by reducing vulnerabilities while balancing usability and productivity.
- **Core Principles**: Focus on **authentication**, **authorization**, and **accounting**.
- **Key Steps**:
  - Disable unnecessary services.
  - Apply patches and updates regularly.
  - Establish **security baselines** to detect anomalies.
  - Use group policies for centralized control.

![](/img/user/AWS CLOUD/attachments/Pasted image 20250202190751.png)

- **Types of Hardening**:
  - **Server Hardening**: Secure data, ports, and permissions.
  - **Application Hardening**: Update security measures for standard and third-party apps.
  - **Mobile Device Management (MDM)**: Secure BYOD environments.
  `For securing mobile devices, use a mobile device management (MDM) solution. Use MDM to enforce corporate and security policies regarding the use of devices. Companies that permit bring your own device (BYOD) should implement MDM`
- **Physical Security**: Restrict access, use surveillance, and design disaster-resistant facilities.
- **AWS Tools**:
  - **Trusted Advisor**: Best practice recommendations.
  - **GuardDuty**: Threat detection using machine learning.
  - **Shield**: DDoS protection.
  - **CloudTrail**: Tracks user activity for auditing.
- **Training**: Educate employees to combat social engineering and phishing.
- **Key Takeaway**: Harden systems by minimizing attack surfaces, applying patches, and using tools like AWS for automated security management.

---

| Feature                    | **AWS Trusted Advisor**                                                                          | **Amazon GuardDuty**                                                                          | **AWS Shield**                                                                    | **AWS CloudTrail**                                                              |
| -------------------------- | ------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| **Purpose**                | Provides recommendations for best practices in security, performance, cost, and fault tolerance. | Detects threats using machine learning, anomaly detection, and threat intelligence.           | Protects against DDoS attacks.                                                    | Tracks user activity and API calls for auditing and security.                   |
| **Function**               | Identifies security gaps and optimizes AWS resources.                                            | Monitors AWS accounts, workloads, and network activity for suspicious behavior.               | Defends applications against large-scale DDoS attacks.                            | Logs AWS API calls for governance, compliance, and debugging.                   |
| **Focus Area**             | Security, cost optimization, performance, and resilience.                                        | Threat detection and anomaly identification.                                                  | DDoS mitigation and network protection.                                           | User activity tracking and audit logs.                                          |
| **Detection & Prevention** | Preventative – Helps improve AWS configurations proactively.                                     | Detects ongoing security threats and alerts users.                                            | Mitigates DDoS attacks in real-time.                                              | Provides logs for post-incident analysis but does not actively prevent attacks. |
| **Threat Handling**        | No direct threat detection, only best-practice suggestions.                                      | Identifies threats such as compromised instances, credential theft, and malicious activities. | Shields against volumetric, state-exhaustion, and application-layer DDoS attacks. | Records actions for forensic investigation and compliance.                      |
| **AWS Services Monitored** | AWS resources (EC2, RDS, IAM, S3, etc.).                                                         | VPC Flow Logs, CloudTrail logs, and DNS logs.                                                 | AWS applications and networks.                                                    | All AWS API calls across accounts.                                              |
| **Use Case**               | Optimize AWS resource security, cost, and performance.                                           | Identify security breaches, unauthorized access, and malicious activity.                      | Protect against DDoS attacks on AWS-hosted applications.                          | Audit AWS activity and detect policy violations.                                |


---
# PREVENTION - DATA SECURITY

**CIA Triad:** **Confidentiality** (protect data), **Integrity** (prevent tampering), **Availability** (ensure access).
### **Encryption**

- **Symmetric:** Same key for encryption & decryption. **Fast, used for large data (AES, IDEA, Twofish)**.
- **Asymmetric:** Public & private key pair. **More secure, slower (RSA, DH, ElGamal)**.
- **Hybrid:** Uses asymmetric for key exchange, symmetric for bulk data (TLS, secure messaging).
### **AWS Encryption Services**

- **CloudHSM:** Hardware security module for key management & compliance.
- **AWS KMS:** Fully managed cryptographic key service, integrates with AWS.

---
# PREVENTION - PUBLIC KEY INFRASTRUCTURE

Public key infrastructure (PKI) is a collection of technologies that are used to apply cryptography principles to transfer information securely between two entities. It is based on a practical distribution and implementation of keys, with a set of tools to achieve confidentiality, integrity, non-repudiation, and authenticity

![](/img/user/AWS CLOUD/attachments/Pasted image 20250202193157.png)


**Components:**
- **Certificate Authority (CA):** Issues and manages digital certificates.
- **Registration Authority (RA):** Verifies certificate requests before CA approval.
- **Certificate Revocation List (CRL):** A list of revoked certificates.
- **Online Certificate Status Protocol (OCSP):** Used to check if a certificate is revoked in real time.
- **Certificates:** Digital IDs proving ownership of public keys.

**How it Works:** A user requests a certificate from RA, which passes it to CA. After verification, CA issues the certificate.

==**ACM - AWS Certificate Manager :** A service to manage certificates for AWS services, simplifying their use and renewal.==

---

# PREVENTION - IDENTITY MANAGEMENT

**AAA Principles:**
    - **Authentication:** Verifying identity (e.g., password, ID).
    - **Authorization:** Granting access based on identity.
    - **Accounting:** Tracking user actions (e.g., login logs).

 ==**AWS Identity Management Services:**==
    - **AWS SSO:** Centralizes SSO access to AWS accounts.
    - **Amazon Cognito:** Manages user authentication for apps.
    - **AWS IAM:** Controls access to AWS resources using policies.

---

# 4. PREVENTION - IDENTITY AND ACCESS MANAGEMENT (AWS)

- **IAM Overview**: Manages access to AWS resources (authentication and authorization). It’s free and global.
- **Components**:
    - **Users**: Person/application with credentials and permissions.
    - **Groups**: Collections of users for easier permission management.
    - **Roles**: Provide temporary access to resources and avoid long-term credentials.
- **Security Credentials**: Includes IAM username/password, access keys, MFA, and key pairs. Avoid using root for daily tasks, enable MFA for extra security.
- **Authentication & Authorization**: IAM policies define resource access and actions; explicit deny takes precedence.
- **IAM Policies**:
    - **Managed Policies**: Standalone policies.
    - **Inline Policies**: Embedded into a user/group/role.
    - **Access Control**: Actions are denied by default, with policies allowing or denying access.
- **Access to AWS Services**: Access AWS services through Console, CLI, SDKs, and APIs.

---

# DETECTION

