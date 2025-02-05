---
{"dg-publish":true,"permalink":"/AWS CLOUD/4.Security/4 Prevention - data security, PKI, IAM/","created":"2025-02-02T19:16:39.237+05:30"}
---

one short security - [aws security - last min rev](../aws%20security%20-%20last%20min%20rev.md)
# 1. DATA SECURITY

- **Security Lifecycle:** Prevention, detection, response, analysis. Focus on **prevention** to secure data.
- **CIA Triad:** **Confidentiality** (protect data), **Integrity** (prevent tampering), **Availability** (ensure access).
- **Data States:** **Data in motion** (transmitted) & **data at rest** (stored). Use encryption to secure both.

### **Encryption**

- **Symmetric:** Same key for encryption & decryption. **Fast, used for large data (AES, IDEA, Twofish)**.
- **Asymmetric:** Public & private key pair. **More secure, slower (RSA, DH, ElGamal)**.
- **Hybrid:** Uses asymmetric for key exchange, symmetric for bulk data (TLS, secure messaging).

> [!NOTE]
> ### **AWS Encryption Services**
> 
> - **CloudHSM:** Hardware security module for key management & compliance.
> - **AWS KMS:** Fully managed cryptographic key service, integrates with AWS.

### **Hashing & Data Integrity**

- **Purpose:** Ensures data hasn’t been altered.
- **Algorithms:** **SHA1, MD5**.
- **Usage:** Verify file integrity, detect tampering.

### **Access Control**

- **DAC:** User-based permissions, decentralized (uses ACLs, IAM).
- **RBAC:** Role-based permissions, centralized, easier to manage.

### **Key Takeaways**

- **Encryption** protects confidentiality, **hashing** ensures integrity, **RBAC/DAC** controls access.
- **Multi-layered security** (encryption, hashing, access control) is essential for strong data protection.

---

# 2. Public key infrastructure

- **PKI Definition:** A framework using cryptography to enable secure communication via **digital certificates**. Ensures **confidentiality, integrity, authenticity, and non-repudiation**.
    
- **Key Components:**
    
    - **Certificate Authorities (CAs):** Issue & manage certificates. Includes **root CAs** (offline, top-tier trust) and **subordinate CAs** (handle requests).
    - **Certificates:** Digital documents proving public key ownership, used for authentication.
    - **Registration Authorities (RAs):** Verify certificate requests before passing to the CA.
    - **Certificate Revocation Lists (CRLs):** Lists revoked/invalid certificates. **OCSP** allows real-time revocation checks.
    - **Entities:** Organizations requesting/using certificates.
    - **Certificate Templates:** Blueprints for generating certificates.
- **PKI Operation:**
    
    1. Entity submits **certificate request** to RA.
    2. RA verifies and forwards it to CA.
    3. CA issues a certificate after checking revocation lists.
    4. Entities use **public keys attached to certificates** to verify identities.
- **Uses of Certificates:**
    
    - **SSL/TLS:** Secures web connections & online transactions.
    - **Code Signing:** Verifies software authenticity.
- **Obtaining a Certificate:**
    
    - Submit a **Certificate Signing Request (CSR)** with details to a CA.
    - CA verifies, issues the certificate, which is then installed on a server.
- **Certificate Lifecycle:**
    
    - **Expiration & Revocation:** Certificates expire or can be revoked (e.g., key compromise).
    - **CRLs & OCSP:** Used to check validity.
- **Certificate Storage:** Stored on devices, **smart cards, or TPM chips**.
    

> [!NOTE]
> - **AWS Certificate Manager (ACM):** Automates SSL/TLS certificate provisioning & renewal in AWS.

    
- **Key Takeaway:** PKI ensures **trusted communication & secure transactions** through certificate-based authentication.

---
# 3. PREVENTION - IDENTITY MANAGEMENT

- **Identity Management (IM):** Manages user identities and their access to resources based on authentication, authorization, and accounting (AAA). Ensures **scalability** and plays a role in the **prevention phase** of security.
    
- **AAA Principles:**
    - **Authentication:** Verifying identity (e.g., password, ID).
    - **Authorization:** Granting access based on identity.
    - **Accounting:** Tracking user actions (e.g., login logs).
    
