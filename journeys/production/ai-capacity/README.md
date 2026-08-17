# Plan model and GPU capacity

> **Goal:** separate demand, quota, deployable capacity, and cost before making a
> launch commitment.

Foundry model deployments and self-managed GPU virtual machines use different
quota systems. Decide which path the product actually needs.

## Foundry model capacity

1. Estimate expected tokens per request and requests per time interval.
2. Confirm model, deployment type, subscription, and region.
3. Review the subscription's quota for that exact combination.
4. Start with standard consumption deployment for uncertain demand.
5. Load test using representative prompts and output lengths.
6. Evaluate priority or provisioned deployment only when latency and throughput
   requirements justify them.
7. Confirm deployable regional capacity independently from approved quota.
8. Request increases before the committed launch date and keep a fallback.

Provisioned-throughput quota does not guarantee that capacity is currently
available in a region. Releasing a deployment can also release its capacity back
to the shared pool.

## Self-managed GPU capacity

Use GPU virtual machines only when the workload requires control unavailable
from a managed model endpoint. Check both regional vCPU quota and the target VM
family quota. If the quota is not adjustable in the portal, use the documented
support path.

Before committing to a VM family:

- verify regional availability and quota;
- test the actual model and batch profile;
- define image, driver, patching, and scaling ownership;
- include idle capacity in the cost model; and
- design a fallback family, region, or managed endpoint.

## Launch evidence

| Evidence | Owner |
| --- | --- |
| Demand model and load-test results | Application team |
| Quota approval | Subscription owner |
| Current regional capacity check | Deployment owner |
| Cost model | Engineering and finance owner |
| Fallback path | Product and engineering owner |

## Official sources

- [Azure OpenAI in Foundry Models quota](https://learn.microsoft.com/en-us/azure/foundry/openai/how-to/quota)
- [Provisioned throughput](https://learn.microsoft.com/en-us/azure/foundry/openai/concepts/provisioned-throughput)
- [Increase VM-family vCPU quotas](https://learn.microsoft.com/en-us/azure/quotas/per-vm-quota-requests)
- [Request a quota increase in the portal](https://learn.microsoft.com/en-us/azure/quotas/quickstart-increase-quota-portal)

[Back to production foundation](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/journeys/production)
