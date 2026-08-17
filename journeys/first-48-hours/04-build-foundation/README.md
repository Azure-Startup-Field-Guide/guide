# 4. Build the smallest foundation that can grow

> **Verified in the August 16, 2026 repository audit against current official
> Microsoft documentation.**

## The recommendation

Choose the simplest managed platform that satisfies a concrete requirement.
Do not begin with Kubernetes, private networking, or an enterprise-scale
landing zone solely because you expect the company to grow.

![Decision tree for choosing Azure Virtual Machines, Azure Kubernetes Service, Container Apps, Functions, or App Service](https://raw.githubusercontent.com/Azure-Startup-Field-Guide/guide/main/static/img/platform-choice.svg)

## Match the workload to the platform

| Workload need | Start by evaluating |
| --- | --- |
| Guest OS, driver, appliance, specialized hardware, or VM-only software | Azure Virtual Machines or Virtual Machine Scale Sets |
| Web application or HTTP API | Azure App Service |
| Event-driven task or scheduled function | Azure Functions |
| Containerized service without direct Kubernetes requirements | Azure Container Apps |
| Kubernetes API, operators, specialized scheduling, or an existing Kubernetes platform | Azure Kubernetes Service |
| Relational application data | Azure Database for PostgreSQL, Azure SQL Database |
| Globally distributed NoSQL data | Azure Cosmos DB |
| Secrets, keys, and certificates | Azure Key Vault |
| Application telemetry | Azure Monitor and Application Insights |

This is a decision sequence, not a universal architecture. Validate service,
region, quota, compliance, and workload requirements before committing.

## When IaaS is the deliberate choice

Virtual machines belong in the startup foundation when the workload needs guest
operating-system control that a managed platform does not provide. Common
examples include:

- commercial or third-party software certified for a specific VM image;
- kernel, driver, agent, network-appliance, or host-level requirements;
- lift-and-shift migration that cannot yet be refactored;
- GPU, HPC, confidential, storage-optimized, or other specialized compute;
- vendor licensing or support tied to a virtual-machine deployment; and
- protocols or runtime behavior unavailable from App Service, Functions, or
  Container Apps.

For a repeatable, identically configured fleet, evaluate
[Virtual Machine Scale Sets](https://learn.microsoft.com/en-us/azure/virtual-machine-scale-sets/overview)
instead of creating independent VMs by hand. A single VM can fit a unique
server, development environment, or intentionally nonredundant workload, but it
is an explicit availability risk for a production-critical user flow.

Read the full
[managed platform or virtual machines decision](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/decisions/paas-vs-iaas)
before selecting IaaS.

## Minimum IaaS baseline

Choosing VMs means the startup owns the guest operating system and more of the
availability model. At minimum:

1. deploy the VM or scale set through infrastructure as code;
2. use a controlled image and document image ownership;
3. define guest patching, vulnerability, and dependency responsibilities;
4. use managed identity where the workload accesses Azure resources;
5. minimize public management exposure and protect administrative access;
6. configure logs, metrics, health, and actionable alerts;
7. define disk, backup, restore, RTO, and RPO behavior;
8. design availability zones, scale sets, or accepted downtime from the
   workload target; and
9. track VM, disk, networking, licensing, backup, and idle-capacity cost.

Do not choose VMs only because the team is familiar with SSH or RDP, because the
hourly compute price looks lower, or because host-level control might be useful
later. Compare the complete operating responsibility.

## Use infrastructure as code from the first shared environment

The first production-like environment should be reproducible. Prefer:

- Azure Verified Modules when a suitable module exists;
- Bicep or Terraform checked into the application or platform repository;
- workload identity federation for CI/CD rather than stored client secrets;
- separate development and production boundaries appropriate to the team's
  risk; and
- a deployment path that includes telemetry and rollback.

Azure Developer CLI (`azd`) can connect application code, infrastructure, and
deployment workflows for supported templates. Review a template before using
it; a deploy button is not an architecture review.

## Decide how much landing zone you need

For an opinionated startup-sized baseline, review the community-maintained
[Startup-Scale Landing Zone](https://startupscalelanding.zone/). For
enterprise-scale governance and complex organizational requirements, use the
official [Azure landing zone](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/landing-zone/)
guidance.

Choose based on current constraints and known near-term requirements. Document
the conditions that will trigger a move to a more complex platform.

## Production-readiness questions

- Can another engineer deploy the environment from source control?
- Are application identities using least privilege?
- Are secrets outside code and deployment logs?
- Can you identify the owner and cost of each resource?
- Will a failure produce an actionable signal?
- Can you restore data and roll back a release?
- If the workload uses VMs, who owns images, guest patching, access, and
  availability?
- What requirement would force the next architecture change?

## Next

Read
[5. Get the right help](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/journeys/first-48-hours/05-get-help)
before you need it.

## Official sources

- [Platform Foundations for Startups](https://learn.microsoft.com/en-us/startups/build/infra/platform-foundations)
- [Choose an Azure compute service](https://learn.microsoft.com/en-us/azure/architecture/guide/technology-choices/compute-decision-tree)
- [Azure Virtual Machines baseline architecture](https://learn.microsoft.com/en-us/azure/architecture/virtual-machines/baseline)
- [Well-Architected guidance for virtual machines and scale sets](https://learn.microsoft.com/en-us/azure/well-architected/service-guides/virtual-machines)
- [Azure Developer CLI overview](https://learn.microsoft.com/en-us/azure/developer/azure-developer-cli/overview)
- [Azure Verified Modules](https://aka.ms/AVM)
- [Azure Well-Architected Framework](https://learn.microsoft.com/en-us/azure/well-architected/)
- [Azure landing zones](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/landing-zone/)