- **Authentication Factors:**
    - **Something you know** (password).
    - **Something you have** (smart card).
    - **Something you are** (biometrics).
    - **Multi-factor authentication (MFA):** Combines multiple factors (e.g., password + verification code).
      
- **Personally Identifiable Information (PII):** Data that uniquely identifies individuals (e.g., name, SSN). **Critical to protect**.
    
- **Password Policies:**
    - **Weak policies** are easy to crack.
    - **Strong policies** require complexity, length, and regular changes.
      
- **Password Attacks & Countermeasures:**
    - **Dictionary and rainbow table attacks** can be mitigated with strong policies and account lockouts.
      
- **Identity Management Tools:**
    - **Password Managers:** Secure and centralize password management.
    - **Single Sign-On (SSO):** One login for multiple services.
    - **Federated Identity:** Uses tokens for identity verification across systems.
      

> [!NOTE]
> - **AWS Identity Management Services:**
>     - **AWS SSO:** Centralizes SSO access to AWS accounts.
>     - **Amazon Cognito:** Manages user authentication for apps.
>     - **AWS IAM:** Controls access to AWS resources using policies.

### **Key Points:**

- **AAA** and **authentication factors** (knowledge, possession, biometrics) are central.
- Strong **password policies** and **MFA** are crucial for security.
- AWS tools like **IAM** and **Cognito** help manage identities and access securely.


---
# 4. PREVENTION - IDENTITY AND ACCESS MANAGEMENT (AWS)

- **IAM Overview**: AWS Identity and Access Management (IAM) manages access to AWS resources, handling authentication (who can access) and authorization (what they can do). IAM is free and global, not region-specific.
- **Components**:
    - **Users**: Represents a person/application with credentials and permissions.
    - **Groups**: Collections of users to manage permissions together. Users can belong to multiple groups.
    - **Roles**: Used to delegate access to AWS resources, provide temporary access, and eliminate long-term credentials sharing.
- **Security Credentials**:
    - Includes email/password, IAM username/password, access keys, MFA, and key pairs.
    - **Root User**: Full access, but it’s best to avoid using it for everyday tasks.
    - **MFA**: Adds an extra layer of security and should be enabled for root and IAM users.
- **Authentication & Authorization**: IAM controls both. IAM policies define what resources users can access and actions they can perform.
    - **Explicit Deny**: Always takes precedence over allow.
    - **Policies**: Stored in JSON format; can be identity-based (attached to users, groups, roles) or resource-based (attached to specific resources).
    - **Policy Simulator**: Tool for testing and troubleshooting IAM policies.
- **IAM Policies**:
    - **Managed Policies**: Standalone policies attached to multiple users/groups/roles.
    - **Inline Policies**: Embedded directly into a user, group, or role.
    - **Access Control**: All actions are implicitly denied unless explicitly allowed, and policies are evaluated for allow or deny.
- **Access to AWS Services**: Access AWS services through the Management Console, CLI, SDKs, and APIs.


---
# ==NOTEBOOKLM SUMMARIZATION EXTRA THEORY ==

## 1. Data Security

**Data Security and the Security Lifecycle** The document emphasizes that **data security** is a critical aspect of the **prevention phase** within the broader security lifecycle. The security lifecycle consists of several stages: prevention, detection, response, and analysis. The document focuses on preventative measures used to secure data from potential threats.

**The CIA Triad** Information security is fundamentally based on the **CIA triad**: confidentiality, integrity, and availability.

- **Confidentiality** ensures that private data is protected from unauthorized access.
- **Integrity** verifies that data has not been tampered with and remains correct and authentic.
- **Availability** ensures that authorized users can access data when they need it. This module primarily addresses confidentiality and integrity.

**Data in Motion vs. Data at Rest** Data must be protected whether it is **in motion** (being transmitted) or **at rest** (stored on a device). Data in motion travels through networks and between devices, whereas data at rest is stored on devices such as smartphones, servers, and hard drives. The document underscores the need to use **cryptographic techniques, encryption, and controls** to secure data in both states.

**Cryptography and Encryption**

- **Cryptography** is the discipline encompassing the principles and techniques for ensuring data security, including confidentiality and data integrity.
- **Encryption** is the process of converting readable data into unreadable data (ciphertext) using a **cipher**. A cipher involves algorithms to encrypt and decrypt the data.
- A **key**, a series of numbers and letters, is used by the algorithm to encrypt and decrypt data. Only those who have the appropriate key can decrypt the data.
- Encryption is crucial for maintaining data confidentiality, as only users with the key can access the original data.

