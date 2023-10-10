# Deploy Terraform GitHub Action

Hello! This GitHub Action is designed to facilitate the deployment of Terraform configurations. If you're new to Terraform or GitHub Actions, this guide will provide a clear understanding.

## Overview

This action is designed to:

1. Trigger manually using the `workflow_dispatch` event.
2. Initialize the Terraform working directory.
3. Apply the Terraform plan.

## Inputs

Here are the inputs you can provide to this action:

- `additionalTerraformParameters`: Any additional parameters you want to pass to Terraform. Default is an empty string.
- `resourceGroup`: The Azure Resource Group. This is a required input.
- `resourceGroupLocation`: The location of your Azure Resource Group. Default is `eastus`.
- `targetEnvironment`: The target environment for your Terraform deployment. Default is `Dv`.
- `terraformVersion`: The version of Terraform you want to use. Default is `1.5.7`.
- `variablesYamlPath`: The path to your variables YAML file. Default is `./pipelines/variables.yaml`.
- `vmImage`: The VM image to run the action on. Default is `ubuntu-latest`.
- `workingDirectory`: The path to your Terraform workspace. Default is `./env`.

## Permissions

This action requires special permissions for OIDC authentication:

- `id-token`: write
- `contents`: read
- `pull-requests`: write

## Environment Variables

These environment variables are used by the Terraform Azure provider to set up OIDC authentication:

- `ARM_CLIENT_ID`
- `ARM_CLIENT_SECRET`
- `ARM_SUBSCRIPTION_ID`
- `ARM_TENANT_ID`

Ensure these are stored as secrets in your GitHub repository and are not exposed in your code.

Read more about GitHub Actions secrets [here](https://docs.github.com/en/actions/reference/encrypted-secrets).

## How to Use

1. **Setup Your Workflow**: In your main workflow file, you can call this action using the following syntax:

```yaml
- name: Deploy Terraform
  uses: [YOUR_REPOSITORY]/[YOUR_ACTION_PATH]@main
  with:
    resourceGroup: 'YOUR_RESOURCE_GROUP'
    # Add other inputs as needed
```

2. **Trigger the Workflow**: This workflow can be triggered manually using the `workflow_dispatch` event.

3. **Review the Output**: Always inspect the Terraform plan output before applying any changes to ensure the desired modifications are being made.

## Tips

- Familiarize yourself with the Terraform documentation for clarity on any commands or configurations.
- Ensure you have the necessary permissions and secrets set up in your GitHub repository for the Terraform Azure provider.
- If you encounter any challenges or have questions, refer to the documentation or seek assistance. Continuous learning and collaboration are essential in engineering!

Happy Terraforming! 🚀
