# Production foundation

Use this path when a prototype is becoming a service that customers depend on.
The goal is not enterprise ceremony. It is a minimum, owned operating system for
deploying, observing, recovering, and paying for the product.

## Recommended order

1. [Use secretless GitHub Actions deployments](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/journeys/production/github-actions-oidc)
2. [Establish the minimum observability baseline](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/journeys/production/observability)
3. [Define backup and recovery](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/journeys/production/backup-recovery)
4. [Run the production readiness review](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/journeys/production/readiness-review)
5. [Prepare for credit graduation](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/journeys/production/credit-graduation)

AI products should also complete:

1. [Build the first Microsoft Foundry workload](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/journeys/production/ai-application)
2. [Plan model and GPU capacity](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/journeys/production/ai-capacity)

## The production contract

Before calling a workload production, name the owner and evidence for each item:

| Question | Minimum evidence |
| --- | --- |
| How is it deployed? | Reviewed pipeline using workload identity federation |
| How is it observed? | Logs, metrics, traces, alerts, and service-health routing |
| How is it recovered? | RTO/RPO, configured protection, and a tested restore |
| How is it secured? | Threats, least privilege, secrets, and dependency ownership |
| How does it fail? | Critical flows and a failure-mode analysis |
| How is cost controlled? | Budget, anomaly routing, tags, and a named owner |
| Who responds? | On-call and escalation paths |

The evidence can be short. Missing ownership cannot.

[Back to the guide](https://github.com/Azure-Startup-Field-Guide/guide)