**Practical Applications of Encryption** The document provides examples of how encryption is used to protect data:

- **Data at rest encryption:**
    - **File system encryption** allows for encrypting individual files or a set of files.
    - **Drive encryption** protects the entire drive and its contents, with tools like BitLocker and VeraCrypt.
- **Data in motion encryption:**
    - **Secure Sockets Layer (SSL)/Transport Layer Security (TLS)** protocols secure data transmitted across networks, indicated by "https" in a URL.
    - **Kerberos** is used to encrypt communications between devices.
    - **IP Security (IPsec)** secures virtual private networks (VPNs).
    - **Secure/Multipurpose Internet Mail Extensions (S/MIME)** and **Pretty Good Privacy (PGP)** secure the content of messages sent via instant messaging or secure email.

**Types of Encryption** The document outlines three primary types of encryption:

- **Symmetric Encryption:** Employs the same key for both encryption and decryption.
    - It is **fast and reliable**, suitable for large amounts of data.
    - It is used in payment applications, database encryption, and for verifying message senders.
    - Examples of symmetric encryption standards include **Advanced Encryption Standard (AES), International Data Encryption Algorithm (IDEA), and Twofish**.
- **Asymmetric Encryption:** Utilizes a key pair consisting of a public key and a private key.
    - It is more complex and **slower** than symmetric encryption but provides better key management capabilities.
    - It is used for encrypting emails and creating digital signatures.
    - Standards include **Rivest-Shamir-Adleman (RSA), Diffie-Hellman (DH), and ElGamal**.
- **Hybrid Encryption:** Combines both symmetric and asymmetric encryption methods to offer enhanced protection.
    - TLS and messaging apps utilize hybrid encryption.
    - The session is established using asymmetric encryption, with symmetric encryption used for the duration of the session.

**Comparison of Encryption Methods** The document compares symmetric and asymmetric encryption based on several factors:

|Feature|Symmetric|Asymmetric|
|:--|:--|:--|
|Encryption Process|Fast and straightforward|Complex and time-consuming|
|Process Speed|Fast (even with large data)|Slow|
|Keys|One key (128 or 256 bits)|Two keys (2048 bits or higher)|
|Level of Security|Very secure if the key is safe|Offers higher security due to no shared key|
|Manageability|Becomes complex with more keys|Includes an easy-to-manage key system|
|Security Services|Only confidentiality|Non-repudiation, authentication, and more|
|Use Cases|Transmitting large amounts of data|Authentication and digital signatures|

- **Symmetric encryption** is ideal for speed, whereas **asymmetric encryption** is preferred when security is paramount.

**Hybrid Encryption Process**

- A message is encrypted using a **secret key** (symmetric encryption), and then this secret key is encrypted using the recipient's **public key** (asymmetric encryption).
- The encrypted message and the encrypted secret key are transmitted to the recipient.
- The recipient uses their **private key** to decrypt the encrypted secret key and then uses this decrypted secret key to decrypt the message.

**AWS Key Management Services**

- **AWS CloudHSM** is a cloud-based hardware security module (HSM) which allows you to generate and manage your own encryption keys.
    - It is primarily used to support customer-managed applications, which are designed to use HSMs to meet compliance obligations.
    - It's a fully managed service and allows for exporting keys to other HSMs.
- **AWS Key Management Service (AWS KMS)** helps create and manage cryptographic keys and control their usage across AWS services and applications.
    - It's a fully managed service and is integrated with AWS services.
    - Keys can be stored in its default key store or within AWS CloudHSM to meet compliance obligations.

**Hashing and Data Integrity**

- **Data integrity** ensures that data remains accurate and consistent when stored or transmitted over a network.
- **Hashing** is a one-way encryption method used to verify data integrity. It creates a unique fixed size output for each input.
- A **hash function** generates a unique hash value or message digest from the content of a file or message.
- If a file is hashed multiple times using the same function, the resulting hash value will always be the same.
- A change in the file results in a different hash value. This helps in detecting whether the file has been tampered with or corrupted.
- Common algorithms are **SHA1** and **MD5**.
- Hashes are often used to verify the integrity of downloaded files.

