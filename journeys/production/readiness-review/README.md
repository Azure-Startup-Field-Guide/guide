# Production readiness review

> **Goal:** prove that the critical user flow is ready to operate, not that every
> possible control exists.

Run this review before the first production launch and after material
architecture changes.

## Review the critical flow

1. Draw the flow from user entry to every required dependency.
2. Rank user and system flows by criticality.
3. Perform a failure-mode analysis for the critical flow.
4. Define availability, latency, RTO, and RPO targets.
5. Identify single points of failure and intentional risks.
6. Verify scaling, throttling, self-protection, and recovery behavior.
7. Test observability, deployment rollback, and restore procedures.
8. Assign every accepted risk an owner and revisit date.

## Five-pillar gate

| Well-Architected pillar | Minimum question |
| --- | --- |
| Reliability | What fails, how is impact contained, and how is service restored? |
| Security | Which identities, data, secrets, and trust boundaries need protection? |
| Cost Optimization | What drives unit cost and who detects waste? |
| Operational Excellence | How is change deployed, observed, and operated? |
| Performance Efficiency | How does the design meet demand and degrade safely? |

## Azure foundation gate

For a first production workload, keep governance proportional:

- an owned subscription and billing boundary;
- management groups only when the operating model requires them;
- naming, tagging, region, and resource-organization conventions;
- least-privilege identity and policy guardrails;
- deployment through infrastructure as code;
- centralized cost and operational visibility; and
- a documented path to an Azure landing zone as complexity grows.

Do not copy an enterprise landing zone without the teams and operating model
needed to own it.

## Exit criteria

The review is complete when owners accept the remaining risks and the team can
demonstrate deployment, detection, diagnosis, recovery, and cost visibility for
the critical flow.

## Official sources

- [Azure Well-Architected Framework](https://learn.microsoft.com/en-us/azure/well-architected/)
- [Reliability design-review checklist](https://learn.microsoft.com/en-us/azure/well-architected/reliability/checklist)
- [Azure landing zones](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/landing-zone/)
- [Azure Well-Architected Review](https://learn.microsoft.com/en-us/assessments/azure-architecture-review/)

[Back to production foundation](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/journeys/production)
