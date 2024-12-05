## Terminology
- **Data Center** - Facility used to house and manage data. Core elements: Hardware components (compute, storage, networks, etc) and Software components (Applications and operating systems)
- **Cloud User** - Person/ organizatio requesting resources and services
- **Cloud Service Provider (CSP)** - Org that provides cloud platform, infrastructure, applications, and services
- **Multitenancy** - Architecture common to cloud computing where customers share available resources without knowledge of each other
- **Cloud-native** - Designed for the cloud environment
- **Vendor lock-in** - Reliance on proprietary software that restricts orgs from adopting alt solutions easily
- **Economies of scale** - Relation between per-unit cost and production volume. More production leads to decrease in price
- **Organizational Agility** - Ability of org to adapt to changes in market
- **Capital Expenses (CAPEX)** - Costs associated w/ fixed assets (Including purchase, maintenance, and improvement)
- **Operational Expenses (OPEX)** - Costs associated w/ day-to-day operations of business
- **Vertical scaling** - Adding resources to same node (memory, processing, etc)
- **Horizontal scaling** - Adding more nodes to distributed system
- **Total Cost of Ownership (TCO)** - Complete cost of an service over its lifetime
- **Monolithic application** - Designed as a single unit
- **Microservices-based application** - Application broken down into many services that interact
- **Serverless** - Independent of the need to provision or manage servers
------------------------------------------------------
## NIST Cloud Model
Special publication 800-145 widely accepted standard that includes:
1. Definition
3. 5 Essential characteristics
4. 4 Deployment models
5. 3 Service models

### Definition
Cloud computing is a model for enabling convenient, on-demand network access to a shared pool of computing resources. Can be rapidly provisioned and released w/ minimal effort or interaction w/ service provider

### Characteristics of Cloud computing
1. **On-demand Self Service** - User can provision resources w/out needing interaction w/ service provider
2. **Broad network access** - Access to resources is available via multiple client platforms
3. **Resource pooling** - Service provider creates pools (multitenancy) to serve multiple consumers at once
4. **Rapid Elasticity** - Resources can be scaled to match demand
5. **Measured Service** - Resource usage is monitored and based on consumption (Pay as you go)

### Cloud Deployment Models

#### Public
- Cloud infrastructure provisioned for general public use.
- Hosted on premises of the Cloud Service Provider (CSP).
- Consumers access services via the Internet, paying metered usage charges.
- Resembles a utility model with cost-effectiveness through multitenancy and scalability.
- Enterprises lack control over data and equipment location, posing regulatory concerns.
- Examples: AWS, Google, Salesforce.

#### Private
- Exclusive use by a single organization with multiple consumers (departments, business units).
- Infrastructure owned and managed on-premise by the organization (cost-intensive).
- Requires in-house IT skills and expertise.
- Better control over data location and security, but limited scalability.
- Preferred for companies with existing data centers, developed IT infrastructure, or legal/compliance requirements.
- Note: Private cloud can be managed off-premise by a third party if the organization lacks expertise or for cost reasons.
#### Hybrid
- Combination of public and private (or other) cloud models.
- Unique entities bridged by standardized or proprietary technology for data and application portability.
- Management is more challenging but allows better alignment with business needs.
- Example: An organization with its own data center may use a public cloud for cost-effective data backup.
#### Community Cloud
- Infrastructure provisioned for use by multiple organizations with shared concerns (mission, security, policy, compliance).
- Owned, managed, and operated by the organizations or a third party.
- Can be on- or off-premise.
- Example: US Government agencies with similar security, privacy, and audit requirements can utilize a Community cloud.
### Cloud Service Models
Defines type of service the cloud provider is offering

#### Characteristics of IaaS (Infrastructure as a Service)
- Provision of hardware services.
- Reduces or eliminates capital costs and complexities of owning hardware (renting servers instead of buying).
- Cloud Service Provider (CSP) manages the infrastructure; client is responsible for OS and applications.
- Base layer of the cloud services stack, serving as the foundation for both PaaS and SaaS.
#### Characteristics of PaaS (Platform as a Service)
- Environment for low-cost and rapid development of new applications (e.g., web and mobile).
- Platforms accessed through an Application Programming Interface (API).
- Application developers have control over deployed applications but not the underlying cloud infrastructure (networks, servers, storage, OS).
- High risk of vendor lock-in.
***API*** -
- An API enables communication between software components.
- It defines how programmers can extend existing applications or build new ones.
- API requests are constructed using HTTP.
- JSON (JavaScript Object Notation) is commonly used for data format.
- Developers use HTTP requests to ask for JSON-formatted data.
- If correctly formatted as per API documentation, the server responds with JSON data.
![[Pasted image 20240116211543.png]]
#### Characteristics of SaaS (Software as a Service)
- Most popular service model.
- SaaS applications are cloud-native and multitenant.
- Prebuilt applications consumed without significant customization.
- Deployment, maintenance, patching, and updates handled by the Cloud Service Provider (CSP).
- Users use the software without controlling or managing the underlying infrastructure.
- Applications accessible anytime from anywhere using any client device (device and location independence).

### Shared Responsibility Model
![[Pasted image 20240116205551.png]]

## Considerations for Cloud Adoption

### Deployment Model
- **Startups:** Opt for cost-effective public cloud.
- **SMBs:** Use hybrid cloud for flexibility.
- **Enterprises:** Prefer private cloud for global control.

### Migrate or Retain?
- **Mission-critical:** On-premise or private cloud.
- **Regulatory Compliance:** Limits moving sensitive info to public cloud.
- **Legacy Applications:** Keep in-house for proprietary tech.
- **Dependencies:** Consider latency when migrating.

### Application Types
- **Non-critical Apps:** Suitable for public cloud (collaboration, productivity, development).

### Cloud Service Provider
- **Experience:** Check provider's history.
- **Meeting Requirements:** Ensure alignment with organizational needs.
- **Scalability and Transferability:** Assess ease of service management and application transfer.
- **Maintenance:** Verify provider communication on maintenance and downtime.
## Strategies for Application Migration

Organizations consider various strategies for application migration based on business needs. Some common approaches include:

### Rehosting (Lift-and-shift)
- Redeploy on-premise applications to cloud IaaS.
- Quick but lacks full cloud potential.
- Manual or automated tools like AWS VM Import/Export.

### Re-platforming
- Optimize without changing core architecture.
- Example: Migrate to managed services like Amazon RDS for reduced administrative overhead.

### Repurchasing
- Invest in cloud-native SaaS applications.
- Frees IT staff from maintenance.
- Examples: Move HR system to Workday, Outlook to Office 365.

### Rebuilding/Re-architecting
- Change core architecture (e.g., microservices or serverless).
- Goal: Increase performance, scale, agility, or add features.
- Most expensive option.
------------------------------------------------------