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

- Custom roles

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

Big-data data-streaming service capable of millions of events per second, which Apache Kafka compatibility.

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
