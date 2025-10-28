# Secret Service Action

A GitHub composite action that exchanges a GitHub Actions OIDC token for secrets from the secret service.

## Prerequisites

Your workflow must have the `id-token: write` permission to request OIDC tokens.

## Usage

```yaml
jobs:
  publish:
    runs-on: ubuntu-latest
    permissions:
      id-token: write  # Required for OIDC token
    steps:
      # For security please pin this to the SHA of the latest release
      #  - https://github.com/electron/secret-service-action/releases/latest
      - uses: electron/secret-service-action@{sha}
```

## Inputs

| Name | Description | Required |
|------|-------------|----------|
| `endpoint` | The secret service endpoint to exchange the OIDC token for secrets | No |

## Outputs

| Name | Description |
|------|-------------|
| `secrets` | The returned secrets (masked in GHA) in JSON format |
