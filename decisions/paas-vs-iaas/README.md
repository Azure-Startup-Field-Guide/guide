# Managed platform or virtual machines?

> **Default for a new startup workload:** use a managed application platform
> unless a concrete requirement needs guest operating-system control.

Azure Virtual Machines are not a legacy-only option. They are the right choice
for some commercial software, specialized compute, migration, and
infrastructure workloads. The tradeoff is that the startup owns more of the
operating system and availability model.

## Start with a managed platform when

- the workload is a standard web application, API, event handler, or container;
- the product does not differentiate through operating-system management;
- built-in deployment, scaling, patching, and health features meet the
  requirements;
- scale-to-zero or consumption behavior matters; or
- the team needs to preserve engineering capacity for product work.

Evaluate App Service, Azure Functions, or Azure Container Apps before accepting
VM operations. Evaluate AKS when Kubernetes requirements are explicit.

## Choose Azure Virtual Machines when

- software requires a supported VM image or specific operating system;
- the workload needs kernel, driver, agent, appliance, or host-level control;
- a migration cannot yet be refactored to a managed platform;
- GPU, HPC, confidential, storage-optimized, or other specialized VM hardware
  is required;
- licensing or vendor support requires a VM deployment; or
- the application depends on protocols or runtime behavior unavailable from the
  managed alternatives.

## Single VM or Virtual Machine Scale Sets?

| Requirement | Starting point |
| --- | --- |
| One unique server or administrative workload | Single VM |
| Identically configured stateless fleet | Virtual Machine Scale Sets |
| Metric- or schedule-based horizontal scaling | Virtual Machine Scale Sets |
| Rolling fleet updates and health-based repair | Virtual Machine Scale Sets |
| Different configuration on every machine | Individual VMs or redesign |

A production-critical service on one VM has an explicit availability risk.
Accept and document that risk, or design redundancy that meets the workload's
target.

## The responsibility you accept

With IaaS, the startup owns:

- image selection and lifecycle;
- guest operating-system configuration and patching;
- installed software and dependency vulnerabilities;
- VM availability, scaling, and health;
- disk, backup, restore, and disaster-recovery configuration;
- management access and network exposure;
- monitoring and incident response; and
- rightsizing, licensing, idle capacity, and shutdown behavior.

Azure still operates the physical datacenter, hardware, host infrastructure,
and the Azure control plane according to the cloud shared-responsibility model.

## Do not choose VMs only because

- the team already knows how to SSH or use RDP;
- the VM hourly price looks lower than a managed service;
- a container can run on a manually managed VM;
- future customization might require host access; or
- one large machine postpones designing a scaling model.

Compare the full operating cost, including people, storage, networking, backup,
security, availability, and recovery.

## Revisit the decision when

Re-evaluate IaaS when patching, fleet inconsistency, incidents, or capacity
management slows product delivery, or when a managed service adds the missing
capability. Re-evaluate PaaS when a verified host-level or vendor requirement
cannot be met within its supported boundary.

## Official sources

- [Choose an Azure compute service](https://learn.microsoft.com/en-us/azure/architecture/guide/technology-choices/compute-decision-tree)
- [Azure Virtual Machines baseline architecture](https://learn.microsoft.com/en-us/azure/architecture/virtual-machines/baseline)
- [Well-Architected guidance for virtual machines and scale sets](https://learn.microsoft.com/en-us/azure/well-architected/service-guides/virtual-machines)
- [Virtual Machine Scale Sets overview](https://learn.microsoft.com/en-us/azure/virtual-machine-scale-sets/overview)
- [Shared responsibility in the cloud](https://learn.microsoft.com/en-us/azure/security/fundamentals/shared-responsibility)

[Back to technology decisions](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/decisions)