**Permissions and Access Control**

- **Permissions** are used to allow explicit access to a resource.
- Permissions are assigned to **subjects** (individuals, devices, or systems).
- There are two main types of access control:
    - **Discretionary Access Control (DAC):** Access control based on the identity of individuals or groups.
        - Utilizes **Access Control Lists (ACLs)**, which specify which users have access to which resources and the allowed operations.
        - Access control is decentralized.
        - AWS Identity and Access Management (IAM) uses ACLs to control access to resources.
    - **Role-Based Access Control (RBAC):** Access control based on roles assigned to users.
        - Permissions are assigned to roles and individuals are assigned to these roles.
        - It simplifies permission management, as permissions are distributed based on job roles.
        - It is efficient, customizable, and is extensively used in the commercial sector.

**Key Points on Access Control**

- **DAC** is decentralized and uses ACLs and Access Control Entries (ACEs) for auditing and dynamic access control.
- **RBAC** is efficient for managing staff turnovers and hires, is very customizable, and offers a good level of granularity.

**Checkpoint Questions**

- The three types of encryption are **symmetric, asymmetric, and hybrid**.
- A **hash function** is an algorithm that takes a file as an input and creates a unique digital signature as an output.
- An **access control list (ACL)** is a document that defines a list of accesses or restrictions to resources for individuals or groups of individuals.

**Key Takeaways**

- **Encryption** is used to protect data confidentiality using symmetric, asymmetric, or hybrid methods.
- **Hashing** protects data integrity by creating unique digital signatures.
- **Permissions** control access to resources through ACLs or role-based approaches.

---
## 2. Public key Infrastructue

**What is Public Key Infrastructure (PKI)?**

- PKI is a framework that uses **cryptography** to enable secure communication and data transfer between entities. It's a system for creating, managing, distributing, using, storing, and revoking digital certificates.
- It's rooted in the practical implementation of cryptographic **keys**, and aims to provide **confidentiality, integrity, non-repudiation, and authenticity**. These principles are fundamental to ensuring that data remains private, unaltered, and that actions can be reliably attributed to the correct entity.
- At its core, PKI is built on **trust**. This means that all the components within the infrastructure must have a configured relationship, ensuring the reliability of the system. It helps prevent rogue systems from interfering with communication between two entities.

**Key Components of PKI**

- **Certificate Authorities (CAs)**:
    - These are the entities that **issue digital certificates**, acting as the cornerstone of trust within the PKI framework. They manage the trust relationships between different entities.
    - CAs can be **root CAs** which are at the top of the hierarchy, kept offline, and are not directly involved in servicing entities. They initialise the PKI structure and store the root CA keys.
    - **Subordinate CAs** are also known as registration authorities, which verify and validate requests and issue certificates to entities. They help in expanding the PKI environment.
    - CAs produce key documents:
        - **Certificate Practice Statement (CPS):** Which defines the standards, practices and algorithms a CA uses.
        - **Certificate Policy:** This defines the rules customers must follow, such as payment requirements and revocable offenses.
    - CAs can be internal (within an organisation) or external (third party). An external CA is trusted by every entity, while an internal CA is trusted only within the organisation.
- **Certificates**:
    - These are **digital documents that prove the ownership of a public key**, they contain the public key and information about the entity the certificate belongs to, and the entity that provided and verified it.
    - They are like digital identification cards and are used to represent online identities of individuals, computers, or other entities.
    - Certificates can be self-signed, but a certificate signed by a CA is more reliable and trusted.
- **Registration Authorities (RAs)**:
    - These are entities, either organisations or companies, which verify certificate requests before they are passed to the certificate authority.
- **Revocation Lists (CRLs)**:
    - These are lists that contain invalidated certificates that are no longer trusted. These are checked to verify the validity of the certificate.
    - A CRL must be accessible at all times.
    - Managing multiple CRLs can be a large administrative task. The Online Certificate Status Protocol (OCSP) is used in enterprise environments to retrieve the revocation status of certificates.
- **Entities**:
    - These are organisations or companies that either request certificates or verify that certificates are not on a revocation list.
- **Certificate Templates**:
    - These are models or blueprints that are used to create digital certificates.

