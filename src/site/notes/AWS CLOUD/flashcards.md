---
{"dg-publish":true,"permalink":"/AWS CLOUD/flashcards/","title":"AWS Flashcards","created":"2025-02-21T15:53:26.922+05:30"}
---


- Auto scaling grp manages the number of instances wheareas elastic load balancing distributes the traffic across them
- High economies of scale** means **reducing costs as the scale of operations increases**. (Means aws continiously tries to lower the costs of its services)

### **Differences Between AWS Billing & Cost Management Tools**

| Feature              | **A. AWS Bills**              | **B. Cost Explorer**                 | **C. AWS Cost and Usage Report (CUR)** | **D. AWS Budgets**           | E. AWS Billing conductor                                                                                                        |
| -------------------- | ----------------------------- | ------------------------------------ | -------------------------------------- | ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| **Purpose**          | View monthly bills & invoices | Analyze past & forecast future costs | Detailed raw cost & usage data         | Set alerts for budget limits | Customize, group, and manage AWS **billing and chargeback** for accounts within an organization.                                |
| **Data Depth**       | Basic summary of charges      | Graphical cost trends & filtering    | Most detailed, per-resource usage      | High-level budget tracking   | Provides **summary-level billing data**.<br>Supports integration with **AWS Cost Explorer, QuickSight, and external BI tools**. |
| **Use Case**         | Checking total AWS charges    | Identifying cost trends & anomalies  | Deep analysis of cost breakdown        | Prevent overspending         | Helps businesses **allocate, customize, and distribute** AWS costs internally (e.g., chargeback for business units).            |
| **Update Frequency** | Monthly                       | Daily                                | Hourly/Daily                           | Continuous monitoring        |                                                                                                                                 |
| **Format**           | Web UI, CSV download          | Interactive graphs & filters         | CSV reports in S3                      | Email & SNS alerts           | Generates **detailed CSV reports** in Amazon S3.                                                                                |

### **Key Takeaways:**

- **Use AWS Bills** to see your total invoice.
- **Use Cost Explorer** to analyze trends & forecast costs.
- **Use AWS Cost and Usage Report (CUR)** for **detailed** per-resource usage in S3.
- **Use AWS Budgets** to **set alerts** when spending exceeds limits.

---
### **Difference Between AWS CloudWatch, CloudTrail, CloudFormation, Config, GuardDuty, Trusted Advisor, AWS Health Dashboard, Shield, Security Hub, Inspector, and WAF**

