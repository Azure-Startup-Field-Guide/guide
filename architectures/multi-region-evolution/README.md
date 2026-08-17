# Multi-region evolution

Use this pattern to explain the graduation from a zone-aware single region to a
multi-region design after explicit recovery targets justify it.

![Multi-region evolution reference architecture](https://raw.githubusercontent.com/Azure-Startup-Field-Guide/guide/main/static/img/multi-region-evolution-reference.svg)

## Stage 1: one region

Use availability zones and service-native resiliency where supported. Configure
backup and recovery, remove single points of failure in the critical flow, and
test the regional recovery plan.

## Stage 2: multiple regions

Add a global routing layer and a second application stamp only when the required
RTO/RPO cannot be met by the first design. Select active-passive or active-active
behavior for each component, especially data.

## Required proof

- regional failure and traffic-routing behavior;
- data replication, conflict, and failback rules;
- identity, secret, DNS, and certificate operation in both regions;
- quota and capacity in the recovery region;
- monitoring that distinguishes regional and dependency failures; and
- an exercised failover and failback record.

The diagram shows logical stamps, not a claim that every Azure service is
zone-redundant or regionally available. Verify each selected service.

[SVG source](https://raw.githubusercontent.com/Azure-Startup-Field-Guide/guide/main/static/img/multi-region-evolution-reference.svg)
| [Back to reference architectures](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/architectures)