**How PKI Operates**

- When an entity needs a certificate, they first submit a **registration request to a registration authority server**.
- The **RA server** verifies the request and then passes it to the **CA server**.
- The CA server checks the **revocation list** to ensure the certificate is still valid.
- Once verified, the **CA server** sends the certificate back to the entity.
- **Trust** is established through the exchange of public keys that validate and identify the involved parties, these public keys are attached to the certificates that the CA issues.

**Uses of Certificates**

- **SSL/TLS**: Certificates are used to establish secure internet connections between a client and a server. This is commonly used to secure data transfers, login processes and online transactions such as credit card payments.
- **Code Signing**: Certificates verify the authenticity of applications and scripts. This makes sure that the code has not been tampered with after it has been signed.
- For example, a customer purchasing something on a website will have their connection secured with TLS. The payment page will be a secure TLS connection with a payment solution provider, and then the provider sends the results of the transaction back to the website, also via a secure connection.

**Obtaining a Certificate**

- To obtain a certificate from an external CA, you usually submit a **Certificate Signing Request (CSR)**.
    - You use a tool to create a CSR file on your server, including organisation details.
    - This file is sent to the CA, and you receive the digital certificate in return.
    - Finally, this is installed on the server.
- The **AWS Cloud** offers an internal certificate authority, which can be accessed via the **AWS Certificate Manager (ACM)** service.

**Certificate Lifecycle**

- Certificates have an **expiration date** and can be **revoked**.
- Reasons for revocation include the certificate expiring, a key compromise, a hold state, if it is superseded, or if the operation ceases.
- When certificates are expired or revoked, they are added to the **Certificate Revocation List (CRL)** and cannot be trusted.
- The **Online Certificate Status Protocol (OCSP)** can be used to quickly verify if a certificate is still valid.

**Certificate Storage**

- Certificates can be stored locally on the computer, or on smart cards or trusted platform module (TPM) chips.

**AWS Certificate Manager (ACM)**

- ACM is an AWS service that is designed to manage the provisioning, deployment and renewal of SSL/TLS certificates for AWS services and internal resources.
- It removes the manual process of managing certificates, making it easier to secure applications within the AWS cloud.

---

# 3. PREVENTION - IDENTITY MANAGEMENT

**Identity Management Overview**

- Identity management is the **active administration** of subjects, objects, and their relationships regarding access permissions.
- It ensures users receive the **appropriate access** to resources at the correct level and time.
- It helps systems remain **scalable** in granting access to resources.
- Identity management is a key part of the **prevention phase** of the security lifecycle.

**Core Principles: AAA**

- The main principles of identity management are **authentication, authorisation, and accounting (AAA)**.
    - **Authentication** is validating a user's identity.
    - **Authorisation** determines what permissions a user has.
    - **Accounting** logs user actions for auditing.

**AAA Example**

- When a visitor enters a company, the following steps are followed:
    - **Identification**: The visitor shows their ID.
    - **Authentication**: The receptionist validates the ID.
    - **Authorisation**: The receptionist confirms access with the visitor's contact and issues a badge.
    - **Accounting**: The visitor signs a log with details.
- A similar process is followed when a user logs into a computer with an ID card and password.

**Authentication Factors**

- Authentication is controlled using multiple factors.
- There are three types of authentication factors:
    - **Something you know**: This includes passwords, passphrases, and PINs. It is simple but least secure.
    - **Something you have**: This includes smart cards, tokens, USB keys, smartphones, and virtual cards. It is more secure than "something you know" and used as a second factor.
    - **Something you are**: This uses biometric devices, such as fingerprint readers, facial recognition, and retina scanners. It is the most complex and reliable when configured well, but expensive.

**Personally Identifiable Information (PII)**

- PII is data that can uniquely identify an individual.
- Examples include government ID numbers, names, birth dates, addresses, email addresses, account numbers, phone numbers, and fingerprints.
- PII can fall under all three authentication factors.
    - For example, a government ID number (something you know), a bank card (something you have), or a fingerprint (something you are).
- PII is important to protect because it cannot be easily changed or cracked like passwords.

**Password Policies**

- Strong password policies are essential to maintain security.
- A basic policy with a small number of characters and no complexity can be easily cracked.
- A good policy should include:
    - A minimum of 12 characters.
    - At least one capital letter, number, and symbol.
    - Password expiration after a set time period with password reuse restrictions.

