## Terminology
- **Metadata** - Provides information about stored data (May include file owner, creation, type, size, etc)
- **Digital Transformation** - Integrating tech in all areas of business
- **Bytes** - Storage capacity measurement
- **Data archiving** - Identifying and storing data long term for compliance or regulatory reasons
- **High Availability (HA)** - System ability to be available without failure (99.99% availibility is 00:52:35 out of the year)
- **Schema** - Structure or org of data w/in relational database table
- **Sharding** - Partitioning a large database into smaller portions called shards

## Storage Types

### Block Storage
- Files broken into data (Blocks)
- No shared metadata
- Traditional method 
- Provides high performance required for transactional databases

### File Storage
- Hierarchical storage organized with directories
- Files tagged w/ meta data & can be retrieved
- Easier & less expensive than block storage
- Traditional method ideal for file sharing

### Object Storage
- Files stored in flat space with unique ID
- Allows object retrieval w/out physical location knowledge
- Supports advanced metadata
- ideal for unstructured data
## Storage in AWS cloud

### Examples
**Amazon Elastic Block Store (EBS)**
- Block volumes can be created an dattached to EC2 instances
- Persistent storage
- Volume types: SSD & HDD
- Used as storage volumes for EC2 instances, database workloads
- https://aws.amazon.com/ebs/
**Amazon Elastic File System (EFS)**
- Used with EC2 instances
- https://aws.amazon.com/efs/
**Amazon Simple Storage Service (S3)**
- Object storage that has 99.99% durability
- No limit on type or amount data 
- Data stored as objects in logical containers called buckets
- Single object can be up to 5 TB in size
- Used for static website hosting, data backups for disaster recovery (DR)
- https://aws.amazon.com/s3/

### Storage Network Elements
**Hosts** 
- Computer/ server that accesses storage resources
- Host may use NIC or Host Bus Adapter (HBA) to interface with network
**Storage Systems**
- Stores primary and backup data
- Variety of storage systems available (HDDs, SSDs, optical Drives, etc)
**Switches**
- Connects multiple devices & facilitates flow of frames

## RAID
### Techniques
- **Striping** - Spreading data across multiple drives to use in parallel
- **Mirroring** - Same data stored on two different disks (Two copies of data)
- **Parity** - Ensures protection w/out maintaining full set of dupe data, computed as combination of data bits spread between multiple drives
### RAID Levels
![[Pasted image 20240119001459.png]]
**RAID 0 (Striping)** 
- Uses two disks and stripes between (Highest speed)
**RAID 1 (Mirroring)**
- Stores identical copies of data on two drives for redundancy
- Requires twice the storage
**RAID 5 (Striping w/ Distributed Parity)**
- Stripes data across disks in set
- Uses parity for data reconstruction
- Requires three drives
**RAID 6 (Striping w/ Double Distributed Parity)**
- Builds on RAID 5
- Stores double parity
- Can recover from loss of two drives
**RAID 10 (RAID 1 + 0 (Striping & Mirroring))**
- Nested level
- Takes mirrored sets w/ data striped between
- High read & write
- Needs double # Drives
## Storage Tiering

**Tier 1** - Mission-critical data (SSDs)
**Tier 2** - Data from business applications w/ fast response time ( Customer Relationship Management (CRM), Enterprise Resource Planning (ERP), email on HDDs)
**Tier 3** - Older emails/ data on completed transactions
**Tier 4** - Rarely used/ archived data (Large # of low-cost magnetic drives)
https://aws.amazon.com/s3/storage-classes/

## Storage Tech

### Directly Attached Storage (DAS)
- Comprised of host connected to one/ more drvies
- Simple to install
- Low cost
- Bound to host machine
### Network Attached Storage (NAS)
- File-level storage attached to LAN
- UNIX/ LINUX have built-in support for NAS via NFS
- Low cost
- Good performance
### Storage Area Networks (SAN)
- Block-level storage
- Dedicated network of servers & storage
- Seperate from LAN & built on protocol like Fiber
- Hosts require HBA for connection
- High bandwidth, availability, etc
- Requires specialized skills

### Storage Replication

**Regional Replication (w/in geo region)**
- Primary & secondary site seperated geographically
- Each site powered by different suppliers
- inter-connected via high-speed links

**Multiregional Replication (multiple regions)
- Expands replication to sites across globe

**Synchronous Replication**
- Writes data to local store w/ immediate replicaion
- Application not informed of data write until all operations completed
- Requires high-speed, low-latency connections between sites
- Replication between AZs w/in region to ensure High Availability (HA)
**Asynchronous Replication**
- Stores data locally and reports to application
- Not all members of replica set may be fully consistent
- AWS regions are examples of this connection used in its backbone

## Databases

***Relational Databases***
- Invented in 1970s
- Data is organized in tabular format w/ columns & rows
- Row - Data item
- Column- Properties/ attributes of data
- SQL commands used for storing & retrieving data

***Non-relational Databases***
- Invented in 2009
- Schema-less/ flexible schema
- Suitable for all data (un/semi/structured)
- NoSQL databases (Not only - support for other query mechanisms)
**Key-value** - Data stored in form of key/ vaule pairs. Key - unique ID
**Document** - Info stored in JSON structures. Easy read/write
**Graph** - Uses nodes (Data entities) & edges (Relations between entities) very flexible
**Wide-column** - Structure of rows/ columns w/ flexible schema

## ACID compliance

***A***tomocity, ***C***onsistency, ***I***solation, and ***D***urability

