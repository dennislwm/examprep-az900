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

A _region_ is a geographical area on the planet that contains _at least one_ or more **datacenters** that are nearby and networked together with a _low-latency_ network. When you deploy a resource, you'll need to choose the region where you want your resource deployed.

These regions give you the flexibility to bring applications closer to your users no matter where they are. They provide better scalability, redundancy and also preserve data residency for your services.

#### Region Pairs

Each Azure region is always paired with another region within the same geography (such as US, Europe, or Asia) _at least 300 miles_ away. This approach allows for the replication of resources across a geography that helps reduce the likelihood of interruptions because of events such as natural disasters, power outages etc.

Advantages of region pairs:

* Provide reliable services and data redundancy, if an outage occurs, one region is prioritized to make sure at least one is restored as quickly as possible.
* Planned Azure updates are rolled out to one region at a time within a pair to minimize downtime and risk of outage.
* Data continues to reside within the same geography as its paired (except for Brazil South) for tax- and law-enforcement jurisdiction purposes.

### Describe the benefits and usage of Availability Zones

_Availability zones_ are physically separate datacenters within an Azure region. Each availability zone is made up of one or more datacenters equipped with _independent power, cooling, and networking_. 

An availability zone is set up to be an _isolation boundary_. Your services and data are made redundant so that if one zone goes down, the other continues working.

Availability zones are connected through high-speed, private fiber-optic networks. Not every region has support for availability zones.

### Describe the benefits and usage of Resource Groups

_Resource group_ is a logical container for resources deployed on Azure. All resources must be in a resource group, and a resource can only be a member of a single resource group.

Resources within a resource group can be from different Azure regions. Resource groups cannot be nested, however you can move resources between resource groups.

Resource groups can help manage and organize your Azure resources. If you delete a resource group, all resources contained within it are also deleted.

* Logical grouping: Placing resources of similar usage, type, or location in a resource group.
* Life cycle: Organizing resources by life cycle can be useful, where you might try an experiment and then dispose of it.
* Authorization: Applying RBAC permissions to a resource group, you can ease administration and limit access to allow only what's needed.

### Describe the benefits and usage of Subscriptions

A _subscription_ provides you with authenticated and authorized access to Azure products and services. Using Azure requires an Azure subscription.

An account can have one or more subscriptions that have different billing models and to which you apply different access-management policies. 

You can use Azure subscriptions to define boundaries around Azure products, services and resources. There are two types of subscription boundaries that you can use:

* **Billing boundary**: Determines how an Azure account is billed fo using Azure. You can create multiple subscriptions for different types of billing requirements,  such as production, development, testing etc.

* **Access control boundary**: Applies access-management policies at the subscription level. An example is that within an organization, you have different departments to which you apply distinct subscription policies, such as HR, IT etc.

Depending on your needs, you can set up multiple invoices within the same billing account. To do this, create additional billing proifles. Each billing profile has its own monthly invoice and payment method.

### Describe the benefits and usage of Management Groups

_Azure management groups_ provide a level of scope above subscriptions. You organize subscriptions into containers called management groups and apply your governance conditions to the management groups.

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

**Azure Resource Manager (ARM)** is the deployment and management service for Azure. It provides a management layer that enables you to create, update, and delete resources in your Azure account. You use management features like access control, locks, and tags to secure and organize your resources after deployment.

The benefits of using ARM:

* Manage your infrastructure through declarative templates rather than scripts. An ARM template is a JSON file that defines what you want to deploy to Azure.
* Deploy, manage, and monitor all the resources for your solution as a group, rather than handling these resources individually.
* Redeploy your solution throughout the development life cycle and have confidence your resources are deployed in a consistent state.
* Defined the dependencies between resources so they're deployed in the correct order.
* Apply access control to all services because RBAC is natively integrated into the management platform.
* Apply tags to resources to logically organize all the resources in your subscription.
* Clarify your organization's billing by viewing costs for a group of resources that share the saem tag.

### Explain Azure resources

