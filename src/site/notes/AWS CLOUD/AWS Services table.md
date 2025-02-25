---
{"dg-publish":true,"permalink":"/AWS CLOUD/AWS Services table/","created":"2025-01-26T23:52:50.326+05:30"}
---

# List of all the imp aws services in clf-02
## Analytics

|Service Name|Easy Description|Examples|
|---|---|---|
|**Amazon Athena**|Serverless interactive query service that lets you analyze data in Amazon S3 using standard SQL.|Ad-hoc querying of log files; data lake analysis.|
|**AWS Data Exchange**|Facilitates finding, subscribing to, and using third-party data in the cloud.|Accessing market research data or financial datasets.|
|**Amazon EMR**|Managed big data platform to run frameworks like Apache Hadoop and Spark.|Large-scale data processing and ETL jobs.|
|**AWS Glue**|Fully managed extract, transform, load (ETL) service for data preparation and integration.|Automating data cleaning and migration into data warehouses.|
|**Amazon Kinesis**|Real-time data streaming service for collecting, processing, and analyzing streaming data.|Live analytics on clickstream or IoT sensor data.|
|**Amazon Managed Streaming for Apache Kafka (MSK)**|Managed Apache Kafka service to build and run streaming applications.|Real-time event processing and log aggregation.|
|**Amazon OpenSearch Service**|Managed search and analytics engine based on OpenSearch/Elasticsearch.|Full‑text search, log analytics, and data visualization.|
|**Amazon QuickSight**|Business intelligence service for creating interactive dashboards and visualizations.|Interactive reporting and self-service analytics.|
|**Amazon Redshift**|Scalable cloud data warehouse for analyzing large volumes of structured data.|Complex queries and data warehousing for analytics.|

---

## Application Integration

|Service Name|Easy Description|Examples|
|---|---|---|
|**Amazon EventBridge**|Serverless event bus that connects applications using events.|Triggering workflows on business events; automation tasks.|
|**Amazon SNS (Simple Notification Service)**|Pub/sub messaging and mobile push notifications service.|Sending alerts, notifications, and mobile messages.|
|**Amazon SQS (Simple Queue Service)**|Managed message queuing service to decouple distributed components.|Buffering requests between microservices; task queues.|
|**AWS Step Functions**|Service that coordinates multiple AWS services into serverless workflows.|Orchestrating microservices or long-running processes.|

---

## Business Applications

|Service Name|Easy Description|Examples|
|---|---|---|
|**Amazon Connect**|Cloud-based contact center service designed for customer support.|Setting up a call center; managing customer inquiries.|
|**Amazon SES (Simple Email Service)**|Cost-effective service for sending bulk and transactional emails.|Marketing campaigns; order confirmations.|

---

## Cloud Financial Management

|Service Name|Easy Description|Examples|
|---|---|---|
|**AWS Billing Conductor**|Centralized service for managing billing and cost allocation.|Consolidated billing for multi‑account environments.|
|**AWS Budgets**|Tool to set custom budgets and alerts based on your usage and cost thresholds.|Monitoring monthly spend; cost control alerts.|
|**AWS Cost and Usage Report**|Detailed reports on your AWS usage and associated costs.|In-depth cost analysis and chargeback reporting.|
|**AWS Cost Explorer**|Visual interface to explore, analyze, and manage your AWS spending.|Identifying cost trends and potential savings.|
|**AWS Marketplace**|Digital catalog offering third‑party software and services for AWS.|Procuring vetted applications and software licenses.|
- **Use AWS Budgets** to get alerts when you exceed spending limits.
- **Use AWS Cost Explorer** for visual trends and forecasting.
- **Use AWS Cost and Usage Report** for **detailed** cost tracking (ideal for finance teams).
- **Use AWS Billing Conductor** for **custom billing setups** in multi-account organizations.

---

## Compute