| **Service**                            | **Purpose (Detailed Explanation)**                                                                                                                                                                          | **Key Features**                                                                                                                                                                                                                                                                                                                                                                                       | **Common Use Cases**                                                                                                                                                                                                                           |
| -------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **AWS CloudTrail**                     | Tracks and records all AWS API calls made by users, roles, and services. It provides a **detailed audit log** of who did what in the AWS environment, helping in security, compliance, and troubleshooting. | - Logs every AWS **API call and user activity**. - Captures the **who, what, when, and where** of every action. - Stores logs in **Amazon S3** for auditing. - Integrates with **CloudWatch for real-time alerts**. - Supports **multi-region and multi-account logging**.                                                                                                                             | - **Security auditing**: Track unauthorized access or configuration changes. - **Compliance monitoring**: Maintain logs for regulatory needs. - **Troubleshooting**: Investigate failed API calls and errors.                                  |
| **Amazon CloudWatch**                  | Monitors AWS resources and applications in real-time by collecting and analyzing logs, metrics, and events. It helps track performance, detect anomalies, and trigger automated responses.                  | - Monitors EC2, Lambda, RDS, DynamoDB, API Gateway, and more. - Creates alarms for CPU usage, disk space, memory, etc. - Collects logs from applications and AWS services. - Uses **CloudWatch Logs, Metrics, Alarms, and Dashboards**. - Supports **CloudWatch Events and Logs Insights** for real-time monitoring.                                                                                   | - Monitor **server health, application performance, and AWS resource utilization**. - Set up **alerts for high CPU usage, errors, or failures**. - Automate actions like **scaling EC2 instances** when needed.                                |
| **AWS CloudFormation**                 | Automates AWS resource deployment using infrastructure-as-code (IaC). It allows users to define resources (EC2, RDS, S3, IAM, etc.) in a template and deploy them in a predictable, repeatable manner.      | - Uses **YAML or JSON templates** to define infrastructure. - Supports **version control** and rollback in case of failure. - Creates and manages **stacks** for deploying multiple resources together. - Automates provisioning of **EC2, VPCs, RDS, Lambda, IAM roles, and more**. - Integrates with **AWS CDK (Cloud Development Kit) for code-based infrastructure**.                              | - **Automate infrastructure deployment** instead of manual setup. - **Manage large-scale environments** efficiently. - **Enforce security and compliance** by ensuring consistent configurations.                                              |
| **AWS Config**                         | Continuously monitors, records, and evaluates AWS resource configurations to ensure compliance with security policies and best practices.                                                                   | - **Tracks configuration changes** for AWS resources like EC2, S3, IAM, RDS. - **Evaluates compliance** with custom or AWS-provided rules. - **Provides a history of changes** for auditing and troubleshooting. - **Sends alerts** if a resource becomes non-compliant. - **Generates reports** to assess security posture over time.                                                                 | - **Ensure security compliance** (e.g., check if all S3 buckets are private). - **Track changes in AWS resources** to investigate issues. - **Audit configuration history** to find misconfigurations and prevent security risks.              |
| **Amazon GuardDuty**                   | A security monitoring service that detects **suspicious activities and potential threats** in AWS environments by analyzing logs, network traffic, and user behavior.                                       | - Uses **machine learning and anomaly detection**. - Monitors **VPC Flow Logs, CloudTrail logs, and DNS logs**. - Detects **compromised IAM credentials, unauthorized access, malware, and port scanning**. - Provides **real-time threat intelligence**. - No need for manual configuration—**fully managed service**.                                                                                | - **Detect security breaches**, unauthorized access, or compromised resources. - **Monitor AWS accounts for unusual activity** (e.g., login from unknown locations). - **Prevent attacks like crypto-mining, DDoS, and brute force attempts**. |
| **AWS Trusted Advisor**                | Provides **recommendations to optimize AWS usage** in terms of security, performance, cost, and best practices. It helps in identifying misconfigurations and underutilized resources.                      | - Security checks: **Detects open security groups, weak IAM policies, and unencrypted S3 buckets**. - Cost optimization: **Identifies unused EC2 instances, idle resources**. - Performance improvements: **Suggests better resource configurations**. - Fault tolerance: **Identifies high-risk single points of failure**. - Service limits: **Alerts when AWS limits are close to being exceeded**. | - **Identify and fix security vulnerabilities** (e.g., open ports, public S3 buckets). - **Reduce AWS costs** by removing unused resources. - **Ensure high availability and fault tolerance**.                                                |
| **AWS Health Dashboard**               | Provides real-time information about **AWS service availability and health**. It notifies users about ongoing AWS outages, scheduled maintenance, and service degradation.                                  | - **Personalized alerts** based on your AWS region and services. - Displays **ongoing and past AWS incidents**. - Offers a **Public Health Dashboard** for general AWS status. - Integrates with **AWS Organizations for multi-account visibility**. - Sends **proactive notifications for upcoming maintenance**.                                                                                     | - **Check AWS service outages** affecting your resources. - **Receive alerts for planned maintenance**. - **Diagnose service disruptions** before troubleshooting internally.                                                                  |
| **AWS Shield**                         | Protects AWS applications from **DDoS (Distributed Denial of Service) attacks** automatically.                                                                                                              | - Two tiers: **Shield Standard (free) and Shield Advanced (paid)**. - Protects **AWS resources like CloudFront, Route 53, and ALB**. - Shield Advanced offers **real-time attack visibility and 24/7 response team support**. - Works with **AWS WAF** to block malicious traffic. - **Automated attack detection and mitigation**.                                                                    | - **Prevent DDoS attacks on web applications and APIs**. - **Ensure high availability** of AWS services even during attacks. - **Get real-time attack insights and response support**.                                                         |
| **AWS Security Hub**                   | **Aggregates security findings** from AWS security services and third-party tools to provide a **centralized security dashboard**.                                                                          | - Integrates with **GuardDuty, Inspector, Macie, IAM Access Analyzer**. - Uses **AWS security standards like CIS AWS Foundations Benchmark**. - Provides **automated security scorecards and compliance checks**. - Supports **custom security rules and threat prioritization**. - Helps with **continuous security monitoring across AWS accounts**.                                                 | - **Centralized security monitoring** for AWS accounts. - **Ensure compliance** with security frameworks. - **Detect misconfigurations and security vulnerabilities quickly**.                                                                 |
| **AWS Inspector**                      | **Scans AWS workloads for vulnerabilities and security issues**, including EC2, Lambda, and container images.                                                                                               | - **Automated security assessment** for EC2, Lambda, and container workloads. - Detects **outdated packages, CVEs, and insecure configurations**. - Integrates with **AWS Security Hub**. - Provides **continuous scanning** and **risk-based prioritization**. - Works without manual configurations—**fully managed**.                                                                               | - **Find and fix vulnerabilities in AWS workloads**. - **Ensure EC2 instances and Lambda functions are secure**. - **Automate vulnerability assessments instead of manual penetration testing**.                                               |
| **AWS WAF (Web Application Firewall)** | Protects web applications from **common web threats** like SQL injection, XSS, and bot attacks.                                                                                                             | - **Blocks malicious web traffic** before it reaches the application. - Works with **CloudFront, ALB, API Gateway, and AppSync**. - Uses **custom rules and managed rules from AWS Marketplace**. - Provides **rate-based rules to prevent brute force attacks**. - Can be integrated with **AWS Shield for enhanced protection**.                                                                     | - **Prevent SQL injection, XSS, and bot attacks on web apps**. - **Protect APIs and web applications from abuse**. - **Ensure compliance with security policies for web traffic**.                                                             |

