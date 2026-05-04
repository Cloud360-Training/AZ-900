# Microsoft Azure Compute & Networking Services - Complete Explanation

![Microsoft Azure Compute & Networking Services](https://private-us-east-1.manuscdn.com/sessionFile/PELdhIFr8k4l8jvbPIIMbc/sandbox/5rPxC2x5IeyHvQo9DHA8Xr-images_1777914988805_na1fn_L2hvbWUvdWJ1bnR1L21hcmtkb3duX3dpdGhfaW1hZ2VzL2ltYWdlcy9henVyZS1jb21wdXRlLW5ldHdvcmtpbmc.png?Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cHM6Ly9wcml2YXRlLXVzLWVhc3QtMS5tYW51c2Nkbi5jb20vc2Vzc2lvbkZpbGUvUEVMZGhJRnI4azRsOGp2YlBJSU1iYy9zYW5kYm94LzVyUHhDMng1SWV5SHZRbzlESEE4WHItaW1hZ2VzXzE3Nzc5MTQ5ODg4MDVfbmExZm5fTDJodmJXVXZkV0oxYm5SMUwyMWhjbXRrYjNkdVgzZHBkR2hmYVcxaFoyVnpMMmx0WVdkbGN5OWhlblZ5WlMxamIyMXdkWFJsTFc1bGRIZHZjbXRwYm1jLnBuZyIsIkNvbmRpdGlvbiI6eyJEYXRlTGVzc1RoYW4iOnsiQVdTOkVwb2NoVGltZSI6MTc5ODc2MTYwMH19fV19&Key-Pair-Id=K2HSFNDJXOU9YS&Signature=P8ZwbtLXjZMhFNbwi8JryzDf4ElK-oOfbYRPY98F9QixC6zdwkSliEuIQjJffWRcnYc0pvZA6rLXaUA1w1fdKgb9yZKSz8JhZ1XcnbOmzxwq0GoTI1uj9kmXw8VUexVtkOMR7-vtivPblhErOEsXj~GcW72D1iok9i2MJ~e87zZLYQtzXKXLuxEhCH49PBIMQnpdsyAWNJy31YFdV9uwCuKa5WOl8p3RYK1nj21zoAm92lTVUWko5ZgZAdz-eACJNd1-3UKeiE5lxuLhw0~DkV4qgGM5f7rcXbgva7JhXOuIyUszlQeW6-LuVS5EIBpH66rimCjWPsUWQen~XHLC0g__)

## Overview

This diagram illustrates how Azure's compute and networking services work together to deliver scalable compute, secure networking, and hybrid connectivity. It shows the complete flow from users accessing applications through Azure's global infrastructure to on-premises data centers.

---

## Traffic Flow Architecture

### Entry Points

#### **Internet**
The public internet serves as the entry point for users worldwide accessing Azure-hosted applications and services.

#### **Users**
End users accessing applications from various devices and locations globally.

#### **Web & App Traffic**
Application traffic including web requests, API calls, and data transfers flowing through Azure's infrastructure.

---

## Azure Front Door

### Purpose
Global entry point and application acceleration service.

### Key Features

**Global Performance**: Routes users to the best available endpoint based on geographic proximity and performance metrics.

**Traffic Distribution**: Automatically directs traffic to the nearest Azure region, reducing latency and improving user experience.

**High Availability**: Provides redundancy across multiple regions with automatic failover capabilities.

**DDoS Protection**: Built-in protection against distributed denial-of-service attacks at the edge.

### Use Cases

Organizations use Azure Front Door to accelerate web application delivery globally, ensuring users receive content from the nearest edge location. This is particularly valuable for content delivery networks, global web applications, and APIs serving worldwide audiences.

### Real-World Example

A global e-commerce platform uses Azure Front Door to route customers to the nearest regional data center, reducing page load times from 3 seconds to under 1 second and improving conversion rates by 15%.

---

## Application Gateway

### Purpose
Layer 7 (application layer) load balancing and web application firewall.

### Key Capabilities

**Web Application Firewall (WAF)**: Protects applications from common web exploits including SQL injection, cross-site scripting, and DDoS attacks.

**SSL/TLS Termination**: Handles encryption/decryption at the gateway, offloading CPU-intensive operations from backend servers.

**URL-Based Routing**: Routes requests to different backend pools based on URL paths, enabling microservices architectures.

**Host-Based Routing**: Routes traffic based on hostname, supporting multi-tenant scenarios.

**Session Affinity**: Maintains user sessions by routing requests from the same user to the same backend server.

### Architecture in Diagram

The Application Gateway sits between Azure Front Door and backend compute resources, providing application-level security and intelligent routing before traffic reaches the actual application servers.

### Use Cases

Application Gateway is ideal for protecting web applications from attacks, routing traffic to different backend services based on URL patterns, and terminating SSL connections to reduce server load.

### Real-World Example

A financial services company uses Application Gateway to protect their customer portal from web attacks, route mobile app traffic to optimized backend services, and terminate SSL connections, reducing server CPU usage by 30%.

---

## Load Balancer

### Purpose
Layer 4 (transport layer) load balancing for high availability and performance.

### Key Features

**Traffic Distribution**: Distributes incoming traffic across multiple backend instances in a round-robin or hash-based manner.

**Health Probes**: Continuously monitors backend instances and automatically removes unhealthy instances from the load-balancing pool.

**High Availability**: Provides 99.99% uptime SLA with redundancy across availability zones.

**Session Persistence**: Maintains connections from the same client to the same backend server when required.

### Difference from Application Gateway

While Application Gateway operates at Layer 7 (application layer) with awareness of HTTP/HTTPS, Load Balancer operates at Layer 4 (transport layer) with lower latency but without application-level intelligence.

### Use Cases

Load Balancer is used for distributing traffic across multiple VMs running the same service, ensuring high availability and scalability of backend services.

### Real-World Example

A video streaming service uses Load Balancer to distribute viewer traffic across 50 backend servers, automatically removing servers during maintenance and adding them back when ready, maintaining 99.99% availability.

---

## Compute Services

### Azure Virtual Machines

**Purpose**: Infrastructure as a Service (IaaS) compute resources providing complete control over the operating system and software.

**Characteristics**: Provision Windows or Linux virtual machines in seconds, choose from various sizes optimized for different workloads, and pay only for the resources you use.

**Use Cases**: Lift-and-shift migrations from on-premises data centers, running legacy applications, custom software requiring specific configurations.

**Scaling**: Virtual Machine Scale Sets automatically scale VM instances up or down based on demand or schedules.

### Virtual Machine Scale Sets

**Purpose**: Automatically manage and scale multiple identical VMs as a group.

**Capabilities**: Deploy 1 to 1,000+ identical VMs from a single configuration, automatically scale based on CPU, memory, or custom metrics, perform rolling updates with zero downtime.

**Benefits**: High availability, automatic scaling, simplified management of large VM fleets.

### App Service

**Purpose**: Fully managed platform for building and hosting web apps, mobile backends, and RESTful APIs.

**Features**: Built-in authentication and authorization, auto-scaling based on demand, continuous deployment from Git repositories, support for multiple languages and frameworks.

**Advantages**: No infrastructure management, automatic patching and updates, built-in security and compliance.

**Pricing**: App Service Plans provide shared or dedicated compute resources with predictable costs.

### Azure Kubernetes Service (AKS)

**Purpose**: Managed Kubernetes container orchestration platform for deploying and managing containerized applications at scale.

**Capabilities**: Automatic scaling of containers, self-healing of failed containers, rolling updates and rollbacks, integration with Azure DevOps for CI/CD.

**Use Cases**: Microservices architectures, cloud-native applications, containerized workloads requiring orchestration.

### Azure Functions

**Purpose**: Serverless compute service for event-driven workloads with automatic scaling and pay-per-execution pricing.

**Characteristics**: Write code without managing infrastructure, automatically scales from zero to thousands of executions, triggered by various events (HTTP, timers, messages, database changes).

**Use Cases**: Data processing, IoT event handling, scheduled tasks, real-time analytics.

### Azure Container Instances

**Purpose**: Run containers on-demand without managing servers or orchestration platforms.

**Features**: Deploy containers in seconds, pay only for execution time, support for both Linux and Windows containers.

**Use Cases**: Batch processing, quick testing, lightweight applications not requiring full Kubernetes.

---

## Networking Services

### Virtual Network (VNet)

**Purpose**: Isolated network environment in Azure for deploying and connecting resources.

**Components**: Custom IP address space (10.0.0.0/16), subnets for network segmentation (Web Subnet 10.0.1.0/24, App Subnet 10.0.2.0/24, Data Subnet 10.0.3.0/24).

**Security**: Network Security Groups (NSGs) filter traffic at the subnet and NIC level, allowing or denying traffic based on rules.

**Use Cases**: Multi-tier application architectures, network isolation between environments, hybrid connectivity scenarios.

### Subnets

The diagram shows three subnets within the VNet, each serving a specific purpose in the application architecture:

- **Web Subnet**: Hosts frontend web servers accessible from the internet
- **App Subnet**: Hosts application servers with restricted access
- **Data Subnet**: Hosts databases with the most restrictive access

This segmentation implements defense-in-depth security principles.

### Network Security Groups (NSGs)

**Purpose**: Stateful firewall for filtering traffic at the subnet and network interface level.

**Rules**: Allow or deny traffic based on source/destination IP, port, and protocol.

**Application**: Applied to subnets (affects all resources) or network interfaces (affects specific VMs).

**Benefits**: Granular traffic control, security policy enforcement, audit logging.

### Secure Network Isolation

Resources in the Web Subnet can communicate with the internet and App Subnet, App Subnet resources can communicate with Data Subnet, but Data Subnet resources cannot directly access the internet, implementing a secure multi-tier architecture.

### VPN Gateway

**Purpose**: Secure site-to-site VPN connectivity between Azure and on-premises networks or between Azure regions.

**Features**: Encrypted tunnels over public internet, multiple connection types (site-to-site, point-to-site, VNet-to-VNet), high availability with active-active mode.

**Use Cases**: Hybrid connectivity for secure on-premises access, extending corporate networks to Azure.

### Azure Firewall

**Purpose**: Centralized network security with threat intelligence.

**Capabilities**: Stateful firewall with threat intelligence-based filtering, application and network layer protection, centralized policy management.

**Benefits**: Advanced threat protection, centralized management, compliance with security standards.

### Azure DNS

**Purpose**: DNS hosting and name resolution for Azure resources and custom domains.

**Features**: Host DNS zones, alias records for Azure resources, private DNS zones for internal resolution, global distribution.

### Front Door

**Purpose**: Global HTTP/HTTPS load balancing and application acceleration.

**Features**: Routes users to the nearest endpoint, provides DDoS protection, enables global content delivery with low latency.

### ExpressRoute

**Purpose**: Private, dedicated network connections between on-premises networks and Azure.

**Characteristics**: Direct connection (not over public internet), consistent bandwidth and low latency, higher reliability and security than VPN.

**Connectivity Options**: Co-location, point-to-point, any-to-any (MPLS VPN).

**Use Cases**: Mission-critical workloads, hybrid scenarios requiring guaranteed performance.

---

## Connectivity Architecture

### Internet Path

Users on the internet connect through Azure Front Door for global acceleration, then Application Gateway for security and routing, then Load Balancer for traffic distribution to backend compute resources.

### On-Premises Path

On-premises users and data centers connect securely through ExpressRoute (dedicated private connection) or VPN Gateway (encrypted tunnel), bypassing the public internet for sensitive data and mission-critical workloads.

### Hybrid Connectivity

The diagram illustrates how Azure enables hybrid scenarios where on-premises infrastructure seamlessly connects to cloud resources, enabling gradual cloud migration and maintaining on-premises systems alongside cloud services.

---

## Security Principles

### Defense in Depth

Multiple security layers protect applications and data:
- Network layer: NSGs, firewalls, DDoS protection
- Application layer: Application Gateway WAF
- Transport layer: SSL/TLS encryption
- Data layer: Encryption at rest and in transit

### Zero Trust

Verify every access attempt regardless of source, implement least privilege access, continuously monitor for threats.

### Least Privilege

Resources have minimum necessary permissions, subnets are isolated, traffic between subnets is explicitly allowed.

---

## Scalability and High Availability

### Auto-Scaling

Virtual Machine Scale Sets automatically scale based on demand, Application Service scales based on CPU or custom metrics, Azure Functions scale automatically from zero to thousands.

### Redundancy

Multiple instances across availability zones ensure service continuity, automatic failover removes failed instances from load balancing pools, health probes continuously monitor instance health.

### Global Distribution

Azure Front Door routes traffic to nearest region, reducing latency and improving user experience worldwide.

---

## Real-World Architecture Example

A global SaaS application uses this architecture:

1. Users worldwide access the application through Azure Front Door for global acceleration
2. Application Gateway provides DDoS protection and routes traffic based on URL patterns
3. Load Balancer distributes traffic across multiple App Service instances
4. App Service instances in the Web Subnet handle HTTP requests
5. Backend services in the App Subnet process business logic
6. Data Subnet hosts SQL Database with restricted access
7. On-premises data center connects through ExpressRoute for secure data synchronization
8. Azure Monitor tracks performance and alerts on issues
9. Virtual Machine Scale Sets automatically scale based on demand

This architecture provides global performance, security, scalability, and hybrid connectivity.

---

## Certification Exam Tips (AZ-900, AZ-104, AZ-700)

- Understand the role of each networking service in the architecture
- Know when to use Load Balancer vs Application Gateway
- Understand VNet subnets and NSGs for network security
- Be familiar with VPN Gateway vs ExpressRoute differences
- Know Azure Front Door benefits for global applications
- Understand auto-scaling and high availability concepts
- Be aware of hybrid connectivity scenarios
- Know the shared responsibility model for network security

---

## Conclusion

Azure's compute and networking services work together to provide a secure, scalable, and globally distributed platform for modern applications. Understanding how these services integrate is essential for designing robust cloud architectures and preparing for Azure certifications.
