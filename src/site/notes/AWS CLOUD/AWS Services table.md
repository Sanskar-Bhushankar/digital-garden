---
{"dg-publish":true,"permalink":"/AWS CLOUD/AWS Services table/","created":"2025-01-26T23:52:50.326+05:30"}
---



Here’s a **structured table** of **all in-scope AWS services** for the AWS Certified Cloud Practitioner (CLF-C02) exam, grouped by category, with precise definitions. This list aligns with the **official exam guide's Appendix A**:

---

### **1. Compute Services**
| **Service**               | **Definition**                                                                 |
|---------------------------|-------------------------------------------------------------------------------|
| **EC2**                   | Virtual servers in the cloud. Provides resizable compute capacity.            |
| **Lambda**                | Serverless compute service. Runs code in response to events without provisioning servers. |
| **Elastic Beanstalk**     | PaaS for deploying and scaling web applications. Manages infrastructure (e.g., EC2, load balancing). |
| **Batch**                 | Runs batch computing workloads at scale. Automates job scheduling and resource provisioning. |
| **Lightsail**             | Simplified virtual private server (VPS) for small-scale applications. Includes preconfigured apps. |
| **AWS Outposts**          | Run AWS infrastructure on-premises for hybrid cloud deployments.              |
| **AWS Wavelength**        | Embeds AWS compute and storage in telecom 5G networks for ultra-low-latency apps. |
| **AWS Fargate**           | Serverless compute engine for containers. Works with ECS/EKS.                 |

---

### **2. Storage Services**
| **Service**               | **Definition**                                                                 |
|---------------------------|-------------------------------------------------------------------------------|
| **S3**                    | Object storage for scalable data storage. Offers 11 nines durability.         |
| **EBS**                   | Block storage volumes for EC2 instances. Ideal for databases and file systems. |
| **EFS**                   | Managed file storage for Linux workloads. Accessible by multiple EC2 instances. |
| **FSx**                   | Managed file systems for Windows (FSx for Windows) and Lustre (FSx for Lustre). |
| **Storage Gateway**       | Hybrid storage service. Connects on-premises apps to cloud storage (S3, EBS). |
| **AWS Backup**            | Centralized backup service for AWS resources (EC2, EBS, RDS, etc.).           |
| **S3 Glacier**            | Low-cost archival storage for long-term data retention. Retrieval times vary (minutes to hours). |

---

### **3. Database Services**
| **Service**               | **Definition**                                                                 |
|---------------------------|-------------------------------------------------------------------------------|
| **RDS**                   | Managed relational databases (MySQL, PostgreSQL, Oracle, SQL Server, Aurora). |
| **DynamoDB**              | Serverless NoSQL database with single-digit millisecond latency.              |
| **Aurora**                | High-performance MySQL/PostgreSQL-compatible relational database.             |
| **Redshift**              | Data warehousing service for petabyte-scale analytics.                        |
| **Neptune**               | Managed graph database for applications with highly connected data.           |
| **MemoryDB for Redis**    | Redis-compatible in-memory database for microsecond latency.                  |
| **DMS**                   | Database Migration Service. Migrates databases to AWS with minimal downtime.  |
| **SCT**                   | Schema Conversion Tool. Converts database schemas (e.g., Oracle→Aurora).      |

---

### **4. Networking & Content Delivery**
| **Service**               | **Definition**                                                                 |
|---------------------------|-------------------------------------------------------------------------------|
| **VPC**                   | Virtual private cloud. Isolated network for AWS resources (EC2, RDS, etc.).   |
| **Route 53**              | DNS management service. Routes traffic to AWS or external endpoints.          |
| **CloudFront**            | Content Delivery Network (CDN). Caches content at edge locations for low latency. |
| **Direct Connect**        | Dedicated network connection from on-premises to AWS. Bypasses the public internet. |
| **VPN**                   | Securely connects on-premises networks to AWS via IPsec tunnels.              |
| **Global Accelerator**    | Improves application performance by routing traffic through AWS’s global network. |
| **API Gateway**           | Managed service to create, publish, and secure APIs at scale.                 |

