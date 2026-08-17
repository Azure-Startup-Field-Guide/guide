# Single-tenant or multitenant SaaS?

> **Default:** share infrastructure where the isolation model is understood, and
> reserve dedicated deployments for requirements that justify their cost.

Tenancy is not one application-wide switch. Identity, compute, data, messaging,
networking, and observability can use different isolation models.

## Start with a shared model when

- many tenants use the same product version and lifecycle;
- logical isolation can satisfy the security requirements;
- the application can carry and enforce tenant context on every request;
- shared capacity improves unit economics; and
- the team can detect noisy-neighbor and cross-tenant risks.

## Use dedicated resources when

- a contractual or regulatory requirement demands stronger isolation;
- a customer requires customer-managed keys or dedicated network boundaries;
- tenant-specific performance or availability commitments require separate
  capacity;
- customer customization cannot safely share a release lifecycle; or
- shared Azure resource limits create a verified constraint.

## Use a hybrid model deliberately

A common evolution is a shared tier for most tenants and dedicated deployment
stamps for regulated or high-scale tenants. Define which capabilities differ by
tier, how tenants move between tiers, and whether data migration is supported.

## Minimum multitenant controls

1. Resolve an authenticated request to one tenant context.
2. Authorize every data and resource operation against that tenant.
3. Include tenant identifiers in logs, metrics, traces, and audit events.
4. Test attempts to cross tenant boundaries.
5. Define per-tenant quotas and noisy-neighbor controls.
6. Document every store containing tenant data.
7. Make support access auditable and time-bound.
8. Define tenant deletion, export, and recovery procedures.

## Cost and operations

Dedicated deployments simplify some isolation arguments but create a fleet that
must be patched, observed, upgraded, and recovered consistently. Shared
deployments reduce marginal cost but require stronger application isolation,
capacity management, and tenant-aware diagnostics.

Treat both product pricing and Azure resource placement as part of the tenancy
decision. A tier that promises dedicated behavior must fund the additional
operating model.

## Revisit the decision when

Re-evaluate tenancy when enterprise customers request isolation, tenant growth
creates noisy-neighbor risk, a region or compliance boundary changes, or the
fleet becomes too expensive to operate consistently.

## Official sources

- [Architecting multitenant solutions on Azure](https://learn.microsoft.com/en-us/azure/architecture/guide/multitenant/overview)
- [Tenancy models](https://learn.microsoft.com/en-us/azure/architecture/guide/multitenant/considerations/tenancy-models)
- [Multitenancy checklist](https://learn.microsoft.com/en-us/azure/architecture/guide/multitenant/checklist)
- [Governance and compliance approaches](https://learn.microsoft.com/en-us/azure/architecture/guide/multitenant/approaches/governance-compliance)
- [SaaS tenancy patterns for Azure SQL Database](https://learn.microsoft.com/en-us/azure/azure-sql/database/saas-tenancy-app-design-patterns)

[Back to technology decisions](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/decisions)