_Resources_ are instances of services that you create, like VMs, storage, SQL databases etc.

## Describe core resources available in Azure

These services all share several common characteristics:

* **Durable** and highly available with redundancy and replication.
* **Secure** through automatic encryption and role-based access control.
* **Scalable** with virtually unlimited storage.
* **Managed**, handling maintenance and any critical problems for you.
* **Accessible** from anywhere in the world over HTTP or HTTPs.

### Describe the benefits and usage of Virtual Machines, Azure App Services, Azure Container Instances (ACI), Azure Kubernetes Service (AKS), and Windows Virtual Desktop

#### Virtual Machines

_Virtual machines (VMs)_ are software emulations of physical computers. They include a virtual processor, memory, storage, and networking resources.

VMs host an operating system, and you can install and run software just like a physical computer. When using a remote desktop client, you can use and control the VM as if you were sitting in front of it.

Azure VMs provides IaaS and can be used in different ways. VMs are an ideal choice when you need:

* Total control over the operating system (OS).
* The ability to run custom software.
* To use custom hosting configurations.

**VM scale sets** are an Azure compute resource that you can use to deploy and manage a set of identical VMs. With all VMs configured the same, virtual machine scale sets are designed to support true autoscale.

**Azure Batch** enables large-scale parallel and high-performance computing (HPC) batch jobs with the ability to scale to thousands of VMs. When you're ready to run a job, Azure Batch does the following:

* Starts a pool of compute VMs for you.
* Installs applications and staging data.
* Runs jobs with as many tasks as you have.
* Identifies failures.
* Requeues work.
* Scales down the pool as work completes.

#### Azure App Service

**Azure App Service** enables you to build and host web apps, mobile back-ends, and RESTful APIs in the programming language of your choice without managing infrastructure. It supports Windows and Linux and enables automated deployments from GitHub, Azure DevOps, or any Git repository to support a continuous deployment model.

This _PaaS_ environment allows you to focus on the website and API logic while Azure handles the infrastructure to run and scale your web applications.

* Deployment and management are intergrated into the platform.
* Endpoints can be secured.
* Sites can be scaled quickly to handle high traffic loads.
* The built-in load balancing and traffic manager provide high availability.

#### Azure Container Instance

VMs are limited to a single OS per machine. If you want to run multiple instances of an application on a single VM, containers are an excellent choice.

VMs appear to be an instance of an OS, but containers are instances of an application or envinronment. One of the most popular container engines is **Docker**, which is supported by Azure.

Containers are managed through a container orchestrator, which can start,stop, and scale out application instances as needed.

**Azure Container Instances** offers the simplest way to run a container in Azure without having to manage any VMs. It is a _PaaS_ offering that allows you to upload your containers, which it runs for you.

#### Azure Kubernetes Service (AKS)

**Azure Kubernetes Service** is a complete orchestration service for containers. Orchestration is the task of automating and managing a large number of containers and how they interact.

#### Windows Virtual Desktop

**Windows Virtual Desktop** on Azure is a desktop and application virtualization service that runs on the cloud. It enables your users to use a cloud-hosted version of Windows from any location.

Windows Virtual Desktop works across devices like Windows, Mac, iOS, Android, and Linux. It works with apps that you can use to access remote desktops and apps. You can also use most modern browsers to access Windows Virtual Desktop-hosted experiences.

You can provide individual ownership through personal (persistent) desktops. With Windows Virtual Desktop, the data and apps are separated from the local hardware. Windows Virtual Desktop runs them instead on a remote server. The risk of confidential data being left on a personal device is reduced.

Some key features of Windows Virtual Desktop:

* **Simplified management**: Use Azure Active Directory and role-based access controls (RBACs) to manage access to resources. As with other Azure services, Windows Virtual Desktop uses Azure Monitor for monitoring and alerts.
* **Performance management**: Gives you options to load balance users on your VM _host pools_. Host pools are collections of VMs with the same configuration assigned to multiple users. For the best performance, you can configure load balancing to occur as users sign in (breadth mode). With breadth mode, users are sequentially allocated across the host pool for your workload. To save costs, you can configure your VMs for depth mode load balancing where users are fully allocated on one VM before moving to the next. 
* **Multi-session Windows 10 deployment**: Windows Virtual Desktop lets you use Windows 10 Enterprise multi-session, the only Windows client-based operating system that enables multiple concurrent users on a single VM.