|Service Name|Easy Description|Examples|
|---|---|---|
|**AWS Batch**|Managed service to run batch computing jobs at any scale.|Processing large sets of computational jobs, like media transcoding.|
|**Amazon EC2**|Scalable virtual servers in the cloud for running applications and workloads.|Hosting web applications; running custom server environments.|
|**AWS Elastic Beanstalk**|PaaS that simplifies deployment and scaling of web applications and services.|Quickly deploying websites or APIs without managing the underlying infrastructure.|
|**Amazon Lightsail**|Simplified virtual private servers ideal for small applications and websites.|Simple web hosting; small-scale app deployment.|
|**AWS Local Zones**|Extends AWS regions to deliver compute, storage, and other services closer to end-users.|Low‑latency applications, gaming, or media processing at the edge.|
|**AWS Outposts**|Fully managed AWS infrastructure delivered on-premises for a hybrid cloud setup.|Running AWS services in local data centers or on-premises environments.|
|**AWS Wavelength**|Brings AWS compute and storage services to the edge of telecom networks for ultra-low latency.|Mobile gaming and AR/VR applications with minimal latency.|

### **Key Difference**

- **Local Zones** = Mini AWS regions **with compute and storage** closer to users.
- **Edge Locations** = **Only for content caching and network acceleration** (no compute).
- **Elastic Beanstalk** = Fully managed **PaaS** for deploying scalable apps.
- **Lightsail** = Simple **VPS** with fixed pricing for basic hosting needs.

---

## Containers

|Service Name|Easy Description|Examples|
|---|---|---|
|**Amazon ECR (Elastic Container Registry)**|Managed Docker container registry for storing and managing container images.|Storing Docker images used for microservices.|
|**Amazon ECS (Elastic Container Service)**|Highly scalable container orchestration service to run Docker containers.|Running containerized web applications or services.|
|**Amazon EKS (Elastic Kubernetes Service)**|Managed Kubernetes service to run containerized applications using Kubernetes.|Deploying Kubernetes clusters for microservice architectures.|

---

## Customer Engagement

|Service Name|Easy Description|Examples|
|---|---|---|
|**AWS Activate for Startups**|Program offering credits, training, and support for early-stage startups.|Helping startups accelerate their cloud adoption.|
|**AWS IQ**|Marketplace that connects customers with AWS-certified experts for projects.|Finding consultants for architecture reviews or migrations.|
|**AWS Managed Services (AMS)**|Provides operational management for AWS environments.|Outsourcing day‑to‑day cloud operations and monitoring.|
|**AWS Support**|Technical support services tailored to AWS customers’ needs.|Troubleshooting, best practices guidance, and advisory support.|

---

## Database

|Service Name|Easy Description|Examples|
|---|---|---|
|**Amazon Aurora**|Managed relational database with high performance and MySQL/PostgreSQL compatibility.|Enterprise-grade web applications; high‑availability databases.|
|**Amazon DynamoDB**|Fully managed NoSQL database offering single‑digit millisecond latency.|High‑throughput applications; session management.|
|**Amazon MemoryDB for Redis**|Managed, Redis‑compatible in‑memory data store for caching and real‑time analytics.|Caching for high‑performance apps; real‑time leaderboards.|
|**Amazon Neptune**|Managed graph database service for highly connected data.|Social networks; recommendation engines.|
|**Amazon RDS**|Managed relational database service supporting multiple database engines.|Traditional web applications; business databases.|

---

## Developer Tools

|Service Name|Easy Description|Examples|
|---|---|---|
|**AWS AppConfig**|Service to deploy application configurations safely and dynamically.|Feature flag management; configuration updates without downtime.|
|**AWS CLI**|Command-line tool to interact with AWS services from your terminal or scripts.|Automating routine AWS tasks; scripting deployments.|
|**AWS Cloud9**|Cloud-based integrated development environment (IDE) for coding in the browser.|Collaborative coding; remote development environments.|
|**AWS CloudShell**|Browser-based shell with preconfigured AWS tools for quick command-line access.|On-the‑fly AWS resource management; troubleshooting.|
|**AWS CodeArtifact**|Managed repository service for storing and sharing software packages and dependencies.|Dependency management for software projects.|
|**AWS CodeBuild**|Fully managed build service to compile source code, run tests, and produce artifacts.|Continuous integration and automated build processes.|
|**AWS CodeCommit**|Managed source control service that hosts secure Git repositories.|Version control for code repositories.|
|**AWS CodeDeploy**|Automates code deployments to any instance, including EC2 and on-premises servers.|Rolling updates and blue/green deployments.|
|**AWS CodePipeline**|Orchestrates continuous integration and continuous delivery (CI/CD) workflows.|Automated release pipelines for faster software delivery.|
|**AWS CodeStar**|Provides a unified user interface for managing software development projects on AWS.|Project management and CI/CD integration for development teams.|
|**AWS X-Ray**|Analyzes and debugs distributed applications by tracing requests across services.|Performance troubleshooting in microservices architectures.|

