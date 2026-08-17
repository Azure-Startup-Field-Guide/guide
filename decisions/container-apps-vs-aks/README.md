# Azure Container Apps or Azure Kubernetes Service?

> **Default for most startups:** begin with Azure Container Apps unless you can
> name a requirement for direct Kubernetes API access, cluster-level control, or
> multi-workload isolation.

This decision is about operating responsibility, not whether containers can
scale. Both services can run production workloads. The important question is
whether Kubernetes itself is a product requirement your team is prepared to
operate.

## Choose from requirements, not ambition

| Requirement | Start with |
| --- | --- |
| Deploy containerized APIs, workers, or jobs without managing a cluster | Azure Container Apps |
| Scale individual application components, including supported scale-to-zero scenarios | Azure Container Apps |
| Use revisions, traffic splitting, managed ingress, and service discovery through Azure APIs | Azure Container Apps |
| Access the Kubernetes API, Custom Resource Definitions, or operator ecosystem directly | Azure Kubernetes Service |
| Apply Kubernetes-native network policies or fine-grained isolation between colocated workloads | Azure Kubernetes Service |
| Host multiple unrelated workloads on a shared orchestration platform | Azure Kubernetes Service |
| Reuse an existing Kubernetes platform and operating model | Azure Kubernetes Service |

If the workload is only a web application or HTTP API and does not otherwise
need containers, also evaluate Azure App Service. Containerization should not be
a prerequisite invented by the platform choice.

## The startup default

Use **Azure Container Apps** when one team owns a workload and wants Azure to
manage the orchestration layer. It provides application-level capabilities such
as ingress, revisions, traffic splitting, service discovery, jobs, and
event-driven scaling without exposing the underlying Kubernetes control plane.

This default preserves engineering time for the product. It also keeps the
decision reversible: a well-packaged stateless container can move later when a
specific Kubernetes requirement appears.

### Container Apps boundary to understand

A Container Apps environment is a top-level workload and security boundary.
Official architecture guidance notes that applications inside one environment
do not have granular intra-environment access controls. Use separate
environments for distinct security boundaries, or evaluate AKS when many
unrelated workloads require Kubernetes-native isolation and policy.

## When AKS is justified

Choose **Azure Kubernetes Service** when at least one requirement depends on
Kubernetes rather than merely on containers:

- direct use of the Kubernetes API;
- operators, Custom Resource Definitions, or Kubernetes-native platform tools;
- cluster-level networking, policy, scheduling, or topology requirements;
- multiple workloads requiring namespace, access, and network isolation;
- an established Kubernetes operating model that the team intends to reuse; or
- a portability requirement defined in terms of Kubernetes APIs and validated
  against the actual dependencies of the workload.

AKS reduces work on the Azure-managed control plane, but adopting Kubernetes
still creates ongoing responsibilities. The workload team must account for
cluster and node upgrades, node pools, networking, workload identity,
observability, policy, capacity, and recovery.

### AKS Automatic or AKS Standard?

If Kubernetes is required but extensive cluster customization is not, evaluate
**AKS Automatic** first. Azure preconfigures and manages common operational
tasks such as node management, scaling, security defaults, and upgrades.

Use **AKS Standard** when the workload requires topology, node, networking, or
platform choices beyond the Automatic experience. Start from the current AKS
baseline architecture and document every intentional deviation.

## Do not use these as AKS requirements

- "We will need to scale."
- "Large companies use Kubernetes."
- "It will future-proof the platform."
- "The application already has a Dockerfile."
- "We might build many services someday."

These statements do not identify a capability that Container Apps lacks. Turn
each concern into a measurable workload or organizational requirement before
accepting the additional operating surface.

## Cost and operating model

Do not compare only compute rates. Estimate:

- minimum and peak application replicas;
- idle capacity and scale-to-zero behavior;
- shared versus dedicated compute requirements;
- networking, logging, and data-transfer costs;
- cluster and node-pool capacity for AKS;
- engineering time for upgrades, policy, observability, and incident response;
- the cost of separate environments or clusters needed for isolation; and
- the cost of a future migration if a documented exit condition occurs.

Public rates vary by region and configuration. Use the
[Azure pricing calculator](https://azure.microsoft.com/pricing/calculator/) and
your actual agreement pricing rather than copying a point-in-time estimate.

## Decision record

Before deployment, record:

1. the workload and team that own the platform;
2. the concrete requirements that selected the service;
3. the security and networking boundaries;
4. the expected minimum, normal, and peak capacity;
5. who owns day-2 operations;
6. the production-readiness evidence required; and
7. the condition that will trigger a new decision.

## Revisit the decision when

Re-evaluate Container Apps if you require direct Kubernetes APIs, operators,
unsupported networking or isolation controls, or a shared platform for
unrelated workloads.

Re-evaluate AKS if the team spends more effort operating the platform than
shipping the workload, Kubernetes-specific capabilities remain unused, or a
managed application platform now satisfies the requirements.

## Official sources

- [Azure Platform Foundations for Startups](https://learn.microsoft.com/en-us/startups/build/infra/platform-foundations)
- [Choose an Azure container service](https://learn.microsoft.com/en-us/azure/architecture/guide/choose-azure-container-service)
- [Comparing Container Apps with other Azure container options](https://learn.microsoft.com/en-us/azure/container-apps/compare-options)
- [Azure Container Apps overview](https://learn.microsoft.com/en-us/azure/container-apps/overview)
- [What is Azure Kubernetes Service?](https://learn.microsoft.com/en-us/azure/aks/what-is-aks)
- [AKS Automatic](https://learn.microsoft.com/en-us/azure/aks/intro-aks-automatic)
- [AKS baseline architecture](https://learn.microsoft.com/en-us/azure/architecture/reference-architectures/containers/aks/baseline-aks)

[Back to technology decisions](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/decisions)
