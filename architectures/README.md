# Reference architectures

These startup-sized patterns are conversation starters, not deployable
templates. Adapt them to workload requirements and validate the result with the
Azure Well-Architected Framework.

## Patterns

| Pattern | Start here when |
| --- | --- |
| [Managed web application](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/architectures/managed-web-app) | A web product needs a small production baseline |
| [Virtual-machine workload](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/architectures/vm-workload) | Guest OS or specialized compute requirements justify IaaS |
| [Asynchronous AI application](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/architectures/async-ai-app) | Model work is slow, bursty, or should not block requests |
| [Multi-region evolution](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/architectures/multi-region-evolution) | Recovery targets justify moving beyond one region |

## Diagram standard

Every diagram in this library:

- uses directional arrows from caller to dependency;
- labels services, relationships, regions, and trust boundaries;
- keeps editable SVG source in `static/img`;
- describes assumptions and omitted concerns;
- links to official Microsoft architecture guidance; and
- includes decision and revisit triggers.

Architecture diagrams become dangerous when they are accurate once and then
abandoned. Update or retire a diagram whenever the architecture changes.

## Official sources

- [Architecture diagrams in the Well-Architected Framework](https://learn.microsoft.com/en-us/azure/well-architected/architect-role/design-diagrams)
- [Azure Architecture Center](https://learn.microsoft.com/en-us/azure/architecture/browse/)
- [Azure architecture icons](https://learn.microsoft.com/en-us/azure/architecture/icons/)
- [Architecture Center source repository](https://github.com/MicrosoftDocs/architecture-center)

[Back to the guide](https://github.com/Azure-Startup-Field-Guide/guide)
