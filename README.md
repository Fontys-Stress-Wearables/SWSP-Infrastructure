# SWSP Infrastructure

This repo contains a compose file and the configuration to run all services for the SWSP using the github packages.

## Requirements

Before you run the services you need to set the Azure AD client secret.
The docker compose file reads the secret from the `AzureAd__ClientSecret` environment variable.

You can set this variable either from the terminal or using an env-file.
To create an env-file with your client secret you can run:

```bash
$ echo "AzureAd__ClientSecret=<CLIENT SECRET>" > .env
```