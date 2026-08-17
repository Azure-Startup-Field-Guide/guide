# Secretless GitHub Actions deployments

> **Goal:** deploy to Azure without storing a client secret in GitHub.

GitHub Actions can exchange its OpenID Connect (OIDC) token for an Azure access
token through Microsoft Entra workload identity federation.

## Minimum implementation

1. Create a Microsoft Entra application or user-assigned managed identity.
2. Assign only the Azure role required at the narrowest practical scope.
3. Add a federated identity credential for the expected GitHub repository and
   branch, tag, pull request, or environment.
4. Add `id-token: write` to the deployment job permissions.
5. Use `azure/login` with client, tenant, and subscription identifiers.
6. Put production deployment behind a protected GitHub environment.
7. Remove the old client secret only after the federated path succeeds.

## Example shape

```yaml
permissions:
  contents: read
  id-token: write

steps:
  - uses: actions/checkout@v4
  - uses: azure/login@v2
    with:
      client-id: ${{ vars.AZURE_CLIENT_ID }}
      tenant-id: ${{ vars.AZURE_TENANT_ID }}
      subscription-id: ${{ vars.AZURE_SUBSCRIPTION_ID }}
```

Pin action versions according to the repository's dependency policy. The three
identifiers are not passwords, but repository or environment variables keep the
workflow portable.

## Trust-boundary checklist

- Do not trust every branch when only `main` should deploy.
- Use GitHub environments when approvals or environment-specific identity are
  required.
- Do not grant subscription-wide Contributor when a resource-group deployment
  role is sufficient.
- Separate production and nonproduction identities.
- Review the OIDC subject claim when a repository is renamed, transferred, or
  its trust model changes.
- Keep workflow permissions minimal for each job.

## Verification

The pipeline should deploy using OIDC after all client secrets have been
removed. An untrusted branch or repository must not be able to obtain the same
Azure access.

## Official sources

- [Use GitHub Actions to connect to Azure](https://learn.microsoft.com/en-us/azure/developer/github/connect-from-azure-openid-connect)
- [Workload identity federation](https://learn.microsoft.com/en-us/entra/workload-id/workload-identity-federation)
- [Create a trust relationship](https://learn.microsoft.com/en-us/entra/workload-id/workload-identity-federation-create-trust)
- [Configuring OIDC in Azure](https://docs.github.com/en/actions/how-tos/secure-your-work/security-harden-deployments/oidc-in-azure)

[Back to production foundation](https://github.com/Azure-Startup-Field-Guide/guide/tree/main/journeys/production)
