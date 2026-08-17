# Relational or NoSQL data?

> **Default:** begin with a managed relational database unless a documented
> access pattern, scale model, or distribution requirement justifies NoSQL.

The shape of the application data is less important than how the workload reads,
writes, relates, partitions, and recovers it.

## Start with relational data when

- transactions span related records;
- referential integrity belongs in the data model;
- query patterns will evolve;
- reporting and ad hoc queries are important; or
- the team already has strong SQL operational experience.

Evaluate **Azure Database for PostgreSQL** when PostgreSQL compatibility,
extensions, tooling, or open-source ecosystem fit matters. Evaluate **Azure SQL
Database** when the application depends on SQL Server or T-SQL capabilities,
Microsoft data tooling, or Azure SQL tenancy patterns such as elastic pools.

## Choose Azure Cosmos DB when

- the data and access patterns naturally fit a supported nonrelational model;
- horizontal partitioning is an explicit design requirement;
- globally distributed reads or writes are required;
- predictable low-latency access at distributed scale is a product requirement;
  or
- tenant or workload isolation maps cleanly to a partition strategy.

Do not choose Cosmos DB only because the schema might change. Before deployment,
identify the partition key, expected request patterns, item growth, consistency
requirements, and how the team will observe request-unit consumption.

## Decision matrix

| Requirement | Evaluate first |
| --- | --- |
| PostgreSQL compatibility or ecosystem | Azure Database for PostgreSQL |
| SQL Server or T-SQL compatibility | Azure SQL Database |
| Relational transactions and joins | PostgreSQL or Azure SQL |
| Document or key-value access at distributed scale | Azure Cosmos DB |
| Global distribution | Cosmos DB, then validate consistency and topology |
| Database-per-tenant SaaS | Azure SQL or PostgreSQL tenancy patterns |
| Shared multitenant data | Any option, with explicit tenant isolation |

## Cost and operating questions

Compare more than the entry SKU:

- minimum and peak compute or throughput;
- storage, backup, and data-transfer growth;
- read-to-write ratio and query efficiency;
- high availability and disaster recovery;
- idle or bursty workload behavior;
- observability and support requirements; and
- the engineering cost of migrations and data-model changes.

Do not copy public pricing into an architecture decision. Use the Azure pricing
calculator and the startup's actual agreement pricing.

## Revisit the decision when

Re-evaluate the data platform when query patterns stabilize differently than
expected, a global distribution requirement becomes real, tenant isolation
changes, the partition strategy no longer scales, or database operations slow
product delivery.

## Official sources

- [Prepare to choose a data store in Azure](https://learn.microsoft.com/en-us/azure/architecture/guide/technology-choices/data-store-considerations)
- [Understand data store models](https://learn.microsoft.com/en-us/azure/architecture/data-guide/technology-choices/understand-data-store-models)
- [Azure SQL decision tree](https://learn.microsoft.com/en-us/azure/azure-sql/azure-sql-decision-tree)
- [Azure Database for PostgreSQL overview](https://learn.microsoft.com/en-us/azure/postgresql/overview)
- [Azure Cosmos DB serverless](https://learn.microsoft.com/en-us/azure/cosmos-db/serverless)
- [Multitenancy and Azure Cosmos DB](https://learn.microsoft.com/en-us/azure/architecture/guide/multitenant/service/cosmos-db)

[Back to technology decisions](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/decisions)
