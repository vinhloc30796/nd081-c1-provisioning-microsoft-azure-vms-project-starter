# Write-up Template

### Analyze, choose, and justify the appropriate resource option for deploying the app.

*For **both** a VM or App Service solution for the CMS app:*
- *Analyze costs, scalability, availability, and workflow*
- *Choose the appropriate solution (VM or App Service) for deploying the app*
- *Justify your choice*

### Assess app changes that would change your decision.

*Detail how the app and any other needs would have to change for you to change your decision in the last section.* 

# Loc Nguyen - Submission

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