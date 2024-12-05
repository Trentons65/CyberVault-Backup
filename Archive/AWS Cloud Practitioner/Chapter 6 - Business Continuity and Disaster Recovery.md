## Terminology
- **Disaster** - Event that may cause partial or complete disruption to business; disasters can happen from human actions, technical failures or natural reasons
- **Failover** - Process of moving operations over to a secondary app/site in the event the primary goes down.
- **Failback** - Process of restoring operations over to the primary app/site following repairs.
- **Resource saturation** - Condition where a resource has more load than it can handle

## Business Continuity V Disaster Recovery

***Business Continuity*** - 
- Set of processes and procedures that enable an org to continue essential business functions in the event of a disruptive event
***Disaster Recovery*** - 
- Focus on restoring business operations to normal following an event
- Misconfigurations, power outages, cyber attacks and natural disasters are common reasons that lead to disasters
- Subset of Business Continuity planning

These plans must be updated and tested regularly
Regulated industries (Health, Finance, etc) have higher legally mandated standards for these plans  

## (Step 1) Business Impact Analysis and Risk Assessment

***Business Impact Analysis***
- Enables orgs to evaluate the potential impact of a disaster on apps and services. The impact can be measured in loss of revenue, reputation, and compliance.
- Applications are grouped into three tiers: Mission-critical (Tier 1), Important (Tier 2), and Non-essential (Tier 3)

***Risk Assessment***
- Helps orgs evaluate different disruptive conditions and their level of risk. 
- Level of risk = Likelihood x consequence (Cost of impact/recovery)

### Metrics
**Recovery Time Objective (RTO)**
Maximum tolerable time between a service outage and restoration following a disaster
- Acceptable amount of downtime

**Recovery Point Objective (RPO)**
Maximum tolerable data loss from service outage following a disaster
- Frequency of data backups needed

Common RTO and RPO numbers for apps:
- Tier 1 - RTO (15 min) & RPO (~0)
- Tier 2 - RTO (4 hr) & RPO (2 hr) 
- Tier 3 - RTO (8-24 hr) & RPO (4 hr)

### Resiliency Planning