### Describe the benefits and usage of Virtual Networks, VPN Gateway, Virtual Network peering, and ExpressRoute

_Azure virtual networks_ enable Azure resources, such as VMs, web apps, and databases, to communicate with each other, with users on the internet, and with your on-premises client computers. You can think of an Azure network as a set of resources that links other Azure resources.

Azure virtual networks provide the following key networking capabilities:

* **Isolation and segmentation**: Define a private IP address space by using either public or private IP address ranges. You can divide that IP address space into subnets and allocate part of the defined address space to each named subnet.
* **Internet communications**: Enable incoming connections from the internet by defining a public IP address or a public load balancer.
* **Communicate beteween Azure resources**: Enable Azure resources to communicate securely with each other through virtual networks or service endpoints.
* **Communicate with on-premises resources**: Create a virtual network that spans both your local and cloud environments through _point-to-site virtual private networks (VPNs)_, _site-to-site_ VPNs, or **Azure ExpressRoute**.
* **Route network traffic**: Routes traffic between subnets on any connected virtual networks, on-premises networks, and the internet. You also can control routing and override those settings through _route tables_ and **Border Gateway Protocol (BGP)**.
* **Filter network traffic**: Filter traffic between subnets by using _network security groups_ and _network virtual appliances_.
* **Connect virtual networks**: Link virtual networks together by using virtual network _peering_. These virtual networks can be in separate regions, which allows you to create a global interconnected network through Azure.

#### VPN Gateway

VPNs use an encrypted tunnel within another network. They're typically deployed to connect two or more trusted private networks to one another over an untrusted network (typically the public internet). Traffic is encrypted while traveling over the untrusted network to prevent eavesdropping or other attacks.

_Azure VPN Gateway_ instances are deployed in Azure Virtual Network instances and enable the following connectivity:

* Connect on-premises datacenters to virtual networks through a _site-to-site_ connection.
* Connect individual devices to virtual networks through a _point-to-site_ connection.
* Connect virtual networks to other virtual networks through a _network-to-network_ connection.

You can deploy only one VPN gateway in each virtual network, but you can use one gateway to connect to multiple locations, which includes other virtual networks or on-premises datacenters.

A virtual network gateway is composed of two or more VMs that are deployed to a specific subnet you create, which is called the _gateway subnet_. You can't directly configure the VMs that are part of the virtual network gateway and you should never deploy additional resources to the gateway subnet.

When you deploy a VPN gateway, you specify the VPN type: either _policy-based_ or _route-based_. The main difference between these two types of VPNs is how traffic to be encrypted is specified.

_Policy-based VPN gateways_ specify statically the IP address of packets that should be encrypted through each tunnel. This type of device evaluates every data packet against those sets of IP addresses to choose the tunnel where that packet is going to be sent through.

If defining which IP addresses are behind each tunnel is too cumbersome, route-based gateways can be used. _Route-based VPNs_ are the preferred connection method for on-premises devices. They're more resilient to topology changes such as the creation of new subnets.

#### Virtual Network Peering

_Virtaul Network peering_ uses Azure VPN gateway instances deployed in Azure Virtual Network instances to connect virtual networks to other virtual networks through a _network-to-network_ connection.

#### ExpressRoute

**Azure ExpressRoute** lets you extend your on-premises networks into the Microsoft cloud over a private connection with the help of a connectivity provider. Connectivity can be from an _any-to-any (IP VPN)_ network, a _point-to-point_ Ethernet network, or a virtual _cross-connection_ through a connectivity provider at a colocation facility. 

