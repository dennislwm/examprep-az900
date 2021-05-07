# Describe Core Azure Services

This section exam weighting has decreased to 15-20% from 30-35%.

<!-- TOC depthfrom:2 depthto:3 -->

- [Describe the core Azure architectural components](#describe-the-core-azure-architectural-components)
  - [Describe the benefits and usage of Regions and Region Pairs](#describe-the-benefits-and-usage-of-regions-and-region-pairs)
  - [Describe the benefits and usage of Availability Zones](#describe-the-benefits-and-usage-of-availability-zones)
  - [Describe the benefits and usage of Resource Groups](#describe-the-benefits-and-usage-of-resource-groups)
  - [Describe the benefits and usage of Subscriptions](#describe-the-benefits-and-usage-of-subscriptions)
  - [Describe the benefits and usage of Management Groups](#describe-the-benefits-and-usage-of-management-groups)
  - [Describe the benefits and usage of Azure Resource Manager](#describe-the-benefits-and-usage-of-azure-resource-manager)
  - [Explain Azure resources](#explain-azure-resources)
- [Describe core resources available in Azure](#describe-core-resources-available-in-azure)
  - [Describe the benefits and usage of Virtual Machines, Azure App Services, Azure Container Instances ACI, Azure Kubernetes Service AKS, and Windows Virtual Desktop](#describe-the-benefits-and-usage-of-virtual-machines-azure-app-services-azure-container-instances-aci-azure-kubernetes-service-aks-and-windows-virtual-desktop)
  - [Describe the benefits and usage of Virtual Networks, VPN Gateway, Virtual Network peering, and ExpressRoute](#describe-the-benefits-and-usage-of-virtual-networks-vpn-gateway-virtual-network-peering-and-expressroute)
  - [Describe the benefits and usage of Container Blob Storage, Disk Storage, File Storage, and storage tiers](#describe-the-benefits-and-usage-of-container-blob-storage-disk-storage-file-storage-and-storage-tiers)
  - [Describe the benefits and usage of Cosmos DB, Azure SQL Database, Azure Database for MySQL, Azure Database for PostgreSQL, and SQL Managed Instance](#describe-the-benefits-and-usage-of-cosmos-db-azure-sql-database-azure-database-for-mysql-azure-database-for-postgresql-and-sql-managed-instance)
  - [Describe the benefits and usage of Azure Marketplace](#describe-the-benefits-and-usage-of-azure-marketplace)

<!-- /TOC -->

## Describe the core Azure architectural components

Azure provides more than 100 services that enable you do everything from running your existing applications on Vms, to exploring new software paradigms, such as intelligent bots and mixed reality.

### Describe the benefits and usage of Regions and Region Pairs

#### Regions

A region is a geographical area on the planet that contains _at least one_ or more **datacenters** that are nearby and networked together with a _low-latency_ network. When you deploy a resource, you'll need to choose the region where you want your resource deployed.

These regions give you the flexibility to bring applications closer to your users no matter where they are. They provide better scalability, redundancy and also preserve data residency for your services.

#### Region Pairs

Each Azure region is always paired with another region within the same geography (such as US, Europe, or Asia) _at least 300 miles_ away. This approach allows for the replication of resources across a geography that helps reduce the likelihood of interruptions because of events such as natural disasters, power outages etc.

Advantages of region pairs:

* Provide reliable services and data redundancy, if an outage occurs, one region is prioritized to make sure at least one is restored as quickly as possible.
* Planned Azure updates are rolled out to one region at a time within a pair to minimize downtime and risk of outage.
* Data continues to reside within the same geography as its paired (except for Brazil South) for tax- and law-enforcement jurisdiction purposes.

### Describe the benefits and usage of Availability Zones

Availability zones are physically separate datacenters within an Azure region. Each availability zone is made up of one or more datacenters equipped with _independent power, cooling, and networking_. 

An availability zone is set up to be an _isolation boundary_. Your services and data are made redundant so that if one zone goes down, the other continues working.

Availability zones are connected through high-speed, private fiber-optic networks. Not every region has support for availability zones.

### Describe the benefits and usage of Resource Groups

Resource groups is a logical container for resources deployed on Azure. All resources must be in a resource group, and a resource can only be a member of a single resource group.

Resource groups cannot be nested, however you can move resources between resource groups.

Resource groups can help manage and organize your Azure resources. If you delete a resource group, all resources contained within it are also deleted.

* Logical grouping: Placing resources of similar usage, type, or location in a resource group.
* Life cycle: Organizing resources by life cycle can be useful, where you might try an experiment and then dispose of it.
* Authorization: Applying RBAC permissions to a resource group, you can ease administration and limit access to allow only what's needed.

### Describe the benefits and usage of Subscriptions

A subscription provides you with authenticated and authorized access to Azure products and services. Using Azure requires an Azure subscription.

An account can have one or more subscriptions that have different billing models and to which you apply different access-management policies. 

You can use Azure subscriptions to define boundaries around Azure products, services and resources. There are two types of subscription boundaries that you can use:

* **Billing boundary**: Determines how an Azure account is billed fo using Azure. You can create multiple subscriptions for different types of billing requirements,  such as production, development, testing etc.

* **Access control boundary**: Applies access-management policies at the subscription level. An example is that within an organization, you have different departments to which you apply distinct subscription policies, such as HR, IT etc.

Depending on your needs, you can set up multiple invoices within the same billing account. To do this, create additional billing proifles. Each billing profile has its own monthly invoice and payment method.

### Describe the benefits and usage of Management Groups

Azure management groups provide a level of scope above subscriptions. You organize subscriptions into containers called management groups and apply your governance conditions to the management groups.

All subscriptions within a management group automatically inherit the conditions applied to the management group. For example, you can apply policies to a management group that limits the region available for VM creation.

You can build a flexible structure of management groups and subscriptions to organize your resources into a hierarchy for unified policy and access management.

Another scenario is to provide user access to multiple subscriptions. By moving multiple subscriptions under a management group, you can create one role-based access control (RBAC) assignment on the management group, which will inherit that access to all the subscriptions.

#### Important facts about management groups

* 10,000 management groups can be supported in a single directory.
* A management group tree can support up to six level of depth. This limit doesn't include the root level or the subscription level.
* Each management group and subscription can support only one parent.
* Each management group can have many children.
* All subscriptions and management groups are within a single hierarchy in each directory.

### Describe the benefits and usage of Azure Resource Manager

Azure Resource Manager (ARM) is the deployment and management service for Azure. It provides a management layer that enables you to create, update, and delete resources in your Azure account. You use management features like access control, locks, and tags to secure and organize your resources after deployment.

The benefits of using ARM:

* Manage your infrastructure through declarative templates rather than scripts. An ARM template is a JSON file that defines what you want to deploy to Azure.
* Deploy, manage, and monitor all the resources for your solution as a group, rather than handling these resources individually.
* Redeploy your solution throughout the development life cycle and have confidence your resources are deployed in a consistent state.
* Defined the dependencies between resources so they're deployed in the correct order.
* Apply access control to all services because RBAC is natively integrated into the management platform.
* Apply tags to resources to logically organize all the resources in your subscription.
* Clarify your organization's billing by viewing costs for a group of resources that share the saem tag.

### Explain Azure resources

Resources are instances of services that you create, like VMs, storage, SQL databases etc.

## Describe core resources available in Azure

These services all share several common characteristics:

* **Durable** and highly available with redundancy and replication.
* **Secure** through automatic encryption and role-based access control.
* **Scalable** with virtually unlimited storage.
* **Managed**, handling maintenance and any critical problems for you.
* **Accessible** from anywhere in the world over HTTP or HTTPs.

### Describe the benefits and usage of Virtual Machines, Azure App Services, Azure Container Instances (ACI), Azure Kubernetes Service (AKS), and Windows Virtual Desktop

### Describe the benefits and usage of Virtual Networks, VPN Gateway, Virtual Network peering, and ExpressRoute

### Describe the benefits and usage of Container (Blob) Storage, Disk Storage, File Storage, and storage tiers

### Describe the benefits and usage of Cosmos DB, Azure SQL Database, Azure Database for MySQL, Azure Database for PostgreSQL, and SQL Managed Instance

#### Cosmos DB

Azure Cosmos DB is a globally distributed, multi-model database service. You can elastically and independently scale throughput and storage across any number of Azure regions worldwide.

Cosmos DB provides comprehensive SLAs for throughput, latency, availability and consistency guarantees, and you can take advantage of its fast APIs.

Cosmos DB supports schema-less data, which lets you build highly responsive and "always on" applications to support constantly changing data. At the lowest level, it stores data in atom-record-sequence (ARS) format.

The data is abstracted and projected as an API, and your choices include SQL, MongoDB, Cassandra, Tables, and Gremlin. This level of flexibility means that your developers can stick with the API that they're most comfortable with.

#### Azure SQL Database

Azure SQL Database is a relational database (RDB) based on the Microsoft SQL Server database engine. It is a high-performance, reliable, fully managed, and secure database.

SQL Database is a PaaS database engine, therefore it handles upgrading, patching, backups, and monitoring without user involvement. Users can focus on domain-specific database administration and optimization activities that are critical for your business.

SQL Database enables you to process both relational data and non-relation structures, such as graphs, JSON, spatial and XML. You can used advanced features, such as intelligent query processing, as the newest capabilities of SQL Server are released first to SQL Database, then to SQL Server itself.

You can migrate your existing SQL Server databases with minimal downtime by using Azure Database Migration Service. The Microsoft Data Migration Assistant can generate assessment reports that provide recommendations to help guide you through required changes prior to performing a migration.

#### Azure Database for MySQL

Azure Database for MySQL is a relational database service that is based on MySQL Community Edition, versions 5.6, 5.7 and 8.0 with all the benefits of a fully managed PaaS. Users can focus on rapid application development and accelerating your time-to-market, rather than having to manage VMs and infrastructure.

Similar to SQL Database, you can migrate your existing SQL Server databases using Azure Database Migration Service, with assessment reports generated by Microsoft Data Migration Assistant to help guide you.

Database for MySQL offers several service tiers, and each tier provides different performance and capabilities to support lightweight to heavyweight database workloads. You can build your first app on a small database for a few dollars a month, and then adjust the scale to meet the needs of your solution.

#### Azure Database for PostgreSQL

Azure Database for PostgreSQL is a relational database service that is based on the open-source PostgreSQL database engine with all the benefits of a fully managed PaaS.

Azure Database for PostgreSQL is available in two deployment options: **Single Server** and **Hyperscale (Citus)**.

The **Single Server** deployment option offers three pricing tiers: Basic, General Purpose, and Memory Optimized. Each tier offers different resource capabilities to support your database workloads.

The **Hyperscale (Citus)** option horizontally scales queries across multiple machines by using sharding. Its query engine parallelizes incoming SQL queries across these servers for faster responses on large datasets. It serves applications that require greater scale and performance, generally workloads that are approaching, or already exceed, 100 GB of data.

The Hyperscale (Citus) deployment option supports multi-tenant applications, real-time operational analytics, and high throughput transactional workloads. Applications built for PostgreSQL can run distributed queries on Hyperscale (Citus) with standard connection libraries and minimal changes.

#### SQL Managed Instance

Azure SQL Managed Instance is a scalable cloud data service that provides the broadest SQL Server database engine compatiblity with all the benefits of a fully managed PaaS. Like Azure SQL Database, your company will not have to perform upgrading, patching, backup etc.

Azure SQL Database and Azure SQL Managed Instance offer many of the same features; however, SQL Managed Instance provides several options that might not be available to SQL Database. For example, SQL Managed Instance supports more characters for collation, such as Cyrillic.

Similar to SQL Database, you can migrate your existing SQL Server databases using Azure Database Migration Service, with assessment reports generated by Microsoft Data Migration Assistant to help guide you.

### Describe the benefits and usage of Azure Marketplace

Azure Marketplace helps connect users with Microsoft partners, independent software vendors, and startups that are offering their solutions and services, which are optimized to run on Azure. Customers can find, try, purchase and provision Azure certified applications and services from hundreds of service providers.

The benefits of using Azure Marketplace is that you can provision end-to-end solutions quickly and reliably, hosted in your own Azure environment. At the time of writing, there are more than 8,000 listings.
