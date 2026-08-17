# Asynchronous AI application

Use this pattern when model work can exceed an interactive request window, must
absorb bursts, or needs independent retry and concurrency controls.

![Asynchronous AI application reference architecture](https://raw.githubusercontent.com/Azure-Startup-Field-Guide/guide/main/static/img/async-ai-app-reference.svg)

## Flow

1. The API authenticates the caller and creates a job.
2. A managed queue separates request acceptance from model execution.
3. A worker processes jobs using managed identity.
4. The worker calls a Microsoft Foundry model deployment and stores status or
   results.
5. The client polls, subscribes, or receives a product-owned notification.
6. Azure Monitor correlates API, queue, worker, and model telemetry.

## Reliability contract

- make job submission idempotent;
- define retry, poison-message, timeout, and cancellation behavior;
- bound worker concurrency to model quota and downstream capacity;
- avoid putting sensitive prompts or outputs into logs;
- meter token and job cost by product or tenant where appropriate; and
- define the customer experience when the model or region is unavailable.

## Decide before using

Confirm model release status, region, quota, capacity, safety, evaluation, data
handling, and recovery requirements. A queue improves decoupling but does not
make a non-idempotent operation safe.

[SVG source](https://raw.githubusercontent.com/Azure-Startup-Field-Guide/guide/main/static/img/async-ai-app-reference.svg)
| [Back to reference architectures](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/architectures)