---

### **5. Security, Identity & Compliance**
| **Service**               | **Definition**                                                                 |
|---------------------------|-------------------------------------------------------------------------------|
| **IAM**                   | Manages access to AWS resources. Defines users, groups, roles, and policies.  |
| **KMS**                   | Key Management Service. Creates and controls encryption keys.                 |
| **CloudHSM**              | Hardware Security Module (HSM) for managing cryptographic keys (FIPS 140-2 Level 3). |
| **Shield**                | DDoS protection. Standard (free) and Advanced (paid with 24/7 support).       |
| **WAF**                   | Web Application Firewall. Protects web apps from common exploits (SQLi, XSS). |
| **GuardDuty**             | Threat detection using ML. Analyzes CloudTrail, VPC Flow Logs, and DNS logs.  |
| **Inspector**             | Automated security assessments for EC2 instances and container images.       |
| **Macie**                 | Discovers and protects sensitive data (e.g., PII) in S3 using ML.             |
| **Artifact**              | Central repository for AWS compliance reports (SOC, PCI, ISO).                |
| **Cognito**               | User identity and access management for web/mobile apps (e.g., sign-up/sign-in). |
| **Secrets Manager**       | Securely stores and rotates database credentials, API keys, etc.              |
| **Certificate Manager**   | Provisions and manages SSL/TLS certificates for AWS services.                 |

---

### **6. Management & Governance**
| **Service**               | **Definition**                                                                 |
|---------------------------|-------------------------------------------------------------------------------|
| **CloudWatch**            | Monitoring and observability service. Collects logs, metrics, and alarms.     |
| **CloudFormation**        | Infrastructure as Code (IaC). Templates for provisioning AWS resources.       |
| **Systems Manager**       | Centralized management of EC2 instances (e.g., patching, run commands).       |
| **Config**                | Tracks resource configurations and compliance over time.                      |
| **Trusted Advisor**       | Recommends cost optimization, security, and performance improvements.         |
| **Organizations**         | Manages multiple AWS accounts. Enables consolidated billing and SCPs.         |
| **Control Tower**         | Automates multi-account AWS environment setup with governance guardrails.     |
| **Service Catalog**       | Creates and manages approved IT service portfolios for users.                 |

---

### **7. Analytics & Machine Learning**
| **Service**               | **Definition**                                                                 |
|---------------------------|-------------------------------------------------------------------------------|
| **Athena**                | Serverless SQL query service for analyzing data in S3.                        |
| **EMR**                   | Elastic MapReduce. Processes big data using Hadoop, Spark, and Hive.          |
| **Glue**                  | Serverless ETL (Extract, Transform, Load) service. Prepares data for analytics. |
| **Kinesis**               | Real-time data streaming and analytics (Data Streams, Firehose, Analytics).   |
| **QuickSight**            | Business intelligence tool for creating interactive dashboards.               |
| **SageMaker**             | End-to-end ML service. Builds, trains, and deploys machine learning models.   |
| **Lex**                   | Builds conversational interfaces (chatbots) using voice/text.                 |
| **Rekognition**           | Image and video analysis using ML (e.g., facial recognition).                 |

---

### **8. Application Integration & Messaging**
| **Service**               | **Definition**                                                                 |
|---------------------------|-------------------------------------------------------------------------------|
| **SNS**                   | Pub/Sub messaging service. Sends notifications via email, SMS, or HTTP.       |
| **SQS**                   | Message queuing service. Decouples microservices and distributed systems.     |
| **EventBridge**           | Serverless event bus. Routes events between AWS services and SaaS apps.       |
| **Step Functions**        | Coordinates serverless workflows (e.g., Lambda, ECS).                         |

---

