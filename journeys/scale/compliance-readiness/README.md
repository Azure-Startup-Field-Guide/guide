# Compliance and enterprise readiness

> **Default:** derive controls from customer, data, geography, and regulation
> requirements instead of collecting generic certifications.

Compliance is shared responsibility. Azure certifications can support the
startup's control environment, but they do not certify the startup's product.

## Start with the requirement

1. Identify the customer, regulator, contract, or data class creating the
   requirement.
2. Define which systems, people, regions, and vendors are in scope.
3. Map data collection, processing, storage, transfer, retention, and deletion.
4. Select the relevant control framework.
5. Map inherited Azure controls and startup-owned controls.
6. Assign evidence owners and collection frequency.
7. Track exceptions, compensating controls, and remediation dates.
8. Validate the design with qualified legal, privacy, and security specialists.

## Minimum enterprise evidence

- architecture and data-flow diagrams;
- asset and data inventory;
- identity, privileged-access, and access-review records;
- secure development and dependency process;
- logging, alerting, and incident-response evidence;
- backup and recovery tests;
- vulnerability and patch ownership;
- business continuity assumptions;
- vendor and subprocessor inventory; and
- current Azure compliance documentation for selected services and regions.

## Azure tools and boundaries

Microsoft Purview Compliance Manager can help assess and track improvement
actions. Microsoft Defender for Cloud regulatory-compliance capabilities can
assess Azure resource configuration against standards when the required plan
and policy assignments are in place.

These tools provide evidence and posture management. They do not replace legal
interpretation, product controls, independent audits, or contractual review.

## Avoid

- claiming certification because Azure has it;
- selecting services before confirming regional and compliance availability;
- treating a policy assignment as proof that a control operates effectively;
- collecting evidence with no owner or retention plan; and
- letting a questionnaire become the first architecture review.

## Official sources

- [Microsoft Trust Center](https://www.microsoft.com/trust-center)
- [Azure compliance documentation](https://learn.microsoft.com/en-us/azure/compliance/)
- [Shared responsibility in the cloud](https://learn.microsoft.com/en-us/azure/security/fundamentals/shared-responsibility)
- [Microsoft Purview Compliance Manager](https://learn.microsoft.com/en-us/purview/compliance-manager)
- [Regulatory compliance in Defender for Cloud](https://learn.microsoft.com/en-us/azure/defender-for-cloud/concept-regulatory-compliance-standards)

[Back to scale and enterprise readiness](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/journeys/scale)