---

## End User Computing

|Service Name|Easy Description|Examples|
|---|---|---|
|**Amazon AppStream 2.0**|Managed application streaming service for delivering desktop applications remotely.|Providing software access without local installation.|
|**Amazon WorkSpaces**|Managed virtual desktop service to provision cloud‑based desktops for users.|Remote work setups; secure virtual desktops for employees.|
|**Amazon WorkSpaces Web**|Browser‑based virtual desktop experience accessible without heavy client software.|Quick access to cloud desktops through a web browser.|

---

## Frontend Web and Mobile

|Service Name|Easy Description|Examples|
|---|---|---|
|**AWS Amplify**|A set of tools and services to build, deploy, and host web and mobile applications.|Rapid frontend development; mobile app backend integration.|
|**AWS AppSync**|Managed GraphQL service that enables real‑time data queries and synchronization.|Building chat apps; real‑time dashboards.|
|**AWS Device Farm**|Cloud-based service for testing mobile apps on real devices across various configurations.|Cross‑platform mobile app testing; ensuring app compatibility.|

---

## Internet of Things (IoT)

|Service Name|Easy Description|Examples|
|---|---|---|
|**AWS IoT Core**|Managed cloud platform to securely connect and manage IoT devices.|Telemetry collection; remote monitoring of sensors.|
|**AWS IoT Greengrass**|Extends AWS capabilities to edge devices for local compute, messaging, and data caching.|Processing data locally on IoT devices before syncing to the cloud.|

---

## Machine Learning

|Service Name|Easy Description|Examples|
|---|---|---|
|**Amazon Comprehend**|Natural language processing service to derive insights from text data.|Sentiment analysis; entity recognition in customer feedback.|
|**Amazon Kendra**|Intelligent search service that uses machine learning to deliver relevant search results.|Enterprise document search; knowledge base applications.|
|**Amazon Lex**|Service to build conversational interfaces and chatbots using voice and text.|Virtual assistants; customer service chatbots.|
|**Amazon Polly**|Converts text into lifelike speech using deep learning.|Voice-enabled applications; audio book generation.|
|**Amazon Rekognition**|Image and video analysis service that detects objects, people, and activities.|Security surveillance; content moderation in media.|
|**Amazon SageMaker**|End‑to‑end platform for building, training, and deploying machine learning models.|Custom ML model development; data science projects.|
|**Amazon Textract**|Uses machine learning to extract text and data from scanned documents.|Automating form processing; document data extraction.|
|**Amazon Transcribe**|Automatic speech recognition service that converts audio to text.|Transcribing customer service calls; captioning videos.|
|**Amazon Translate**|Provides real‑time language translation using advanced deep learning technologies.|Multilingual website content; real‑time translation in apps.|

---

## Management and Governance

