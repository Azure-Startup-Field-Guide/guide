# Managed service or self-hosted component?

> **Default:** use a managed Azure service when it satisfies the workload's
> functional, security, compliance, and regional requirements.

Self-hosting converts a product dependency into an operating responsibility.
That can be the correct trade, but it must be explicit.

## Prefer a managed service when

- the product does not differentiate on operating that component;
- supported configuration meets the workload requirements;
- platform patching, availability, backup, and scaling reduce team burden;
- Azure identity, networking, monitoring, and support integrations are useful;
  or
- the team needs to ship product capability faster than platform capability.

## Self-host only when

- required OS, runtime, extension, or protocol control is unavailable;
- licensing or data-sovereignty constraints require it;
- a validated performance characteristic cannot be met by the managed option;
- the team already has the required operational expertise and capacity; or
- portability is a contractual requirement backed by an exercised migration
  path.

## Compare the full responsibility

| Area | Managed service | Self-hosted component |
| --- | --- | --- |
| Platform patching | Primarily provider-operated | Team-operated |
| High availability | Service capability and configuration | Team architecture and operations |
| Backup and recovery | Integrated options, still must be configured and tested | Entirely team-designed |
| Scaling | Service controls and limits | Team-selected tooling and capacity |
| Customization | Constrained | Broad |
| Support boundary | Azure service support | Azure infrastructure plus component support |

Managed does not mean automatic. The startup still owns data design, access,
configuration, monitoring, recovery targets, and application behavior.

## Minimum self-hosting gate

Before self-hosting, document:

1. the unsupported requirement;
2. the patching and vulnerability response owner;
3. high-availability and recovery architecture;
4. monitoring and on-call coverage;
5. upgrade and rollback procedures;
6. license and support terms;
7. three-year operating-cost assumptions; and
8. the condition for returning to a managed service.

## Revisit the decision when

Re-evaluate self-hosting when incidents or upgrades consume product capacity,
the managed service adds the missing requirement, or only one person can operate
the component. Re-evaluate a managed service when a verified requirement cannot
be met within its supported boundaries.

## Official sources

- [Choose an Azure compute service](https://learn.microsoft.com/en-us/azure/architecture/guide/technology-choices/compute-decision-tree)
- [Shared responsibility in the cloud](https://learn.microsoft.com/en-us/azure/security/fundamentals/shared-responsibility)
- [Well-Architected service guides](https://learn.microsoft.com/en-us/azure/well-architected/service-guides/)
- [Azure Virtual Machines service guide](https://learn.microsoft.com/en-us/azure/well-architected/service-guides/virtual-machines)
- [Azure Kubernetes Service service guide](https://learn.microsoft.com/en-us/azure/well-architected/service-guides/azure-kubernetes-service)

[Back to technology decisions](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/decisions)
