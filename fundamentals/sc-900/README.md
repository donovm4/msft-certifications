# SC-900

## Official Certification Doc

- [Overview](https://learn.microsoft.com/en-us/credentials/certifications/security-compliance-and-identity-fundamentals/?practice-assessment-type=certification&WT.mc_id=certposter_poster_wwl)

## Fundamental Concepts

- Security
- Compliance
- Identity

## What is Data?

**Data** is any piece of information translated into binary digital format that can be moved ro processed.

## What is an Identity?

**Identity** can be a user (something that needs to prove themselves in order to access something), an application, or a device.

- Administration
  - What management rights over identites?
- Authentication (AuthN)
  - Who is the user?
  - Verification
- Authorization (AuthZ)
  - What *can* a user do?
  - What level is the user at?
  - What level can the user get to?
- Audit
  - What has the user *done*?

### Identity Provider (IdP)

Entra ID Tenant:
- Azure
- M365
- Users
- Applications
- Devices
- OAuth2
- OIDC
- SAML
- third-party applications

> The big thing here is **TRUST**  
> There is trust between these services and an *INSTANCE* of the identity provider.

## Shared responsibility model

When it comes to cloud-based services, implementing security and complain is shared responsibility between customer and cloud provider.

- On-prem
  - The customer is responsible for everything - physical security <--> encrypting sensitive data
- IaaS
  - The cloud provider is responsible for securing the physical hosts, baremetal networking, and datacenter(s).
- PaaS
  - The customer is responsible for securing the applications and data.
- SaaS
  - The customer only responsible about the data supplied, the physical devices used to access SaaS software, user accounts and identities.

## Defense in depth

You **do not** want to rely on only one method of defense. You do want layers of protection, as the data is the most important item here.

- Physical Security (of the datacenter)
- Identity
- Perimeter on the network (something like DDos prevention)
- Network (subnet, segmenting, traffic limitations)
- Compute (antimalware, firewalls, patches)
- Application (vulnerability testing)
- Data (encryption)

> You do not want to be so secure that you cannot continue business processes

## CIA

Confidentiality
- sensitive data is encrypted  

Integrity
- data is not manipulated  

Availability
- data is available to those who need it, when they need it

## Zero Trust

- verify explicitly / constantly
- least privelege
  - just enough access
  - just-in-time access
- assume breach
  - assume the attacker is already on the network
  - focus on being able to spot that the network

### Hierarchy of Zero Trust (when it comes to identities)

- Identities
  - Devices
    - Applications
    - Data
  - Infrastructure
  - Networks

## Encryption

**Data Encryption** is the process of turning data into ciphertext that *should* be unreadable to unauthorized parties.

**Keys** are some data used as part of cryptographic operation to encrypt and decrypt.

### Symmetric

The key used to encrypt the data, is the same key used to decrypt the data.

Example:  
1. `Data` is encrypted using `Key1` to generate `Encrypted_data`  
2. `Encrypted_data` is decrypted using `Key1` to read `Data`

**Issue**: *How do I secure share the key between both parties?*

### Asymmmetric

There are two keys:
- public (everyone has access to use)
- private (only "known" to the individual who owns the key pair)

The public key of the person who I want to share the data with is used to encrypt the data. The private key of the person who I want to share the data with is used to decrypt the data.

Example:
1. Ron wants to share `Data` with Sakina
2. Ron uses Sakina's `public_key` to generate `Encrypted_data`
3. Sakina receives `Encrypted_data`
4. Sakina is able to decrypt `Encrypted_data` by using their own `private_key`

## Hashing

This is the concept of running an algorithm on a fixed set of data to generate some value.  

> This value will also be the same, no matter how many times it is generated (so long as the algorithm and the data set stay consistent).

The original hash can be made public, and data accessers can check the hash of their 'copy' to ensure data integrity.

Real-world scenario:
Passwords are not supposed to be stored in plaintext.  
The password hashes are generated and stored in database.  
When the password is being validated, the hash is generated and compared to what is stored in database.  

## GRC

- Governance
  - what are the rules and practices that an organizations use in their organizational processes?

- Risk
  - threats that can impact the organization
  - internal and external
  - how does the organization plan for, detect, and react to?

- Compliance
  - what rules do the organization need to adhere to?

## Authentication

### Active Directory Domain Services

Authentication for on-prem: 
- Kerberos
- NTLM

### Hybrid identities

We sync the identities from the ADDS up to the Cloud Identity Provider.

Examples:
- Entra Connect
- Entra Cloud Sync

### Federation

Let's say we have two tenants:
- `Tenant_A`
  - `resource1`
- `Tenant_B`
  - `User1`

`User1` lives in `Tenant_B` but wants to access `resource1` which lives in `Tenant_A`.

**Federated trust** is when `Tenant_A` trusts `Tenant_B` to run through authentication processes, which will then allow `User1` to access `Tenant_A` 'from' `Tenant_B`.

### Types of accounts

- Internal user
  - created in 'our' identity provider
- External user
  - invited from an external identity provider
- Service principal (workload identites for applications)
  - can authenticate using password, certificate
- Managed identity
  - can be assigned to Azure compute resource
  - system-assigned
    - managed directly on the resource
  - user-assigned
    - can be assigned to more than one resource
- EntraID-joined device
  - authenticate to the device through Entra
- EntraID-registered device
  - device itselft is known through Entra
- Hybrid-joined device
  - combination of joined and registered

### Multifactor Authentication (MFA)

> Something I know, I have, I am

#### Methods (combination)

- Passwords
- SMS
- Voice
- tokens (software / hardware / one-time passcode)

### Passwords

Password only is not secure - VERY BAD!

It is better to use multiple methods to prove the user is who they say they are.

### Passwordless

> - fill in later

### Passkeys

- Phishing-resistant
- Proximity-based

> Authenticator App  
> Windows Hello for Business
> FIDO

### Self-service password reset

- lockout thresholds
- nummber of methods needed to complete reset
- security questions

## Authorization

> Mainly focusing on conditional access

User has already be *authenticated*, now we move onto **access**

### Role-based Access Control (RBAC)

- What is the desired role / set of permissions?
- What identity do I want to assign the role to?
- What scope does the identity has permissions over?

## Audit and governance

### Entra Identity Governance
- triggers
- actions
- dynamic groups

### Access Reviews
- validates permissions needed
- can be proctored process
- can be self-serviced process

### Privilege Identity Management (PIM)

### Identity protection
- User Risk Level assessment
- specific sign-in actions

### Permissions management
- cross-cloud
- identifies which permissions are *granted*
- identifies which permissions are *used*

### Entra Private Access
- TCP
- UDP
- facilitates traffic from device to Entra to private network
- facilitates traffic from device to Entra to Internet

## Security Solutions

### Azure

#### DDoS Protection

**Distributed denial of service** (DDoS) attacks try to exhaust application reources making it unavailable to actual users.

- protects at layers 3 and 4
- automatic adaptive-tuning to protect resources
- requires no application or resource changes
- analytics
- metrics
- alerts

- Tiers: 
  - Network protection
  - IP protection

#### Azure Firewall

- works within the virtual network
- works on layers 4 and 7

#### Azure Web Application Friewall (WAF)

- exploit protection
- SQL injection
- cross-site attacks
- DDoS protection

> Azure Front Door is global  
> Region WAF

#### Network Security Group (NSGs)

- Source Port
- Source IP
- Destination Port
- Destination IP
- Protocol
- Rules:
  - Allow
  - Deny

#### Azure Virtual Network Manager

- Security Admin rules 
- priority over NSGs
- Rules:
  - Allow
  - Always Allow
  - Deny

#### Azure Bastion

- securely connect to VMs in Azure **WITHOUT** public ip
- working around to prevent port-scanning.
- RDP
- SSH
- SKUs:  
  - Basic
  - Standard
  - Premium

#### Azure Key Vault

##### Secrets

- passwords
- shared access signatures

Something you write and read

##### Keys

- import
- generate
- cannot be exported from Key Vault
- run cryptographic operations

##### Certifications

- lifecycle management on certificates
- TLS certificates for example
- Tiers:
  - Standard
    - software-protected keys
    - key rotation
  - Premium
    - software-protected keys
    - HSM-protected keys
    - key rotation

### MSFT Defender for Cloud

#### CNAPP - Cloud Native App Protection Platform

##### CSPM - Cloud Security Posture Management

- leverages Azure Policy
- Microsoft Security Benchmark

##### CWPP - Cloud Workload Protection Platform

Other solution areas under the Defender suite:

- Storage
- Servers
- Compute
- Databases

##### DevSecOps

The goal here is to implement security practices earlier in the development pipelines:

- GitHub
- DockerHub
- Azure DevOps

### MSFT Sentinel

#### SIEM - Security Incident and Event Management

- collect signals from various systems:
  - agents
  - logs
  - diagnostic settings
- detect issues
- investigate

#### SOAR - Security Orchestration Automated Response

- investigate
- respond automatically

### Security Copilot

Works in the same way as everything else, BUT incorporates the use of AI, usually large language models (LLMs).
- natural language
- prompt engineering

Integration / Embedded: 

- Sentinel
- Entra
- Intune
- Defender
- Purview

### Defender XDR

> Integrated with Sentinel portal

Solutions for:

- Office 365
- Defender for Endpoint
- Cloud apps
- Defender for Identity
- vulnerability management
- threat intelligence

## Compliance

6 Key Principles:

- Control
- Transparency
- Security
- Strong legal protections
- No content-based targeting
- Benefit the customer

### Service Trust Portal

- certifications
- references
- standards used
- reports
- industry details
- regional details

### MSFT Priva

- helps organizations understand what Private Personal Data they have and what to do with it
  - discovery
  - risk management
  - limit transfer
  - subject rights request
  - workflow automation
  - reporting

### Purview

Various solutions available

- Governance
- Compliance
  - Compliance Manager
    - compliance score
    - organization responsibilities
    - MSFT responsibilities
    - improvement actions
    - assessments
    - regulations
    - policies
    - alerts
- Data security
  - Data Lifecycle Management
    1. Know the Data
        - Find Data
        - Classify the Data (trainable classifiers, sensitive types, EDM)
          - Built-in
          - Custom
    2. Protect the Data
        - Sensitivity labels
        - watermarks
        - encryption 
    3. Prevent Loss
        - DLP - digital loss protection
    4. Govern the Data
        - Policies
          - Retention
          - Deletion
          - Labels
        - Records management

#### Content Search

#### eDiscovery (Standard)

- case creation
- legal holds

#### eDiscovery (Premium)

- complete e2e workflow

## Audit

M365 Operations are captured to a log.

Users can search against the logs.

Tiers:  

- Standard
  - 90-day retention
  - command access
  - GUI access
  - API access
- Premium
  - 1 year retention
  - higher bandwidth
  - command access
  - GUI access
  - API access

