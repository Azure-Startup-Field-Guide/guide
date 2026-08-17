# 3. Make credits visible before they become spend

> **Verified in the August 16, 2026 repository audit against current official
> Microsoft documentation.**

## The recommendation

Treat startup credits as temporary runway, not as free infrastructure. Establish
ownership, attribution, and a review cadence before deploying services that can
scale automatically.

## Minimum controls

### Name an owner

One person must own the weekly review of:

- remaining credit balance;
- top services by consumption;
- unexpected regions or subscriptions;
- idle non-production resources; and
- forecasted pay-as-you-go exposure.

### Apply a small tag set

Use infrastructure as code to apply, at minimum:

| Tag | Example | Why |
| --- | --- | --- |
| `environment` | `dev`, `staging`, `prod` | Separate production from experiments |
| `owner` | team or role, not a personal secret | Route cost and operational questions |
| `workload` | `api`, `rag`, `data-platform` | Attribute spend to product decisions |
| `stage` | `experiment`, `mvp`, `production` | Identify resources that should expire |

### Use the controls available to your billing type

Open **Cost Management + Billing** and determine which views, budgets, alerts,
and exports are available for the sponsored subscription. Microsoft
documentation notes that some sponsorship subscription types do not support
every Cost Management feature, so verify the actual experience rather than
assuming a menu will be present.

If budget alerts are available:

1. set thresholds that provide time to act;
2. notify more than one person;
3. test the recipient path; and
4. review forecasted as well as actual consumption.

If a control is unavailable, keep the weekly manual review and open a support
request for the supported alternative.

### Create an expiration habit

Every experiment should have an owner and a review date. Remove stale disks,
public IP addresses, test clusters, model deployments, and oversized databases
when the experiment ends.

## Review unit economics while credits remain

Track a unit connected to product value, such as:

- cost per active customer;
- cost per successful workflow;
- cost per API request;
- cost per document processed; or
- cost per successful AI task.

The correct time to change architecture is before credits expire, not after the
first pay-as-you-go invoice.

## Plan the exit from credits

Current program documentation says remaining credits expire at graduation and
the subscription transitions to standard pay-as-you-go. Before deploying a
production workload:

- record the sponsorship end date and billing owner;
- forecast the same workload without credits;
- define which experiments will be removed or resized first; and
- review the transition plan at least monthly.

## Next

Continue to
[4. Build the foundation](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/journeys/first-48-hours/04-build-foundation).

## Official sources

- [Best Ways to Use Startup Credits](https://learn.microsoft.com/en-us/startups/benefits/azure-credits/use-azure-credits)
- [Azure Usage and Billing](https://learn.microsoft.com/en-us/startups/benefits/azure-credits/azure-usage-and-billing)
- [Program Graduation](https://learn.microsoft.com/en-us/startups/microsoft-for-startups/program-graduation)
- [Start using Cost Analysis](https://learn.microsoft.com/en-us/azure/cost-management-billing/costs/quick-acm-cost-analysis)
- [Tutorial: Create and manage Azure budgets](https://learn.microsoft.com/en-us/azure/cost-management-billing/costs/tutorial-acm-create-budgets)
