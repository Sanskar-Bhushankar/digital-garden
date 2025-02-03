---
{"dg-publish":true,"permalink":"/aws-cloud/4-security/5-detection/","title":"AWS Security Detection","tags":["aws","security","detection"],"created":"2024-12-13T17:42:16.365+05:30"}
---

one short security - [aws security - last min rev](../aws%20security%20-%20last%20min%20rev.md)
## CIA Triad

confidentiality - Confidentiality ensures that information is accessible only to authorized individuals, maintaining privacy and preventing unauthorized disclosure.

Integrity - Integrity ensures that data remains accurate, trustworthy, and consistent throughout its lifecycle

Availability - availability ensures that information and resources are accessible to authorized users when needed.

DDoS (Distributed Denial of Service) is when lots of computers flood a website or service with so much traffic that it crashes and stops working for everyone else.

The specific AWS service designed to help prevent DDoS (Distributed Denial of Service) attacks is called **AWS Shield**.

## IDS (Intrusion detection system)

An Intrusion Detection System (IDS) works by monitoring network traffic or system activities in real-time. It analyzes incoming data packets, system logs, or other sources to detect signs of malicious activities or policy violations. When suspicious behavior is identified, the IDS generates alerts or notifications to security personnel or automated systems for further investigation or action. IDS can operate in two main modes:

1. **Signature-Based Detection:** Compares incoming data packets or system activity against a database of known attack patterns or signatures. If a match is found, it triggers an alert.

2. **Anomaly-Based Detection:** Establishes a baseline of normal network or system behavior. It then identifies deviations from this baseline that may indicate an attack or unauthorized activity. 


## IDS VS IPS
**IDS (Intrusion Detection System)** and **IPS (Intrusion Prevention System)** 

| Feature        | **IDS (Intrusion Detection System)**                           | **IPS (Intrusion Prevention System)**                                        |
| -------------- | -------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| **Function**   | Detects and alerts on potential security breaches              | Detects and actively blocks potential security breaches                      |
| **Action**     | Passive; only provides alerts, no direct action on traffic     | Active; blocks or prevents malicious traffic in real time                    |
| **Deployment** | Typically placed in "monitoring" mode, behind the firewall     | Typically placed in-line, directly in the path of network traffic            |
| **Response**   | Sends alerts to administrators for further investigation       | Automatically takes action (e.g., blocks traffic) without human intervention |
| **Use Case**   | Useful for detecting attacks and providing alerts for analysis | Suitable for preventing attacks and stopping threats in real-time            |
