# cf-vault-plugin

Use Codefresh [Vault](https://www.vaultproject.io) plugin to make key-value pairs stored in a vault available as environmental variables for further steps.

NOTE: this plugin currently supports only token authentication and Key/Value secrets engine.
============================================================================================

## Usage

Set required and optional environment variables and add the following step to your Codefresh pipeline:


```yaml
---
version: '1.0'

steps:

  ...

  Vault_to_Env:
    title: Importing vault values
    image: 'codefresh/plugin-vault'
    environment:
      - VAULT_ADDR=${{VAULT_ADDR}}
      - VAULT_PATH=${{VAULT_PATH}}
      - VAULT_AUTH_TOKEN=${{VAULT_AUTH_TOKEN}}

  ...

```

## Environment Variables

| Variables      | Required | Default | Description                                                                             |
|----------------|----------|---------|-----------------------------------------------------------------------------------------|
| VAULT_ADDR     | YES      |         | Vault server URI                                                                         |
| VAULT_PATH   | YES      |         | Path to secrets in vault                                                                       |
| VAULT_AUTH_TOKEN   | YES      |         | Vault authentication token                            |
| VAULT_CLIENT_CERT_BASE64      | NO       |         | Base64 encoded client cerificate                                                             |
| $VAULT_CLIENT_KEY_BASE64  | NO       |         | Base64 encoded client key                                                          
