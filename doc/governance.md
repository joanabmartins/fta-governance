# Azure Governance

Thank you so much for your time this week.

Here are some extra links about the topics that we discussed.

### [Azure CAF](https://aka.ms/caf) 

*	We started our session discussing Cloud Adoption Framework. We talked about the different stages of cloud adoption. 

*	If you are already engaged with FTA, we expect that you are already in the [Ready phase](https://docs.microsoft.com/en-us/azure/cloud-adoption-framework/ready/enterprise-scale/design-guidelines), where you can find prescriptive best practices to help your Azure implementation.

<br><br>

### [Azure Hierarchy](https://docs.microsoft.com/en-us/azure/cloud-adoption-framework/decision-guides/subscriptions/) 
*	We discussed the azure governance hierarchy: [management groups](https://docs.microsoft.com/en-us/azure/governance/management-groups/overview), subscriptions and resource groups. These features make it possible to granularly or broadly (as you wish) give access to azure resources, create policies and control costs. 

*	Subscriptions are also boundaries for resource connection. You can’t have VMs in separate subscriptions connected to the same VNet. You will need to have a vnet for each subscription and if you need communication between them you will need to do an extra configuration ([VNet peering](https://docs.microsoft.com/en-us/azure/virtual-network/virtual-network-peering-overview)) that will also reflect in extra costs.

* All the resources on Azure (vms, disks, app services,..) must be linked to one and only one resource group and subscription.

* We usually tend to advice to follow the simplest design, always being aware of the [subscription limits](https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/azure-subscription-service-limits). 

### [Naming Convention](https://docs.microsoft.com/en-us/azure/cloud-adoption-framework/ready/azure-best-practices/resource-naming)
* It’s important to have a naming convention from the start as you are not able to change names on Azure resources.

### [Policies](https://docs.microsoft.com/en-us/azure/governance/policy/overview)
* We discussed how you can create rules (policies) on Azure to comply your subscription users to follow your requirements. 

* You can use policies with different [effects](https://docs.microsoft.com/en-us/azure/governance/policy/concepts/effects) (deny, audit, deployifnotexists..).

* Policies are most commonly used for cost management (for example, block premium and expensive SKUs), for resource consistency (for example, to enforce naming conventions and deployment locations) and for security (all subscriptions come already with a group of policies assigned by [Security Center](https://docs.microsoft.com/en-us/azure/security-center/security-center-introduction) based on [Azure Security Benchmark](https://docs.microsoft.com/en-us/azure/security-center/recommendations-reference)), 

### [Tags](https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/tag-resources?tabs=json)
* With tags you can add metadata to your resource to logically organize them.
* You can automatically add tags through policies. 
* You can also use tags to filter your azure invoice and understand how much a value with the tag Cost Center: 1 or Department: Finance costs. 


### [Role Based Access Control (RBAC)](https://docs.microsoft.com/en-us/azure/role-based-access-control/overview)
* For access control we talked about the RBAC.

* You have a lot of [built-in roles](https://docs.microsoft.com/en-us/azure/role-based-access-control/built-in-roles) that you can [assign](https://docs.microsoft.com/en-us/azure/role-based-access-control/role-assignments-portal?tabs=current) to user or group on Azure AD to a scope of a resource, resource group, subscription or management group

* You can also [create your own roles](https://docs.microsoft.com/en-us/azure/role-based-access-control/custom-roles) in JSON and assign them the same way.

### [Locks](https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/lock-resources?tabs=json)
* You should lock a subscription, resource group, or resource to prevent other users in your organization from accidentally deleting or modifying critical resources.

### [Advisor](https://docs.microsoft.com/en-us/azure/advisor/advisor-overview)
* Use Azure Advisor as a free tool to help you follow best practices to optimize your Azure deployments. 

* It analyzes your resource configuration and recommends solutions that can help you improve the cost effectiveness, performance, Reliability (formerly called High availability), and security of your Azure resources.
