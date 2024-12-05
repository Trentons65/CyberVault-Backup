## Authorization

Authorization confirms whether an entity has sufficient permissions or privileges to execute some action on a system. This process ensures that only trusted entities are able to perform the action.

If the entity has sufficient permissions or privileges to perform the action, then the action is carried out. If the entity doesn't have sufficient permissions or privileges, then an appropriate error message is returned.

Note that while authentication and authorization are distinct operations, they're closely related. Before you can determine an entity's authorization, you need to authenticate the entity to ensure that it is who it claims to be.

#### Entities

An entity is any object that attempts to perform an action on a system. This is typically a human, but it can also include computers, services, or even other objects such as vehicles.

#### Roles

Typically, an entity in a system is assigned one or more roles. Roles are a collection of privileges or permissions that define what actions an entity performs. This is useful when you have multiple entities that perform the same actions (such as account administration).

## Impact

Since the process of authorization ensures only those with the appropriate permissions or privileges can carry out a task, missing this check or incorrectly implementing it could allow entities who otherwise should not be allowed to carry out the action to be able to do so. This could result in the modification or loss of data to an unauthorized entity.

## Real-world example

In October 2024, Fidelity Investments [reported a data breach](https://www.securityweek.com/fidelity-investments-data-breach-impacts-77000-customers/) impacting 77,000 of its customers.

### Cause

The attackers used two customer accounts that they had created to access images of documents pertaining to approximately 77,000 other customers.

While details are limited, the attacker's use of the two customer accounts indicates that authentication was being performed. The fact that they were then able to access the data for other customers indicates a failure in authorization.

### Impact

- Private data for 77,000 customers was disclosed to unauthorized parties. Depending on the nature of the data, it could be used in a number of ways that would negatively impact those customers financially.
- Fidelity Investment's reputation may be damaged, especially as this is the second breach reported in a year.
- While the full impact of this breach isn't currently known, the estimated losses for the previous breach, which affected 28,000 customers, was $30 million.