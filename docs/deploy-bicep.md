# Deploy Bicep GitHub Action

Welcome! This GitHub Action is crafted to assist in deploying Bicep configurations. If you're venturing into Bicep or GitHub Actions for the first time, this guide will elucidate the process for you.

## Overview

This action is designed to:

1. Trigger manually using the `workflow_dispatch` event.
2. Deploy the specified Bicep template.
3. Capture and upload the Bicep outputs.

## Inputs

Here are the inputs you can provide to this action:

- `bicepTemplatePath`: The path to the top-level Bicep template. Default is `env/main.bicep`.
- `additionalBicepParameters`: Any additional parameters you want to pass to the Bicep deployment. Default is an empty string.
- `clientAffix`: A required input to specify the client affix.
- `env`: The environment for your Bicep deployment. Default is `Dv`.
- `resourceGroup`: The Azure Resource Group. This is a required input.
- `resourceGroupLocation`: The location of your Azure Resource Group. Default is `eastus`.
- `variablesYamlPath`: The path to your variables YAML file. Default is `./pipelines/variables.yaml`.
- `vmImage`: The VM image to run the action on. Default is `ubuntu-latest`.

## How to Use

1. **Setup Your Workflow**: In your main workflow file, you can call this action using the following syntax:

```yaml
- name: Deploy Bicep
  uses: [YOUR_REPOSITORY]/[YOUR_ACTION_PATH]@v1
  with:
    resourceGroup: 'YOUR_RESOURCE_GROUP'
    # Add other inputs as needed
```

2. **Trigger the Workflow**: This workflow can be triggered manually using the `workflow_dispatch` event.

3. **Review the Output**: Always inspect the Bicep deployment output to ensure the desired infrastructure changes are being made.

## Tips

- Familiarize yourself with the Bicep documentation for clarity on any commands or configurations.
- Ensure you have the necessary permissions and secrets set up in your GitHub repository for the Azure login and Bicep deployment.
- If you encounter any challenges or have questions, refer to the documentation or seek assistance. Continuous learning and collaboration are essential in engineering!

Happy Biceping! 💪