ExpressRoute connections don't go over the public Internet. This allows ExpressRoute connections to offer more reliability, faster speeds, consistent latencies, and higher security than typical connections over the Internet. 

Features and benefits of ExpressRoute:

* **Layer 3 connectivity**: Layer 3 connectivity between your on-premises network and the Microsoft Cloud through a connectivity provider. Connectivity can be from an any-to-any (IPVPN) network, a point-to-point Ethernet connection, or through a virtual cross-connection via an Ethernet exchange.
* **Built-in redundancy**: Uses redundant devices to ensure that connections established with Microsoft are highly available.
* **Connectivity to Microsoft cloud services**: Enables direct access to Microsoft cloud services.
* **Across on-premises connectivity**: Enable **ExpressRoute Global Reach** to exchange data across your on-premises sites by connecting your ExpressRoute circuits.
* **Dynamic routing**: Border Gateway Protocol (BGP) routing protocol enables dynamic routing between your on-premises network and services running in the Microsoft cloud.

ExpressRoute supports three connectivity models:

* **CloudExchange colocation**: If your datacenter is colocated at a cloud exchange such as an ISP, you can request a virtual cross-connection to the Microsoft cloud.
* **Point-to-point Ethernet connection**: Connect your offices or datacenters to Azure by using the point-to-point links.
* **Any-to-any connection**: Integrates with your WAN connection to provide a connection like you would have between your datacenter and any branch offices.

### Describe the benefits and usage of Container (Blob) Storage, Disk Storage, File Storage, and storage tiers

#### Container (Blob) Storage

To begin using **Azure Storage**, you first create an Azure Storage account to store your data objects. Data that is copied to an Azure Storage account is maintained automatically in at least three copies.

**Azure Container Storage**, previously called _Blog Storage_, can store massive amounts of data, such as text or binary data. Blob Storage is unstructured, meaning that there are no restrictions on the kinds of data it can hold. 

Container Storage is ideal for:

* Serving images or documents directly to a browser.
* Storing files for distributed access.
* Streaming video and audio.
* Storing data for backup and restore, disaster recovery, and archiving.
* Storing data for analysis by an on-premises or Azure-hosted service.
* Storing up to 8TB of data for virtual machines.

#### Disk Storage

**Azure Disk Storage** provides disks for Azure virtual machines. Disk Storage allows data to be persistently stored and accessed from an attached virtual hard disk.

Disks come in many different sizes and performance levels, from solid-state drives (SSDs) to traditional spinning hard disk drives (HDDs), with varying performance tiers. 

#### File Storage

**Azure File Storage** is a fully managed file shares in the cloud that are accessible via Server Message Block (SMB) and Network File System (NFS) protocols. Applications running in Azure virtual machines or cloud services can mount a file storage share to access file data, just as a desktop application would mount a typical SMB share.

Azure Files ensures the data is encrypted at rest, and the SMB protocol ensures the data is encrypted in transit.

Any number of Azure virtual machines or roles can mount and access the file storage share simultaneously. Typical usage scenarios would be to share files anywhere in the world, diagnostic data, or application data sharing.

#### Storage tiers

Data stored in the cloud can be different based on how it's generated, processed, and accessed over its lifetime. To accommodate these different access needs, Azure provides several _access tiers_, which you can use to balance your storage costs with your access needs.

Container storage tiers:

* **Hot access tier**: for storing data that is accessed frequently, e.g. website.
* **Cool access tier**: for data that is infrequently accessed and stored for at least 30 days, e.g. invoices.
* **Archive access tier**: for data that is rarely accessed and stored for at least 180 days, with flexible latency requirements, e.g. backups.

### Describe the benefits and usage of Cosmos DB, Azure SQL Database, Azure Database for MySQL, Azure Database for PostgreSQL, and SQL Managed Instance

#### Cosmos DB

**Azure Cosmos DB** is a globally distributed, multi-model database service. You can elastically and independently scale throughput and storage across any number of Azure regions worldwide.

Cosmos DB provides comprehensive SLAs for throughput, latency, availability and consistency guarantees, and you can take advantage of its fast APIs.

