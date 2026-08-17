# Virtual-machine workload

Use this pattern when a verified operating-system, appliance, migration,
specialized hardware, licensing, or vendor-support requirement makes IaaS the
deliberate choice.

![Virtual-machine workload reference architecture](https://raw.githubusercontent.com/Azure-Startup-Field-Guide/guide/main/static/img/vm-workload-reference.svg)

## Flow and ownership

1. The workload entry point distributes application traffic to a VM or Virtual
   Machine Scale Set.
2. Redundant instances span availability zones when the region, VM SKU, and
   workload target support that design.
3. Managed identity provides access to Key Vault and other Azure resources.
4. Azure Monitor receives guest, platform, health, and application telemetry.
5. Azure Backup or workload-native protection implements the tested recovery
   design.
6. A protected management path separates administrative access from application
   traffic.

## The startup still owns

- image and guest operating-system lifecycle;
- installed software, agents, drivers, and vulnerabilities;
- patching and safe restart behavior;
- scale-set model and rollout strategy;
- health probes, repair, and capacity;
- disk and data recovery;
- network exposure and administrative access; and
- rightsizing, licensing, and idle cost.

## Decide before using

- [Managed platform or virtual machines?](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/decisions/paas-vs-iaas)
- single VM or repeatable scale-set fleet;
- availability target and zone support;
- image source, hardening, patching, and rollback;
- inbound, outbound, and management network paths;
- backup, RTO, RPO, and regional recovery; and
- quota, VM size, disk, accelerator, and regional availability.

## Intentionally omitted

The diagram does not prescribe a hub network, firewall, public IP, specific
load balancer, database, or image pipeline. Add those only when the workload and
operating model require them.

## Official sources

- [Azure Virtual Machines baseline architecture](https://learn.microsoft.com/en-us/azure/architecture/virtual-machines/baseline)
- [Well-Architected guidance for virtual machines and scale sets](https://learn.microsoft.com/en-us/azure/well-architected/service-guides/virtual-machines)
- [Virtual Machine Scale Sets overview](https://learn.microsoft.com/en-us/azure/virtual-machine-scale-sets/overview)
- [Automatic VM guest patching](https://learn.microsoft.com/en-us/azure/virtual-machines/automatic-vm-guest-patching)

[SVG source](https://raw.githubusercontent.com/Azure-Startup-Field-Guide/guide/main/static/img/vm-workload-reference.svg)
| [Back to reference architectures](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/architectures)
