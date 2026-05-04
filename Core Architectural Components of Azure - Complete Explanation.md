# Core Architectural Components of Azure - Complete Explanation

![Core Architectural Components of Azure](./images/core-azure-components.png)

## Overview

Azure provides a comprehensive, secure, and scalable cloud platform for building, deploying, and managing applications and data. The diagram illustrates the 9 core architectural components that form the foundation of Microsoft Azure's infrastructure and services.

---

## 1. Identity and Access Management

### Purpose
Secure access to resources and centralized identity management.

### Key Components

#### **Microsoft Entra ID (formerly Azure AD)**
- **Function**: Cloud-based identity and access management service
- **Capabilities**: 
  - User authentication and authorization
  - Single sign-on (SSO) across cloud and on-premises applications
  - Multi-factor authentication (MFA)
  - Conditional access policies
- **Use Cases**: Enterprise identity management, hybrid identity scenarios
- **Benefits**: Centralized control, enhanced security, seamless user experience

#### **Role-Based Access Control (RBAC)**
- **Function**: Fine-grained permission management
- **How It Works**: 
  - Define roles with specific permissions
  - Assign roles to users, groups, or applications
  - Control access at subscription, resource group, or resource level
- **Examples**: Owner, Contributor, Reader, Custom roles
- **Best Practice**: Follow principle of least privilege

#### **Key Vault**
- **Function**: Secure storage for cryptographic keys, secrets, and certificates
- **Protections**:
  - Encryption at rest and in transit
  - Hardware security module (HSM) backed options
  - Access logging and monitoring
- **Use Cases**: 
  - Store database connection strings
  - Manage API keys and credentials
  - Rotate secrets automatically
- **Benefits**: Centralized secret management, compliance, audit trails

### Exam Focus (AZ-900)
- Understanding the difference between authentication and authorization
- RBAC principles and role assignment
- Key Vault use cases for secret management
- Microsoft Entra ID capabilities

### Real-World Example
A healthcare organization uses Microsoft Entra ID for employee authentication, RBAC to control access to patient data (doctors can read, administrators can modify), and Key Vault to store database credentials and encryption keys.

---

## 2. Management and Governance

### Purpose
Deploy, govern, monitor, and optimize your Azure environment.

### Key Components

#### **Azure Resource Manager (ARM)**
- **Function**: Centralized deployment and lifecycle management
- **Capabilities**:
  - Infrastructure as Code (IaC) using ARM templates
  - Consistent resource deployment across environments
  - Resource tagging and organization
  - Rollback capabilities
- **Benefits**: Automation, consistency, version control
- **Example**: Deploy entire application stack (VMs, databases, networks) with one template

#### **Azure Policy**
- **Function**: Define and enforce compliance rules
- **How It Works**:
  - Create policies to enforce standards
  - Audit existing resources
  - Deny non-compliant deployments
- **Use Cases**:
  - Enforce encryption on all storage accounts
  - Require specific resource tags
  - Restrict resource types by region
- **Benefits**: Compliance, cost control, security enforcement

#### **Azure Monitor**
- **Function**: Collect and analyze metrics, logs, and health data
- **Capabilities**:
  - Real-time performance monitoring
  - Application Insights for app-level monitoring
  - Log Analytics for centralized log collection
  - Alerts and automated responses
- **Metrics Tracked**: CPU, memory, disk I/O, network, custom metrics
- **Benefits**: Proactive issue detection, performance optimization

#### **Cost Management**
- **Function**: Analyze, monitor, and optimize cloud spending
- **Features**:
  - Cost analysis and budgets
  - Reserved Instances recommendations
  - Spot VM suggestions
  - Spending alerts
- **Benefits**: Cost optimization, budget control, ROI analysis

#### **Log Analytics**
- **Function**: Centralized log collection and querying
- **Capabilities**:
  - Collect logs from multiple sources
  - Query using Kusto Query Language (KQL)
  - Create custom dashboards
  - Integration with other Azure services
