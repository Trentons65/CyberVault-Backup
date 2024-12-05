## Terminology
- **BIOS** - (Basic Input/Output System) Allows computer/ server to boot after being powered on
- **UEFI** - (Unified Extensive Firmware Interface) Replaced BIOS since 2007. Has more modern features and better boot time
- **Workload** - Application/ service that comsumes resources
- **Multicore processor** Processor that has 2 or more proccessing units. Mor ecores is often preferred over higher speed processors
- **Hyperthreading** - Intel tech that splits each core into 2 logical cores
- **Overcommitment/ Oversubscribing/ Overprovisioning** - Ability to allocate more virtual resources than is physically available on host

## Server Virtualization

Virtualization allows a physical server to run multiple VMs concurrently
- Each VM contains an OS and an application
- Hardware-Assisted Virtualization (HAV) is built into the processor and must be enabled in BIOS/UEFI

### Hypervisors

Hypervisors are low-level programs that manage virtual infrastructure
Host - Physical server that runs the hypervisor
Guests - VM running on the host
Virtualization is abstraction of physical hardware

***Type 1 Hypervisor*** 
- Runs directly on the hosts hardware ("Bare-metal" hypervisor)
- Very efficient
- Inherent security 
- Scalable and utilized in production environments

***Type 2 Hypervisor***
- Runs on top of a host OS ("Hosted" hypervisor)
- Cannot boot until the OS has loaded
- Vulnerabilities in host may impact security
- Great for personal/ development purposes

## Components of Virtualization

### CPU
Processing power is assigned to VM as virtual CPUs from pCPUs
- With hyperthreading - each logical core on host = pCPU (physical CPU)
- Without hyperthreading - each physical core on host single CPU

***Overcommitment***
- Create VMs starting with just one vCPU 
- Safe to maintain overcommitment ration of 3:1

***Metrics to monitor***
**On the VM** - CPU utilization
**On the host** - CPU read (Below 5%) and utilization

### Memory
Safe to maintain overcommitment ratio of 1.25:1
**How to maximize** - 
- Memory ballooning - Requests memory resources form other VMs, places all loaned memory into balloon made available to VM when needed, and VMs can make decisions about processes they can swap
- Transparent Page Sharing (TPS) - Combines identical memory in host to maintain single copy and has imperceptible impact on performance
- Memory compression - Memory is compressed and placed into a cache and retrieved when needed (Has some impact on performance)
- Swapping or paging to disk - Insufficient memory => hypervisor dumps data from mem to page file (Slow performance/ used as a last resort)
***Metrics to monitor***
**On the host** -  Watch actual amount of RAM in use by VMs as # => 100% => add more RAM to physical server/ migrate to different host

### Storage