### **9. Migration & Transfer**
| **Service**               | **Definition**                                                                 |
|---------------------------|-------------------------------------------------------------------------------|
| **Snow Family**           | Physical devices (Snowcone, Snowball, Snowmobile) for large-scale data transfer. |
| **Transfer Family**       | Managed file transfer service (SFTP, FTPS, FTP) into/out of S3.               |
| **Migration Hub**         | Tracks application migrations across AWS services and partners.               |

---

### **10. End-User Computing**
| **Service**               | **Definition**                                                                 |
|---------------------------|-------------------------------------------------------------------------------|
| **WorkSpaces**            | Managed virtual desktops in the cloud (Windows/Linux).                        |
| **AppStream 2.0**         | Streams desktop applications to browsers without infrastructure management.   |
| **WorkSpaces Web**        | Provides secure, low-cost access to internal websites and SaaS apps.          |

---

### **11. Developer Tools**
| **Service**               | **Definition**                                                                 |
|---------------------------|-------------------------------------------------------------------------------|
| **CodeCommit**            | Managed Git repositories for source control.                                  |
| **CodeBuild**             | Fully managed CI service. Compiles, tests, and packages code.                 |
| **CodeDeploy**            | Automates code deployments to EC2, Lambda, or on-premises servers.            |
| **CodePipeline**          | CI/CD service for building, testing, and deploying code changes.              |
| **X-Ray**                 | Debugs and analyzes distributed applications (e.g., microservices).           |

---

### **12. Customer Engagement & Support**
| **Service**               | **Definition**                                                                 |
|---------------------------|-------------------------------------------------------------------------------|
| **Connect**               | Cloud-based contact center service (voice, chat).                             |
| **SES**                   | Email sending and receiving service for bulk or transactional emails.         |
| **Support Plans**         | Technical support tiers: Basic (free), Developer, Business, Enterprise.       |
| **AWS Activate**          | Resources for startups (credits, training, support).                         |

---

### **13. Internet of Things (IoT)**
| **Service**               | **Definition**                                                                 |
|---------------------------|-------------------------------------------------------------------------------|
| **IoT Core**              | Managed service to connect and manage IoT devices at scale.                   |
| **IoT Greengrass**        | Extends AWS to edge devices for local compute, messaging, and ML.             |

---

### **14. Other Key Services**
| **Service**               | **Definition**                                                                 |
|---------------------------|-------------------------------------------------------------------------------|
| **Marketplace**           | Digital catalog for third-party software (e.g., SAP, Splunk).                 |
| **Health Dashboard**       | Provides alerts about AWS service disruptions and scheduled maintenance.      |
| **Elastic Disaster Recovery** | Automates disaster recovery for on-premises and cloud-based apps.            |

---

### **Exam Tips**  
- **Focus on Use Cases**: Know which service to use for scenarios (e.g., S3 for static websites, Lambda for event-driven apps).  
- **Pricing Models**: Understand cost differences (e.g., On-Demand vs. Reserved Instances).  
- **Security**: Memorize IAM policies, encryption tools (KMS, CloudHSM), and compliance reports (AWS Artifact).  
- **Support Plans**: Know the differences between Basic, Business, and Enterprise Support.  


---

Here’s a **comprehensive, exam-focused table** of **all AWS services** relevant to the AWS Certified Cloud Practitioner (CLF-C02) exam, including those listed in the official guide and commonly tested services. Each service is grouped by category with precise definitions:

---

### **1. Compute Services**  
| **Service**               | **Definition**                                                                 |
|---------------------------|-------------------------------------------------------------------------------|
| **Amazon EC2**            | Virtual servers in the cloud with resizable compute capacity.                |
| **AWS Lambda**            | Serverless compute service for event-driven code execution.                  |
| **AWS Elastic Beanstalk** | Fully managed PaaS for deploying apps (handles infrastructure).              |
| **AWS Batch**             | Runs batch jobs at scale without managing servers.                           |
| **AWS Lightsail**         | Simplified VPS for small-scale apps (preconfigured templates).               |
| **AWS Outposts**          | Run AWS infrastructure on-premises for hybrid cloud.                         |
| **AWS Wavelength**        | Embeds AWS compute in 5G networks for ultra-low-latency apps.                |
| **AWS Fargate**           | Serverless compute engine for containers (ECS/EKS).                          |

