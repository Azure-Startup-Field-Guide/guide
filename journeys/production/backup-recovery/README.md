# Backup and recovery baseline

> **Goal:** recover the product and its data within explicitly agreed targets.

A successful backup job is not recovery evidence. Begin with the business
impact, define recovery time objective (RTO) and recovery point objective (RPO),
then select protection that meets them.

## Minimum baseline

1. Inventory every stateful component in the critical user flow.
2. Define RTO and RPO for each component and the end-to-end product.
3. Identify native database recovery, Azure Backup, replication, and export
   mechanisms that apply.
4. Configure protection in the same region as the protected resource when the
   service requires regional vault placement.
5. Enable the strongest generally available soft-delete and immutability
   controls supported by the selected vault and region.
6. Separate backup administration from workload administration.
7. Monitor failures through Azure Monitor and Backup Center.
8. Restore into an isolated location and record the actual recovery result.

## Recovery record

Keep a short record for each test:

| Field | Evidence |
| --- | --- |
| Scenario | Deletion, corruption, region loss, or credential compromise |
| Scope | Data and services restored |
| Recovery point | Timestamp and measured data loss |
| Recovery time | Start to verified service |
| Validation | Queries or user flows executed |
| Gaps | Missing dependency, permission, capacity, or runbook step |
| Owner and date | Person accountable for the next test |

## Important distinctions

- Backup protects recoverable state; high availability keeps a service running.
- Geo-replication does not replace protection from logical deletion or
  corruption.
- Soft delete adds a recovery window but does not eliminate the need to test.
- Vault features and release status can differ by vault type and region. Verify
  the selected design in current documentation before making it a hard control.

## Revisit the baseline when

Repeat the design and restore test after data-store changes, major schema
changes, new regions, new compliance requirements, or an RTO/RPO change.

## Official sources

- [Azure Backup architecture and components](https://learn.microsoft.com/en-us/azure/backup/backup-architecture)
- [Azure Backup best practices](https://learn.microsoft.com/en-us/azure/backup/guidance-best-practices)
- [Recovery Services vault overview](https://learn.microsoft.com/en-us/azure/backup/backup-azure-recovery-services-vault-overview)
- [Secure backups by default](https://learn.microsoft.com/en-us/azure/backup/secure-by-default)
- [Backup support matrices](https://learn.microsoft.com/en-us/azure/backup/backup-support-matrix)

[Back to production foundation](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/journeys/production)
