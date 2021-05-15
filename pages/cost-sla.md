# Describe Azure cost management and Service Level Agreements

This section exam weighting has decreased to 10-15% from 20-25%.

<!-- TOC depthfrom:2 depthto:3 -->

- [Describe methods for planning and managing costs](#describe-methods-for-planning-and-managing-costs)
  - [Identify factors that can affect costs resource types, services, locations, ingress and egress traffic](#identify-factors-that-can-affect-costs-resource-types-services-locations-ingress-and-egress-traffic)
  - [Identify factors that can reduce costs reserved instances, reserved capacity, hybrid use benefit, spot pricing](#identify-factors-that-can-reduce-costs-reserved-instances-reserved-capacity-hybrid-use-benefit-spot-pricing)
  - [Describe the functionality and usage of the Pricing calculator and the Total Cost of Ownership TCO calculator](#describe-the-functionality-and-usage-of-the-pricing-calculator-and-the-total-cost-of-ownership-tco-calculator)
  - [Describe the functionality and usage of Azure Cost Management](#describe-the-functionality-and-usage-of-azure-cost-management)
- [Describe Azure Service Level Agreements SLAs and service lifecycles](#describe-azure-service-level-agreements-slas-and-service-lifecycles)
  - [Describe the purpose of an Azure Service Level Agreement SLA](#describe-the-purpose-of-an-azure-service-level-agreement-sla)
  - [Identify actions that can impact an SLA i.e. Availability Zones](#identify-actions-that-can-impact-an-sla-ie-availability-zones)
  - [Describe the service lifecycle in Azure Public Preview and General Availability](#describe-the-service-lifecycle-in-azure-public-preview-and-general-availability)

<!-- /TOC -->

## Describe methods for planning and managing costs

Azure offers both free and paid subscription options:

* **Free trial**: provides you with 12 months of popular free services, a credit to your balance for 30 days, and more than 25 services that are _always_ free.

* **Pay-as-you-go**: pay for what you use by attaching a credit/debit card to your account, and also you can apply for volume discounts and prepaid invoicing.

* **Member offers**: you existing membership to certain Microsoft products might provide you with Azure credits and reduced rates, e.g. Visual Studio subscribers, Microsoft for Startups members etc.

### Identify factors that can affect costs (resource types, services, locations, ingress and egress traffic)

#### Resource type

The _type_ of resource can influence the cost of Azure resources, e.g. with a storage account you can specify a type such as blob, disk, a performance tier such as standard or premium, and an access tier such as hot, cool or archive.

#### Usage meters

Azure creates and uses meters to generate a usage record for each resource that's later used to help calculate your bill. The following kinds of meters are relevant to tracking its usage:

* CPU time
* Public IP address time spent
* Incoming (ingress) and outgoing (egress) network traffic of a VM
* Disk size
* Amount of disk I/O operations

#### Resource usage

In Azure, you can delete or deallocate a VM. Deleting a VM means it is removed from your subscription.

Deallocating a VM means that while the VM is no longer assigned to a CPU or network, the associated disks are still kept in Azure. You're not billed for costs associated with compute time or IP address, but you're still billed for disk storage.

#### Location

Different Azure regions can have different associated prices. Also, each region can influence the network traffic cost as well.

### Identify factors that can reduce costs (reserved instances, reserved capacity, hybrid use benefit, spot pricing)

Azure Advisor identifies unused or underutilized resources and recommends an action for each of them. This information helps you to configure your resources to match your actual workload.

You can use _spending limits_ to prevent accidental overrun. A related concept is _quota_, or limits on the number of resources you can provision within your subscription.

**Azure Reservations** offers discounted prices on certain Azure services, which can save you up to 72 percent compared to PAYG prices. To receive a discount, you reserve resources by prepaying.

Azure Reservations are available to customers with an Enterprise agreement, Cloud solution providers, and PAYG subscribers.

Azure Hybrid Benefit allows you to repurpose software licenses on Azure, e.g. you might be able to repurpose your existing Windows Server licenses that are covered by Software Assurance.

### Describe the functionality and usage of the Pricing calculator and the Total Cost of Ownership (TCO) calculator

#### Total Cost of Ownership (TCO) Calculator

The **Total Cost of Ownership (TCO) Calculator** helps you estimate the cost savings of operating your solution on Azure over time, instead of in your on-premises datacenter.

With the TCO calculator, you enter the details of your on-premises workloads, then you review the suggested industry average cost, which you can adjust, for related operational costs. These costs include electricity, network maintenance, and IT labor.

You're then presented with a side-by-side report. Using the report, you can compare those costs with the same workloads running on Azure.

Working with the TCO calculator involves three steps:

1. Define your workloads - based on four categories: servers, databases, storage, and networking.
2. Adjust assumptions - specify whether you need greater redundancy, or whether you can save money if your are enrolled for **Software Assurance**.
3. View the report - choose a time frame between one and five years, you can view each category and also a side-by-side comparison, and you can download, share or save this report.

#### Pricing Calculator

The **Pricing Calculator** helps you to estimate the cost of your workload on Azure. It takes into account factors such as resource type, services, location, traffic, storage etc.

The options that you can configure in the Pricing calculator vary between products, but they can include:

* **Region**: a geographical location in which you can provision a service.
* **Tier**: Free tier or Basic tier have different levels of availability or performance and associated costs.
* **Billing options**: highlight the different ways you can pay for a service, and can include options to save costs.
* **Support options**: enable you to select additional support pricing options for certain services.
* **Programs and offers**: your subscription type might enable you to choose from specific licensing programs or other offers.
* **Azure Dev/Test pricing**: lists the available prices for development and test workloads.

### Describe the functionality and usage of Azure Cost Management

**Azure Cost Management** + Billing is a free service that helps you understand your Azure bill, manage your account and subscriptions, monitor and control Azure spending, and optimize resource use. Its features include:

* Reporting - generate reports using historical data and forecast future usage and expenditure
* Data enrichment - improve accountability by categorizing resources with tags
* Budgets - create and manage cost and usage budgets by monitoring resource demand trends, consumption rates, and cost patterns.
* Alerting - get alerts based on your cost and usage budgets.
* Recommendations - receive recommendations to eliminate idle resources and to optimize them.

## Describe Azure Service Level Agreements (SLAs) and service lifecycles

### Describe the purpose of an Azure Service Level Agreement (SLA)

A _service-level agreement_ (SLA) is a formal agreement between a service company, such as Azure, and its customers. Understanding the SLA for each Azure service helps you to understand what guarantees you can expect from them.

A typical SLA breaks down into these sections:

* **Introduction**: explains what to expect in the SLA, including its scope and how subscription renewals can affect the terms.
* **General terms**: contains terms that are used throughout the SLA so that both parties have a consistent vocabulary.
* **SLA details**: defines the specific guarantees for the service, such as performance commitments typically range from 99.9 to 99.99 percent, eg. Azure Database for MySQL guarantees 99.99 percent uptime, which is equivalent to a maximum _downtime_ of 52.56 minutes per year.

An SLA describes how Microsoft responds when an Azure service fails to perform its specification. For example, you might receive a _service credit_, which is the percentage of fees you paid that are credited back to you, as compensation when a service fails to perform.

Free products typically don't have an SLA, eg. Azure Advisor.

### Identify actions that can impact an SLA (i.e. Availability Zones)

An _application_ SLA defines the SLA requirements for a specific application. This term typically refers to an application that you build on Azure, eg. you decide that an SLA of 99.9 percent is acceptable for your application.

The type of services or resources may impact an SLA, eg. a VM has an SLA of 99.9 percent SLA, while an SQL Database has an SLA of 99.99 percent. The process of combining SLAs help you to compute the _composite_ SLA for a set of services.

Computing the composite SLA requires that you multiply the SLA of individual service. For example, using our VM and SQL Database, we have a composite SLA of 0.99 x 0.999 = 0.98901 (or 98.901 percent).

What happens when the composite SLA doesn't meet your needs? To improve the availability of the application, avoid having any single point of failure, in other words, instead of adding more VMs, you can deploy an extra VM across different availability zones in the same Azure region.

Deploying two VMs across two availability zones raises the VM SLA to 99.99 percent. Hence recalculating your composite SLA gives you an application SLA of 0.999 x 0.999 = 0.9998 (or 99.98 percent).

The revised SLA of 99.98 percent exceeds your target SLA of 99.9 percent.

### Describe the service lifecycle in Azure (Public Preview and General Availability)

The _service lifecycle_ defines how every Azure service is released for public use. 

The service lifecycle has several phases:

* **Development phase**: Azure team collects and defines its requirements, and build the service.
* **Public preview phase**: the public can access and experiment with the service so that it can provide feedback.
* **General availability (GA)**: after the service is validated and tested, it is released to all customers as production ready.

Each Azure preview defines its own terms and conditions. All preview-specific terms and conditions supplement your existing Azure service agreement.

Although you can use an Azure preview feature in production, some previews aren't covered by customer support, so make sure you're aware of any limitations around its use before you deploy it to production.