|Service Name|Easy Description|Examples|
|---|---|---|
|**AWS Auto Scaling**|Automatically adjusts capacity to maintain application performance based on demand.|Scaling compute resources up/down during traffic spikes.|
|**AWS CloudFormation**|Infrastructure as Code service to provision and manage AWS resources via templates.|Automated deployments; repeatable infrastructure setups.|
|**AWS CloudTrail**|Logs and monitors API calls and account activity across AWS services.|Auditing user actions; security compliance tracking.|
|**Amazon CloudWatch**|Monitoring and observability service for AWS resources and applications.|Collecting metrics and logs; triggering alarms based on thresholds.|
|**AWS Compute Optimizer**|Provides recommendations to optimize compute resource utilization and cost.|Right‑sizing EC2 instances; optimizing resource usage.|
|**AWS Config**|Tracks configuration changes and assesses compliance of AWS resources.|Monitoring changes in resource settings; compliance auditing.|
|**AWS Control Tower**|Simplifies the setup and governance of multi‑account AWS environments.|Establishing landing zones; centralized account governance.|
|**AWS Health Dashboard**|Offers a personalized view into AWS service health and events affecting your resources.|Incident notifications; proactive operational alerts.|
|**AWS Launch Wizard**|Guides you through the deployment of applications with a step‑by‑step wizard interface.|Simplified deployment of complex enterprise applications.|
|**AWS License Manager**|Helps track and manage software licenses across AWS and on‑premises environments.|Managing Microsoft or other licensed software deployments.|
|**AWS Management Console**|Web‑based interface for managing AWS services and resources.|Day‑to‑day resource management; monitoring services.|
|**AWS Organizations**|Centralized management and governance for multiple AWS accounts.|Multi‑account billing; consolidated policy management.|
|**AWS Resource Groups & Tag Editor**|Organize and manage AWS resources by grouping them with tags.|Tagging resources for cost allocation and operational management.|
|**AWS Service Catalog**|Curated catalog of IT services that helps organizations centrally manage commonly deployed services.|Standardizing and provisioning approved services.|
|**AWS Systems Manager**|Provides a unified interface to manage, patch, and configure AWS resources.|Automation of operational tasks; patch management.|
|**AWS Trusted Advisor**|Offers real‑time recommendations for cost optimization, performance, and security best practices.|Regular checks and recommendations to optimize resources.|
|**AWS Well-Architected Tool**|Helps review and improve your cloud architectures based on AWS best practices.|Conducting architectural reviews; identifying risk areas.|

---

## Migration and Transfer

|Service Name|Easy Description|Examples|
|---|---|---|
|**AWS Application Discovery Service**|Gathers on‑premises data to plan migrations by identifying applications and dependencies.|Assessing current workloads before migrating to AWS.|
|**AWS Application Migration Service**|Automates the migration of on‑premises applications to AWS with minimal downtime.|Lift‑and‑shift migrations for legacy applications.|
|**AWS Database Migration Service (DMS)**|Migrates databases to AWS quickly and securely with minimal downtime.|Transferring databases from on‑premises to cloud environments.|
|**AWS Migration Hub**|Provides a central dashboard to track migration progress across multiple services.|Monitoring the status of several simultaneous migrations.|
|**AWS Schema Conversion Tool (SCT)**|Converts database schemas to formats compatible with AWS database engines.|Migrating from commercial databases to open‑source engines.|
|**AWS Snow Family**|Physical devices to securely transfer large amounts of data into and out of AWS.|Moving petabytes of data from remote locations to AWS.|
|**AWS Transfer Family**|Managed file transfer service that supports protocols like SFTP for secure transfers.|Integrating on‑premises file storage with Amazon S3.|

---

## Networking and Content Delivery

|Service Name|Easy Description|Examples|
|---|---|---|
|**Amazon API Gateway**|Managed service for creating, publishing, maintaining, and securing APIs.|Building RESTful or WebSocket APIs for serverless backends.|
|**Amazon CloudFront**|Content delivery network (CDN) that speeds up the distribution of static and dynamic content.|Delivering websites, videos, and APIs globally with low latency.|
|**AWS Direct Connect**|Provides a dedicated, private network connection from your premises to AWS.|Private connectivity for large data transfers or hybrid cloud setups.|
|**AWS Global Accelerator**|Improves availability and performance for global applications by routing traffic optimally.|Enhancing user experience for international web applications.|
|**Amazon Route 53**|Scalable Domain Name System (DNS) service for reliable and cost-effective routing.|Domain registration; routing traffic to applications.|
|**Amazon VPC**|Provides an isolated virtual network to launch AWS resources in a secure environment.|Creating a private network for secure cloud applications.|
|**AWS VPN**|Establishes secure, encrypted connections between on‑premises networks and AWS.|Connecting remote offices or data centers to AWS resources.|

---

## Security, Identity, and Compliance