---

### **2. Storage Services**  
| **Service**               | **Definition**                                                                 |
|---------------------------|-------------------------------------------------------------------------------|
| **Amazon S3**             | Object storage with 11 nines durability. Supports versioning, lifecycle policies. |
| **Amazon EBS**            | Block storage for EC2 instances (SSD/HDD volumes).                           |
| **Amazon EFS**            | Managed file storage for Linux workloads (shared across EC2).                |
| **Amazon FSx**            | Managed file systems for Windows (FSx for Windows) and Lustre (FSx for Lustre). |
| **AWS Storage Gateway**   | Hybrid storage connecting on-premises apps to S3/EBS.                        |
| **AWS Backup**            | Centralized backup for AWS resources (EC2, EBS, RDS, etc.).                  |
| **Amazon S3 Glacier**     | Low-cost archival storage with retrieval options (minutes to hours).         |
| **AWS Elastic Disaster Recovery** | Automates disaster recovery for on-premises and cloud apps.              |

---

### **3. Database Services**  
| **Service**               | **Definition**                                                                 |
|---------------------------|-------------------------------------------------------------------------------|
| **Amazon RDS**            | Managed relational databases (MySQL, PostgreSQL, Aurora, etc.).              |
| **Amazon Aurora**         | High-performance, MySQL/PostgreSQL-compatible database.                      |
| **Amazon DynamoDB**       | Serverless NoSQL database with single-digit millisecond latency.             |
| **Amazon Redshift**       | Data warehousing for petabyte-scale analytics.                               |
| **Amazon Neptune**        | Managed graph database for highly connected data.                            |
| **Amazon MemoryDB for Redis** | Redis-compatible in-memory database with microsecond latency.            |
| **AWS Database Migration Service (DMS)** | Migrates databases with minimal downtime.                |
| **AWS Schema Conversion Tool (SCT)** | Converts database schemas (e.g., Oracle to Aurora).       |

---

### **4. Networking & Content Delivery**  
| **Service**               | **Definition**                                                                 |
|---------------------------|-------------------------------------------------------------------------------|
| **Amazon VPC**            | Isolated virtual network for AWS resources (subnets, route tables, gateways).|
| **Amazon Route 53**       | DNS management with routing policies (latency, geolocation).                 |
| **Amazon CloudFront**     | Global CDN for low-latency content delivery (integrates with Shield).        |
| **AWS Direct Connect**    | Dedicated network connection from on-premises to AWS.                        |
| **AWS VPN**               | Secure IPsec tunnels between on-premises networks and AWS.                   |
| **AWS Global Accelerator**| Improves app availability/performance using AWS’s edge network.              |
| **Amazon API Gateway**    | Managed service to create, publish, and secure APIs.                         |

---

### **5. Security, Identity & Compliance**  
| **Service**               | **Definition**                                                                 |
|---------------------------|-------------------------------------------------------------------------------|
| **AWS IAM**               | Manages access to AWS resources via users, groups, roles, and policies.      |
| **AWS KMS**               | Creates and controls encryption keys (AWS-managed or customer-managed).      |
| **AWS Shield**            | DDoS protection (Standard: free; Advanced: paid with 24/7 support).          |
| **AWS WAF**               | Web Application Firewall to block SQLi, XSS, and bad bots.                   |
| **AWS GuardDuty**         | ML-based threat detection (analyzes CloudTrail, VPC Flow Logs).              |
| **AWS Macie**             | Discovers and protects sensitive data (e.g., PII) in S3 using ML.            |
| **AWS Artifact**          | Central repository for compliance reports (SOC, PCI, ISO).                   |
| **AWS Secrets Manager**   | Securely stores and rotates credentials (e.g., RDS passwords).               |
| **AWS Certificate Manager** | Provisions and manages SSL/TLS certificates for AWS services.             |
| **AWS Detective**         | Investigates security incidents using log data.                              |

