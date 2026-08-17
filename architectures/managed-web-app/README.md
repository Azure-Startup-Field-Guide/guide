# Managed web application

Use this pattern for a startup web product that benefits from managed compute,
managed data, secretless identity, and a small operational surface.

![Managed web application reference architecture](https://raw.githubusercontent.com/Azure-Startup-Field-Guide/guide/main/static/img/managed-web-app-reference.svg)

## Flow

1. A managed edge terminates the public entry path and applies routing and
   protection required by the workload.
2. Azure App Service or Azure Container Apps runs the application.
3. Managed identity reaches Key Vault and the selected managed data service.
4. Application and platform telemetry flows to Azure Monitor.
5. GitHub Actions deploys through workload identity federation.

## Decide before using

- [Azure Container Apps or AKS?](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/decisions/container-apps-vs-aks)
- [Relational or NoSQL data?](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/decisions/relational-vs-nosql)
- whether private networking is required;
- whether the edge service and compute are available in the required region;
- RTO, RPO, backup, and availability-zone requirements; and
- how user identity and tenant context reach the application.

## Intentionally omitted

The diagram does not prescribe DNS, certificates, network topology, cache,
messaging, deployment slots, data replication, or disaster recovery. Add them
only from workload requirements.

[SVG source](https://raw.githubusercontent.com/Azure-Startup-Field-Guide/guide/main/static/img/managed-web-app-reference.svg)
| [Back to reference architectures](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/architectures)