|Service Name|Easy Description|Examples|
|---|---|---|
|**AWS Artifact**|Provides on‑demand access to AWS compliance reports and documentation.|Accessing audit and compliance reports for regulatory needs.|
|**AWS Audit Manager**|Automates the process of collecting evidence for audits and compliance.|Streamlining compliance audits and evidence collection.|
|**AWS Certificate Manager (ACM)**|Manages SSL/TLS certificates to secure your websites and applications.|Automating certificate renewals for HTTPS websites.|
|**AWS CloudHSM**|Offers managed hardware security modules (HSM) for performing cryptographic operations.|High‑security key management and encryption operations.|
|**Amazon Cognito**|Provides user sign‑up, sign‑in, and access control for web and mobile apps.|User authentication for mobile and web applications.|
|**Amazon Detective**|Helps analyze, visualize, and investigate security issues using machine learning.|Investigating suspicious activities and security incidents.|
|**AWS Directory Service**|Offers managed directory services, including Microsoft Active Directory integration.|Centralized user and resource management in enterprise environments.|
|**AWS Firewall Manager**|Centralizes management of firewall rules and policies across accounts and applications.|Enforcing security policies across VPCs and accounts.|
|**Amazon GuardDuty**|Continuous threat detection service that monitors for malicious activity.|Detecting compromised instances or unauthorized activities.|
|**AWS Identity and Access Management (IAM)**|Manages users, roles, and permissions to securely control access to AWS resources.|Fine‑grained access control policies for AWS accounts.|
|**AWS IAM Identity Center (AWS SSO)**|Simplifies single sign‑on access for multiple AWS accounts and business applications.|Centralized authentication and user management across services.|
|**Amazon Inspector**|Automated security assessment service to improve application security and compliance.|Regular vulnerability scanning of EC2 instances.|
|**AWS Key Management Service (KMS)**|Creates and controls encryption keys used to secure data across AWS services.|Managing encryption keys for data at rest and in transit.|
|**Amazon Macie**|Uses machine learning to discover, classify, and protect sensitive data.|Identifying and safeguarding personally identifiable information (PII).|
|**AWS Network Firewall**|Managed firewall service to protect VPCs from network threats.|Implementing VPC-level security with customizable rules.|
|**AWS Resource Access Manager (RAM)**|Allows sharing of AWS resources across accounts securely.|Sharing VPC subnets or license configurations between teams.|
|**AWS Secrets Manager**|Securely stores and manages sensitive information such as API keys and passwords.|Rotating credentials and securing secret data.|
|**AWS Security Hub**|Provides a centralized view of security alerts and compliance status across AWS accounts.|Consolidating and managing security findings from multiple sources.|
|**AWS Shield**|Managed DDoS protection service that safeguards applications against attacks.|Mitigating DDoS attacks on web applications.|
|**AWS WAF**|Web application firewall that helps protect applications from common web exploits.|Blocking malicious web requests and filtering traffic.|

---

## Serverless

|Service Name|Easy Description|Examples|
|---|---|---|
|**AWS Fargate**|Serverless compute engine for running containers without managing servers.|Running containers for microservices without EC2 management.|
|**AWS Lambda**|Executes code in response to events without provisioning or managing servers.|Event‑driven functions such as image processing, data transformation, or real‑time file processing.|

---

## Storage

|Service Name|Easy Description|Examples|
|---|---|---|
|**AWS Backup**|Centralized backup service for automating and managing backups across AWS services.|Regular backup of databases, file systems, and application data.|
|**Amazon EBS (Elastic Block Store)**|Block storage service designed for use with Amazon EC2 instances.|Persistent storage for virtual machines and databases.|
|**Amazon EFS (Elastic File System)**|Scalable file storage that can be mounted on EC2 instances and on‑premises.|Shared file storage for content management systems and web servers.|
|**AWS Elastic Disaster Recovery**|Service that replicates and recovers IT infrastructure during disruptions.|Enabling quick recovery and minimizing downtime after a disaster.|
|**Amazon FSx**|Managed file storage optimized for Windows or high‑performance computing applications.|File systems for Windows-based applications or HPC workloads.|
|**Amazon S3**|Scalable object storage service for a wide variety of data types and use cases.|Data lakes, static website hosting, backup storage.|
|**Amazon S3 Glacier**|Low‑cost, long‑term archival storage designed for infrequent access.|Archiving historical data or compliance records.|
|**AWS Storage Gateway**|Hybrid cloud storage solution that integrates on‑premises software with cloud storage.|Seamless file, volume, or tape backup between on‑premises and AWS.|

---
---

# OLD TABLE (DONT REFER)

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