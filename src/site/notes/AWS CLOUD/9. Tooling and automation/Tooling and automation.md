---
{"dg-publish":true,"permalink":"/AWS CLOUD/9. Tooling and automation/Tooling and automation/","title":"Tooling and automation (systems manager, cloud formation, Ops works)","tags":["aws-systems-manager","aws-ops-works","aws-cloudformation"],"created":"2025-02-19T13:03:44.135+05:30"}
---

## AWS Systems Manager

AWS Systems Manager is a collection of capabilities designed to help you manage applications and infrastructure within the AWS Cloud. It allows users to automate administrative tasks, manage OS configurations, apply patches, and create system images. Systems Manager can automate the configuration and management of systems both on-premises and in the AWS Cloud.

**Core Capabilities of Systems Manager**:

|Capability|Description|
|:--|:--|
|Documents|Defines the actions that Systems Manager performs on managed instances. Documents can be pre-defined by Amazon, customized, or shared between accounts.|
|Automation|Automates common and repetitive IT operations and management tasks across AWS resources. It uses SSM documents to define a series of steps to be performed on AWS resources, such as remediating unreachable instances or patching instances.|
|Run Command|Automates the execution of predefined commands against EC2 instances. It allows for running commands immediately or on a schedule and supports both predefined and custom commands. It reduces management overhead by eliminating the need for bastion hosts or SSH keys.|
|Session Manager|Enables secure connections to instances without opening inbound ports, using bastion hosts, or managing SSH keys. It provides auditable instance management and helps comply with corporate security policies.|
|Patch Manager|Automates the deployment of OS and software patches across EC2 instances or on-premises machines. It involves creating patch baselines, defining maintenance windows, applying patches, and auditing results.|
|Maintenance Windows|Allows scheduling windows of time to run administrative and maintenance tasks across instances, such as patching, updating drivers, or installing software. Tasks can include commands run by Run Command, Automation workflows, Step Functions workflows, or Lambda functions.|
|State Manager|Maintains consistent configuration of EC2 or on-premises instances by preventing configuration drift. It uses SSM documents to define the desired state and applies it to the instances on a defined schedule.|
|Parameter Store|Provides a centralised store to manage configuration data or secrets. It stores data as name-value pairs, which can be plain text or encrypted. It uses AWS KMS to encrypt parameter values.|
|Inventory|Collects information about instances and the software installed on them, such as application data, files, network configurations, and system properties. It provides a comprehensive understanding of system configurations across multiple instances without needing to log in to each one.|

### AWS CloudFormation

AWS CloudFormation allows you to create, update, and delete a set of AWS resources as a single unit. With CloudFormation, infrastructure can be modeled in a text file written in JSON or YAML.

**Key Features**:

- Previewing proposed changes to a stack.
- Detecting drift.
- Invoking AWS Lambda functions.

**How CloudFormation Works**:

1. ==Define Resources==: Define AWS resources in a template, or use a prebuilt template.
2. ==Upload Template==: Upload the template to CloudFormation, or store it in Amazon S3.
3. ==Run Create Stack Action==: The CloudFormation service reads the template and creates the specified resources in the AWS account.
4. ==Stack Creation==: Observe the stack-creation process. The stack retains control of the resources, allowing for updates, drift detection, or deletion.

**Benefits of CloudFormation**:

- **Reusability, Repeatability, and Maintainability**: Deploy complex environments rapidly, duplicate environments, ensure configuration consistency.
- **Single Action Resource Management**: Delete resources in a single action by deleting the stack and propagate changes to all stacks by updating the templates.

### AWS OpsWorks

AWS OpsWorks is a configuration management service that helps automate how servers are configured, deployed, and managed. It provides managed instances of Chef and Puppet.

**Features of OpsWorks**:

- Automates configuration management.
- Based on Chef and Puppet open-source automation platforms.

**OpsWorks Offerings**:

- **AWS OpsWorks for Chef Automate**: Provides a fully managed Chef Automate server for workflow automation.
- **AWS OpsWorks for Puppet Enterprise**: Provides a managed Puppet Enterprise server and automation tools for orchestration, provisioning, and visualisation.
- **AWS OpsWorks Stacks**: A configuration management service that helps configure and operate applications using Chef.