Cosmos DB supports schema-less data, which lets you build highly responsive and "always on" applications to support constantly changing data. At the lowest level, it stores data in atom-record-sequence (ARS) format.

The data is abstracted and projected as an API, and your choices include SQL, MongoDB, Cassandra, Tables, and Gremlin. This level of flexibility means that your developers can stick with the API that they're most comfortable with.

#### Azure SQL Database

**Azure SQL Database** is a relational database (RDB) based on the Microsoft SQL Server database engine. It is a high-performance, reliable, fully managed, and secure database.

SQL Database is a PaaS database engine, therefore it handles upgrading, patching, backups, and monitoring without user involvement. Users can focus on domain-specific database administration and optimization activities that are critical for your business.

SQL Database enables you to process both relational data and non-relation structures, such as graphs, JSON, spatial and XML. You can used advanced features, such as intelligent query processing, as the newest capabilities of SQL Server are released first to SQL Database, then to SQL Server itself.

You can migrate your existing SQL Server databases with minimal downtime by using Azure Database Migration Service. The Microsoft Data Migration Assistant can generate assessment reports that provide recommendations to help guide you through required changes prior to performing a migration.

#### Azure Database for MySQL

**Azure Database for MySQL** is a relational database service that is based on MySQL Community Edition, versions 5.6, 5.7 and 8.0 with all the benefits of a fully managed PaaS. Users can focus on rapid application development and accelerating your time-to-market, rather than having to manage VMs and infrastructure.

Similar to SQL Database, you can migrate your existing SQL Server databases using Azure Database Migration Service, with assessment reports generated by Microsoft Data Migration Assistant to help guide you.

Database for MySQL offers several service tiers, and each tier provides different performance and capabilities to support lightweight to heavyweight database workloads. You can build your first app on a small database for a few dollars a month, and then adjust the scale to meet the needs of your solution.

#### Azure Database for PostgreSQL

**Azure Database for PostgreSQL** is a relational database service that is based on the open-source PostgreSQL database engine with all the benefits of a fully managed PaaS.

Azure Database for PostgreSQL is available in two deployment options: **Single Server** and **Hyperscale (Citus)**.

The **Single Server** deployment option offers three pricing tiers: Basic, General Purpose, and Memory Optimized. Each tier offers different resource capabilities to support your database workloads.

The **Hyperscale (Citus)** option horizontally scales queries across multiple machines by using sharding. Its query engine parallelizes incoming SQL queries across these servers for faster responses on large datasets. It serves applications that require greater scale and performance, generally workloads that are approaching, or already exceed, 100 GB of data.

The Hyperscale (Citus) deployment option supports multi-tenant applications, real-time operational analytics, and high throughput transactional workloads. Applications built for PostgreSQL can run distributed queries on Hyperscale (Citus) with standard connection libraries and minimal changes.

#### SQL Managed Instance

**Azure SQL Managed Instance** is a scalable cloud data service that provides the broadest SQL Server database engine compatiblity with all the benefits of a fully managed PaaS. Like Azure SQL Database, your company will not have to perform upgrading, patching, backup etc.

Azure SQL Database and Azure SQL Managed Instance offer many of the same features; however, SQL Managed Instance provides several options that might not be available to SQL Database. For example, SQL Managed Instance supports more characters for collation, such as Cyrillic.

Similar to SQL Database, you can migrate your existing SQL Server databases using Azure Database Migration Service, with assessment reports generated by Microsoft Data Migration Assistant to help guide you.

### Describe the benefits and usage of Azure Marketplace

**Azure Marketplac**e helps connect users with Microsoft partners, independent software vendors, and startups that are offering their solutions and services, which are optimized to run on Azure. Customers can find, try, purchase and provision Azure certified applications and services from hundreds of service providers.

The benefits of using Azure Marketplace is that you can provision end-to-end solutions quickly and reliably, hosted in your own Azure environment. At the time of writing, there are more than 8,000 listings.
