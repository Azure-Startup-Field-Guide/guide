# Consumption or committed capacity?

> **Default:** remain on consumption or pay-as-you-go pricing until measured
> usage supports a commitment.

Commitments optimize a known baseline. They should not be used to make an
unproven forecast look cheaper.

## Stay on consumption when

- the workload is new or changes frequently;
- traffic is bursty, seasonal, or difficult to forecast;
- scale-to-zero materially reduces idle cost;
- region, model, or compute family might change; or
- the team is still measuring unit economics.

## Evaluate a commitment when

- a stable baseline remains after rightsizing;
- the service, region, family, and term are unlikely to change;
- utilization and forecast data support the commitment;
- an owner will review coverage and utilization; and
- the commitment does not consume runway needed for product change.

## Separate three decisions

| Decision | Purpose |
| --- | --- |
| Reservation | Discount for a specific, predictable usage shape |
| Savings plan | Flexible hourly spend commitment across eligible compute |
| Capacity reservation or provisioned throughput | Availability or predictable service capacity |

A quota grant, cost reservation, and capacity guarantee are not interchangeable.
For Microsoft Foundry provisioned throughput, quota and available regional
capacity are separate checks.

## Minimum commitment review

1. Rightsize and remove idle resources first.
2. Measure the stable baseline independently from peak demand.
3. Compare reservation, savings-plan, and consumption coverage.
4. Confirm scope, region, service, term, exchange, and cancellation behavior.
5. Assign an owner for utilization and expiration.
6. Model a demand decrease and a platform migration.
7. Reconcile public estimates with the startup's actual agreement pricing.

## Revisit the decision when

Re-evaluate commitments when utilization falls, the service or region changes,
architecture migration begins, or a new workload creates a different stable
baseline.

## Official sources

- [Get the best rates for your workload](https://learn.microsoft.com/en-us/azure/well-architected/cost-optimization/get-best-rates)
- [Decide between a savings plan and a reservation](https://learn.microsoft.com/en-us/azure/cost-management-billing/savings-plan/decide-between-savings-plan-reservation)
- [Save with Azure Reservations](https://learn.microsoft.com/en-us/azure/cost-management-billing/reservations/save-compute-costs-reservations)
- [Azure Cosmos DB serverless](https://learn.microsoft.com/en-us/azure/cosmos-db/serverless)
- [Provisioned throughput for Microsoft Foundry Models](https://learn.microsoft.com/en-us/azure/foundry/openai/concepts/provisioned-throughput)

[Back to technology decisions](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/decisions)
