# AZ-500: Azure Security Engineer Associate

> Learning Path - AZ-500: Secure Identity and Access

## Microsoft Entra ID

> previously Azure AD

- cloud-based identity and access management service
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
  - Privileged Identitiy Management (PIM)
  - Entra ID Protection for 
- `Pay-As-You-Go`
  - Business-to-Customer (B2C)

### Features

- Application Management: process of creating, configuring, managing, and monitoring apps in cloud
  - when an application is registered in Entra tenant, users assigned to app can securely access it.
  > Secure access through OAuth, OIDC, SAML
  - Application types supported:
    - singal-page apps (SPA)
    - web apps
    - web APIs
    - Mobile and native apps
    Service, daemon, script
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
  - MSFT Entra Governance
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

## Users & Guests

### Internal

Interal members are most likely full-time users in the organization.  
Internal guests are users with guest-level permissions.  

### External

External users are users that have external accounts but have member access... pretty common in multitenant organizations.  
External guests are users autheniticate using external methods and have guest-level privileges.



## Terminology & Key Terms

- `Identity`: _anything_ that can get **authenticated**
- `Account`: identity with data associated
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





## MSFT Cloud Security Benchmark
### Identity management and privileged access

Some of the identity and access management systems include:
- single sign-on (SSO)
- strong AUTHN
- managed identities
  - also service principals
- conditional access
- anomaly detection and monitoring