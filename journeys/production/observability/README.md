# Minimum observability baseline

> **Goal:** know when users are affected, why, and who must respond.

Collecting logs is not the same as operating an observable product. Start from
critical user flows and the decisions the team needs to make during an incident.

## Minimum baseline

1. Send application logs, platform logs, metrics, and distributed traces to an
   owned Azure Monitor design.
2. Configure diagnostic settings for the Azure resources on the critical path.
3. Correlate telemetry with a request or trace identifier.
4. Add environment, version, region, and tenant context where appropriate.
5. Alert on user impact and exhausted safety margins, not every raw signal.
6. Route Azure Service Health notifications to an owned channel.
7. Create one dashboard or workbook for the core user flow.
8. Test the alert route and incident handoff.

## First signals to define

| Signal | Product question |
| --- | --- |
| Availability | Can a user complete the critical flow? |
| Latency | Is the flow meeting its target? |
| Errors | Which failures are increasing and for whom? |
| Saturation | Which dependency is approaching a limit? |
| Dependencies | Is the failure inside or outside the application? |
| Deployment | Did health change after a release? |

## Alert quality

Every actionable alert needs:

- a condition linked to user or recovery impact;
- a severity and owner;
- an evaluation window that avoids obvious noise;
- a runbook or first diagnostic query;
- a destination that someone monitors; and
- a review after incidents or repeated false positives.

Azure Monitor Baseline Alerts provides Microsoft-maintained recommended alert
patterns and Azure Policy implementations. Treat it as a starting catalog,
then deploy only the signals that match the resources and operating model.

## Revisit the baseline when

Add capability when the product introduces a new critical flow, region, tenant
tier, asynchronous boundary, external dependency, or on-call team.

## Official sources

- [Azure Monitor overview](https://learn.microsoft.com/en-us/azure/azure-monitor/fundamentals/overview)
- [Best practices for Azure Monitor Logs](https://learn.microsoft.com/en-us/azure/azure-monitor/logs/best-practices-logs)
- [Monitoring best practices](https://learn.microsoft.com/en-us/azure/architecture/best-practices/monitoring)
- [Azure Monitor Baseline Alerts](https://azure.github.io/azure-monitor-baseline-alerts/welcome/)
- [Operational Excellence design principles](https://learn.microsoft.com/en-us/azure/well-architected/operational-excellence/principles)

[Back to production foundation](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/journeys/production)
