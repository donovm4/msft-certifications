# AZ-500: Azure Security Engineer Associate

> Learning Path - [AZ-500: Secure Identity and Access](https://learn.microsoft.com/en-us/credentials/certifications/azure-security-engineer/?practice-assessment-type=certification&source=learn)

## Table of Contents

- [Entra ID](#microsoft-entra-id)
- [Entra External ID](#msft-entra-external-id)
- [IAM](#identity-and-access-management)

## Microsoft Entra ID

> previously Azure AD

- cloud-based identity and access management (IAM) and network access management service
- ensures user identities are securely managed and can access resources properly
- can be used to access internal resources
- can be used to access external resources:
  - M365
  - Azure
  - SaaS applications

### Who uses Entra ID?

- IT Administrators
  - control access to apps and app resources
  - set AUTHN requirements, like multi-factor authentication (MFA)
  - automate user provisioning 
  - protections and governance for identities and credentials
- App Developers
  - can use Entra ID as standard AUTHN provider
  - leverage SSO
  - leverage Entra APIs for using personalized experiences w/ organizational data
- M365, O365, Azure, Dynamics CRM Online users
  - these tenants are also Entra tenants, automatically

### Licensing

> Business services use Entra ID for sign-in activities and identity protections automatically, through `Entra ID Free`

- `Entra ID Free`
  - user and group management
  - on-prem directory sync
  - basic reports
  - self-service password reset (SSPR) for cloud users
  - SSO across Azure, M365, other SaaS apps.
- `Entra ID P1`
  - hybrid users can access on-prem and cloud resources
  - advanced administration
    - dynamic groups
    - self-service group management
    - MSFT Identity Manager
    - cloud write-back capabilities
- `Entra ID P2`
  - risk-based conditional access
  - Privileged Identity Management (PIM)
  - Entra ID Protection for 
- `Pay-As-You-Go`
  - Business-to-Customer (B2C)

### Features

- Identity Management
- Application Management: process of creating, configuring, managing, and monitoring apps in cloud
  - when an application is registered in Entra tenant, users assigned to app can securely access it.
  > Secure access through OAuth, OIDC, SAML
  - Application types supported:
    - singal-page apps (SPA)
    - web apps
    - web APIs
    - Mobile and native apps
    - Service, daemon, script
    > daemon - authenticates users and calls APIs without user interaction
- Authentication
  - SSPR
  - MFA
  - banned password list
  - smart lockout
- MSFT Identity Manager
  - for devs to build apps leveraging SSO
  - token calls for APIs and Graph
- B2B
  - management of guest users and external partners
  - feature under Entra External ID
- B2C
  - control how users sign-up, sign-in, manage their profile from apps
- Conditional Access
- Device Management
  - manage how devices access data
- Domain services
  - join Azure VMs to domain without domain controller
- Enterprise users
  - manage licenses, app access, groups, roles
- Hybrid identity
  - provide single user identity for AUTHN and AUTHZ, with Entra Connect and Entra Connect Health
- Identity governance
  - MSFT Entra ID Governance
  - access reviews
- Identity protection
  - vulnerability detection
  - anomaly protection
  - policies
  - actionable steps to resolution
- Managed Identities
- PIM
  - just-in-time (JIT) access
  - just enough access
- Monitoring and health
- Workload identities
  - give an identity to software workloads, such as:
    - apps
    - services
    - scripts
    - containers

### Identity and Access Management

#### Users

A user can be an identity

##### Types

- Internal
  - Interal members are most likely full-time users in the organization.  
  - Internal guests are users with guest-level permissions.  

- External
  - External users are users that have external accounts but have member access... pretty common in multitenant organizations.  
  - External guests are users autheniticate using external methods and have guest-level privileges.

> You need to add access permissions _for each separate_ app, resource, and service **after** creating a user

#### Groups

Entra ID enables the granting of same-level access and permissions to groups of users instead of just each individual users

##### Types

- Security
  - control members, groups, and computer access to shared resources
- M365
  - give members access to a shared mailbox
  - potentially give users or service principals outside organization access to the group

##### Methods of assigning group membership

- Assigned
  - assign specific members
- Dynamic User
  - leverage conditions to add / remove users automatically
- Dynamic Device
  - leverage conditions to add / remove devices automatically

> You need to add access permissions _for each separate_ app, resource, and service **after** creating a group

##### Adding access rights

- Direct assignment
  - directly assigning the user to a resource
- Group assignment
  - assigning group to the resource
  - managed by _both_ resource owner and group owner
- Rule-based assignment
  - essentially dynamic group assignment based on conditions
- External authorite assignment
  - access comes from external source (SaaS or on-prem AD)
  - resource owner assigns group to resource
  - group membership managed by external source

## MSFT Entra External ID

- invite guest users into organization
- simple process:
  - invitation
  - redemption
- self-service sign-up
- user type is typically set to `guest`
-  principal name contains the `#EXT#` identifier

### B2B Collaboration / External Identites

The partner uses their own identity management system(s). Guest users can sign-in to your apps and services, with their own identities:
- MSFT Entra accounts
  - work
  - school
- MSA (personal accounts)
- social
  - Facebook
  - Google
- SAML / WS-Fed IdP federation protocols
  - protocols by which AUTHN data is transfered between two _parties_
  > - Security Assertion Markup Language (SAML)
  > - Web Services Federation (WS-Fed)


> B2B collaboration is enabled by default

### `CONCEPT`: _External_ Tenant versus _Workforce_ Tenant Configuration

#### External

- exclusively for apps you want to publish to consumers or business customers
- custom self-service registrations flows (sign-up, sign-in)
- custom sign-in with Company branding settings
- customer data collection during sign-up, user activity, engagement data

#### Workforce

- standard MSFT Entra tenant
- contains employee, internal apps, organizatinal resources
- internal users can collaborate with external users, leveraging B2B

### B2B Direct Connect

- create a two-way trust relationship with other MSFT Entra organizations
  - enables Teams Connect shared channel features
- use cross-tenant access settings to manage trust 

### Azure Active Directory B2C (Azure AD B2C)

- legacy solution for customer identity and access management (CIAM)
- separate consumer-based directory/tenant, managed through Azure AD B2C service

### MSFT Graph APIs

- available for creatings and managing External ID features
- Examples:
  - cross-tenant access API enables developers to programmatically create B2B Collaboration and Direct Connect policies
  - leverage the invitation manager API for building custom onboarding experiences for business guests

## MSFT Entra Identity Protection

- helps organizations...
  - detect
  - investigate
  - remediate

### Detect

- during each sign-in, real-time detections run and generate session risk level
  - rish level determines the policies applied to protect user / organization
- there is a catalog of tections to protect organizations
  - based on trillions of signals from AD, MSAs, Xbox
    - Anonymous IP usage
    - Brute-force / password spray attacks
    - credential leaks

### Investigate

There are 3 key reports for administrators:

1. Risk detections  
    - each risk detected
    - only available with Entra ID P2
2. Risky sign-ins
    - one or more risk detections reported on sign-in
    > Limited info with Medium + High only, by default  
    > Full access with Entra ID P2
3. Risky users  
    - the use has on or more Risky sign-in associated
    - one or more risk detections have been reported
    > Limited info with Medium + High only, by default  
    > Full access with Entra ID P2

### Remediate

There are both automatic and manual methods for remediation

- Automatic rememdiation
  - Risk-based Condition Access policy examples:
    - require strong AUTHN method
    - MFA
    - perform secure password reset
- Manual remediation
  - leveraged when user remediation isn't enabled
  - administrator manually reviews reports
    - in portal
    - through API
    - in M365 Defender (is this the equivalent to XDR?)
  - administrators can perform manual actions:
    - dismiss
    - confirm user safety
    - confirm compromise of risk(s)

### Using the Data

Data from Identity Protection can be export to other tools.

- integrate with MSFT Sentinel
- send to Log Analytics Workspaces
- archive data in storage account
- stream data to Event Hubs
- send to another SIEM solution

## MSFT Entra Connect

- On-prem MSFT app designed for hybrid identities.
- common identity for accessing on-prem and cloud resources

### Features

- Password Hash Sync
  - syncs passwords of on-prem AD with Entra ID
- Pass-through AUTHN
  - password sync without federation environment requirements
  - technically free feature
- Federation
  - enables hybrid environment with management of on-prem Federation Services (AD FS)
- Synchronization
- Health monitoring

## MSFT Entra Application Proxy

> Application proxy connector tool

- provides secure remote access to on-premises web apps
- SSO
- users access cloud and on-premises app through:
  - external URL
  - internal app portal

## MSFT Entra Verified ID

`decentralized identities`: concept of individuals being in control of managing their data without relying on centralized authorities or third-party intermediaries

- establish a **unique** and **decentralized** identity for each individual user
  - generated by users themselves
  - immutability
  - censorship resistance
  - tamper evasiveness
- standards-based, secure management across platform and services
  - private, self-owned identities
  - trusted
  - verifiable
- examples of digital credentials:
  - ID documents
  - certifications
  - licenses

> Example DID system: ION

> collaboration with DIF and W3C

## MSFT Entra Connect Health

- robust monitoring solution for on-prem identity infrastructure
  - alerts
    - failed sign-ins
    - Extranet lockouts
    - ADFS issues
    - maintenance
    - alerts through email
  - performance monitoring
  - usage analytics
  - ease of use (single pane of glass)
> Install agent on each on-prem identity server

## MSFT Entra Cloud Sync

- enables synchronization of users, groups, contacts to Entra ID
- uses Entra cloud provisioning agent
- orchestrated in MSFT Online Services

### Key Features

- can be leveraged alongside Entra Connect Sync
- assists with multi-forested, disconnect ADs syncing to Entra ID
- light-weight provisioning agents bridge AD to Entra ID, configs maintained in cloud
  - multiple agents for high availability
- support for groups up to 50,000 members by leveraging organizational units (OUs)

## Authentication (AUTHN)

Authentication is the foundation for cloud access.

> CONTEXT: this is for organizations that leverage on-prem AD service

### Options

- Cloud Entra Password Hash Sync
  - same username and password as on-prem
  - no _additional_ infrastructure deployment required
  - requires less effort of these three options
- Cloud Entra Pass-through Sync
  - password validation leveraging software agent running on on-prem servers
    > RECOMMENDATION: leverage 3 agent deployments for high availability
  - servers validate users on-prem (password AUTHN does not happen in cloud)
- Federation
  - Entra ID will leverage separate identity AUTHN system to validate password
  - usually requires more effort to implement and maintain (versus cloud AUTHN)
> RECOMMENDATION(S):
> - leverage deployment of additional servers for Pass-through or Federation for HA / DR efforts
> - leverage Password Hash Sync regardless of on-top of Pass-through or Federation in case of on-prem outages, and Entra ID protection and credential leak reports

## Kerberos

- provides domain-based AUTHN
- Windows Server OS implement Kerberos v5 AUTHN protocol and extensions for public key AUTHN.
  - implemented as security support provider (SSP)
  - accessed through Security Support Provider Interface (SSPI)
- AD DS is required for Kerberos implementations within domain or forest.
  - Kerberos Key Distribution Center (KDC) integrated on domain controller
  - KDC uses domain's AD DS database

### Benefits

- delegated AUTHN
  - services on Windows Server OS can impersonate client computer
  - act on client's behalf
  - authentication provided via Kerberos protocol and NTLM
- single sign-on
- interoperability
- efficiency
- mutual AUTHN

## MSFT Entra Privileged Identity Management 

- user interface for assigning and managing privileged roles and access
- accessible in Azure Portal through ID Governance


## New Tech LAN Manager (NTLM)

Family of AUTHN protocols

NTLM protocols authenticate users and devices using challenge/response method to prove user AUTHN with server/domain
  - domain AUTHN service of domain of the account
  - look up account if in local database

> `LAN` = Local Area Network

## Password-less AUTHN

### Windows Hello for Business

  - Biometric or PIN
  - Cloud AP provider
    - requests nonce
    - provides signed nonce
    - decrypts session key and using TPM
    - sends successful AUTHN message
  - MSFT Entra ID 
    - sends nonce
    - validates signed nonce 
    - provides primary refresh token (PRT), session key
  - Windows 1809 or later

### Microsoft Authenticator

  - app turns iOS or Android phone into **password-less** credential
  - push notifications
  - app calls Entra ID
  - challenge presented to user authenticating

### Passkeys FIDO2 (Fast IDentity Online 2)

- unphishable standards-based password-less AUTHN method
- users sign-in to resources with either:
  - external security key
    - USB
    - Bluetooth
    - NFC
  - platform key built into device
- Windows 1903 or later

#### Key Distribution

- central key provisioning processes
- allow users to purchase FIDO 2.0-compatible keys

#### Key Activation

- self-active security keys
- users register keys
  - enable second factor after first use

### Certificate-based authentication (CBA)

- AUTHN directly with X.509 certificates against Microsoft Entra ID


## Multi-Factor Authentication (MFA)

1. Something you have
    - trusted devices
2. Something you know
    - passwords
3. Something you are
    - biometrics

## MSFT Sentinel

- cloud-native SIEM and SOAR platform
- collects and analyzes security data
- real-time threat detection
- automated incident response
- customizable dashboards
- advanced analytics, leveraging AI & ML, analytics rules to trigger events when definded patterns are met
- scalable and integratable

### Capabilities

- build playbooks
  - automated  workflows 
  - respond to threat variant (based on instructions and analysis) of known signature profiles of attack vectors
- advanced analytics, leveraging AI & ML
- incident response
- threat hunting
- vulnerability scanning
- security operations automation
- integrate with...
  - Defender for Endpoint
  - Defender for Cloud
  - third-party security tooling
- MITRE ATT&CK framework integration

### Threat Hunting

> Prerequisites:  
> - Security Reader / Admin
> - Reader
> - Contributor
> - Owner

- queries / specialized searches
- proactively identify potential threats / malicious activities
- NOT triggers by alerts
- User-initiated

Threat Hunting queries are usually written in KQL

- search large amount of data
- filter events
- aggregate data

#### Steps

1. Hypothesize approach (identify the DRIVERS for investigation)
2. Identify data sources
3. Leverage MSFT / MITRE Attack frameworks
4. Build queries
5. Refine queries as needed

### SIEM - Security Incident and Event Management

> SIM - security information management, collection
> SEM - security event management, analysis

- collect signals from various systems:
  - agents
  - logs
  - diagnostic settings
- detect threats / issues
- investigate
- visibility / visualizations 

> Log Analytics Workspaces are foundational for Sentinel functionality

### SOAR - Security Orchestration Automated Response

- investigates (orchestrated processes to streamline investigations and responses)
- respond automatically
  - isolate malware-infected devices
  - block bad traffic
  - reset compromised accounts
  - collection of forensic evidence

### Benefits

- reduced complexity
- centralized view from various data sources across enterprise
- threat intelligent
- proactive hunting
- scalable
- integration with 1st and 3rd-party solutions

## Terminology

- `Identity`: _anything_ that can get **authenticated**
- `Account`: identity with data associated to it
- `Entra account`: identity created through Entra ID
  > Sometimes can be a Work or School account.
- `Account Administrator`: role that enables user to manage all subscriptions in an account
  > conceptually the billing owner of the subscription
- `Service Administrator`: role that enables user to manage all Azure resource and access
  > equivalent of a user with Owner at subscription level
- `Owner`: role that enables user to manage all Azure resources
  > built on role-based access control (RBAC), which is considered a newer AUTHZ system
- `Entra Global Administrator`: role that enables users to assign administrator roles to users
  > automatically assigned to whoever creates the Entra tenant
- `Security Administrator`: role that enables user to manage security-related features, permissions, and compliance in M365 Security Center
- `Subscription`: concept in the billing model used to pay for Azure services
- `Tenant`: dedicated, trusted instance of Entra ID; represents a single organization; manages users, apps, resources.
- `Single tenant`: Azure tenants accessing services in a dedicated environment
- `Multi-tenant`: Azure tenants accessing services in shared environment, across multiple organizations
- `Entra directory`: includes the users, groups, apps of tenant; used to perform identity and access management functions for resources
- `Custom domain`
- `MSFT account (MSA)`: personal accounts providing access to MSFT products and/or services


## MSFT Defender for Cloud

- cloud-native app protection platform (CNAPP)
- security measures and best practices
- protect apps from cyber threats and vulnerabilities

## MSFT Defender for Identity

- leverages on-prem and cloud-based identities
- prevent, detect, investigate, respond
- integrated with XDR

## Conditional Access

## Permissions

- Contributor: full access to manage a resource _except_ permission modification

## MSFT Cloud Security Benchmark

### Identity management and privileged access

Some of the identity and access management systems include:
- single sign-on (SSO)
- strong AUTHN
- managed identities, service principals
- conditional access
- anomaly detection and monitoring

## Azure Key Vault

- securely storage and access secrets
  - API keys
  - passwords
  - certificates

### Access

- access policies
  - customized permissions
    - encryption / decryption
    - listing, writing, reading
  - Built-In:
    - Azure VMs deployment
    - ARM template deployment
    - Azure Disk Encryption
- RBAC on the _control plane_ / management of KeyVault
- Access policies on the _data plane_ / access and management of the data