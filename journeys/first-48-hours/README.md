# Your first 48 hours on Azure

This journey is for a founder or early engineer who is applying to Microsoft
for Startups, activating credits, or preparing the first Azure deployment.

The order matters. Credit activation begins with an individual Microsoft
account, but a production environment should not remain dependent on one
person.

## Outcome

By the end of this journey you should have:

- the correct sponsored subscription and credit context;
- a second administrative account to reduce lockout risk;
- a verified company domain in Microsoft Entra ID;
- more than one person able to administer the environment;
- an initial cost-control loop;
- a deployment path matched to the workload rather than to hype; and
- a clear support route for program, billing, quota, and architecture questions.

## The path

| Step | Time | Result |
|---|---:|---|
| [1. Apply and activate](01-apply-and-activate.md) | 20-60 min | Correct account and sponsored subscription |
| [2. Establish company identity](02-company-identity.md) | 30-90 min | Company-backed tenant and resilient administration |
| [3. Set cost guardrails](03-cost-guardrails.md) | 20-45 min | Owners, tags, review cadence, and available alerts |
| [4. Build the foundation](04-build-foundation.md) | 1-4 hr | Deliberate first deployment path |
| [5. Know where to get help](05-get-help.md) | 5 min | Correct escalation route before an incident |

## Stop conditions

Do not deploy production workloads yet if:

- you cannot identify which account owns the sponsored subscription;
- only one person can administer the tenant and subscription;
- the tenant does not represent the company;
- you cannot tell whether a resource is using the sponsored subscription; or
- nobody owns cost review and cleanup.

These are easier to fix before data, customers, and deployment pipelines depend
on the environment.

## Official anchor

Microsoft's current
[Properly Setting Up Your Azure Account](https://learn.microsoft.com/en-us/startups/build/azure-getting-started/set-up-account)
guide explicitly says to complete the identity and administration steps before
building workloads. This journey makes that sequence the front door instead of
an easy-to-miss follow-up.

[Back to the main guide](../../README.md)
