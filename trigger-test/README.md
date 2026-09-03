# trigger-test

Calls the SDLC control plane test endpoint to validate the end-to-end flow:
FastAPI → Service Bus → Worker → Storage (hello.txt).

## Usage

```yaml
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: IndentWork/sdlc-actions/trigger-test@main
        with:
          api-url: ${{ vars.SDLC_API_URL }}
          tenant-id: ${{ vars.SDLC_TENANT_ID }}
```

## Inputs

| Input | Required | Description |
|---|---|---|
| `api-url` | Yes | SDLC Control Plane API URL |
| `tenant-id` | Yes | Tenant UUID from the SDLC control plane |

## Required GitHub Variables

Set these in the tenant's `sdlc-config` repo settings → Variables:

| Variable | Value |
|---|---|
| `SDLC_API_URL` | `https://ca-sdlc-base-dev.xxx.centralindia.azurecontainerapps.io` |
| `SDLC_TENANT_ID` | Tenant UUID from POST /tenants response |
