# Platform engineering triggers

> **Default:** do not build a platform until repeated product-team needs justify
> a platform product.

Platform engineering should reduce cognitive load through supported,
self-service paths. A repository of templates without users, ownership, or
feedback is not a platform.

## Signals that justify investment

- teams repeatedly build the same environment, pipeline, identity, or
  observability foundation;
- delivery is blocked on a small number of infrastructure specialists;
- security and policy requirements are implemented inconsistently;
- product teams need a supported path across multiple subscriptions or regions;
- operational incidents repeat because every workload is different; or
- a paved path can remove measurable lead time without hiding necessary
  product choices.

No single team count or subscription count proves the need. Use repeated demand
and measurable friction.

## Build the first paved path

1. Interview the internal users and choose one recurring journey.
2. Define the product team's responsibilities and the platform contract.
3. Compose a thin path from versioned infrastructure modules, deployment
   workflows, policy, identity, observability, and documentation.
4. Provide an escape hatch with review, not an unsupported fork.
5. Pilot with one real workload.
6. Measure adoption, deployment lead time, failure rate, support demand, and
   user satisfaction.
7. Assign a long-lived product owner and support model.

## Use current Azure building blocks

- Azure landing-zone architecture and accelerators;
- Azure Verified Modules for Bicep or Terraform;
- Azure Policy for guardrails;
- Deployment Stacks or Template Specs where their lifecycle fits;
- Microsoft Entra workload identities; and
- Azure Monitor and cost-management standards.

Do not start new designs with Azure Blueprints. Microsoft documentation states
that Azure Blueprints is deprecated and will be retired; use current
landing-zone and infrastructure-as-code approaches.

## Revisit the platform boundary when

The paved path blocks product differentiation, users bypass it, support demand
grows faster than adoption, or the platform team owns application concerns it
cannot operate.

## Official sources

- [What is platform engineering?](https://learn.microsoft.com/en-us/platform-engineering/what-is-platform-engineering)
- [Platform engineering capability model](https://learn.microsoft.com/en-us/platform-engineering/capability-model)
- [Azure landing zones](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/landing-zone/)
- [Azure Verified Modules](https://aka.ms/AVM)
- [Migrate from Azure Blueprints](https://learn.microsoft.com/en-us/azure/governance/blueprints/deprecation)

[Back to scale and enterprise readiness](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/journeys/scale)
