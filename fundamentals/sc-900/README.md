# SC-900

## Official Certification Doc

- [Overview](https://learn.microsoft.com/en-us/credentials/certifications/security-compliance-and-identity-fundamentals/?practice-assessment-type=certification&WT.mc_id=certposter_poster_wwl)

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

## Identity Provider (IdP)

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

## Active Directory Domain Services

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

## Types of accounts

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