- **Use Cases**: Troubleshooting, security analysis, performance investigation

### Exam Focus (AZ-900)
- ARM templates for infrastructure deployment
- Azure Policy for compliance and governance
- Azure Monitor for observability
- Cost management tools and optimization strategies

### Real-World Example
A financial services company uses ARM templates to deploy consistent infrastructure, Azure Policy to enforce encryption and compliance requirements, Azure Monitor to track application performance, and Cost Management to optimize spending across departments.

---

## 3. Compute Services

### Purpose
Power your applications with scalable compute services.

### Key Components

#### **Virtual Machines (VMs)**
- **Function**: Scalable, on-demand computing resources
- **Supported OS**: Windows and Linux
- **Capabilities**:
  - Choose VM size based on workload
  - Scale up or down based on demand
  - Pay-as-you-go pricing
  - Support for custom images
- **Use Cases**: Lift-and-shift migrations, legacy applications, custom software
- **Sizes**: General purpose, compute optimized, memory optimized, GPU-enabled

#### **App Service**
- **Function**: Fully managed platform for web and mobile apps
- **Features**:
  - Built-in authentication and authorization
  - Auto-scaling capabilities
  - Continuous deployment from Git
  - Support for multiple languages (.NET, Java, Python, Node.js, PHP)
- **Benefits**: No infrastructure management, built-in security, easy deployment
- **Pricing**: App Service Plan based (shared or dedicated resources)

#### **Azure Kubernetes Service (AKS)**
- **Function**: Managed Kubernetes container orchestration
- **Capabilities**:
  - Automatic scaling of containers
  - Self-healing of failed containers
  - Rolling updates and rollbacks
  - Integration with Azure DevOps
- **Use Cases**: Microservices, containerized applications, cloud-native apps
- **Benefits**: Simplified Kubernetes management, high availability

#### **Azure Functions**
- **Function**: Serverless compute for event-driven workloads
- **Characteristics**:
  - Pay only for execution time
  - Automatic scaling
  - No server management
  - Triggered by various events (HTTP, timers, messages)
- **Use Cases**: Data processing, IoT, real-time analytics, scheduled tasks
- **Languages Supported**: C#, JavaScript, Python, Java, PowerShell

### Exam Focus (AZ-900)
- Differences between VMs, App Service, AKS, and Functions
- When to use each compute option
- Scalability and auto-scaling capabilities
- Serverless computing concepts

### Real-World Example
An e-commerce company uses VMs for legacy order processing, App Service for their web storefront, AKS for microservices-based recommendation engine, and Functions for processing real-time inventory updates.

---

## 4. Networking

### Purpose
Build secure, scalable, and high-performance network architectures.

### Key Components

#### **Virtual Network (VNet)**
- **Function**: Isolated network environment in Azure
- **Capabilities**:
  - Custom IP address space
  - Subnets for network segmentation
  - Network security groups (NSGs) for traffic filtering
  - Service endpoints for secure Azure service access
- **Use Cases**: Multi-tier applications, hybrid connectivity, network isolation
- **Benefits**: Security, control, network segmentation

#### **Load Balancer**
- **Function**: Distribute traffic across multiple resources
- **Types**:
  - **Layer 4 (Transport)**: TCP/UDP traffic distribution
  - **Layer 7 (Application)**: Application Gateway for HTTP/HTTPS
- **Capabilities**:
  - Health probes to detect failed instances
  - Session persistence
  - High availability
- **Use Cases**: Web applications, APIs, backend services

#### **Application Gateway**
- **Function**: Web traffic load balancing with advanced routing
- **Features**:
  - Web Application Firewall (WAF) protection
  - SSL/TLS termination
  - URL-based routing
  - Cookie-based session affinity
- **Benefits**: Application-level load balancing, security, advanced routing

#### **VPN Gateway**
- **Function**: Secure site-to-site VPN connectivity
- **Capabilities**:
  - Connect on-premises networks to Azure
  - Encrypted tunnels over public internet
  - Multiple connection types (site-to-site, point-to-site)
  - High availability with active-active mode
