# Build the first Microsoft Foundry workload

> **Goal:** reach a secure, observable model call before adding agent or platform
> complexity.

Microsoft documentation now uses **Microsoft Foundry**. Older projects and
links can still use Azure AI Foundry or the classic portal terminology.

## Starter path

1. Confirm the model, deployment type, region, and data requirements.
2. Create a Foundry project and grant the team least-privilege access.
3. Deploy a model through the current Foundry experience.
4. Call it through the current Foundry SDK or REST quickstart.
5. Keep credentials out of source and prefer Microsoft Entra authentication
   where supported.
6. Record latency, token usage, errors, and content-safety outcomes.
7. Add evaluation data for the product's real tasks before expanding access.
8. Define the fallback when a model or regional deployment is unavailable.

## Choose the smallest build surface

| Need | Starting point |
| --- | --- |
| Direct model inference | Foundry Models deployment and SDK |
| Managed prompt-based agent | Foundry Agent Service prompt agent |
| Existing framework or custom runtime | Hosted agent or application-owned runtime |
| Fast experiment | Supported quickstart, with preview and region caveats checked |

Do not add retrieval, agents, fine-tuning, or multiple models until the simplest
flow has a measurable quality or product gap.

## Production gates

- model and feature release status verified;
- model availability verified in the required region;
- quota and capacity checked separately;
- identities and data access reviewed;
- inputs, outputs, and sensitive-data handling documented;
- evaluations cover quality and safety failure modes;
- spend and token usage are observable; and
- fallback and incident ownership are named.

## Preview caution

Foundry evolves quickly. A portal experience, model, agent capability, or
instant-deployment path can have its own release status and regional
availability. Verify each selected capability, not only the Foundry service
landing page.

## Official sources

- [Microsoft Foundry documentation](https://learn.microsoft.com/en-us/azure/foundry/)
- [Set up Foundry resources](https://learn.microsoft.com/en-us/azure/foundry/tutorials/quickstart-create-foundry-resources)
- [Get started with the Foundry SDK](https://learn.microsoft.com/en-us/azure/foundry/quickstarts/get-started-code)
- [Foundry Agent Service overview](https://learn.microsoft.com/en-us/azure/foundry/agents/overview)
- [Microsoft Foundry training](https://learn.microsoft.com/en-us/training/azure/ai-foundry)

[Back to production foundation](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/journeys/production)
