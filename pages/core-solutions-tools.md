# Describe core solutions and management tools on Azure

This section exam weighting has remained the same at 10-15%.

<!-- TOC depthfrom:2 depthto:3 -->

- [Describe core solutions available in Azure](#describe-core-solutions-available-in-azure)
  - [Describe the benefits and usage of Internet of Things IoT Hub, IoT Central, and Azure Sphere](#describe-the-benefits-and-usage-of-internet-of-things-iot-hub-iot-central-and-azure-sphere)
  - [Describe the benefits and usage of Azure Synapse Analytics, HDInsight, and Azure Databricks](#describe-the-benefits-and-usage-of-azure-synapse-analytics-hdinsight-and-azure-databricks)
  - [Describe the benefits and usage of Azure Machine Learning, Cognitive Services and Azure Bot Service](#describe-the-benefits-and-usage-of-azure-machine-learning-cognitive-services-and-azure-bot-service)
  - [Describe the benefits and usage of serverless computing solutions that include Azure Functions and Logic Apps](#describe-the-benefits-and-usage-of-serverless-computing-solutions-that-include-azure-functions-and-logic-apps)
  - [Describe the benefits and usage of Azure DevOps, GitHub, GitHub Actions, and Azure DevTest Labs](#describe-the-benefits-and-usage-of-azure-devops-github-github-actions-and-azure-devtest-labs)
- [Describe Azure management tools](#describe-azure-management-tools)
  - [Describe the functionality and usage of the Azure Portal, Azure PowerShell, Azure CLI, Cloud Shell, and Azure Mobile App](#describe-the-functionality-and-usage-of-the-azure-portal-azure-powershell-azure-cli-cloud-shell-and-azure-mobile-app)
  - [Describe the functionality and usage of Azure Advisor](#describe-the-functionality-and-usage-of-azure-advisor)
  - [Describe the functionality and usage of Azure Resource Manager ARM templates](#describe-the-functionality-and-usage-of-azure-resource-manager-arm-templates)
  - [Describe the functionality and usage of Azure Monitor](#describe-the-functionality-and-usage-of-azure-monitor)
  - [Describe the functionality and usage of Azure Service Health](#describe-the-functionality-and-usage-of-azure-service-health)

<!-- /TOC -->

## Describe core solutions available in Azure

### Describe the benefits and usage of Internet of Things (IoT) Hub, IoT Central, and Azure Sphere

IoT enables devices to gather and then relay information for data analysis. A few common sensors that measure attributes of the physical world include QR code, proximity sensors, light sensors etc.

IoT devices can send their sensor readings to a specific endpoint via a message. The message's data is then collected and aggregated, and it can be converted into reports and alerts

Alternatively, all devices could be updated with new firmware to fix issues or add new functionality by sending software updates from Azure IOT services to each device. Essentially, the IoT devices can both send messages to and receive messages from an IoT hub.

#### Azure IoT Hub

**Azure IoT Hub** is a managed service that acts as a central message hub for bi-directional secure communication between your IoT application and the devices it manages. 

It supports multiple messaging patterns, such as device-to-cloud telemetry, file upload from devices, and request-reply methods to control your devices from the cloud. After an IoT hub receives messages from a device, it can route that message to other Azure services.

IoT Hub allows for _command and control_, i.e. you can have either manual or automated remote control of connected devices, so you can instruct the device to perform an operation, such as set target temperature etc. IoT Hub _monitoring_ helps you maintain the health of your solution by tracking event such as device failures, connections etc.

#### Azure IoT Central

**Azure IoT Central** builds on top of IoT Hub by adding a visual dashboard that allows you to connect, monitor, and manage your IoT devices. To help you get up and running quickly, IoT Central provides starter templates for common scenarios across various industries, such as energy, healthcare etc.

You can customize the design starter templates directly in the UI by choosing from existing themes or creating your own custom theme, setting the logo etc. You can also tailor the starter templates for the specific data that's sent from your devices, the reports you want to see, and the alerts you want to send.

#### Azure Sphere

**Azure Sphere** creates an end-to-end, highly secure IoT solution for customers that encompasses everything from hardware and operating system on the device to the secure method of sending messages from the device to the message hub.

Azure Sphere comes in three parts:

* **Micro-controller unit (MCU)**: processing the operating system and signals from attached sensors.
* **Customized Linux OS**: handles communication with the security service and can run the vendor's software.
* **Azure Sphere Security Service (AS3)**: makes sure that the device has not been maliciously compromised.

### Describe the benefits and usage of Azure Synapse Analytics, HDInsight, and Azure Databricks

Microsoft Azure suppports a broad range of technologies and services to provide big data and analytic solutions, including Azure Synapse Analytics, HDInsight, and Databricks, and Data Lake Analytics.

#### Azure Synapse Analytics

Azure Synapse Analytics (formerly Azure SQL Data Warehouse) is a limitless analytics service that brings together enterprise data warehousing and big data analytics. You can query data on your terms by using either serverless or provisioned resources at scale. You have a unified experience to ingest, prepare, manage, and serve data for immediate BI and machine learning needs.

#### Azure HDInsight

Azure HDInsight is a fully managed, _open-source_ analytics service that makes it easier, faster, and more cost-effective to process massive amounts of data. You can run popular open-source frameworks and create cluster types such as Apache Spark, Apache Hadoop, Apache Kafka, Apache HBase, Apache Storm, and Machine Learning Services. HDInsight also supports a broad range of scenarios such as extraction, transformation, and loading (ETL), data warehousing, machine learning, and IoT.

#### Azure Databricks

Azure Databricks help you unlock insights from all your data and build _AI_ solutions. You can set up your Apache Spark environment in minutes, and then autoscale and collaborate on shared projects in an interactive workspace. Azure Databricks supports Python, Scala, R, Java, and SQL, as well as data science frameworks and libraries including TensorFlow, PyTorch, and scikit-learn.

#### Azure Data Lake Analytics

**Azure Data Lake Analytics** is an on-demand analytics job service that enables you to write queries to transform your data and extract valuable insights.  The analytics service can handle jobs of any scale instantly by setting the dial for how much power you need. You only pay for your job when it's running, making it more cost-effective. 

### Describe the benefits and usage of Azure Machine Learning, Cognitive Services and Azure Bot Service

##### Azure Machine Learning

**Azure Machine Learning (AML)** is a platform for making predictions. It consists of tools and services that allow you to connect to data to train and test models to find one that will most accurately predict a future result.

* Create a process that defines how to obtain data, handle missing or bad data, split the data into a training set or test set, and deliver the data to the training process.
* Train and evaluate predictive models by using tools and programming languages familiar to data scientists.
* Create pipelines that define where and when to run the compute-intensive experiments that are required to score the algorithms based on the training and test data.
* Deploy the best-performing algorithm as an API to an endpoint so that it can be consumed in real time by other applications.

##### Azure Cognitive Service

**Azure Cognitive Service (ACS)** provides prebuilt machine learning models that enable applications to see, hear, speak, understand and even begin to reason. Use ACS to solve general problems, such as analyzing text for emotional sentiment, and you don't need special machine learning knowledge to use these services.

While AML requires you to bring your own data and train models over that data, ACS provides pretrained models so that you can bring in your live data to get predictions on. ACS can be divided into the following categories:

* **Language**: Allow your apps to process natural language with prebuilt scripts, evaluate sentiment, and learn how to recognize what users want.
* **Speech**: Convert speech into text and text into speech. Translate from one language to another and enable speaker verification and recognition.
* **Vision**: Add recognition and identification capabilities when you're analyzing pictures, videos, and other visual content.
* **Decision**: Add personalized recommendations for each user that improve each time they're used, moderate content to monitor and remove offensive or risky content, and detect abnormalities in your time series data.

##### Azure Bot Service

**Azure Bot Service (ABS)** and **Bot Framework** are platforms for creating virtual agents that understand and reply to questions just like a human. ABS is different from AML and ACS in that it has a specific use case, namely it creates a virtual agent that can intelligently communicate with humans.

Behind the scenes, the bot uses other Azure services, such as ACS, to understand what their human counterparts are asking for. Bots can be used to shift simple, repetitive tasks, such as taking a dinner reservation, or gathering profile information, on to automated systems.

Users converse with a bot by using text, interactive cards, and speech. A bot interaction can be a quick question and answer, or it can be a sophisticated conversation that intelligently provides access to services.

### Describe the benefits and usage of serverless computing solutions that include Azure Functions and Logic Apps

_Serverless_ computing is the abstraction of servers, infrastructure, and operating systems. With serverless computing, Azure takes care of managing the server infrastructure and the allocation and deallocation of resources based on demand.

* **Abstraction of servers**:  Each function execution can run on a different compute instance that the platform manages for you. This execution context is transparent to the code.

* **Event-driven scale**: Each function respond to incoming events, or triggers, such as timer, HTTP, queue etc.

* **Micro-billing**: Each time your code runs, you pay for the usage. If no active function executions occur, you're not charged.

Azure has two implementations of serverless compute:

* **Azure Functions**: you write code to complete each step.
* **Azure Logic Apps**: you use a GUI to define the actions and how they relate to one another.

#### Azure Functions

**Azure Functions** are code that can execute in almost any programming language in the cloud in response to an event. An example of an event might be an HTTP request, a new message on a queue, or a message on a timer.

An Azure function is a stateless environment. A function behaves as if it's restarted every time it responds to an event. However if state is required, the function can be connected to an Azure storage account.

Azure Functions can perform orchestration tasks by using an extension called **Durable Functions**, which allow developer to chain functions together while maintaining state.

#### Azure Logic Apps

**Azure Logic Apps** are similar to functions, as both enable you to trigger logic based on an event. While functions execute code, Logic Apps execute _workflows_ that are designed to automate business scenarios and are built from predefined logic blocks. 

Azure Functions is a serverless compute service, while Azure Logic Apps is intended to be a serverless orchestration service. Although you can use Azure Functions to orchestrate a long-running business process this was not its primary use case when it was designed.

Logic Apps is a low-code/no-code development platform hosted as a cloud service. For example, **Zapier** is similar to Azure Logic Apps.

You create Logic App workflows using a visual designer on the Azure Portal or in Visual Studio. There workflows are persisted as a JSON file with a known workflow schema.

Azure provides more than 200 different connectors and processing blocks to interact with different services, such as Salesforce, Oracle, SAP etc. You can also build custom connectors and workflow steps if the service you need to interact with isn't covered. 

### Describe the benefits and usage of Azure DevOps, GitHub, GitHub Actions, and Azure DevTest Labs

#### Azure DevOps

Azure DevOps is a suite of services that address every stage of the software development lifecycle.

* **Azure Repos**: a centralized source-code repository like GitHub.
* **Azure Boards**: an agile project management suite that includes Kanban boards.
* **Azure Pipelines**: a CI/CD pipeline automation tool.
* **Azure Artifacts**: a repository for hosting artifacts, such as compiled source code, which can be fed into testing or deployment pipeline steps.
* **Azure Test Plans**: an automated test tool that can be used in a CI/CD pipeline.

Azure DevOps is a mature tool and has evolved into a SaaS offering from Microsoft.

#### GitHub and GitHub Actions

**GitHub** is a popular code repository for open-source software. Git is a decentralized source-code management tool, and GitHub is a hosted version of Git that serves as the primary remote.

GitHub offers the following functionality:

* a shared source-code repository/
* facilitates project management, including Kanban boards.
* supports issue reporting, discussion and tracking.
* features CI/CD pipeline automation tooling.
* includes a wiki for collaborative documentation.
* can be run from the cloud or on-premises.

**GitHub Actions** enalbles workflow automation with triggers for many lifecycle events. One such example would be automating a CI/CD _toolchain_.

A _toolchain_ is a combination of software tools that aid in the delivery, development, and management of software applications throughout a system's development lifecycle. The output of one tool in the toolchain is the input of the next tool in the toolchain.

Typical tool functions range from performing automated dependency updates to building and configuring the software, delivering the build artifcates to various locations, testing etc.

GitHub is a lighter-weight tool than Azure DevOps, with a focus on individual developers contributing to the open-source code. Azure DevOps, on the other hand, is more focused on enterprise development, with heavier project management and planning tools, and finer access control.

#### Azure DevTest Labs

**Azure DevTest Labs** provides an automated means of managing the process of building, setting up, and tearing down virtual machines that contain builds of your software projects. This way, developers and testers can perform tests across a variety of enviroments and builds.

This capability isn't limited to VMs, as you can deploy anything in Azure via an ARM template. Provisioning pre-created lab environments with their required configurations and tools already installed is a huge time saver for quality assurance professionals and developers.

## Describe Azure management tools

### Describe the functionality and usage of the Azure Portal, Azure PowerShell, Azure CLI, Cloud Shell, and Azure Mobile App

All capabilities that are available in the Azure portal are also available through Azure PowerShell, Azure CLI, REST APIs, and client SDKS.

#### Azure Portal

The Azure portal is a web-based, unified console that provides an alternative to command-line tools.

* Build, manage, and monitor everything.
* Create custom dashboards for an organized view of resources.
* Configure accessibility options for an optimal experience.

#### Azure PowerShell

**Azure PowerShell** is a shell that can execute commands called _cmdlets_. These commands call the Azure Rest API to perform every possible management task in Azure.

Capturing the commands in a script makes the process repeatable and automatable. Azure PowerShell is available for Windows, Linux, and Mac and you can access it in a web browser via **Azure Cloud Shell**.

#### Azure CLI

The Azure _command-line interface_ (CLI) is an executable program that can execute commands in Bash. The commands call the Azure Rest API to perform every possible management task in Azure.

In many respects, the Azure CLI is almost identical to Azure PowerShell in what you can do with it. The primary difference is the syntax you use, if you're already proficient in PowerShell or Bash, you can use the tool you prefer.

### Describe the functionality and usage of Azure Advisor

**Azure Advisor** evaluates your Azure resources and make recommendations to help you improve reliability, security, and performance, achieve operational excellence, and reduce costs.
Advisor is designed to help you save time on cloud optimization.

The recommendations are divided into five categories:

* **Reliability**: Ensure and improve the continuity of your business-critical applications.
* **Security**: Detect threats and vulnerabilities that might lead to security breaches.
* **Performance**: Improve the speed of your applications.
* **Cost**: Optimize and reduce overall Azure spending.
* **Operational Excellence**: Help you achieve process and workflow efficiency, resource manageability, and deployment best practices.

### Describe the functionality and usage of Azure Resource Manager (ARM) templates

**Azure Resource Manager (ARM)** templates describe resources you want to use in a declarative JSON format, similar to **Terraform**. The benefit is that the entire ARM template is verified before any code is executed to ensure that the resources will be created and connected correctly.

The template orchestrates the creation of those resources in parallel, that is all instances are created at the same time. Templates can even execute PowerShell and Bash scripts before or after the resource has been set up.

### Describe the functionality and usage of Azure Monitor

**Azure Monitor** is a platform for collecting, analyzing, visualizing and potentially taking action based on the metric and logging data from your entire Azure and on-premises environment.

You can view real-time and historical performance across each layer of your architecture, or aggregated and detailed information. You can view high-level reports on the **Azure Monitor Dashboard** or create custom views by using **Power BI** and **Kusto** queries.

Some products such as **Azure Application Insights (AAI)**, a service for sending telemetry information from application source code to Azure, uses Azure Monitor under the hood. With AAI, you can take advantage of the powerful data-analysis platform in Azure Monitor to gain deep insights into an application's operations and diagnose errors without having to wait for users to report them.

### Describe the functionality and usage of Azure Service Health

**Azure Service Health (ASH)** provides a status of the health of the Azure services, regions, and resources. The `status.azure.com` site displays only major issues that broadly affect Azure customers, but doesn't provide a full picture.

ASH helps you keep an eye on several event types:

* **Service issues**: problems in Azure, such as outages etc that may affect you.
* **Planned maintenance**: events that can affect the availability of Azure services that you rely on.
* **Health advisories**: announcements far in advance that require you to act on to avoid service interruption.
