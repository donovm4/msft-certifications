# AZ-305: Designing MSFT Azure Infrastructure Solutions

## Cloud Adoption Framework (CAF)

Comprehensive guidance and tools to help organizations adopt Azure.

- informed decision-making
- design, build, manage
- secure and scale

Foundational Phases:
1. Strategy
  - define business goals
2. Plan
  - align adoption plans with measurable business goals
3. Ready
  - prepare landing zones, implementing
    - networking
    - security
    - governance controls
4. Adopt
  - migrate workloads
  - modernize existing workloads
  - build new cloud-native workloads/features

Operational:
1. Govern
  - manage risks and compliance
    - policy enforcement
    - access controls
    - compliance monitoring
2. Secure
  - protect the environment
3. Manage
  - operate and optimize
    - Azure Monitor
    - MSFT Defender for Cloud
    - Azure Cost Management

## Well-Architected Framework (WAF)

Comprehensive guidance and best practices to access and improve cloud workloads

Pillars:
1. Reliability
  - workloads function and recover with minimal downtime
    - Redundancy
    - Failover
    - Backups
2. Operational Excellence
  - monitoring
  - automation (DevOps)
3. Security
  - protect data from cyber threats
4. Cost Optimization
  - rate optimizations
  - usage optimizations
  - FinOps practices
5. Performance Efficiency
  - workloads enabled to scale as needed

## Governance / Management Hierarchy

1. Management Groups

  - Root Management Group
    - ...

  - Management Groups
    - ...

2. Subscriptions

    - Logical unit that links Azure account / tenant to Azure resources and services.

      - Enterprise Agreement (EA)
      - Microsoft Customer Agreement (MCA)
      - Pay-As-You-Go
      - Dev/Test
      - Student 

3. Resource Groups
    - ...

4. Resources

## Service Principal

- user
- group
- managed identity

## Roles

- MSFT Built-in roles
  - Entra roles
  - 
- Custom roles

Settings:
  - Eligible
    - User must be elevated to the role
  - Active
    - Role is always active (based on timeframe set)

## Role Assignments

1. Service principal
2. Role definition
3. Scope

## Activity Log

Tracks all management activities in Azure, creating an audit trail
- creation
- modification
- deletion

## Azure Monitor

Insights into workload's performance, availability, functionality

### Metrics & Logs

- collecting from:
  - resources
  - applications
  - guest OS
  - activity logs

### Alerts

  - notified for critical conditions
  - based on queries / conditions:
    - baseline
    - custom
    - leverage:
      - metrics
      - Activity Log
      - log queries
  - action groups
    

### Application Insights

  - performance anomalies
  - usage patterns
  - code-level diagnosis
  > distributed tracing system for applications
  > The `Instrumentation Key` is **required** for leveraging monitoring _into_ applications
  

### Log Analytics

  - write / run complex queries on data collected from various sources
    - VMs
    - app services
    - data collection APIs
  - leverages `KQL` as data organized as tables
  > `KQL` is _specifically designed_ for querying and analyzing log data collected

### Workbooks

  - interactive, flexible visualization and reporting

## Azure Data Explorer (ADX)

Fast fully-managed big-data analytics platform, optimized for querying and analyzing large-scale data

  - structured
  - semi-structured
  - multiple data sources and data formats
    - telemetry logs
    - JSON
    - CSV
  - leverages `KQL`

## Azure Event Hubs

Big-data data-streaming service capable of millions of events per second, with Apache Kafka compatibility.

## MSFT Entra ID

Centralized cloud-based identity and access management (IAM) service
- Identity Provider managing access of:
  - users
  - groups
  - devices 
  - applications
- AUTHn
- AUTHz
- auditing, security and compliance

## MSFT Entra External ID

- invite guest users into organization
- process:
  - invitation
  - redemption
- self-service sign-up
- user type is typically set to `guest`
-  principal name contains the `#EXT#` identifier

B2B Collaboration / External Identities
- The partner uses their own identity management system(s). Guest users can sign-in to your apps and services, with their own identities:
  - MSFT Entra accounts
    - work
    - school
  - MSA (personal accounts)
  - social
    - Facebook
    - Google
  - SAML / WS-Fed IdP federation protocols
    - protocols by which AUTHN data is transferred between two _parties_
  > - Security Assertion Markup Language (SAML)
  > - Web Services Federation (WS-Fed)

