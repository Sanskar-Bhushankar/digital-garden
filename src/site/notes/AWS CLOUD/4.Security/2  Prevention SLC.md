---
{"dg-publish":true,"permalink":"/AWS CLOUD/4.Security/2  Prevention SLC/","created":"2024-12-11T17:36:55.708+05:30"}
---

one short security - [aws security - last min rev](../aws%20security%20-%20last%20min%20rev.md)
## Prevention in security Lifecycle

![](/img/user/AWS CLOUD/4.Security/attachments/Pasted image 20241211173920.png)

1. Prevention
	- Stopping the threat before it occus
	- Identifying the assets to be protected
	- Assessing assets vulnerability
	- Implementing countermeasures
2. Detection
	-  Identifying security events in real-time.
	- Using monitoring tools effectively.
	- Setting up alert mechanisms. 
3. Response
    - Mitigating incidents promptly.
    - Following incident response protocols.
    - Coordinating response efforts.
4.  Analysis
    - Investigating incidents thoroughly.
    - Identifying root causes.
    - Documenting lessons learned.


` by default aws blocks every service the customer will decide what to open and what not to`

###  What do you understand by `resources` in AWS?
Resources in AWS refer to virtual servers, databases, storage, and other components provisioned and managed within the AWS cloud infrastructure.

## Prevention

### 1. Identifying assets
- network device
- servers
- application and services

### we can identify this from the sources 
- Network topology - network infrastructure layout
- Architecture diagram -how different components interct
- System Documentation- describing each assest purpose


### AWS System Manager Inventory Function ss

![](/img/user/AWS CLOUD/4.Security/attachments/Pasted image 20241211180756.png)

The AWS Systems Manager inventory function offers centralized management, detailed instance inventory, automation for tasks like software and patch management, enhanced security through up-to-date instance information, and operational insights for improved efficiency within AWS environments.

### AWS service name for identity management ?
 **AWS Identity and Access Management (IAM)**. It provides secure access control to AWS services and resources for users and groups within your AWS account.

### 2. Assessing asset vulnerability
- **Types of Assessments**:
    - **Network Assessment**: Identify open ports and exposed devices.
    - **Host Assessment**: Check running applications, services, and patch status.
    - **Application Assessment**: Evaluate source code for security vulnerabilities.
    - **Data Assessment**: Ensure data in transit and at rest are adequately protected.

- **Resources for Threat Identification**:
	- Use reputable sources like the Common Vulnerabilities and Exposures (CVE) website.
	- CVE lists publicly disclosed cybersecurity vulnerabilities.
	- Helps in identifying and addressing security weaknesses using automated tools like scanners.

![](/img/user/AWS CLOUD/4.Security/attachments/Pasted image 20241211182210.png)

### 3. Prevention strategy

![](/img/user/AWS CLOUD/4.Security/attachments/Pasted image 20241211183008.png)
1. **Layered Security Model**:
	  - Uses multiple layers for defense.
	  - Includes: Perimeter, Network, Endpoint, Application, Data security.

	- **Protection Strategy**:
		  - Secures valuable assets by requiring attackers to breach multiple layers.
		  - Examples: Firewalls for perimeter security, ACLs for network security, antivirus for endpoint security, specialized tools for application and data security.

	- Castle Eample
	- ![](/img/user/AWS CLOUD/4.Security/attachments/Pasted image 20241211183335.png)
		- Layers: Moat, Outer wall, Inner wall, Keep.
		- Each layer must be breached for attackers to reach assets.
		- Analogous to layered defenses in systems for increased security.

**OSI Model Example**:
- Layers: Physical, Data link, Network, Transport, Session, Presentation, Application.
- Security measures implemented at each layer:
- Physical: Securing network devices.
- Data link: Filtering based on MAC addresses.
- Network and transport: Using firewalls and ACLs.
- Session and presentation: Authentication and encryption.
- Application: Virus scanners and IDS.
- Protecting each layer enhances overall system security by making it harder to breach.




## Types of prevention measures (Onion layers)
![](/img/user/AWS CLOUD/4.Security/attachments/Pasted image 20241211184141.png)

- **Network Hardening**: Strengthen network security by blocking exploration protocols, closing unused ports, and maintaining an updated asset inventory. Use firewalls and segmentation for added protection.
    
- **Systems Hardening**: Secure hosts by regularly applying OS patches, removing unnecessary applications, and monitoring configuration changes to prevent vulnerabilities.
    
- **Data Security**: Protect data integrity and confidentiality through encryption for data in transit and at rest, digital certificates, and role-based access controls.
    
- **Identity Management**: Control access with the principle of least privilege, enforce strong password policies, and implement authentication, authorization, and accounting (AAA) principles for auditing and security.


![](/img/user/AWS CLOUD/4.Security/attachments/Pasted image 20241211184230.png)

![](/img/user/AWS CLOUD/4.Security/attachments/Pasted image 20241211184306.png)

