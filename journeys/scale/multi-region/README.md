# Multi-region decision framework

> **Default:** use one region with availability zones when supported. Add a
> second region only when recovery or product requirements justify it.

Multiple regions increase dependency, data, deployment, observability, testing,
and incident complexity. They are not a substitute for understanding failure.

## Start from recovery targets

1. Rank critical user and system flows.
2. Define availability, RTO, and RPO targets.
3. Identify regional dependencies and failure modes.
4. Confirm whether availability zones and service-native recovery meet the
   targets.
5. If they do not, select a multi-region pattern for each stateful component.
6. Define traffic routing, data replication, failover, failback, and conflict
   behavior.
7. Verify capacity and quota in the recovery region.
8. Exercise the full failover and failback process.

## Common patterns

| Pattern | Use when | Main tradeoff |
| --- | --- | --- |
| Backup and redeploy | Longer recovery is acceptable | Lowest standing complexity |
| Active-passive | Faster recovery is required | Idle or reduced-capacity secondary |
| Active-active | Very low recovery time and global traffic justify it | Highest data and operating complexity |

The right pattern can differ by component. A globally distributed edge does not
make a single-region database multi-region.

## Hard questions

- What happens to writes during partition or failover?
- Can identity, secrets, DNS, certificates, and pipelines operate in both
  regions?
- Is the recovery region allowed for every data class?
- Are model, GPU, and other constrained services available there?
- Does the team know when to fail over and who can authorize it?
- How is data reconciled before failback?

## Revisit the design when

Recovery targets, customer geography, data residency, regional service
availability, or the product's dependency graph changes.

## Official sources

- [Mission-critical architecture on Azure](https://learn.microsoft.com/en-us/azure/architecture/reference-architectures/containers/aks-mission-critical/mission-critical-intro)
- [Recommendations for regions and availability zones](https://learn.microsoft.com/en-us/azure/well-architected/reliability/regions-availability-zones)
- [Disaster recovery strategy](https://learn.microsoft.com/en-us/azure/well-architected/reliability/disaster-recovery)
- [Multiregion web application pattern](https://learn.microsoft.com/en-us/azure/architecture/reference-architectures/app-service-web-app/multi-region)

[Back to scale and enterprise readiness](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/journeys/scale)