---

### **6. Management & Governance**  
| **Service**               | **Definition**                                                                 |
|---------------------------|-------------------------------------------------------------------------------|
| **AWS CloudWatch**        | Monitoring and observability (metrics, logs, alarms).                        |
| **AWS CloudFormation**    | Infrastructure as Code (IaC) for templated resource provisioning.            |
| **AWS Systems Manager**   | Manages EC2 instances (patching, run commands, Parameter Store).             |
| **AWS Config**            | Tracks resource configurations and compliance over time.                     |
| **AWS Trusted Advisor**   | Recommends cost, security, and performance optimizations.                    |
| **AWS Organizations**     | Manages multiple AWS accounts (consolidated billing, SCPs).                  |
| **AWS Control Tower**     | Sets up and governs multi-account AWS environments.                          |
| **AWS License Manager**   | Tracks software licenses (e.g., Microsoft SQL Server on EC2).                |
| **AWS Well-Architected Tool** | Reviews workloads against the Well-Architected Framework.                |

---

### **7. Analytics & Machine Learning**  
| **Service**               | **Definition**                                                                 |
|---------------------------|-------------------------------------------------------------------------------|
| **Amazon Athena**         | Serverless SQL queries on S3 data.                                            |
| **Amazon EMR**            | Managed big data frameworks (Hadoop, Spark).                                 |
| **AWS Glue**              | Serverless ETL service for data preparation.                                  |
| **Amazon Kinesis**        | Real-time data streaming (Data Streams, Firehose, Analytics).                |
| **Amazon QuickSight**     | Business analytics tool for interactive dashboards.                          |
| **Amazon SageMaker**      | End-to-end ML service for building, training, and deploying models.          |
| **Amazon Lex**            | Builds conversational chatbots (voice/text).                                 |
| **Amazon Rekognition**    | Image/video analysis (facial recognition, object detection).                 |
| **Amazon Textract**       | Extracts text and data from scanned documents.                               |
| **Amazon Transcribe**     | Converts speech to text.                                                     |
| **Amazon Translate**      | Translates text between languages.                                           |

---

### **8. Application Integration & Messaging**  
| **Service**               | **Definition**                                                                 |
|---------------------------|-------------------------------------------------------------------------------|
| **Amazon SNS**            | Pub/Sub messaging service for notifications (email, SMS, HTTP).              |
| **Amazon SQS**            | Message queuing service for decoupling microservices.                        |
| **Amazon EventBridge**    | Serverless event bus for routing events between AWS/SaaS apps.               |
| **AWS Step Functions**    | Coordinates serverless workflows (e.g., Lambda, ECS).                        |

---

### **9. Migration & Transfer**  
| **Service**               | **Definition**                                                                 |
|---------------------------|-------------------------------------------------------------------------------|
| **AWS Snow Family**       | Physical devices (Snowcone, Snowball, Snowmobile) for large-scale data transfer. |
| **AWS Transfer Family**   | Managed file transfer (SFTP, FTPS, FTP) to/from S3.                          |
| **AWS DMS**               | Database Migration Service for homogeneous/heterogeneous migrations.         |
| **AWS Application Migration Service** | "Lift-and-shift" migration of on-premises servers to AWS.            |

---

### **10. End-User Computing**  
| **Service**               | **Definition**                                                                 |
|---------------------------|-------------------------------------------------------------------------------|
| **Amazon WorkSpaces**     | Managed virtual desktops (Windows/Linux).                                     |
| **Amazon AppStream 2.0**  | Streams desktop apps to browsers without managing infrastructure.             |
| **Amazon WorkSpaces Web** | Secure, low-cost access to internal websites and SaaS apps.                   |

