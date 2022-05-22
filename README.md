# SWSP Infrastructure

This repo contains a compose file and the configuration to run all services for the SWSP using the github packages.

## Requirements

### Azure AD client secret
Before you run the services you need to set the Azure AD client secret.
The docker compose file reads the secret from the `AzureAd__ClientSecret` environment variable.

You can set this variable either from the terminal or using an env-file.
To create an env-file with your client secret you can run:

```bash
$ echo "AzureAd__ClientSecret=<CLIENT SECRET>" > .env
```

### Authenticating Docker to access GitHub packages
Before you can run the docker compose, you will have to authenticate your docker client against GitHub to give it access to the package registry.

First, generate a Personal Access Token by clicking on your profile picture in the top right when in GitHub, going to "settings", then to "developer settings" and then "Personal Access Tokens". Here you can create a new token and specify what rights it should give. Make sure that "packages:read" at least is checked and then generate the token.

Now, make sure Docker desktop is running and then open your CLI of choice and enter:
```
docker login ghcr.io -u YOURUSENAMEHERE --password YOURPERSONALACCESSTOKENHERE
```

You should now be able to run Docker compose up in the infrastructure folder and pull all packages from the package registry.