**Password Attacks**

- **Dictionary attacks** use a list of words to attempt logins.
- **Rainbow table attacks** use precomputed hashes to find matching passwords.
- Countermeasures include using strong password policies and locking accounts after failed login attempts.

**Tools and Services**

- **Password managers** improve security, manage passwords, and allow password resets.
- **Group accounts** should be avoided, as they provide no accountability.
- **Single sign-on (SSO)** synchronizes passwords between different systems.
    - Users log in once to access multiple applications.
    - **Federated users** use a token to verify identity across distinct systems; this is a form of SSO.

**AWS Specific Services**

- **AWS Single Sign-On (SSO)** centrally manages SSO access to AWS accounts. It includes features such as one-click access, user and group management, and compatibility with cloud applications.
- **Amazon Cognito** provides user management, authentication, and authorisation for web and mobile apps. It includes user pools for sign-up and sign-in, and identity pools for access to AWS services.
- **AWS Identity and Access Management (IAM)** controls access to AWS resources through authentication and authorisation. It uses JSON documents as policies.

---

# 4. PREVENTION - IDENTITY AND ACCESS MANAGEMENT

**Introduction to AWS Identity and Access Management (IAM)**

- IAM is a service that allows you to **securely control access to your AWS resources**.
- It lets you centrally manage **authentication** (verifying who can access) and **authorisation** (what they can do).
- IAM is a feature of an AWS account and is available at no charge.
- The core concepts of IAM are users, groups, and roles.
- You will also learn about the different types of security credentials that IAM supports.
- **IAM uses familiar access control concepts** such as users, groups and permissions to control access to specific services.
- IAM is **global and not on a per-region basis**.

**Key Functions of IAM**

- **Manage access**: IAM helps you control who can launch, configure, manage, and delete AWS resources.
- **Granular Control**: It provides fine-grained control over access permissions for users, systems, or applications that programmatically interact with AWS resources.
- **Reduce Shared Credentials**: It minimizes the need to share passwords or access keys.
- **Enable/Disable Access**: IAM makes it easy to grant or revoke a user’s access.
- **Define Credentials**: It lets you define required credentials based on the context of who can access which AWS service and what they are allowed to do with that service.

**IAM Components**

- **Users**:
    - An IAM user is an entity that represents a person or application that interacts with AWS.
    - Each user has a name and credentials.
    - IAM users have no default security credentials.
    - Users are assigned security credentials for authentication.
    - Permissions are attached that authorise them to perform any AWS actions or to access any AWS resources.
    - It is a best practice to create an IAM user with administrative permissions instead of using the account root user.
- **Groups**:
    - IAM groups are collections of IAM users.
    - There are no default groups.
    - Groups cannot be nested.
    - Users can belong to multiple groups.
    - Permissions are specified for the entire group using IAM policies.
    - Groups help manage permissions for a collection of users.
    - If you want a default group you must create it and assign new users to it.
- **Roles**:
    - IAM roles are used to **delegate access to AWS resources**.
    - They provide temporary access.
    - Permissions are defined by IAM policies attached to the role, not to a user or group.
    - Applications or AWS services can programmatically assume a role at runtime.
    - Temporary security credentials are provided when a role is assumed.
    - Roles eliminate the need to share long-term security credentials.
    - Roles are used for federated users, who don't have permanent identities in an AWS account.
    - When creating a role, you specify two policies: a trust policy for who can assume the role, and an access policy for what they can do.
    - The principal (who can assume the role) can be an AWS account, AWS service, SAML provider, or an IdP.

**Security Credentials**

- **Types of Credentials**:
    - **Email address and password**: Used for the AWS account root user.
    - **IAM username and password**: Used to access the AWS Management Console.
    - **Access and secret access keys**: Typically used with the AWS Command Line Interface (AWS CLI) and programmatic requests.
    - **Multi-factor authentication (MFA)**: Provides an extra layer of security.
    - **Key pairs**: Used for specific AWS services like Amazon EC2.
- **Root User**:
    - The AWS account root user has full access to all resources.
    - Root user credentials cannot be controlled.
    - It is strongly recommended not to use root user credentials for daily interactions, instead create an IAM user.
    - Use the root user only for account and service management tasks that can't be done any other way.
