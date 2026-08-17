# MVP to product-market fit

Use this path when customers depend on the product and engineering decisions
must support repeatable growth rather than only the next demonstration.

## 1. Define what must remain true

Before changing the platform, document:

- the critical user flow and product success metric;
- current demand, growth shape, and largest bottleneck;
- service-level and recovery targets;
- unit cost and the biggest cost driver;
- tenant, geography, and data requirements; and
- the engineering constraints slowing product delivery.

## 2. Complete the production contract

Finish the
[production foundation](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/journeys/production):
secretless deployment, observability, backup and recovery, readiness review, and
credit-graduation planning.

## 3. Make the hard product decisions explicit

Use the
[technology decision library](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/decisions)
to record infrastructure, data, tenancy, commitment, and managed-service
choices. Every decision should include invalid assumptions and revisit triggers.

## 4. Scale the operating model only from evidence

Move into the
[scale and enterprise path](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/journeys/scale)
when repeated cost, compliance, platform, region, or governance needs appear.
Do not use enterprise architecture as a proxy for product maturity.

## Product-market-fit review

| Dimension | Question |
| --- | --- |
| Product | Which customer behavior proves value? |
| Reliability | Which failure loses trust or revenue? |
| Scale | Which measured resource or process is approaching a limit? |
| Cost | Does unit cost improve, remain stable, or deteriorate with growth? |
| Tenancy | Can one tenant affect another's security or performance? |
| Delivery | Which repeated platform work slows product teams? |
| Enterprise | Which signed or near-term customer requirement changes the design? |

The next architecture step should remove the most important verified constraint.

[Back to the guide](https://github.com/Azure-Startup-Field-Guide/guide)
