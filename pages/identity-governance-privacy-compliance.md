# Describe identity, governance, privacy, and compliance features

This section exam weighting has remained the same at 20-25%.

<!-- TOC depthfrom:2 depthto:3 -->

- [Describe core Azure identity services](#describe-core-azure-identity-services)
  - [Explain the difference between authentication and authorization](#explain-the-difference-between-authentication-and-authorization)
  - [Define Azure Active Directory](#define-azure-active-directory)
  - [Describe the functionality and usage of Azure Active Directory](#describe-the-functionality-and-usage-of-azure-active-directory)
  - [Describe the functionality and usage of Conditional Access, Multi-Factor Authentication MFA, and Single Sign-On SSO](#describe-the-functionality-and-usage-of-conditional-access-multi-factor-authentication-mfa-and-single-sign-on-sso)
- [Describe Azure governance features](#describe-azure-governance-features)
  - [Describe the functionality and usage of Role-Based Access Control RBAC](#describe-the-functionality-and-usage-of-role-based-access-control-rbac)
  - [Describe the functionality and usage of resource locks](#describe-the-functionality-and-usage-of-resource-locks)
  - [Describe the functionality and usage of tags](#describe-the-functionality-and-usage-of-tags)
  - [Describe the functionality and usage of Azure Policy](#describe-the-functionality-and-usage-of-azure-policy)
  - [Describe the functionality and usage of Azure Blueprints](#describe-the-functionality-and-usage-of-azure-blueprints)
  - [Describe the Cloud Adoption Framework for Azure](#describe-the-cloud-adoption-framework-for-azure)
- [Describe privacy and compliance resources](#describe-privacy-and-compliance-resources)
  - [Describe the Microsoft core tenets of Security, Privacy, and Compliance](#describe-the-microsoft-core-tenets-of-security-privacy-and-compliance)
  - [Describe the purpose of the Microsoft Privacy Statement, Product Terms site, and Data Protection Addendum DPA](#describe-the-purpose-of-the-microsoft-privacy-statement-product-terms-site-and-data-protection-addendum-dpa)
  - [Describe the purpose of the Trust Center](#describe-the-purpose-of-the-trust-center)
  - [Describe the purpose of the Azure compliance documentation](#describe-the-purpose-of-the-azure-compliance-documentation)
  - [Describe the purpose of Azure Sovereign Regions Azure Government cloud services and Azure China cloud services](#describe-the-purpose-of-azure-sovereign-regions-azure-government-cloud-services-and-azure-china-cloud-services)

<!-- /TOC -->

## Describe core Azure identity services

### Explain the difference between authentication and authorization

_Authentication_ and _authorization_ occur sequentially in the identity and access process. First, the identity of a person or service is established during _authentication_ involving the act of challenging a party for legitimate credentials, followed by _authorization_ which establishes what level of access the party has, i.e. what data they're allowed to access and what they can do with it.

### Define Azure Active Directory

**Azure Active Directory (Azure AD)** is Microsoft's cloud-based identity and access management service. It supports _single sign-on_ (SSO), _multi-factor authentication_ (MFA) etc.

Active Directory is related to Azure AD, but they have some key differences. For on-premises environments, Active Directory running on Windows Server provides an identity and access management service that's managed by your own organization.

With Azure AD, Microsoft ensures that the service is available globally, and can help protect you by detecting suspicious sign-in attempts at no extra cost.

### Describe the functionality and usage of Azure Active Directory

Azure AD provides services such as:

* **Authentication**: establish identity of a person or service and includes providing functionality such as self-service password reset, MFA etc.
* **Single sign-on**: enables a person to remember only one username and one password to access multiple applications.
* **Application management**: manage your own applications by using Azure AD, with features like _application proxy_, SSO etc.
* **Device management**: enables devices to be registered to Azure AD and managed through tools like **Microsoft Intune**.

### Describe the functionality and usage of Conditional Access, Multi-Factor Authentication (MFA), and Single Sign-On (SSO)

#### Single Sign-On (SSO)

_Single sign-on_ enables a user to sign in one time and use that credential to access multiple resources and applications. It reduces the strain on help desks, and effort needed to change or disable accounts.

However, under SSO, an attacker would need only a username and password to authenticate. To harden SSO authentication, MFA should be enabled.

#### Multi-Factor Authentication (MFA)

_Multifactor authentication_ is a process where a user is prompted during the sign-in process for an additional form of identification, such as a code on their phone, fingerprint, scan etc.

MFA increases identity security by limiting the impact of credential exposure (for example, stolen usernames and passwords). With MFA enabled, an attacker who has a user's password would also need to have possession of their phone or fingerprint to fully authenticate.

MFA requires one or more elements of identification that fall into three categories:

* **Something the user knows**: e.g. birth city, favorite color
* **Something the user has**: e.g. code sent to the user's mobile phone
* **Something the user is**: typically some sort of biometric property, such as fingerprint or face scan

Azure AD provides MFA authentication capabilities during sign-in via the Microsoft Authenticator app, phone call, or SMS code.

#### Conditional Access

_Conditional access_ is a tool that Azure AD uses to allow (or deny) access to resources based on identity _signals_. It also provides a more granular MFA experience for users. 

For example, a user may be challenged for a MFA if their sign-in signals are unusual or they're at an unexpected location. The signal might be the user's location, the user's device, or the application that the user is trying to access.

Conditional access is useful when you need to:

* **Require MFA to access an application**: configure whether all users or only certain users require MFA, such as administrators.
* **Require access to services only through approved applications**:  allow users to access services, such as Office 365, from a device as long as they use approved client apps.
* **Require users to access your application only from managed devices**: a managed device is a device that meets your standards for security and compliance.
* **Block accesss from untrusted sources**: for example, from unknown locations, etc.

Conditional access comes with a _What If_ tool, which helps you plan and troubleshoot your conditional access policies. You can use this tool to model your proposed policies across recent sign-in attempts from your users to see what the impact would have been if those policies had been enabled.

## Describe Azure governance features

Teams often start their Azure governance strategy at the subscription level. There are three main aspects to consider when you create and manage subscriptions: billing, access control, and subscription limits.

### Describe the functionality and usage of Role-Based Access Control (RBAC)

_Azure role-based access control (Azure RBAC)_ provides built-in roles that describe common access rules for cloud resources. You can also define your own roles, but typical roles are _observers_, _users_, _admins_, and _automated processes_.

RBAC is applied to a _scope_, which is a resource or set of resources. Scopes includ:

* a management group (a collection of multiple subscriptions)
* a single subcription
* a resource group
* a single resource

Azure RBAC is enforced on any action that's initiated against an Azure resource that passes through the ARM. Azure RBAC doesn't enforce access permissions at the application or data level, as these must be handled by your application.

RBAC uses an _allow model_, i.e. it allows you to perform certain actions such as read, write, or delete. You can have multiple roles assigned to you for a single resource, in which you inherit permissions from both roles.

You can apply Azure RBAC to an individual, group, and other special identity types, such as service principals and managed identities. These identity types are used by applications and services to automate access to Azure resources.

### Describe the functionality and usage of resource locks

A _resource lock_ prevents resources from being accidentally deleted or changed. It overwrites any permissions given by RBAC to a role.

You can apply locks to a subscription, a resource group, or a single resource. You can set the lock level to either:

* **CanNotDelete**: authorized persons cannot delete the resource without first removing the lock.
* **ReadOnly**: authorized persons can read a resource, but they cannot change or delete it, i.e. it is like applying the **Reader** role in Azure RBAC to all authorized people.

An authorized person can remove the lock first, before changing or deleting a resource. However, you can define an Azure Blueprint that specifies a certain resource lock must exist.

Azure Blueprint makes the resource lock more robust as it can replace the resource lock if that lock is removed accidentally.

### Describe the functionality and usage of tags

Resource _tags_ are another way to organize resources. Tags provide metadata about your resources and is useful for:

* **Resource management**: locate and act on resources that are associated with specific workloads, environments, business units and owners.
* **Cost management**: group resources so that you can report on costs, allocate internal cost centers, track budgets, and forecast estimated costs.
* **Operations management**: group resources according to how critical their availability is to your business.
* **Security**: classify data by its security level, such as public or confidential.
* **Governance and regulatory compliance**: identify resources that align with governance or regulatory compliance, such as ISO 27001.
* **Workload automation**: group resources so that you can use software such as Azure DevOps to perform automated tasks on those resources.

You can apply tags to a resource group, but those tags aren't automatically applied to the resources within that resource group. You can use **Azure Policy** to ensure that a resource inherits the same tags as its parent resource group.

### Describe the functionality and usage of Azure Policy

**Azure Policy** is a service that enables you to create, assign, and manage both individual policies and group of related policies, known as _initiatives_, that control or audit your resources. These policies enforce different rules and effects over your resource configurations so that those configurations stay compliant with corporate standards.

Azure Policy evaluates your resources and highlights resources that aren't compliant. It can also prevent non-compliant resources from being created.

Azure Policy comes with a number of built-in policy and initative definitions that you can use, under categories such as Storage, Networking, Compute etc. For example, you can define a policy that allows only a certain stock-keeping unit (SKU) size of VMs to be used.

Azure Policy also integrates with Azure DevOps by applying any CI/CD policies that apply to the pre-deployment and post-deployment phases of your application. In some cases, it can automatically remediate non-compliant resources.

Implementing a policy in Azure Policy involves these three steps:

1. Create a policy definition
2. Assign the definition to resources
3. Review the evaluation results.

#### 1. Create a policy definition

A policy definition expresses what to evaluate and what action to take. Every policy definition has conditions under which it's enforced, and an accompanying effect that takes place when the conditions are met.

#### 2. Assign the definition to resources

To implement your policy definitions, you assign definitions to resources. A _policy assignment_ is a policy definition that takes place within a specific scope, which could be a management group, a single subscription, a resource group etc.

Policy assignments are inherited by all child resources within that scope. You can exclude a subscope from the policy assignment if there are specific child resources you need to be exempt from the policy assignment.

#### 3. Review the evaluation results

Policy evaluation happens about once per hour, and that policy is evaluated over your resources within the hour. When a condition is evaluated against your existing resources, each resource is marked as compliant or non-compliant, after that you can review the non-compliant policy results and take any action that's needed.

### Describe the functionality and usage of Azure Blueprints

**Azure Blueprints** enables you to define a repeatable set of governance tools and standard Azure resources. In this way, you can rapidly deploy new environments with the knowledge that you're building within organizational compliance.

Azure Blueprints orchestrates the deployment of various resource templates and other artifacts, such as:

* Role assignments
* Policy assignments
* ARM templates
* Resource groups

Implementing a blueprint in Azure Blueprints involves these three steps:

1. Create an Azure blueprint
2. Assign the blueprint
3. Track the blueprint assignment

Azure Blueprint creates a record that associates a resource with the blueprint that defines it. Blueprints are also versioned, which enables you to track and comment on changes to your blueprint.

Each component in the blueprint definition is known as an _artifact_. Artifacts can contain zero or more parameters that you can configure, for example the built-in blueprint "Allowed locations" includes a parameter that specifies the allowed locations.

### Describe the Cloud Adoption Framework for Azure

The _Cloud Adoption Framework (CAF)_ consists of tools, documentation, and proven practices. It includes these stages:

1. Define your strategy.
2. Make a plan.
3. Ready your organization.
4. Adopt the cloud.
5. Govern and manage your cloud environments.

#### 1. Define your strategy

Answer why? Here are the steps in this stage:

1. **Define and document your motivations**: meet with stakeholders and leadership to help you answer why you're moving to the cloud.
2. **Document business outcomes**: meet with head of finance, marketing, sales, and HR to help you document your goals.
3. **Develop a business case**: validate that moving to the cloud gives you the right _return on investment (ROI)_ for your efforts.
4. **Choose the right first project**: choose a project that is achievable but also shows progress toward your cloud migration goals.

#### 2. Make a plan

Build a plan that maps your aspirational goals to specific actions. Here are the steps in this stage.

1. **Digital estate**: create an inventory of existing digital assets and workloads that you want to migrate to the cloud.
2. **Organizational alignment**: ensure that the right people are involved from both a technical standpoint as well as governance.
3. **Skills readiness**: build a plan to help individuals build their skills they need to operate in the cloud.
4. **Cloud adoption**: build a comprehensive plan that brings together teams from development, operations, and business toward a shared goal.

#### 3. Ready your organization

Create a _landing zone_, or an environment in the cloud to begin hosting your workloads. Here are the steps in this stage.

1. **Azure setup guide**: review the guid to become familiar with the tools and approaches.
2. **Azure landing zone**: build out the Azure subscriptions that support each of the major areas of your business, including governance, accounting, and security.
3. **Expand landing zone**: refined your landing zone to ensure that it meets your cloud infrastructure needs.
4. **Best practices**: use recommended or proven practices to help ensure that your efforts are scalable and maintainable.

#### 4. Adopt the cloud

Begin to migrate your applications to the cloud. This stage is broken into two parts: _migrate_ and _innovate_.

Here are the steps in the migrate part of this stage.

1. **Migrate your first workload**: use Azure migration guide to deploy your first project.
2. **Migration scenarios**: use additional in-depth guides to explore more complex scenarios.
3. **Best practices**: check Azure migration best practices list to verify that you're following recommended practices.
4. **Process improvements**: identify ways to make the migration process scale while requiring less effort.

Here are the steps in the innovate part of this stage.

1. **Business value consensus**: verify that investments in new innovations add value.
2. **Azure innovation guide**: use this guide to accelerate development and build a _minimum viable product (MVP)_ for your idea.
3. **Best practices**: verify that your progress maps to recommended practices.
4. **Feedback loops**: get customers feedback to verify product fit.

#### 5. Govern and manage your cloud environments

Form your cloud governance and management strategies. This stage is broken into two parts: _govern_ and _manage_.

Here are the steps in the govern part of this stage.

1. **Methodology**: define a methodology that incrementally takes you from your first steps all the way to a full cloud governance.
2. **Benchmark**: use the [Microsoft Cloud Adoption Framework Governance Benchmark Tool](https://cafbaseline.com) to access your current state and future state.
3. **Governance foundation**: create an MVP that captures the first steps of your governance plan.
4. **Improve the foundation**: iteratively add governance controls that address tangible risks as you progress toward your end state solution.

Here are the steps in the manage part of this stage.

1. **Management baseline**: define your minimum commitment to operations management, which is a minimum set of tools and processes that should be applied to every asset in an environment.
2. **Define business commitments**: document supported workloads to establish operational commitments with the business and agree on cloud management investments for each workload.
3. **Expand the baseline**: apply recommended best practices to iterate your initial management baseline.
4. **Advanced operations and design principles**: for workloads that require a higher level of business commitment, perform a deeper architecture review to deliver on your resiliency and reliability commitments.

## Describe privacy and compliance resources

Microsoft's online services build upon a common set of regulatory and compliance controls. These controls address today's regulation and adapt as regulations evolve. 

### Describe the Microsoft core tenets of Security, Privacy, and Compliance

### Describe the purpose of the Microsoft Privacy Statement, Product Terms site, and Data Protection Addendum (DPA)

#### Microsoft Privacy Statement

The **Microsoft Privacy Statement** explains what personal data Microsoft collects, how Microsoft uses it, and for what purposes.

#### Online Services Terms

The **Online Services Terms** is a legal agreement between Microsoft and the customer, which details the obligation by both parties with respect to the processing and security of customer data and personal data. The OST applies specifically to Microsoft's online services that you license through a subscription, including Azure, Office 365 etc.

#### Data Protection Addendum (DPA)

The **Data Protection Addendum (DPA)** defines the data processing and security terms for online services, which include:

* Compliance with laws
* Disclosure of processed data
* Data security, which includes security practices and policies, data encryption, data acess, customer responsibilities, and compliance with auditing.
* Data transfer, retention, and deletion.

### Describe the purpose of the Trust Center

The **Trust Center** showcases Microsoft's principles for maintaining data integrity in th cloud and how Microsoft implements and supports security, privacy, compliance and transparency in all of its cloud products and services. It is an important part of Microsoft Trusted Cloud Initiative and provides support and resources for the legal and compliance community.

### Describe the purpose of the Azure compliance documentation

The **Azure compliance documentation** provides you with detailed documentation about legal and regulatory standards and compliance across these categories:

* Global
* US goverment
* Financial services
* Health
* Media and manufacturing
* Regional

There are also additional compliance resources, such as audit reports, white papers etc, where the IT department find reference blueprints that it can apply directly to its Azure subscriptions. Some examples of complaince documentations are Multi-Tier Cloud Security Singapore, ISO 9001 etc

### Describe the purpose of Azure Sovereign Regions (Azure Government cloud services and Azure China cloud services)

Azure has specilized regions for compliance or legal purposes. A few examples include:

* **US DoD Central, US Gov Virginia, US Gov Iowa and more**: These regions are physical and logical network-isolated instances of Azure for U.S. government agencies and partners. These datacenters are operated by screened U.S. personnel and include additional compliance certifications.

* **China East, China North and more**: These regions are available through a unique partnership between Microsoft and 21Vianet, whereby Microsoft doesn't directly maintain the datacenters.

#### Azure Government

**Azure Government** is a separate instance of the Microsoft Azure service. Its services handle data that is subject to certain government regulations and requirements, such as FedRAMP, DIB, ITAR, IRS etc.

Azure Government uses physically isolated datacenters and networks located only in the US, and is available in 8 geographies.

#### Azure China 21Vianet

**Azure China 21Vianet** is operated by Shanghai Blue Cloud Technology Co., Ltd. ("21Vianet"), and is a physically separated instance of cloud services located in China. Its services are based on the same Azure, Office 365, and Power BI techologies that make up the Microsoft global cloud service, with comparable service levels.
