# FinOps maturity for a growing startup

> **Default:** begin with visibility and ownership, then optimize and automate.

FinOps is a collaboration model across engineering, finance, and business
owners. It is not a one-time cost-cutting project.

## Stage 1: know the spend

- Name a cost owner and a technical owner.
- Organize subscriptions, resource groups, and tags around accountable products
  and environments.
- Create budgets and route anomaly or budget signals to owners.
- Review cost by service, environment, product, and tenant where feasible.
- Track credits and standard-billing exposure separately.

## Stage 2: connect cost to product

- Define unit metrics such as cost per active tenant, request, job, or model
  interaction.
- Attribute shared costs with an explicit allocation method.
- Pair Azure cost changes with deployments, traffic, and product metrics.
- Rightsize and remove idle resources before purchasing commitments.
- Track commitment utilization and coverage when commitments exist.

## Stage 3: optimize continuously

- Put cost estimates and ownership into architecture reviews.
- Automate policy for common waste and ownership failures.
- Use recurring optimization reviews, not annual cleanup.
- Treat reliability, performance, and security requirements as constraints on
  optimization.
- Measure verified savings without counting costs that would never have
  occurred.

## Minimum review

| Question | Owner |
| --- | --- |
| What changed this period? | Engineering |
| Was it expected product growth? | Product |
| What is the unit-cost impact? | Engineering and finance |
| Which action is safe now? | Workload owner |
| Which commitment needs review? | Billing owner |

## Revisit the operating model when

Add tooling or process when allocation is unreliable, commitment exposure grows,
teams cannot act on recommendations, or cost decisions repeatedly arrive after
architecture decisions.

## Official sources

- [FinOps Framework overview](https://learn.microsoft.com/en-us/cloud-computing/finops/framework/)
- [FinOps on Azure](https://learn.microsoft.com/en-us/cloud-computing/finops/)
- [Cost Management best practices](https://learn.microsoft.com/en-us/azure/cost-management-billing/costs/cost-mgt-best-practices)
- [Well-Architected cost optimization](https://learn.microsoft.com/en-us/azure/well-architected/cost-optimization/)
- [Microsoft Cost Management](https://learn.microsoft.com/en-us/azure/cost-management-billing/cost-management-billing-overview)

[Back to scale and enterprise readiness](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/journeys/scale)