- **Use Cases**: Hybrid connectivity, secure remote access

#### **ExpressRoute**
- **Function**: Private, dedicated network connections
- **Characteristics**:
  - Direct connection to Azure (not over internet)
  - Consistent bandwidth and low latency
  - Higher reliability and security
  - Multiple connectivity options (co-location, point-to-point, any-to-any)
- **Benefits**: Performance, security, reliability for mission-critical workloads

#### **Azure DNS**
- **Function**: DNS hosting and name resolution
- **Capabilities**:
  - Host DNS zones
  - Alias records for Azure resources
  - Private DNS zones for internal resolution
  - Global distribution
- **Benefits**: High availability, integration with Azure resources

#### **Content Delivery Network (CDN)**
- **Function**: Global content delivery with edge locations
- **Features**:
  - Cache content at edge locations
  - Reduce latency for end users
  - Offload traffic from origin servers
  - DDoS protection
- **Use Cases**: Static content delivery, video streaming, software distribution

### Exam Focus (AZ-900)
- VNet concepts and subnets
- Load balancing options and use cases
- VPN Gateway vs ExpressRoute
- CDN benefits for global content delivery
- Network security with NSGs

### Real-World Example
A global media company uses VNets for network isolation, Load Balancers for traffic distribution, Application Gateway for DDoS protection, ExpressRoute for secure connectivity to headquarters, and CDN for fast video delivery worldwide.

---

## 5. Storage Services

### Purpose
Durable, highly available, and secure storage for all your data.

### Key Components

#### **Blob Storage**
- **Function**: Store large amounts of unstructured data
- **Use Cases**: 
  - Images, videos, documents
  - Backup and disaster recovery
  - Data lakes for analytics
  - Log files and archives
- **Access Tiers**: Hot (frequent access), Cool (infrequent access), Archive (long-term)
- **Benefits**: Massive scalability, cost-effective for large files

#### **Azure Files**
- **Function**: Fully managed file shares in the cloud
- **Protocols**: SMB and NFS
- **Use Cases**:
  - Shared file storage for applications
  - Lift-and-shift file server migrations
  - Configuration file storage
- **Benefits**: Easy migration, familiar file share interface

#### **Managed Disks**
- **Function**: High-performance block storage for VMs
- **Types**: Standard HDD, Standard SSD, Premium SSD, Ultra Disk
- **Use Cases**: VM operating systems, databases, high-performance applications
- **Benefits**: Durability, automatic replication, simplified management

#### **Archive Storage**
- **Function**: Long-term data storage at low cost
- **Characteristics**:
  - Lowest storage cost
  - Retrieval takes hours
  - Suitable for compliance and archival
- **Use Cases**: Compliance records, historical data, infrequent access

### Exam Focus (AZ-900)
- Storage account types and replication options
- Blob storage tiers and lifecycle management
- Managed Disks for VMs
- Storage redundancy (LRS, GRS, RA-GRS, ZRS)

### Real-World Example
A research institution uses Blob Storage for research datasets, Azure Files for shared lab notebooks, Managed Disks for research VM clusters, and Archive Storage for historical research data.

---

## 6. Databases

### Purpose
Managed and scalable database services for modern applications.

### Key Components

#### **Azure SQL Database**
- **Function**: Fully managed relational database
- **Features**:
  - Built-in high availability and disaster recovery
  - Automatic backups
  - Elastic scaling
  - Advanced threat protection
- **Use Cases**: Business applications, transactional systems, data warehouses
- **Benefits**: No infrastructure management, automatic patching, compliance

#### **Cosmos DB**
- **Function**: Globally distributed, multi-model database
- **Capabilities**:
  - Multiple data models (document, key-value, graph, time-series)
  - Global replication with low latency
  - Automatic scaling
  - 99.999% availability SLA
