# Bicep or Terraform?

> **Default for an Azure-only startup:** use Bicep unless the team already has a
> reason to standardize on Terraform.

Both tools can deploy production Azure infrastructure. The decision is about
scope, state, team skills, and ecosystem requirements rather than deployment
capability.

## Choose Bicep when

- Azure is the only infrastructure target;
- immediate access to Azure resource types and API versions matters;
- the team wants Azure-native tooling and no separate state file;
- modules will primarily use Azure Verified Modules; or
- the smallest operational surface is more valuable than cross-cloud
  consistency.

Bicep deployments use Azure Resource Manager to compare the desired template
with the current Azure state. The team still needs source control, review,
deployment history, and safe parameter handling, but it does not operate a
Terraform state backend.

## Choose Terraform when

- the same workflow must manage Azure and other providers;
- the organization already operates Terraform safely;
- required modules or integrations exist only in the Terraform ecosystem;
- a platform team has standardized policy, testing, and state management around
  Terraform; or
- the benefits of one cross-cloud workflow exceed the provider and state
  overhead.

Terraform records managed infrastructure in state. Store remote state in a
protected backend, restrict access, enable recovery, and never commit state or
plan files that can contain sensitive values.

## Decision matrix

| Consideration | Bicep | Terraform |
| --- | --- | --- |
| Azure-only startup | Default | Valid with existing expertise |
| Multiple providers | Limited | Strong fit |
| State ownership | Azure Resource Manager | Team-operated state backend |
| New Azure resource support | Available through Azure resource APIs | Depends on provider support |
| Module source | Azure Verified Modules and internal modules | Registry, Azure Verified Modules, and internal modules |
| Operational surface | Smaller | Includes providers, state, and toolchain |

## Do not choose based on

- repository stars;
- a belief that one syntax is universally more readable;
- the possibility of a future second cloud with no committed workload; or
- a single engineer's preference without considering who will operate the
  deployment pipeline.

## Minimum operating standard

Whichever tool you choose:

1. pin tool, provider, and module versions where supported;
2. keep infrastructure and reviewable configuration in source control;
3. separate production and nonproduction deployment boundaries;
4. use workload identity federation instead of stored deployment credentials;
5. protect sensitive parameters and outputs;
6. run validation and a preview or plan before apply; and
7. document rollback, state recovery, and break-glass ownership.

## Revisit the decision when

Re-evaluate Bicep when a committed multi-provider workload or Terraform-based
platform standard appears. Re-evaluate Terraform when state and provider
operations consume more effort than the cross-provider benefit.

## Official sources

- [Comparing Terraform and Bicep](https://learn.microsoft.com/en-us/azure/developer/terraform/comparing-terraform-and-bicep)
- [What is Bicep?](https://learn.microsoft.com/en-us/azure/azure-resource-manager/bicep/overview)
- [Terraform on Azure overview](https://learn.microsoft.com/en-us/azure/developer/terraform/overview)
- [Azure Verified Modules](https://aka.ms/AVM)

[Back to technology decisions](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/decisions)
