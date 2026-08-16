# 3. Make credits visible before they become spend

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
|---|---|---|
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

## Next

Continue to [4. Build the foundation](04-build-foundation.md).

## Official sources

- [Best Ways to Use Startup Credits](https://learn.microsoft.com/en-us/startups/benefits/azure-credits/use-azure-credits)
- [Start using Cost Analysis](https://learn.microsoft.com/en-us/azure/cost-management-billing/costs/quick-acm-cost-analysis)
- [Tutorial: Create and manage Azure budgets](https://learn.microsoft.com/en-us/azure/cost-management-billing/costs/tutorial-acm-create-budgets)
