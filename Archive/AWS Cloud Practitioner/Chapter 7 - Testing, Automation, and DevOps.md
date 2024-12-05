
## Baselines and Resource Monitoring

Monitor cloud infrastructure & perform tests after cloud adoption to ensure systems are optimal

**Establish a baseline**
*Defines "Normal activity" in network*
Considerations
- How many data samples to collect?
- What should the sampling interval be?

Threshold levels should be defined to generate alerts for deviations from baseline. Alleviates burden from admins.

### Performance Metrics
***CloudWatch*** - AWS monitoring service

**Compute** - 
- CPU utilization for host & VM
- CPU ready
- CPU wait time

**Memory** - 
- Paged pool (Amount of data paged to disk when mem shortage occurs)
- Page faults (# times data is fetched from disk over mem) High # indicates mem should be upgraded
- Memory usage

**Storage** - 
- Read IOPS
- Write IOPS

**Network** - 
- Average & peak bytes sent/received by physical NIC, virtual NIC, & virtual switch

## Application testing in the Cloud

Two main categories of app testing:

1. ***Functional Testing*** - 
	- App features are tested to see if they solve business problems they were designed for
	- QA testers apply specifications against test cases & analyze the outcomes
	- Unit, smoke, sanity, integration, & user acceptance testing are all examples
	- Proceeds Non-functional testing
2. ***Non-functional testing*** -
	- **Performance testing** - determines responsiveness, throughput, scalability
		- Types- 
			- Load test - Tests levels of utilization
			- Stress test - Tests beyond normal cap & to eventually break
			- Spike test - Tests sudden bursts of traffic
			- Volume test - Tests large volumes of data
			- Endurance test - Tests sustainability under continuous load
	- **Latency testing** - Measures time between request & response
	- **Security testing** - Tests access control, data integrity, etc (Pen testing is important in multi-tenant enviroments)
	- **Compatibility testing** - Tests performance across platforms

## Automation & Orchestration

***Automation*** - Running single task w/out direct interaction
- Uses scripts (Python, JavaScript, PowerShell)
- Goal built-into the script
- EX: launching/terminating VMs

***Orchestration*** - Automating entire IT process/ workflow of multiple tasks
- Complex coordination between tasks
- May require decision making based on output
- EX: lifecycle management of containers

***Benefits*** - 
- Eliminates errors
- Enables quick & consistent task completion
- Reduces costs
- Security practices can be automated

## Infrastructure as Code (IaC)

- Allows automatic provisioning of entire IT infrastructure from config files
- Allows deployment of multiple environments in CI/CD pipeline

![[Pasted image 20240207143633.png]]

### Software Development Lifecycle (SDLC)

**Waterfall Model** - 
![[Pasted image 20240207143914.png]]
- Rigid
- Alternations are only possible in early stages
- Not suitable for long-term projects

**Agile Model** - 
Modern approach that is more iterative
- Project divided into sprints
- Deliverables planned at beginning of sprints
- Outcomes are reviewed and future goals decided after each sprint
- Requirements and solutions can evolve improving customer satisfaction

## DevOps

Combination of Development & Operations teams
Business aproach based on agile principles crucial for rapid innovation
You can add security for DevSecOps 
Cloud computing is considered an enabler of DevOps

### CI/CD Pipeline DevOps

***Continuous Integration*** - 
- DevOps team maintains code repository 
- CI service auto builds & runs tests on code changes for immediate feedback

***Continuous Delivery*** - 
- CD deploys all code changes to a testing environment
- Tests are performed on software & APIs through automated processes (U/I testing, integration testing, etc)
- Following successful tests, updates are pushed into production
- Continuous deployment adds automatic pushing of updates
- Choice between Delivery/ Deployment depends on the business

![[Pasted image 20240207195846.png]]

Other DevOps Practices

**Microservices-based architecture** - 
- Breaks apps into sets of services each built around a specific purpose 
- Communication is achieved via APIs
- Adds flexibility and speed

**Infrastructure as Code (IaC)** - 
- Automated deployment of development, testing, & production environments
- Changes are implemented easily through patches/ versions

**Monitoring & Logging** - 
- 24/7 availability of apps necessitates constant monitoring and logging
- Provides insight into impact users receive from updates

**Communication & Collaboration** - 
- Infomation sharing and collaboration is key to DevOps
- Enables companies to align closely with goals

### Benefits of CI/CD
Allows agile development with frequent software updates to achieve customer satisfaction
Automation ensures consistent task completion and speeds up repetitive tasks: also freeing individuals to focus on more creative tasks, problem solving, etc


***Deployment Strategies***

**In-place deployment** - 
- Cheapest
- Experience downtime between instance deployment

**Rolling deployment** - 
- Devs change software instance by instance & sequentially

**Blue/Green deployment** - 
- Utilizes two environments Blue (Production) & Green (Testing)
- 

**Canary deployment** - 