---

### **Summary:**

- **CloudWatch** → **Monitor AWS performance, logs, and metrics**.
- **CloudTrail** → **Track API calls and user actions for auditing**.
- **CloudFormation** → **Automate AWS infrastructure deployment**.
- **Config** → **Track resource configurations for compliance**.
- **GuardDuty** → **Detect security threats and anomalies**.
- **Trusted Advisor** → **Get AWS cost, security, and performance recommendations**.
- **Health Dashboard** → **Track AWS service health and outages**.
- **Shield** → **DDoS protection for AWS applications**.
- **Security Hub** → **Centralized security management and compliance**.
- **Inspector** → **Vulnerability scanning for AWS workloads**.
- **WAF** → **Protect web applications from common web threats**.

---
# Storage gateway 
- used to connect on premise storage to aws cloud storage like s3,block storage

# Direct connect
- A **private, dedicated network** link between your data center and AWS for **fast and secure** connectivity.
- **A dedicated fiber-optic connection** is set up between AWS and your on-premises network.

# AWS vpn
- A **secure internet-based connection** between on-premises and AWS VPC.

|Feature|AWS Direct Connect|AWS VPN|
|---|---|---|
|**Speed**|Up to 100 Gbps|Limited by internet|
|**Security**|Private link (no internet)|Encrypted over public internet|
|**Stability**|Very stable|Depends on internet quality|
|**Cost**|Higher upfront, lower transfer cost|Lower setup cost, but higher data transfer costs|

# **AWS Transit Gateway** 
-  A **central hub** that connects multiple VPCs and on-premises networks efficiently
- **Example**
- You have **3 VPCs** (Sales, HR, IT) and an **on-premises office network**, Instead of linking each VPC separately, you **connect all to a Transit Gateway**. Now, **all networks can communicate through one central hub** efficiently.

---

### **AWS Serverless vs. Server-Based Services**

|**Serverless Services**|**Server-Based Services**|
|---|---|
|**AWS Lambda** (Run code without managing servers)|**Amazon EC2** (Virtual servers in the cloud)|
|**Amazon API Gateway** (Manage APIs without servers)|**Amazon RDS** (Managed relational databases)|
|**AWS Fargate** (Serverless container service)|**Amazon ECS (EC2 Launch Type)** (Managed container service with EC2 instances)|
|**Amazon S3** (Object storage, no server management)|**Amazon EBS** (Block storage attached to EC2)|
|**Amazon DynamoDB** (NoSQL database, fully managed)|**Amazon Redshift** (Data warehouse with provisioned servers)|
|**AWS Step Functions** (Orchestration service)|**Amazon EMR** (Big data processing with EC2 clusters)|
|**AWS App Runner** (Deploy and scale applications easily)|**Amazon MQ** (Managed message broker on EC2)|
|**AWS Glue** (ETL and data integration, serverless)|**Amazon OpenSearch Service** (Managed Elasticsearch, requires EC2 instances)|
|**Amazon EventBridge** (Event-driven architecture, no servers)|**Amazon Elastic Beanstalk (EC2 Option)** (Managed application hosting with EC2)|
|**AWS CloudFront** (Content delivery network, fully managed)|**Amazon Lightsail** (Simple cloud server hosting)|
|**AWS Aurora Serverless** (Autoscaling relational DB)|**Amazon FSx** (Managed file storage on EC2 instances)|
|**Amazon SNS** (Pub/Sub messaging, fully managed)|**Amazon Elasticache (EC2-based option)** (In-memory caching on EC2)|
|**Amazon SQS** (Managed message queuing, no servers)|**Amazon Kinesis (EC2-based option)** (Data streaming service with EC2 instances)|

**Key Differences:**

- **Serverless services** automatically **scale**, have **no infrastructure management**, and offer **pay-per-use** pricing.
- **Server-based services** require **manual provisioning**, **server management**, and typically **run on EC2 instances**.

---

**ECS (Elastic Container Service)** is a container orchestration service where you manage the underlying EC2 instances (servers) for running containers.
**Fargate** is a **serverless** compute option for ECS where AWS manages the infrastructure, so you don't have to provision or manage EC2 instances.
**Key Difference**: ECS (with EC2) gives more control over instances, while Fargate is fully managed and abstracts the infrastructure.

---
