# Describe Cloud Concepts

This section exam weighting has increased to 20-25% from 15-20%.

<!-- TOC depthfrom:2 depthto:3 -->

- [Identify the benefits and considerations of using cloud services](#identify-the-benefits-and-considerations-of-using-cloud-services)
  - [Identify the benefits of cloud computing such as High Availability, Scalability, Elasticity, Agility, and Discover Recovery](#identify-the-benefits-of-cloud-computing-such-as-high-availability-scalability-elasticity-agility-and-discover-recovery)
  - [Identify the differences between Capital Expenditure CapEx and Operational Expenditure OpEx](#identify-the-differences-between-capital-expenditure-capex-and-operational-expenditure-opex)
  - [Describe the consumption-based model](#describe-the-consumption-based-model)
- [Describe the differences between categories of cloud services](#describe-the-differences-between-categories-of-cloud-services)
  - [Describe the shared responsibility model](#describe-the-shared-responsibility-model)
  - [Describe Infrastructure-as-a-Service IaaS](#describe-infrastructure-as-a-service-iaas)
  - [Describe Platform-as-a-Service PaaS](#describe-platform-as-a-service-paas)
  - [Describe serverless computing](#describe-serverless-computing)
  - [Describe Software-as-a-Service SaaS](#describe-software-as-a-service-saas)
  - [Identify a service type based on a use case](#identify-a-service-type-based-on-a-use-case)
- [Describe the differences between types of cloud computing](#describe-the-differences-between-types-of-cloud-computing)
  - [Define cloud computing](#define-cloud-computing)
  - [Describe Public cloud](#describe-public-cloud)
  - [Describe Private cloud](#describe-private-cloud)
  - [Describe Hybrid cloud](#describe-hybrid-cloud)
  - [Compare and contrast the three types of cloud computing](#compare-and-contrast-the-three-types-of-cloud-computing)

<!-- /TOC -->

## Identify the benefits and considerations of using cloud services

Cloud computing is the delivery of computing services over the internet by using a pay-as-you-go (PAYG) pricing model. You typically pay only for the cloud services you use, which helps you:

* Lower your operating costs
* Run your infrastructure more efficiently
* Scale as your business needs change

The cloud helps you move faster and innovate in our ever-changing digital world, where two trends emerge:

* Teams deliver new features to their users at record speeds
* Users expect an increasingly rich and immersive experience with their devices and with software

### Identify the benefits of cloud computing such as High Availability, Scalability, Elasticity, Agility, and Discover Recovery

There are several benefits that a cloud environment has over a physical environment. For example, cloud-based applications employ a myriad of related strategies.

* **High Availability (HA)**: Designed to be available 99.999% of the time, or as close to it as possible.

* **Fault Tolerance**: goes one step further than HA by guaranteeing zero downtime.

* **Reliablity**: Provide a continuous user experience with no apparent downtime even when things go wrong.

* **Scalability**: Scale applications in two ways, while taking advantage of autoscaling:
  * _Vertically_: Increase computing capacity by adding RAM or CPUs to a virtual machine.
  * _Horizontally_: Increase computing capacity by adding more virtual machines.

* **Elasticity**: Configure application to always have the resources they need, increasing or decreasing resources depending to meet the changing demands without worrying about capacity planning.

* **Agility**: Deploy and configure resources quickly as your application requirements change.

* **Geo-distribution**: Deploy applications and data to regional datacenters around the globe, so your customers always have the best performance in their region.

* **Disaster Recovery**: Deploy your applications with confidence that comes from knowing that your data is safe by taking advantage of backup services, data replication, and geo-distribution.

### Identify the differences between Capital Expenditure (CapEx) and Operational Expenditure (OpEx)

There are two different types of expenses that you should consider:

* **Capital Expenditure (CapEx)**: Upfront spending of money on physical infrastructure, and then deducting that upfront expense over time (depreciation), usually years.
* **Operational Expenditure (OpEx)**: Spending money on services and products and being billed for them now. There is no upgront cost, and you can deduct this expense in the same year you spend it.

To summarize, CapEx requires significant upfront financial costs, as well as ongoing maintenance and support expenditures. By contrast, OpEx is a consumption-based model, so an organization is only responsible for the cost of the computing resources that it uses.

### Describe the consumption-based model

A consumption-based model means that end users only pay for the resources that they use.

The benefits of pay-as-you-go (PAYG) include:

* No upfront costs.
* No need to purchase and manage costly infrastructure that user might not use to its fullest.
* Pay for additional resources when they are needed.
* Stop paying for resources that are no longer needed.

## Describe the differences between categories of cloud services

### Describe the shared responsibility model

Cloud computing falls into one of the following computing models. These models define the different level of shared responsibility that a cloud provider and cloud tenant are responsible for.

### Describe Infrastructure-as-a-Service (IaaS)

IaaS model is the closest to managing physical servers. A cloud provider keeps hardware up to date, but a cloud tenant maintains operating system and network configuration.

An advantage of this model is rapid deployment of new compute devices, e.g. Azure virtual machines. Setting up a new VM is considerably faster than procuring, installing and configuring a physical server.

### Describe Platform-as-a-Service (PaaS)

PaaS model is a managed hosting environment. A cloud provider manages the virtual machines and networking resources, while a cloud tenant deploys their applications into the managed hosting environment.

An advantage of this model is a cloud tenant does not have to deal with both physical hardware and software requirements. Examples of PaaS are Azure App Service and Azure SQL database.

### Describe serverless computing

Serverless computing is where a cloud provider automatically provisions, scales and manages the infrastructure required to run the code. Overlapping with PaaS, serverless architectures are highly scalable and event-driven as they use resources only when a specific function or trigger occurs.

It's important to note that servers are still running the code. The "serverless" name comes from the fact that tasks associated with infrastructure provisioning and management are invisible to a cloud tenant.

An advantage of this model is a cloud tenant can focus on the business logic and help teams increase their productivity and bring products to market faster. It allows organizations to better optimize resources and stay focused on innovation.

### Describe Software-as-a-Service (SaaS)

SaaS model is where a cloud provider manages all aspects of the application environment, including VMs, networking resources, data storage, and applications. A cloud tenant only needs to provide their data to the application managed by the cloud provider.

An advantage of this model is you need only to create your content as the SaaS will take care of everything else, e.g. Office 365.

### Identify a service type based on a use case

## Describe the differences between types of cloud computing

There are three deployment models for cloud computing: _public cloud_, _private cloud_, and _hybrid cloud_.

### Define cloud computing

Cloud computing is the deliver of computing services over the internet, which is otherwise known as the cloud. These services include servers, storage, databases, networking, analytics, and intelligence.

### Describe Public cloud

Services are offered over the public internet and available to anyone who wants to purchase them. Public cloud resources are hosted by a third-party service provider.

### Describe Private cloud

Computing resources are used exclusively by users from one business or organization. A private cloud can be physically located at your organization's on-site datacenter, or by a third-party service provider.

### Describe Hybrid cloud

Computing resources that are hosted by both a public cloud and a private cloud by allowing data and applications to be shared between them.

In this model, the public cloud effectively becomes an extension of the private cloud to form a single, uniform cloud.

### Compare and contrast the three types of cloud computing

The two characteristics of public cloud are metered pricing and self-service management.

The two characteristics of private cloud are dedicated hardware and inadequate SLA.

The characteristic of hybrid cloud is a high level of compatibility between the underlying software and services used by both the public and private clouds.