- **Use Cases**: IoT, real-time analytics, mobile apps, global applications
- **Benefits**: Global scale, multiple APIs, high availability

#### **PostgreSQL**
- **Function**: Open-source relational database
- **Features**:
  - Fully managed by Azure
  - Automatic backups and point-in-time restore
  - High availability with read replicas
  - Advanced security features
- **Use Cases**: Web applications, analytics, legacy PostgreSQL migrations
- **Benefits**: Open-source flexibility, managed service convenience

### Exam Focus (AZ-900)
- Differences between SQL Database, Cosmos DB, and PostgreSQL
- When to use relational vs NoSQL databases
- Database scaling and replication options
- Backup and disaster recovery capabilities

### Real-World Example
A SaaS company uses Azure SQL Database for customer account data, Cosmos DB for real-time user activity tracking across global regions, and PostgreSQL for analytics workloads.

---

## 7. Integration and Messaging

### Purpose
Connect services, applications, and data across distributed systems.

### Key Components

#### **Service Bus**
- **Function**: Reliable messaging and enterprise integration
- **Capabilities**:
  - Message queues for asynchronous communication
  - Topics and subscriptions for publish-subscribe patterns
  - Message ordering and deduplication
  - Dead-letter queues for failed messages
- **Use Cases**: Order processing, event notifications, system integration
- **Benefits**: Decoupled systems, reliability, scalability

#### **Event Grid**
- **Function**: Event routing for building event-driven architectures
- **Features**:
  - Route events from Azure services to event handlers
  - Serverless event processing
  - Automatic retry logic
  - Dead-letter support
- **Use Cases**: Real-time data processing, IoT event handling, workflow automation
- **Benefits**: Serverless, scalable, real-time event routing

#### **API Management**
- **Function**: Securely publish, manage, and monitor APIs
- **Capabilities**:
  - API versioning and lifecycle management
  - Developer portal for API discovery
  - Rate limiting and throttling
  - API analytics and monitoring
- **Use Cases**: Expose internal services as APIs, partner integrations, API monetization
- **Benefits**: Control, security, developer experience

### Exam Focus (AZ-900)
- Service Bus for reliable messaging
- Event Grid for event-driven architectures
- API Management for API governance
- Integration patterns and use cases

### Real-World Example
An insurance company uses Service Bus for claim processing workflows, Event Grid to trigger notifications when claims are submitted, and API Management to expose their services to partner companies.

---

## 8. Security

### Purpose
Protect your workloads, data, and infrastructure with built-in security services.

### Key Components

#### **Defender for Cloud**
- **Function**: Unified security management and threat protection
- **Capabilities**:
  - Security posture management
  - Threat detection and response
  - Compliance monitoring
  - Vulnerability scanning
- **Use Cases**: Security monitoring, threat detection, compliance management
- **Benefits**: Centralized security, threat intelligence, compliance

#### **Firewall**
- **Function**: Stateful firewall with threat intelligence
- **Features**:
  - Threat intelligence-based filtering
  - Network and application layer protection
  - Centralized policy management
  - Logging and monitoring
- **Use Cases**: Network perimeter security, DDoS protection
- **Benefits**: Advanced threat protection, centralized management

#### **DDoS Protection**
- **Function**: Mitigate DDoS attacks and ensure high availability
- **Tiers**:
  - Basic: Automatic protection
  - Standard: Enhanced protection with analytics
- **Use Cases**: Web applications, APIs, online services
- **Benefits**: Availability assurance, attack mitigation

#### **Sentinel**
- **Function**: Cloud-native SIEM and SOAR platform
- **Capabilities**:
  - Threat detection and investigation
  - Automated response playbooks
  - Integration with multiple data sources
  - Machine learning-based anomaly detection
- **Use Cases**: Security monitoring, incident response, threat hunting
- **Benefits**: Centralized security monitoring, automated response

### Exam Focus (AZ-900)
- Defense-in-depth security approach
- Defender for Cloud capabilities
- DDoS Protection tiers
- Sentinel for security monitoring
- Security best practices

