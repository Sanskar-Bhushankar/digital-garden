---
{"dg-publish":true,"permalink":"/aws-cloud/1-cloud-foundations/basics-of-cloud/","created":"2024-12-02T16:44:08.597+05:30"}
---


#### **Servers and Data Centers**

- **Server:** A computer that provides data or services to clients over a network.
    - Types of servers include:
        - **Web Server:** Hosts websites and serves web pages to users.
        - **Database Server:** Manages and serves databases for applications.
        - **Mail Server:** Handles email delivery and management.
- **Data Centers:**
    - **Definition:** Secure facilities hosting servers, networks, and storage devices.
    - **Features:** Climate control, power supplies, and physical security ensure optimal conditions.
    - **Ownership Models:**
        - **On-premises Data Centers:** Managed by organizations, involving high costs for hardware, software, facilities, and staffing.
        - **Cloud Model:** Providers (e.g., AWS) manage data centers, offering resources on a **pay-as-you-go** basis.

---

#### **Virtual Machines (VMs)**

- **Definition:** Software-based emulation of a physical computer.
    - **Host:** Physical computer running the VMs.
    - **Hypervisor:** Software layer managing resource allocation (CPU, memory, disk, network) for VMs.
    - **Multiple VMs:** Can run on a single host, each with its own OS and applications.

**Benefits of VMs:**

1. **Cost Savings:** Reduce hardware costs by running multiple VMs on one physical machine.
2. **Efficiency:** Improve resource utilization, reducing waste from underused servers.
3. **Reusability and Portability:** VM images can be cloned and moved easily across hosts.

**Cloud and VMs:**

- VMs are the **building blocks** of cloud computing.
- Services like **Amazon EC2** let users create and manage VMs in a scalable, pay-as-you-go model.


### SDLC Phases 

![Pasted image 20241202164713.png](/img/user/AWS%20CLOUD/1.%20Cloud%20Foundations/attachments/Pasted%20image%2020241202164713.png)


1. **Plan:** Define project goals, resources, and a roadmap to guide development.
2. **Analyze:** Collect and document detailed software requirements in an SRS document.
3. **Design:** Create a technical blueprint and specify architectures in a design document.
4. **Develop:** Write the code to build the software according to the design specifications.
5. **Test:** Verify software functionality, identify defects, and ensure it meets requirements.
6. **Implement:** Deploy the application in a production environment for end-user access.
7. **Maintain:** Monitor, update, and enhance the software to meet evolving needs.

