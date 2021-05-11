# Describe general security and network security features

This section exam weighting has remained the same at 10-15%.

<!-- TOC depthfrom:2 depthto:3 -->

- [Describe Azure security features](#describe-azure-security-features)
  - [Describe basic features of Azure Security Center, including policy compliance, security alerts, secure score, and resource hygiene](#describe-basic-features-of-azure-security-center-including-policy-compliance-security-alerts-secure-score-and-resource-hygiene)
  - [Describe the functionality and usage of Key Vault](#describe-the-functionality-and-usage-of-key-vault)
  - [Describe the functionality and usage of Azure Sentinel](#describe-the-functionality-and-usage-of-azure-sentinel)
  - [Describe the functionality and usage of Azure Dedicated Hosts](#describe-the-functionality-and-usage-of-azure-dedicated-hosts)
- [Describe Azure network security](#describe-azure-network-security)
  - [Describe the concept of defense in depth](#describe-the-concept-of-defense-in-depth)
  - [Describe the functionality and usage of Network Security Groups NSG](#describe-the-functionality-and-usage-of-network-security-groups-nsg)
  - [Describe the functionality and usage of Azure Firewall](#describe-the-functionality-and-usage-of-azure-firewall)
  - [Describe the functionality and usage of Azure DDoS protection](#describe-the-functionality-and-usage-of-azure-ddos-protection)

<!-- /TOC -->

## Describe Azure security features

### Describe basic features of Azure Security Center, including policy compliance, security alerts, secure score, and resource hygiene

#### Azure Security Center

**Azure Security Center** is a monitoring service that provides visibility of your _security posture_ across all of your services, both on Azure and on-premises. Security posture refers to policies and controls, as well as how well you can predict, prevent, and respond to security threats.

* Monitor security settings across on-premises and cloud workloads.
* Apply required security settings to new resources automatically as they come online.
* Provide security recommendations that are based on your current configurations.
* Monitor your resources continuously and identify potential vulnerabilities automatically.
* Detect and block malware from being installed on your VMs using machine learning.
* Detect and analyze potential attacks and investigate threats and any post-breach activity that might have occurred.
* Provide just-in-time access control for network ports in order to reduce your attack surface.

You can use Security Center to view your overall regulatory _compliance_ all from one place, because the company's resources are analyzed against the security controls of any governance policies it has assigned.

You can use Security Center to get a centralized view of all your security alerts. From there, you can dismiss false alerts, investigate them further, remediate alerts manually, or use an automated response with a _workflow automation_.

_Secure score_ is a measurement of an organization's security posture. It is based on _security controls_, or groups of related security recommendations. 

Your score is based on the percentage of security controls that you satisfy. Secure score helps you:

* Report on the current state of your organization's security posture.
* Improve your security posture by providing discoverability, visibility, guidance, and control.
* Compare with benchmarks and establish _key performance indicators (KPIs)_.

In the _resource hygiene_ section, to help prioritize remediation actions, recommendations are categorized as low, medium, and high.

Security Center includes advanced cloud defence capabilities for VMs, network security, and file integrity.

* **Just-in-time VM access**: configure just-in-time access to VMs, where traffic is blocked by default to specific network ports, but allows traffic for a specified time.
* **Adaptive application controls**: control which applications are allowed to run on its VMs using machine learning and provides recommendations.
* **Adaptive network hardening**: compare traffic patterns with current network security group (NSG) settings, and make recommendations for hardening the network.
* **File integrity monitoring**: monitor changes to important files on both Windows and Linux, registry settings, applications, and other aspects that might indicate a security attack.

### Describe the functionality and usage of Key Vault

**Azure Key Vault** is a centralized cloud service for storing an application's secrets securely, by providing access control and logging capabilities.

* **Manage secrets**: store and tightly control access to tokens, passwords, certificates, API keys etc.
* **Manage encryption keys**: create and control the encryption keys that are used to encrypt your data.
* **Manage SSL/TLS certificates**: provision, manage, and deploy your public and private SSL/TLS certificates for both your on-premises and Azure resources.
* **Store secrets backed by hardware security modules (HSMs)**: store secrets and keys that can be protected either by software or FIPS 140-2 Level 2 validated HSMs.

The benefits of using Key Vault are:

* **Centralized application secrets**: centralizing your application secrets enable you to control their distribution, and reduces the chances that secrets are accidentally leaked.
* **Securely stored secrets and keys**: uses industry-standard algorithms, key lengths, and HSMs.
* **Access monitoring and access control**: monitor and control access to your secrets.
* **Simplified administration of application secrets**: easier to renew certificates, and you can scale up and replicate content and use standard certificate management tools.
* **Integration with other Azure services**: integrate Key Vault with other Azure resources.

### Describe the functionality and usage of Azure Sentinel

**Azure Sentinel** is a large scale dedicated security information and event management (SIEM) system. It aggregates security data from many different sources, and uses intelligent security analytics and threat analysis.

Azure Sentinel enables you to:

* **Collect cloud data at scale**: collect data across all users, devices, applications and infrastructure, both on-premises and cloud.
* **Detect previously undetected threats**: Minimize false positives by using Microsoft's comprehensive analytics and threat inetelligence.
* **Investigate threats with AI**: Examine suspicious activities at scale, tapping into years of cybersecurity models.
* **Respond to incidents rapidly**: Use built-in orchestration and automation of common tasks.

When Azure Sentinel detects suspicious events, an investigation graph provides specific alerts or incidents that a company review and act on. The company can use **Azure Monitor Workbooks** to automate responses to threats.

### Describe the functionality and usage of Azure Dedicated Hosts

**Azure Dedicated Host** provides dedicated physical servers to host your Azure VMs. Some organizations must follow regulatory compliance that requires them to be the only customer using the physical mchine that hosts their VMs.

A dedicated host is mapped to a physical server in an Azure datacenter. A host group is a collection of dedicated hosts.

The benefits of a dedicated host are:

* **Exclusivity**: gives you visibility and control over the server infrastructure running your Azure VMs.
* **Compliance**: ensures adherance to regulatory compliance by deploying your workloads on isolated servers.
* **Customization**: choose the number of processors, server capabilities, etc.
* **Maintenance control**: control when regular maintenance updates occur, within a 35-day rolling window.

## Describe Azure network security

### Describe the concept of defense in depth

A _defense in depth_ uses a series of mechanisms to slow the advance of an attack, that aims at acquiring unauthorized access to data. Each layer of protection relates to the network layer, so that if one layer is breached, a subsequent layer is already in place to prevent further exposure.

Here's a brief overview of the role of each layer.

* **Data layer**: controls access to databases, files, blobs etc.
* **Application layer**: apply updates to applications so that they are free from vulnerabilities, store secrets in vaults.
* **Compute layer**: secure access to virtual machines, updates OS, and protect endpoints on devices.
* **Network layer**: limit communications between resources through segmentation and subnets, deny by default.
* **Perimter layer**: protection against DDOS and firewall.
* **Identity and access layer**: controls access to infrastructure and change control, using multifactor authentication and single sign-on (SSO, and provides audit of events.
* **Physical layer**: protect physical servers using fingerprint, security cards etc.

### Describe the functionality and usage of Network Security Groups (NSG)

A _network security group (NSG)_ enables you to filter network traffic to and from an Azure resource within a virtual network. You can think of NSGs like an internal firewall.

An NSG can contain multiple ingress and egress security rules, where each rule can specify the name, priority, IP address, protocol, direction, port and action. When you create a NSG, Azure creates a series of default rules, which you cannot remove, to provide a baseline level of security.

### Describe the functionality and usage of Azure Firewall

**Azure Firewall** is a managed network security that monitors incoming and outgoing traffic and decides whether to allow or block it based on a defined set of security rules. You can limit access to your resources by specifying ranges of IP addresses.

Azure Firewall is a stateful firewall, where it analyzes the complete context of a network connection, not just an individual packet. It provides a central location to create, enforce, and log policies across subscriptions and virtual networks.

Azure Firewall provides many features, including:
* high availiblity 
* unrestricted scalability
* inbound and outbound security rules
* inbound Destination Network Address Translation (DNAT) support
* Azure Monitor logging

### Describe the functionality and usage of Azure DDoS protection

A _distributed denial of service (DDoS)_ attack attempts to overwhelm and exhaust an application's resources, making the application slow or unresponsive to legitimate users. DDoS attacks can target any resource that's publicly reachable through the internet.

**Azure DDoS Protection** protect your applications by analyzing and discarding DDoS traffic before it can affect your service's availability. It identifies the attacker's attempt and blocks further traffic from them, while allowing traffic from legitimate users from reaching your resources.

DDoS protection ensures that you need not incur unneeded expense, such as resources that automatically scale due to meeting the demand of the  requests caused by a DDoS attack. You can also receive credit for any costs accrued for scaled-out resources during a DDoS attack.

The DDoS protection can help prevent:

* **Volumetric attack**: the goal of this attack is to flood the network layer with a substantial amount of seemingly legitimate traffic.
* **Protocol attack**: the goal of this attack is to render the target inaccessible by exploiting a weakness in the layer 3 and 4 protocol stack.
* **Resource (application) layer attack**: the goal of this attack is to disrupt transmission of data in layer 7. You will need a web application firewall (WAF) and DDoS standard tier to protect against this.