### Real-World Example
A financial services company uses Defender for Cloud for continuous security monitoring, Azure Firewall for network protection, DDoS Protection for their public APIs, and Sentinel for threat detection and incident response.

---

## 9. Regions and Availability Zones

### Purpose
Ensure high availability and disaster recovery across geographic regions.

### Key Concepts

#### **Azure Regions**
- **Definition**: Geographic area containing one or more data centers
- **Characteristics**:
  - Independent power, cooling, and networking
  - Hundreds of miles apart for disaster recovery
  - Global distribution (60+ regions worldwide)
- **Examples**: East US, West Europe, Southeast Asia, Japan East
- **Benefits**: Compliance with data residency, reduced latency, disaster recovery

#### **Availability Zones**
- **Definition**: Physically separate data centers within a region
- **Characteristics**:
  - Independent infrastructure
  - High-speed, low-latency network connectivity
  - Synchronous replication
- **Count**: 3 zones per region (where available)
- **Use Cases**: High availability, zero-downtime deployments
- **Benefits**: 99.99% uptime SLA, fault isolation

#### **Region Pairs**
- **Definition**: Two regions paired for replication and failover
- **Characteristics**:
  - At least 300 miles apart
  - Automatic failover for some services
  - Sequential updates to minimize downtime
- **Benefits**: Disaster recovery, business continuity

### Deployment Strategies

**Zone-Redundant**: Replicate across availability zones within a region
- **Availability**: 99.99% uptime
- **Use Case**: High-availability applications

**Geo-Redundant**: Replicate across regions
- **Availability**: 99.99% uptime
- **Use Case**: Disaster recovery, business continuity

**Read-Access Geo-Redundant**: Geo-redundant with read access to secondary region
- **Availability**: 99.99% uptime
- **Use Case**: Read-heavy applications with disaster recovery

### Exam Focus (AZ-900)
- Azure region selection criteria
- Availability Zones for high availability
- Disaster recovery strategies
- Data residency and compliance considerations
- Region pairs and failover

### Real-World Example
A healthcare organization deploys their patient database in East US with zone-redundancy for high availability, and replicates to West US for disaster recovery compliance. They use read-access geo-redundant storage for analytics queries in the secondary region.

---

## Key Benefits Summary

| Benefit | Description |
|---------|-------------|
| **Built-In Security** | Multiple layers of security with encryption, firewalls, and threat protection |
| **Scalability** | Scale resources up or down to meet demand with global infrastructure |
| **High Availability** | 99.99%+ uptime with redundancy across zones and regions |
| **Global Reach** | 60+ regions worldwide for low latency and compliance |
| **Compliance** | Meet regulatory requirements with built-in compliance tools |
| **Cost Optimization** | Pay-as-you-go pricing with cost management tools |

---

## Azure Architecture Best Practices

1. **Defense in Depth**: Use multiple security layers (network, application, data)
2. **High Availability**: Use Availability Zones and region pairs
3. **Scalability**: Design for horizontal scaling with load balancers
4. **Monitoring**: Implement comprehensive monitoring with Azure Monitor
5. **Governance**: Use Azure Policy and RBAC for compliance
6. **Disaster Recovery**: Plan for failover with geo-redundancy
7. **Cost Management**: Monitor spending and optimize resource usage

---

## Certification Exam Tips (AZ-900)

- Understand the 9 core components and their purposes
- Know when to use each service (VMs vs App Service vs Functions)
- Understand high availability and disaster recovery concepts
- Be familiar with security best practices
- Know the difference between regions and availability zones
- Understand shared responsibility model
- Be aware of compliance and governance tools

---

## Conclusion

Azure's core architectural components provide a comprehensive platform for building secure, scalable, and reliable cloud solutions. Understanding these components and how they work together is essential for cloud architects, developers, and IT professionals preparing for Azure certifications or implementing cloud solutions.