- **IAM User Credentials**:
    - IAM username and password are used to access the AWS Management Console.
    - Access keys are used for programmatic access when generated for a user.
- **MFA**:
    - Adds an extra layer of security, requiring a unique authentication code in addition to a username and password.
    - MFA codes are obtained from a device like a smartphone or sent to an email address.
    - AWS recommends enabling MFA on the root user and IAM users.
    - You can use hardware devices or virtual MFA-compliant applications for authentication.
- **AWS Security Token Service (STS)** can request temporary, limited-permission credentials for IAM users or other authenticated users.

**Authentication and Authorisation**

- **Authentication**: IAM is used for user authentication and is the first step to control who can access AWS resources.
- **Authorisation**: Determines what resources users can access and what they can do with those resources.
- **Policies** define authorisation.
- A policy is an object that defines permissions.
- There are no default permissions, all actions are implicitly denied unless explicitly allowed.
- Actions that are explicitly denied are always denied.
- To assign permissions to a user, group or role, you must create an IAM policy.
- IAM is used to configure authorisation based on the user.
- IAM uses access control concepts such as users, groups and permissions.

**IAM Implementation**

- IAM users have no default security credentials.
- Newly created IAM users need assigned security credentials for authentication.
- Permissions that authorise the users to perform actions or access resources also need to be attached.
- A best practice is to create a separate IAM user account with administrative permission instead of using the account root user.

**IAM Policies**

- An IAM policy is a formal statement of one or more permissions.
- Policies are attached to IAM entities: users, groups, or roles.
- Policies authorize the actions that an entity can or cannot perform.
- A single policy can be attached to multiple entities.
- A single entity can have multiple policies attached.
- It is a best practice to put users into a group and attach a policy to that group if you need to attach the same policy to multiple IAM users.
- IAM policies are stored in JSON format.
- It is a best practice to define least privileged access.
- Policies define which actions are allowed, which resources are granted those actions and the effect when the user requests access to the resources.
- The order in which policies are evaluated has no effect on the outcome.
- All policies are evaluated and the result is always either allow or deny.
- When conflicts occur, the most restrictive policy wins.
- IAM checks for explicit deny policies first, then explicit allow policies. If neither exists, it defaults to implicit deny.

**Types of IAM Policies:**

- **Identity-based Policies:** Permissions policies attached to a principal, such as IAM user, role, or group.
    - **Managed Policies:** Standalone, and can be attached to multiple users, groups, and roles.
    - **Inline Policies:** Created and managed, embedded directly into a single user, group, or role.
- **Resource-based Policies:** JSON documents attached to a resource like an S3 bucket. These are inline policies and control which actions a specified principal can perform on that resource. There are no managed resource-based policies.
- The IAM policy simulator can be used to test and troubleshoot policies.

**Policy Assignment and Reusability**

- One policy can be assigned to a user, group, and role.
- This makes reuse available and reduces the need to recreate policies.

**Example IAM Policy**

- The example policy in the source provides both an "allow" and "deny" effect.
- An explicit allow statement grants access to a specific DynamoDB table and S3 bucket.
- An explicit deny ensures that users cannot use any other AWS actions or resources.
- Explicit deny statements take precedence over allow statements.

**Accessing AWS Services**

- You can access AWS services using the AWS Management Console, AWS Command Line Interface (AWS CLI), and Software Development Kits (SDKs) and APIs.

**Summary of the PDF**

This PDF introduces AWS Identity and Access Management (IAM), a crucial service for controlling access to AWS resources. IAM allows you to manage users, groups, and roles, and to set permissions with policies that are stored as JSON documents. **Key takeaways include:**

- **IAM is used for authentication and authorisation of access to AWS resources.**
- **It uses users, groups and roles to manage permissions.**
- **IAM is a free service offered as a feature of your AWS account.**
- **You should avoid using the root account for daily tasks and create an IAM user with administrative permissions instead.**
- **IAM supports different types of security credentials for authentication.**
- **Policies are used to grant or deny specific permissions and an explicit deny always takes precedence.**
- **MFA should be enabled for increased security on the AWS account root user and on any IAM users.**
- **IAM is global and not on a per-region basis.**

