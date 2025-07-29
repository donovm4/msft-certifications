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
    - MSFT Identitfy Manager
    - cloud write-back capabilities
- `Entra ID P2`
  - risk-based conditional access
  - Privileged Identitiy Management (PIM)
  - Entra ID Protection for 
- `Pay-As-You-Go`








## MSFT Cloud Security Benchmark
### Identity management and privileged access

Some of the identity and access management systems include:
- single sign-on (SSO)
- strong AUTHN
- managed identities
  - also service principals
- conditional access
- anomaly detection and monitoring