In summary, these tools ([AWS Systems Manager, AWS CloudFormation, and AWS OpsWorks) ] provide a range of options for automating and managing AWS infrastructure and applications. They enable users to define and codify their infrastructure, automate repetitive tasks, and maintain consistent configurations across their AWS environments.


---
# summary gpt ==last min revision==
### **AWS Systems Manager**

- **What it does:**  
    Manages and automates everyday tasks on both AWS servers and on-premises machines.

|**Capability**|**Description**|**Example**|
|---|---|---|
|**Documents**|Scripts/instructions (SSM documents) that define tasks for managed instances.|Create a document to update software packages across instances.|
|**Automation**|Runs workflows to automate common IT operations and management tasks.|Auto-remediate non-compliant instances.|
|**Run Command**|Executes commands remotely on instances without needing SSH or bastion hosts.|Run a script to update configuration settings.|
|**Session Manager**|Enables secure, auditable access to instances without opening inbound ports.|Log in to an instance securely for troubleshooting.|
|**Patch Manager**|Automates the deployment of OS and software patches across instances.|Schedule automatic OS patching to fix vulnerabilities.|
|**Maintenance Windows**|Schedules designated time windows to perform maintenance tasks on instances.|Set up a window for routine system updates during off-peak hours.|
|**State Manager**|Ensures instances remain in a consistent, desired state to prevent configuration drift.|Enforce configuration standards across servers.|
|**Parameter Store**|Provides a secure, centralized store for configuration data and secrets.|Store and encrypt database credentials.|
|**Inventory**|Collects detailed information about instances, including installed software and configurations.|Generate reports on system configurations across your fleet.|

---

### **AWS CloudFormation**

- **What it does:**  
    Uses templates (in JSON or YAML) to create and manage your entire AWS infrastructure as code.
- **How it works & Example:**
    1. **Define Resources:** Write a template listing the servers, databases, and other resources you need.
    2. **Upload & Run:** Upload the template and let CloudFormation create everything in one go.  
        _Example:_ Deploying a complete web application (with EC2 servers, databases, and load balancers) automatically using a single template.

---

### **AWS OpsWorks**

- **What it does:**  
    Automates server setup and management using popular tools like Chef and Puppet.
- **Key Features & Examples:**
    - **Chef/Puppet Integration:** Uses “recipes” or instructions to configure servers.  
        _Example:_ Automatically installing and configuring a web server on new machines with a Chef recipe.
    - **Managed Services:** Provides fully managed versions of Chef and Puppet, so you don’t need to set them up yourself.

---

**In Short:**

- **Systems Manager** helps you handle day-to-day server tasks like updates, configurations, and secure access.
- **CloudFormation** lets you create and manage your entire AWS environment with a single code template.
- **OpsWorks** focuses on automating server configurations using tools like Chef or Puppet.

Each service is designed to reduce manual work and keep your infrastructure consistent and secure.

---

#### Table 2: Comparison of AWS Systems Manager, AWS CloudFormation, and AWS OpsWorks

|**Feature**|**AWS Systems Manager**|**AWS CloudFormation**|**AWS OpsWorks**|
|---|---|---|---|
|**Purpose**|Manage and automate day-to-day tasks for both AWS and on-premises systems.|Provision and manage AWS resources using infrastructure-as-code (IaC).|Automate server configuration, deployment, and management using Chef/Puppet.|
|**Key Capabilities**|Documents, Automation, Run Command, Session Manager, Patch Manager, Maintenance Windows, State Manager, Parameter Store, Inventory.|Template-based resource definition, stack management, change previews, drift detection, Lambda integration.|Managed Chef Automate, Puppet Enterprise, OpsWorks Stacks, and configuration automation.|
|**Typical Use Cases**|Routine system management, patching, secure remote access, maintaining configuration consistency.|Deploying, updating, and tearing down multi-tier applications or entire infrastructure stacks.|Server configuration management, automated deployments, and orchestration.|
|**Automation Approach**|Uses SSM documents and workflows to perform specific operational tasks automatically.|Uses declarative templates (JSON/YAML) to define infrastructure and automate resource lifecycle management.|Leverages Chef and Puppet recipes to automate server provisioning and configuration.|