---

### **11. Developer Tools**  
| **Service**               | **Definition**                                                                 |
|---------------------------|-------------------------------------------------------------------------------|
| **AWS CodeCommit**        | Managed Git repositories for source control.                                  |
| **AWS CodeBuild**         | Fully managed CI service for compiling, testing, and packaging code.          |
| **AWS CodeDeploy**        | Automates code deployments to EC2, Lambda, or on-premises.                    |
| **AWS CodePipeline**      | CI/CD service for building, testing, and deploying code.                      |
| **AWS X-Ray**             | Debugs and analyzes distributed applications (e.g., microservices).           |

---

### **12. Customer Engagement & Support**  
| **Service**               | **Definition**                                                                 |
|---------------------------|-------------------------------------------------------------------------------|
| **Amazon Connect**        | Cloud-based contact center (voice, chat).                                     |
| **Amazon SES**            | Email service for transactional/bulk emails.                                  |
| **AWS Support Plans**     | Tiers: Basic (free), Developer, Business, Enterprise (TAM access).            |
| **AWS Activate**          | Resources for startups (credits, training, technical support).               |

---

### **13. IoT**  
| **Service**               | **Definition**                                                                 |
|---------------------------|-------------------------------------------------------------------------------|
| **AWS IoT Core**          | Managed service to connect and manage IoT devices at scale.                   |
| **AWS IoT Greengrass**    | Extends AWS to edge devices for local compute and ML.                         |

---

### **14. Frontend & Mobile**  
| **Service**               | **Definition**                                                                 |
|---------------------------|-------------------------------------------------------------------------------|
| **AWS Amplify**           | Builds and deploys full-stack web/mobile apps.                                |
| **AWS AppSync**           | Managed GraphQL API service.                                                  |
| **AWS Device Farm**       | Tests mobile apps on real devices in the cloud.                               |

---

### **15. Containers**  
| **Service**               | **Definition**                                                                 |
|---------------------------|-------------------------------------------------------------------------------|
| **Amazon ECR**            | Managed container registry for Docker images.                                 |
| **Amazon ECS**            | Managed container orchestration service (supports Docker).                    |
| **Amazon EKS**            | Managed Kubernetes service for containerized apps.                            |

---

### **16. Other Key Services**  
| **Service**               | **Definition**                                                                 |
|---------------------------|-------------------------------------------------------------------------------|
| **AWS Marketplace**       | Platform to buy/sell third-party software (e.g., SAP, WordPress).             |
| **AWS Health Dashboard**  | Provides alerts about AWS service disruptions and maintenance.                |

---

### **Out-of-Scope but Commonly Confused**  
| **Service**               | **Note**                                                                      |
|---------------------------|-------------------------------------------------------------------------------|
| **AWS DataSync**          | Not in scope (CLF-C02). Focus on **AWS Snow Family** and **Transfer Family**. |
| **AWS OpsWorks**          | Not in scope. Use **AWS Systems Manager** for configuration management.       |

---

### **Exam Tips**  
1. **Focus on Use Cases**:  
   - Use **S3** for static websites, **Lambda** for event-driven apps, **RDS** for managed SQL databases.  
2. **Shared Responsibility Model**:  
   - AWS manages the cloud infrastructure; you manage data, IAM, and encryption.  
3. **Pricing Models**:  
   - **Reserved Instances** (1-3 years), **Savings Plans** (flexible commitment), **Spot Instances** (up to 90% discount).  
4. **Security Best Practices**:  
   - Enable **MFA**, use **IAM roles**, encrypt data with **KMS**, and audit with **CloudTrail**.  

This table includes **every service listed in the official guide** and clarifies out-of-scope services. Let me know if you need further details! 🚀