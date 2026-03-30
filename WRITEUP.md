# Write-up Template

### Analyze, choose, and justify the appropriate resource option for deploying the app.

**VMs**
- **Cost:** Generally more expensive compared to App Service. But, lower up-front cost compared to traditional on-premises server hardware procurement. Billing is very granular and based on many different aspects of the VM, and can be harder to predict and manage.
- **Scalability:** Virtual Machine Scale Sets and Load Balancers. Flexible Types/sizes of VMs to choose from. More control over scaling, but requires more engineering effort.
- **Availability:** ability to group multiple VMs for high availability; design availability sets and zones, and load balancers. More complex to implement.
- **Workflow:** Full access and control of the VMs. More Labor intensive, configuring/updating/maintaining the VMs and the OS. CI/CD more complex because has to include infrastructure aspects

**App Service**
- **Cost:** Flexibility of cost with ability to choose different tiers of hardware allocation. With light workloads can save on cost compared to VMs. App Service Plans simplify pricing by comparison.
- **Scalability:** Vertical scaling to increase resources to the App (like vCPUs or RAM); adjust using the service plan tier. Horizontal scaling to increase the number of VM instances powering the App. Scaling is built-in and handled more transparently.
- **Availability:** High availability built-in and default
- **Workflow:** Supports Continuous Deployment, with native Github/ADO integration. Focus on the application, not the infrastructure.


**Choice:** App Service  
**Reason:** Since this is a simple modern web app, which does not require running legacy or complex software, I think App Service is the right choice. This lowers the complexity of configuration and maintenance by quite a bit, which also makes it cheaper to implement. It is generally less expensive all-around, especially for lighter workloads. I don't see a need to have a high degree of control of the underlying VM and OS, so I think it is better for that handled by Azure, so I can focus mostly on just the application code.


### Assess app changes that would change your decision.

**Reasons I might want to switch to Azure VMs:**  
If the usage of the app becomes very high, it might make sense to switch to a VM module to handle the higher workload. Particularly if the workload starts to demand more than 14GB of memory of more than 4 vCPUs. It would also become necessary if the project needed to switch to a programming language that is not supported by App Service.
