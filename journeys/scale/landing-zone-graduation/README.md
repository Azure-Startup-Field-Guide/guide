# Graduate to Azure landing zones

> **Default:** keep the startup foundation small, but adopt Azure landing-zone
> design areas as the operating model grows.

An Azure landing zone is an architecture and operating model for application
subscriptions and shared platform capabilities. It is not only a deployment
template.

## Graduation triggers

Evaluate an Azure landing-zone implementation when:

- multiple workloads or teams need consistent subscription vending;
- policy, identity, connectivity, management, or security becomes shared;
- enterprise or regulated customers require stronger governance evidence;
- multiple regions or business units need a common operating model;
- platform and application ownership must be separated; or
- exceptions and manual setup create repeated risk.

Do not use a hard subscription count as the trigger. Use operating complexity
and ownership boundaries.

## Design the target operating model

1. Define platform and application-team responsibilities.
2. Review the Azure landing-zone design areas.
3. Choose management-group and subscription boundaries.
4. Define identity, policy, connectivity, management, security, and cost
   baselines.
5. Decide which shared platform services are actually needed.
6. Select a Microsoft-provided accelerator or compose Azure Verified Modules.
7. Pilot with one application landing zone.
8. Migrate incrementally and track exceptions.

## Avoid the enterprise-scale costume

Do not deploy every possible management group, hub, firewall, policy, or shared
service without an owner and requirement. The architecture should create a path
for growth while keeping the current platform operable by the current team.

## Migration record

For each workload, record:

- current and target subscription;
- identity and role changes;
- policy effects and exemptions;
- network and DNS dependencies;
- logging and security destinations;
- deployment-pipeline changes;
- data-movement or downtime risk; and
- rollback owner.

## Current implementation guidance

Microsoft recommends Azure landing-zone accelerators as the fastest
implementation path for most organizations. Azure Verified Modules can provide
reusable Bicep and Terraform building blocks. Azure Blueprints is deprecated and
should not be selected for new landing-zone designs.

## Official sources

- [Azure landing zones](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/landing-zone/)
- [Landing-zone design areas](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/landing-zone/design-areas)
- [Landing-zone implementation options](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/landing-zone/implementation-options)
- [Azure landing-zone accelerator](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/landing-zone/deploy-landing-zones-with-terraform)
- [Azure Verified Modules](https://aka.ms/AVM)

[Back to scale and enterprise readiness](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/journeys/scale)
