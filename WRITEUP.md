# Write-up Template

### Analyze, choose, and justify the appropriate resource option for deploying the app.

*For **both** a VM or App Service solution for the CMS app:*
- *Analyze costs, scalability, availability, and workflow*
- *Choose the appropriate solution (VM or App Service) for deploying the app*
- *Justify your choice*

### Assess app changes that would change your decision.

*Detail how the app and any other needs would have to change for you to change your decision in the last section.* 

# Loc Nguyen - Submission

### Detailed comparison between the options

| Characteristics 	| Virtual Machine (VM) 	| App Service 	|
|-	|-	|-	|
| Costs 	| Costs can be really low, especially when your requirements are low.  This is due to the flexibility of VM compared to App Service. 	| App Service's cheapest tier costs more than VM's cheapest tier. This is due to the "managed" nature of App Service, leading to less flexibility. 	|
| Scalability 	| VMs' upgrades are less intuitive and more cumbersome, sometimes involving redeployments. 	| App Service has better support for scalability, with inherent support for multiple deployments, and vertical scaling without redeployment. 	|
| Availability 	| From the [documentation](https://azure.microsoft.com/en-us/support/legal/sla/virtual-machines/v1_9/): </br> <ul> <li> For all Virtual Machines that have two or more instances  deployed across two or more Availability Zones in the same Azure region,  we guarantee you will have Virtual Machine Connectivity to at least  one instance at least 99.99% of the time.  </li> <li> For all Virtual Machines that have two or more instances deployed  in the same Availability Set or in the same Dedicated Host Group,  we guarantee you will have Virtual Machine Connectivity to at least  one instance at least 99.95% of the time.  </li> <li> For any Single Instance Virtual Machine using Premium SSD or  Ultra Disk for all Operating System Disks and Data Disks,  we guarantee you will have Virtual Machine Connectivity of at least 99.9%.  </li> <li> For any Single Instance Virtual Machine using Standard SSD Managed Disks  for Operating System Disk and Data Disks, we guarantee you  will have Virtual Machine Connectivity of at least 99.5%.  </li> <li> For any Single Instance Virtual Machine using Standard HDD Managed Disks  for Operating System Disks and Data Disks, we guarantee you will have  Virtual Machine Connectivity of at least 95%. </li> </ul> 	| From the [documentation](https://azure.microsoft.com/en-us/support/legal/sla/app-service/v1_4/): </br> <ul> <li> We guarantee that Apps running in a customer subscription will be available 99.95%  of the time.  </li> <li> No SLA is provided for Apps under either the Free or Shared tiers. </li> </ul> 	|
| Workflow 	| Due to more customizations, the workflow is more complicated  than App Service, both upfront and over time. 	| Due to its managed nature, App Service's workflow is less complicated. It takes less time & effort to set up and maintain. 	|

### Analyze, choose, and justify the resource option

The key reasons for why we would choose to deploy with a VM or with an App Service Solutions are:

- For a VM: managed hardware only (Infrastructure-as-a-Service)
    - more flexibility & customization of the tech stack
    - more customizations of hardware - in terms of specification, scaling, etc.
    - more customizations of OS - in terms of choice, specification, etc.

- For an App Service Solutions: fully managed solution (Platform-as-a-Service)
    - higher speed to deploy
    - vertical scaling of hardware
    - automatic updating of OS 

From the above comparison, for a short deployment such as this Udacity project, I would deploy via
an App Service instead of via a VM.

### Assess changes that would impact the decision

Here are some scenarios where it may make sense to deploy via a VM:
- When I want to lift-and-shift the app from Azure to other cloud vendors without major changes
- When I want more control over the OS-level resources; e.g. when I need to ensure a level of performance,
like in production, or to investigate the node when problems arise

In more details:
- For Costs: if I'm thinking about longer time or more performance in my compute,
then a VM would be more cost efficient over the long term.
- For Scalability: if I'm thinking about more complex combinations of compute
capacity, I'll switch over to a VM.
- For Availability: if I'm thinking about stronger SLA terms, I'll switch 
over to a VM.
- For Workflow: if I'm comfortable making the customizations necessary to
get exactly what I need, I'll switch over to a VM.