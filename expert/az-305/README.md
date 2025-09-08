# AZ-305: Designing MSFT Azure Infrastructure Solutions

## Cloud Adoption Framework (CAF)

Comprehensive guidance and tools to help organizations adopt Azure.

  - informed decision-making
  - design, build, manage
  - secure and scale

Foundational Phases...
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

Operational...
1. Govern
    - build a team
    - access risks
    - document policies
    - enforce policies
    - monitor compliance
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

Pillars...
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

Settings...
  - Eligible
    - User must be elevated to the role
  - Active
    - Role is always active (based on timeframe set)

## Role Assignments

1. Service principal
2. Role definition
3. Scope

## Regions

Geographical area that contains 1-n datacenters

## Availability Zones

Separate datacenters within regions.

Categories...
  - Zonal: resource / service is pinned to a specific zone
  - Zone-redundant: resource / service is replicated across 3 zones within region

![availability zones](https://github.com/donovm4/msft-certifications/blob/main/expert/az-305/images/availability-zones.png)

## Paired Regions

![paired regions](https://github.com/donovm4/msft-certifications/blob/main/expert/az-305/images/region-pairs.png)

## Availability Sets

Protect resources across fault domains _inside_ of a **single** datacenter

## Activity Log

Tracks all management activities in Azure, creating an audit trail
- creation
- modification
- deletion

## Azure Monitor

Insights into workload's performance, availability, functionality

### Metrics & Logs

- collecting from...
  - resources
  - applications
  - guest OS
  - activity logs

### Alerts

  - notified for critical conditions
  - based on queries / conditions...
    - baseline
    - custom
    - leverage...
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
- Identity Provider managing access of...
  - users
  - groups
  - devices 
  - applications
- AUTHn
- AUTHz
- auditing, security and compliance

## MSFT Entra External ID

- invite guest users into organization
- process...
  - invitation
  - redemption
- self-service sign-up
- user type is typically set to `guest`
-  principal name contains the `#EXT#` identifier

B2B Collaboration / External Identities
- The partner uses their own identity management system(s). Guest users can sign-in to your apps and services, with their own identities...
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

Integrates with...
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

Targets...
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

## Designing for Data

### Types of Data

| Structured data | Semi-structured | Unstructured data | 
| --- | --------------- | ----------------- |
|  organized in predefined model | tags clarify how data is organized | schema-less |
| <ul><li>key-value pairs</li><li>Relational databases (SQL)</li></ul> | <ul><li>Cosmos DB / NoSQL</li><li>HTML</li><li>JSON</li><li>XML</li></ul>| <ul><li>documents (.docx, .pptx)</li><li>images</li><li>videos</li><li>Text files (.txt, .pdf, .rtf)</li></ul> |

## Database Encryption

Security methods that turn data unreadable. It can only be decrypted by an authorized key

Transparent Data Encryption (TDE)
  - encrypts entire database
  - data at rest
  - only decrypted when authorized user requests access

Column-level Encryption
  - encrypts specific columns of tables
  - useful for encrypting sensitive data stored

Field-level Encryption
  - encrypts individual fields
  - application-level

End-to-End Encryption (e2e)
  - data encryption n-transit

Secure Socket Layer (SSL) / Transport Layer Security (TLS)
  - data in-motion
  - always encrypted for all encryption

Dynamic Data Masking
  - policy-based security feature
  - hide sensitive data in result of query

Leverage Azure Key Vault for storing encryption keys _securely_

## Azure Cosmos DB

Fully-managed, serverless NoSQL, relational, vector database, supporting unstructured _and_ semi-structured data **without** fixed schema
  - high performance (single-digit millisecond)
  - global distribution (lower latency)
  - scalability

API supported:
  - NoSQL
  - PostgreSQL
  - MariaDB
  - Cassandra
  - MongoDB
  - Table

> 'NoSQL' = Not Only SQL; means that the database does not rely on traditional tabled-based relational model.

> Look into asynchronous / synchronous operations

## Azure SQL Database (PaaS)

> Microsoft recommended

Fully-managed, relational database built on MSFT-managed SQL Server, OS, hardware where networking, disaster recovery, and highest availability are automatically configured
  - scalability
    - hyper-scale (vCore only)
    - serverless (auto-scaling)
  - large
    - up to 100TB
  - security
    - encryption
    - network isolation
    - threat detection
  - performance
    - AI / ML performance tuning
  - reliability

Best for modern applications needing to leverage serverless or Hyper-scale

Storage sizes...
  - General Purpose
    - 1 `GB` - 4 `TB`
  - Business Critical
    - 1 `GB` - 4 `TB`
  - Hyper-scale
    - 10 `GB` - 128 `TB`

  > [!IMPORTANT]
  > [Service tiers](https://learn.microsoft.com/en-us/azure/azure-sql/database/service-tiers-sql-database-vcore?view=azuresql#service-tiers)

Deployment model(s)...
  1. single instance
  2. elastic pools
    - databases share resources:
      - compute 
      - storage

Purchase model(s)...
  1. DTU (database transaction unit)
    - pre-configured resource measures
    - easiest to implement
  2. vCore (virtual core)
    - choose individual scaling of:
      - compute
      - storage
      - I/O
  3. Serverless
    - auto-scaling
    - billed only for what's used

Redundancy...
  - local redundancy for built-in availability
    - LRS
  - leverage zone redundancy for high availability
    - ZRS
    - GRS
  
Support for Azure Hybrid Benefit and Reservations

## Azure SQL Managed Instance (PaaS)

Fully-managed SQL Server that you can deploy databases, where MSFT manages the OS and hardware and customer manages the database server instance (NOT the machine).

Storage size: 32 GB - 16 TB

Best for life-and-shift migrations, instance-scoped features
  - CLR
  - SQL Server Agent
  - Service Broker
  - Linked Servers
  - Database Mail
  - ML services
  - Distributed transactions

Replication...
  1. active-geo replication
  1. failover groups

Deployment model(s)...
  1. Single instance
  2. Instance pools
    - resource sharing between instances

Purchase model(s)...
  1. vCore

Redundancy
  - local redundancy for built-in availability
    - LRS
  - leverage zone redundancy for high availability
    - ZRS
    - GRS
    - GZRS

Backup
  - automatic backups stored in RA-GRS
  - full: every week
  - differential: every 12 hours
  - transaction log: every 10 minutes
  - PITR: 35 days
  - LTR: 10 years

### SQL PaaS Tiers

General Purpose (vCore)

Business Critical (vCore)

Basic (DTU)

Standard (DTU)

Premium (DTU)

## SQL Server on Azure VMs (IaaS)

Leverage SQL Server in Azure without managing on-premises hardware

Best for migrations and applications requiring OS-level access

Deployment model(s)...
  1. SQL virtual machine

Redundancy
  - local redundancy / availability sets
  - leverage zone redundancy for high availability

Supports Azure Hybrid Benefit

## Azure SQL Edge

Optimized engine for IoT (Edge) deployments, relational and nonrelational data
  - stream
  - process
  - analyze

Containerized Linux application
  - Edge Developer
    - 4 cores, 32 `GB` max
    - Development ONLY
  - Edge
    - 8 cores, 64 `GB` max
    - Production

Security...
  1. AUTHn / AUTHz
  2. TDE
  3. Always Encrypted

Deployment...
  - Connected: from Azure Marketplace
  - Disconnect: deployed through container images from docker hub, on Docker containers / Kubernetes clusters

## Azure Storage

Managed, modern data storage solutions for a variety of scenarios, offering...
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

### Azure Blob

Unstructured data storage at massive scale
  - documents
  - images
  - videos
  - other binary data

Read-heavy sequential access workloads

> Blob = Binary Large Objects

Immutable storage / WORM
  - data can't be modified / deleted
  - Levels...
    - account
    - container
    - version
  - Time-based retention...
    - specified time interval
    - deletion possible after expiry (overwrites not possible)
    - Hot, Cool, Archive tiers
  - Legal hold:
    - applicable until _explicitly **cleared**_
    - no modifications or deletions
    - Premium Blob uses for immutable storage

> WORM = Write Once, Read Many

Scenarios...
  - streaming
  - random access
  - big data analytics

### Azure Data Lake Storage (ADLS)

Scalable, secure data lake storage for large-scale analytics with high throughput
  - Ingest data
    - unplanned? AzCopy, CLI, PowerShell, Storage Explorer
    - relational? Data Factory <-- Cosmos DB, SQL DB, SQL MI
    - streaming? Apache Storm, HDInsights, Stream Analytics
  - Access
    - GUI? Storage Explorer
    - Script? PowerShell, CLI, HDFS CLI, SKDs
  - Access control 
    - Azure RBAC
    - ACLs

Supports **any** type of data
  - unstructured
  - semi-structured
  - structured

  > [!TIP]
  > Good for storing large volumes of _text_ data

Supports HNS, Hadoop (HDFS), POSIX

Lifecycle...  
  1. Data Factory 
  2. ADLS 
  3. Synapse

Use cases:
  - Data warehouse
  - support for diverse collection
  - real-time ingestion

Redundancy...
  - built-in LRS
  - manual configuration of data replication

> [!IMPORTANT]
> Azure Back DOES NOT support ADLS

### Azure Files

Fully-managed, mountable, cloud file shares
  - SMB 
  - NFS
  - Rest API

Can store apps and config files on VMs
  - reducing time for VMs --> production-ready

Azure File Sync...
  - cache Azure Files locally on Windows file servers
  - flexibility, performance, compatibility
  - SMB, NFS, FTPS support

Performance levels...
  - Standard uses HDDs
  - Premium Files uses SSDs

Storage Tiers...
  - Premium: 
  - Transaction-optimized: transaction-heavy workloads but no need for lowest latency
  - Hot Access: 
  - Cool Access: cost-efficient storage

### Azure Elastic SAN

Cloud-based SAN configurations, leveraging...
  - deployment simplification
  - scalability
  - management capabilities
  - high availability

Workloads...
  - VMs
  - AKS
  - MariaDB
  - SQL

> Accessible via internet Small Computer Systems Interface (iSCSI)

### Azure Queues

Asynchronous message queueing for application components
  - 80 GB needed to be stored in one queue
  - progress tracking
  - server-side logs required

Accessible via REST-based interface

### Service Bus Queues

Fully-managed message broker to decouple apps and services
  - Supports publish-subscribe and message queues

If you want apps to receive messages without polling
First-In FIrst-Out required
Transactional behavior / Atomicity required


### Azure Tables

Leverage cloud-based, semi-structured NoSQL data
  - key-value pairing
  - schemaless design

### Azure Managed Disks

Persistently store data on virtual hard disks
  - accessible
  - attachable

| Ultra | Premium SSD | Standard SSD | Standard HDD |
| ----- | ----------- | ------------ | --- |
| IO-intensive, like SAP HANA, SQL Server, Oracle | Production and performance-sensitive workloads | web servers, lightly-used, Dev/Test | backup, non-critical, infrequent access |

Hierarchy...
  1. Ultra
  2. Premium SSD
  3. Standard SSD
  4. Standard HDD

Azure Disk Encryption (ADE)
  - VHD is encrypted
  - VHD only accessible by VM owning the disk
  - integrated with Azure Key Vault

Server-side Encryption (SSE)
  - encryption at-rest
  - encryption on the physical disk (in datacenter)
  - **does not** include temp disks or disk caches

Encryption at-host
  - Server encrypts the data
  - encrypted data is stored in Azure Storage
  - includes temp disks and disk caches

Caching...
  1. Options
      - `None`: for **write-only** and **write-heavy** disks
      - `ReadOnly`: for **read-only** and **read-heavy** disks
      - `ReadWrite`: only for applications that handle writing cache to persistent disks when needed
  2. Defaults
      - OS disks - `ReadWrite`
      - data disks - `ReadOnly`
  3. 

  > Disk caching isn't supported for disks 4 TiB and larger

### Azure Container Storage

Volume management, deployment and orchestration integrable with Kubernetes

### Azure NetApp Files (ANF)

Fully-managed, enterprise-grade NAS
  - NFSv3, NFSv4.1
  - SMBv3.x

Random access, latency/IOPS sensitivity, multi-protocol

Workloads...
  - POSIX
  - SAP HANA
  - HCP 

### Azure Managed Lustre

Fully-managed, high throughput, low latency Lustre file systems
  - simplified
  - lower setup costs
  - reduced maintenance

Workloads...
  - HPC 
  - AI workloads

### Networking, Network Security, Security

Shared access signatures (SAS)
  - granular, dedicated access to client access
  - generates token with parameters indicated HOW and WHAT

Storage Account Firewall rules / Resource settings
  - limit requests from public access
    - IP addresses
    - VNets / subnets
    - Trusted Azure services

Private Endpoints
  - special network interface for virtual networks / on-premises scenarios

Secure Transfer

### Encryption

Data is Azure Storage is encrypted at-rest by default, and cannot be disabled

Customer-managed keys
  - more granular control versus Microsoft-managed keys
  - encrypt/decrypt all data in storage account
  - MUST be stored in Azure Key Vault

Customer-provided keys
  - used to encrypt/decrypt data for read and writes to Azure Blob

## Azure Synapse Analytics

MPP architecture for real-time analysis (through running queries) of serverless / large-scale data
  - discovery
  - integration
  - transformation
  - management

Architecture...
  - Control node -   evenly across compute nodes
  - Compute node - provides compute power so data can be processed

Components...
  - SQL pool: serverless or dedicated resource models for node-based architecture
  - Spark pool: clusters that run Apache Spark; Python, C#, Scala, SQL
  - pipelines: applies capabilities of Azure Data Factory
  - Synapse Link: connect to Cosmos DB
  - Synapse Studio: web-based IDE for Synapse Analytics

Notes...
  - T-SQL queries to be able to query relation an nonrelational
  - Save data as SQL tables
  - Supports PowerBI and ML 

Use cases...
  - various data sources
  - ML + Spark
  - ADLS integration
  - real-time analytics

> [!IMPORTANT]
> MPP = Massively Parallel Processing

## Azure Data Factory

Cloud-based serverless ETL (Extract, Transform, Load) data integration service
  - pipelines for scheduling jobs
  - near real-time
  - low code/no code

Big data: lots of raw, unorganized data from various systems

1. Data compression
  - compress data before writing to data storage
  - optimizes bandwidth and storage
2. Diverse sources
  - on-prem
  - cloud
  - third-party
3. Event triggers
  - custom triggers 
  - actions based on conditions
4. Preview / Validation
  - preview / validation _during_ transfer
  - correct errors _before_ analysis
5. Data Flows
  - create ETL processes for data transformations
  - low code / no code
  - visual tools
6. Security integrated
  - RBAC

Process...
  1. Connect + collect 
      - ingest from various sources
      - centralize
  2. Transform + enrich
      - Azure Databricks
      - Azure HDInsights Hadoop
  3. CI/CD
      - GitHub
      - Azure Pipelines
      - ETL process incrementally
  4. Monitor
  
Integration runtimes:
| Azure | Self-hosted | Azure-SSIS |
|--|--|--|
|<ul><li>Data Flow</li><li>Data Movement</li><li>Activity dispatch</li></ul>|<ul><li>Data Movement</li><li>Activity dispatch</li></ul>|<ul><li>SQL Server Integration Services</li></ul>|

## Data Factory vs Synapse Analytics

| --- | Data Factory | Synapse |
| --- | ------------ | ------- |
| --- | supports data sharing across factories | --- |
| Templates | supported | supported |
| --- | cross region data flows | --- |
| Monitoring | data monitoring (Azure Monitor) | Diagnostic logs (Azure Monitor) |

## Azure Databricks

Apache Spark-based analytics platform, large-scale data processing

Clusters
  - single node
  - multi-node

Notebooks
  - interactive coding workspace
  - visual insights
  - collaboration

Jobs
  - schedule automated data processing

Databricks File System (DBFS)
  - distributed datasets
  - used in Notebooks and workflows

Integrates with...
  - Azure Data Lake
  - Azure Synapse Analytics
  - Azure ML

Auto-scaling clusters
Supports RBAC
Supports Scala R

## Azure Stream Analytics

Analyze and process large-volume streaming data, sub-millisecond

## Data paths (Warm, Cold, Hot)

Warm...
  - analysis as data flows through system(s)
  - Stream Analytics for data processing
  - Azure SQL DB, Azure Cosmos DB for storage

Cold...
  - 

Hot...
  -

## Fault / Update domains

| FD-0 | FD-1 | FD-2 |
| ---- | ---- | ---- |
| VM-1<br/>UD-1  | VM-2<br/>UD-2 | VM-3<br/>UD-3 |
| VM-4<br/>UD-4 | VM-5<br/>UD-5 | VM-6<br/>UD-1 |

## Azure Front Door

Routes clients to fastest and most available app backend
  - L7 / Http / Https
  - Internet-facing application backend can be hosted inside / outside Azure

Features...
  - URL-based routing
  - Priority-based routing
  - multi-site hosting
  - Session affinity
  - SSL termination
  - leverage WAF

## Azure ExpressRoute

dedicated PRIVATE CONNECTION (non-Internet) from on-prem to non-MSFT provider to Azure. 

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

Integrates with...
  - virtual networks
  - LAWs
  - Defender for Cloud

SKUs...
  - Basic
  - Standard (L3-L7 filtering)
  - Premium

## Azure Application Gateway

## Azure VPN Gateway

Sends encrypted traffic between Azure VNet and on-premises location(s), over the PUBLIC INTERNET.

## Azure Traffic Manager


| Service             | Traffic     | Global/Regional |
| -------             | -------     | --------------- |
| Azure Front Door    | HTTP/S      | Global          |
| Traffic Manager     | non HTTP/S  | Global          |
| Application Gateway | HTTP/S      | Regional        |
| Azure Load Balancer | non HTTP/S  | Regional        |

## Password Hash Sync (PHS)

  - securely syncs password hashes of on-prem AD --> Entra ID 
    - credentials stored in both directories
  - leverages through Entra Connect installed on on-prem AD

Benefits...
  - single sign-on (SSO)
  - hashes stored instead of plaintext passwords
  - prerequisite for _self-service password reset_ (SSPR)
  - faster AUTHN since AUTHN happens in cloud
  - ideal for hybrid environments
  - _Password Write-back_ if you want to sync cloud changes --> on-prem
  - Leak Credential Report

## Pass-through AUTHN (PTA)

password sync without federation environment requirements
  - technically free feature

Benefits...
  - single sign-on (SSO)

## Single Sign-On (SSO)

> Can be combined with either:
>
>   - PHS
>   - PTA
>
> **Not applicable** to Active Directory Federation Services (ADFS)

## Azure Key Vault 

[Key rotation](https://learn.microsoft.com/en-us/azure/key-vault/keys/how-to-configure-key-rotation)

## Hardware Security Module (HSM)

- customer specific security domain

## Azure Policy

> Policy **DOES NOT** affect existing resources, remediation tasks will need to be created.

- `disabled` is best used for testing before / without implementing
- `modify` affects new resources

## Azure Migrate

Primary tool for assessment and migration of VMs, physical machines, databases
  - TCO Estimation
  - Right-sizing recommendations
  - Dependency mapping
  - Migration planning
  - Minimize downtime
  - Optimize costs

## Design infrastructure solutions

### Azure Virtual Machines

Scenarios...
  1. Build new workloads
  2. Lift-and-Shift (Rehost) migrations

Process...
  1. Start with networking
  2. Pick location of VM
  3. Determine ideal size
  4. Review pricing models (reservations, savings plans, AHUB)
  5. Review storage options
  5. What's the OS?

### Azure Batch 

Run large-scale apps efficiently
  - HPC workloads (compute-intensive)
  - dynamically adjustable resources
  - parallel jobs

### App Service

HTTP-based service for web jobs, RESTful PIs, mobile backends
  - lift-and-shift
  - built-in load balancing
  - CI/CD support/enablement

### Azure Container Instances (ACI)

Run containers on Azure
  - simple applications
  - automated tasks
  - build jobs
  - supports life-and-shift containerized applications

Supports persistent storage by leveraging/mounting Azure Files shares
Supports Linux and Windows

Container groups...
  - collection that gets scheduled on same host machine
  - shared lifecycle, resources, network, storage

Considerations...
  - use a private registry (Docker Trusted Registry, Azure Container Registry)
  - securely manage and govern images
  - monitor resource activity

### AKS

Kubernetes container (full-fledged) orchestration and management on Azure
  - docker support
  - autoscaling
  - static and dynamic storage volume
  - HTTP support
  - Docker support

Horizontal pod autoscaler...
  - increase pod count based on demand

Cluster autoscaler...
  - scales nodes based on node constraints

### Messaging and Events

- Messages contain raw data, where the destination source is expected to process component
  - for distributed applications
- Events are lighter weight (producers, consumers, channels), where destination source is not expected to process component.

### Azure App Configuration

Central management of application settings and feature flags

### Network Requirements

Max IP addresses in VNet: `65,536`
Don't go smaller than CIDR range of `/16`
NAT can help if you overlap your network and cannot redesign it

### Hub-and-Spoke

Isolate workloads but share common services

### User-defined routes (UDRs)

Leveraging static routes / custom routes to overwrite Azure's default routes --> Route Table
  - BGP rules
  - Service endpoints
  - Route order: UDR > BGP > System (defaults)

Enable filtering with Azure Firewall or forced tunneling
Flow from subnet through NVAs