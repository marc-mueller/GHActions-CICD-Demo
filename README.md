# GitHub Actions Demo

## Setup

Perform the following action to setup resource groups and secrets fo the GitHub Actions Workflows

- Create a resource group

  ```
  az group create -n demo-gh-actions -l westeurope
  ```

- Create a service principal

  ```
  az ad sp create-for-rbac --name gh-actions-demo --role contributor --scopes /subscriptions/{subscription-id}/resourceGroups/demo-gh-actions --sdk-auth
  ```

- Create secrets in GitHub repository
  - AZURE_CREDENTIALS --> paste the entire json from the command above
  - AZURE_RG --> resource group name
  - AZURE_SUBSCRIPTION --> subscription id