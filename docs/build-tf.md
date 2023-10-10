# Build Terraform GitHub Action

Hello! This GitHub Action is designed to help you deploy Terraform configurations. If you're new to Terraform or GitHub Actions, this guide will walk you through the process.

## Overview

This action will:

1. Trigger on every `push` event or when manually dispatched using `workflow_dispatch`.
2. Use the `build-tf.yaml` workflow from the `delarooster/Dlr.Yaml.Templates` repository to build the Terraform configurations.

## Inputs

Here are the inputs you can provide to this action:

- `workingDirectory`: The path to your Terraform workspace. For this template, it's set to `./env`.
- `targetEnvironment`: The target environment for your Terraform deployment. For this template, it's set to `dev`.
- `resourceGroup`: The Azure Resource Group. For this template, it's set to `rg-mesh-dev`.

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

Read more about GitHub Actions secrets [here](https://docs.github.com/en/actions/reference/encrypted-secrets).

## How to Use

1. **Fork or Clone the Repository**: If this action is in a repository, you'll first need to fork or clone it.

2. **Setup Your Workflow**: In your main workflow file, you can call this action using the following syntax:

```yaml
- name: Deploy Terraform
  uses: [YOUR_REPOSITORY]/[YOUR_ACTION_PATH]@main
  with:
    resourceGroup: 'YOUR_RESOURCE_GROUP'
    # Add other inputs as needed
```

3. **Run the Workflow**: Once everything is set up, you can either push your changes to trigger the workflow or run it manually using the `workflow_dispatch` event.

4. **Review the Output**: Always check the Terraform plan output before applying any changes to ensure you're making the desired modifications.

## Tips

- Familiarize yourself with the Terraform documentation for any commands or configurations you're unsure about.
- Ensure you have the necessary permissions and secrets set up in your GitHub repository for the Terraform Azure provider.
- If you encounter any issues or have questions, don't hesitate to ask or refer to the documentation. Continuous learning is a key aspect of engineering!

Happy Terraforming! 🚀