B2B Direct Connect (Teams _only_)
- collaborate across Teams environments

> B2B collaboration is enabled by default

## MSFT Entra Private Access

Provides access to corporate data and resources through user identities and permissions, secure and modern alternative to using a VPN to on-prem or hybrid environments.
- Identity-based access control
- adaptive security policies
  - roles
  - device health
  - real-time risk assessment
- seamless user experience
  - automatic routing to resources without VPN

Integrates with:
- MSFT Entra Internet Access
- MSFT Defender for Identity
- Conditional access policies

## MSFT Entra ID Governance

Provides IAM solutions for effective user management while keeping compliance in mind.
- user lifecycle management
- entitlement management
- access reviews
- guest user management
- self-service access requests
- AI / ML insights

> Available through MSFT Entra P1 / P2 licenses

## Role-based Access Control (RBAC)

Provides fine-grained access management to resources and applications in Azure.

## Multi-factor Authentication

Something you know.  
Something you are.  
Something you have.  

## Azure Landing Zones

Structured environments designed to deploy and manage Azure resources on the foundations of CAF principles.
- Platform: shared services such as identity, connectivity, and management
- Application: dedicated subscriptions for applications / workloads

## MSFT Purview

Unified platform that provides solutions for data governance, compliance, security, and management.

### MSFT Purview Data Loss Prevention (DLP)

Create DLP policies that can help you identify, monitor, and auto protect sensitive data from being shared, accidentally or unauthorized...
  - at rest
  - in transit
  - in use

Targets:
  - M365 services
  - Office applic, macOS
  - non-MSFT cloud apps
  - on-prem
  - Fabric, Power BI

### MSFT Purview Data Security Investigations

### MSFT Purview Data Security Posture Management

### MSFT Purview Information Barriers

### MSFT Purview Information Protection

### MSFT Purview Insider Risk Management

### MSFT Purview Privileged Access Management

### MSFT Purview Data Map

### MSFT Purview Unified Catalog

### MSFT Purview Audit

### MSFT Purview Communication Manager

### MSFT Purview Compliance Manager

### MSFT Purview Data Lifecycle Management

### MSFT Purview eDiscovery

## MSFT Priva

## Structured data vs Unstructured data

| --- | Structured data | Unstructured data |
| --- | --------------- | ----------------- |
| What? |  organized in predefined model | schema-less |
| Examples | <ul><li>key-value pairs</li></ul> | <ul> <li>documents</li> <li>images</li> <li>videos</li> </ul> |

## Data Encryption

Security methods that turn data unreadable. It can only be decrypted by an authorized key

Transparent Data Encryption (TDE)
- encrypts entire database
- only decrypted when authorized user requests access

Column-level Encryption
- encrypts specific columns of tables
- useful for encrypting sensitive data stored

Field-level Encryption
- encrypts individual fields
- application-level

End-to-End Encryption (e2e)
- data encryption n-transit

Leverage Azure Key Vault for storing encryption keys _securely_

## Azure Cosmos DB

Fully-managed, serverless NoSQL, relational, vector database, supporting unstructured _and_ semi-structured data **without** fixed schema
- high performance
- global distribution (lower latency)
- scalability

> 'NoSQL' = Not Only SQL; means that the database does not rely on traditional tabled-based relational model.

> Look into asynchronous / synchronous operations

## Azure SQL Database (PaaS)

Fully-managed, relational database built on MSFT-managed SQL Server, OS, hardware
- scalability
  - hyper-scale
  - serverless
- security
  - encryption
  - network isolation
  - threat detection
- performance
  - AI / ML performance tuning
- reliability

## Azure SQL Managed Instance (PaaS)

Fully-managed SQL database, where MSFT manages the OS and hardware

## SQL Server on Azure VMs (IaaS)

Leverage SQL Server in Azure without managing on-premises hardware

## Azure Storage

Managed, modern data storage solutions for a variety of scenarios, offering:
- high availability
- scalability
- security
- global accessibility (HTTP/S via REST API)

### Redundancy / Replication

- Locally-redundant Storage (LRS)

- Zone-redundant Storage (ZRS)

- Geo-redundant Storage (GRS)

- Geo-zone Redundant Storage (GZRS)

