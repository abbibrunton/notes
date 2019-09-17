# Cloud enabling technologies

<!--TOC_START-->
### Contents
- [Overview](#overview)
	- [Fast wide area networks](#fast-wide-area-networks)
	- [Disaster recovery](#disaster-recovery)
	- [Powerful, inexpensive server computers](#powerful-inexpensive-server-computers)
	- [Benefits of virtualization](#benefits-of-virtualization)
	- [Virtualization VS Multi-Tenanting](#virtualization-vs-multitenanting)
	- [Containers](#containers)

<!--TOC_END-->
## Overview
In this module you will learn what technologies allow cloud services to work.

### Fast wide area networks

In order to get the location-independence of the cloud, you need a fast wide-area network. Otherwise the users and the 
servers all need to be physically close, or connected by a dedicated network.

With a fast, wide-area network, we can support users in many different locations, and we can support high-availability 
and disaster recovery solutions that would previously have been unworkable.

### Disaster recovery

Disaster recovery is the strategy of backing up and restore that maintains the electronic records of the copies in 
cloud environment. This is important if you want to be prepared for a man-made or a natural catastrophe.

Cloud providers have these strategies in place for it's clients, of course that comes as an additional cost. You could 
be charged based on bandwidth, storage space or pay-per-use.

You could implement these strategies, but before implementation there are a few things to consider:
* Is the bandwidth fast enough to move the data between primary site and the cloud
* Can the data be encrypted in flight

### Powerful, inexpensive server computers

In order to get the pool of interchangeable resources required by a cloud, we need to be able to buy lots of servers 
and configurable them, and they need to be reasonably powerful.

Building a data centre is a specialist skill, and there are standards and bodies of knowledge related to it.

Data centres are becoming increasingly efficient and cheap, to the extent that it is possible to get a containerised 
`modular data centre` shipped to you.

When choosing a cloud provider, they will probably be able to document the standards
to which their data centre adheres.

TIA-942 and Uptime Institute are the two best-known examples.

### Benefits of virtualization

Benefits can include:
* Elasticity/scalability
* Resource pooling on common infrastructure
* More efficient use of physical resources
* Granularity of monitoring and pricing
* No leakage of data from one guest to another

`Noisy neighbours` – one guest using all the bandwidth/CPU/etc and the servers all need to be physically close, or 
connected by a dedicated network.

### Virtualization VS Multi-Tenanting

Virtualization is a type of multi-tenanting, in that it allows multiple users to share a single physical resource. It 
does this by separating the users at the hypervisor level.
* Namely, every customer has their own virtual machine, from the OS up

However, when we use the term multi-tenanting, we usually use it to refer to application-level separation of users 
within a single virtual machine.
* The virtual machine is hared by many customers
* Isolation is enforced by the application

Software-as-a-service is frequently multi-tenant, for Cloud services such as Gmail
* `My webmail provider almost certainly uses virtualisation, but when I log on, I
  don’t get a virtual machine all to myself. Instead, the application prevents me
  from seeing other users email`
  
### Containers

Subdivide a single virtual machine, which results in less overhead than creating multiple VMs:
* Does not require hardware support or emulation
* Containers are isolated at the user (as opposed to kernel) level

Docker is the best-known container technology (docker.com).

Package an application and its dependencies as a unit.
* Run on any Linux server: flexible and portable
* Windows support expected soon
* Integrated into many other cloud products

### Task

**List all the cloud enabling technologies you have learned about in this module**
<details>
<summary>Show Solution</summary>
* Fast wide area networks
* Disaster recovery
* Powerful, inexpensive server computers
* Benefits of virtualization
* Virtualization VS Multi-Tenanting
* Containers
</details>

**Can you implement disaster recovery for on-premises hosting?**
<details>
<summary>Show Solution</summary>
Yes, with appropriate configuration. Additionally security, and infrastructure has to support it.
</details>

**List out the benefits of virtualization**
<details>
<summary>Show Solution</summary>
* Elasticity/scalability
* Resource pooling on common infrastructure
* More efficient use of physical resources
* Granularity of monitoring and pricing
* No leakage of data from one guest to another
</details>