| Storage Service type | Redundancy supported |
| -------------------- | -------------------- |
| Blob                 | <ul><li>LRS</li><li>ZRS</li><li>(RA)-GRS</li><li>(RA)-GZRS</li></ul> |
| File                 | <ul><li>LRS</li><li>ZRS</li><li>GRS</li><li>GZRS</li></ul> |
| Queue                | <ul><li>LRS</li><li>ZRS</li><li>(RA)-GRS</li><li>(RA)-GZRS</li></ul> |
| Table                | <ul><li>LRS</li><li>ZRS</li><li>(RA)-GRS</li><li>(RA)-GZRS</li></ul> |
| Disk                 | <ul><li>LRS</li><li>ZRS</li></ul> |
| Elastic SAN          | <ul><li>LRS</li><li>ZRS</li></ul> |

| Storage Account type | Redundancy supported |
| -------------------- | -------------------- |
| GPv2                 | <ul><li>LRS</li><li>ZRS</li><li>(RA)-GRS</li><li>(RA)-GZRS</li></ul> |
| Premium Block        | <ul><li>LRS</li><li>ZRS</li></ul> |
| Premium Files        | <ul><li>LRS</li><li>ZRS</li></ul> |
| Premium Page         | <ul><li>LRS</li></ul> |
### Azure Blob / Data Lake Storage (ADLS)

Unstructured data storage at massive scale
- documents
- images
- videos
- other binary data

> Blob = Binary Large Objects

Scenarios:
- streaming
- random access
- big data analytics

### Azure Files

Fully-managed, mountable, cloud file shares
- SMB 
- NFS
- Rest API

### Azure Elastic SAN

Cloud-based SAN configurations, leveraging:
- deployment simplification
- scalability
- management capabilities
- high availability

Workloads:
- VMs
- AKS
- MariaDB
- SQL

> Accessible via internet Small Computer Systems Interface (iSCSI)

### Azure Queues

Asynchronous message queueing for application components

### Azure Tables

Leverage cloud-based, semi-structured NoSQL data
- key-value pairing
- schemaless design

### Azure Managed Disks

Persistently store data on virtual hard disks
- accessible
- attachable

### Azure Container Storage

Volume management, deployment and orchestration integrable with Kubernetes

### Azure NetApp Files (ANF)

Fully-managed, enterprise-grade NAS
- NFSv3, NFSv4.1
- SMBv3.x

Workloads:
  - POSIX
  - SAP HANA
  - HCP 

### Azure Managed Lustre

Fully-managed, high throughput, low latency Lustre file systems
  - simplified
  - lower setup costs
  - reduced maintenance

Workloads:
  - HPC 
  - AI workloads

### Azure Data Lake Storage (ADLS)

## Analytics

## Azure Synapse Analytics

## Azure Data Factory

Cloud-based serverless ETL (Extract, Transform, Load) data integration service
  - pipelines for scheduling jobs

## Azure Databricks

## Fault / Update domains

| FD-0 | FD-1 | FD-2 |
| ---- | ---- | ---- |
| VM-1<br/>UD-1  | VM-2<br/>UD-2 | VM-3<br/>UD-3 |
| VM-4<br/>UD-4 | VM-5<br/>UD-5 | VM-6<br/>UD-1 |

## Azure Front Door

Routes clients to fastest and most available app backend
  - L7 / Http / Https
  - Internet-facing application backend can be hosted inside / outside Azure

Features:
  - URL-based routing
  - Priority-based routing
  - multi-site hosting
  - Session affinity
  - SSL termination
  - leverage WAF

## Azure ExpressRoute



> ExpressRoute **does not** support encryption natively.

Customer / Provider will have to provide encryption solution themselves
  - typically a S2S VPN (IPSec encryption in-transit)  
  - private peering between on-prem <--> Azure VNet over ExpressRoute circuit
Prioritize IPSec-protected connections over ExpressRoute direct connections
  - provide larger amount of addresses for IPSec VPN BGP Session > direct ExpressRoute path
  - Advertise disjoint prefixes

## Azure Firewall

Cloud-native, scalable, reliable firewall security service
  - integrated threat intelligence
  - centralized network policy
  - detailed logging

Integrates with:
  - virtual networks
  - LAWs
  - Defender for Cloud

SKUs:
  - Basic
  - Standard (L3-L7 filtering)
  - Premium

# Azure Application Gateway

## Azure Traffic Manager

## Azure VPN Gateway