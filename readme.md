# GitHub Actions Guide

Welcome to our GitHub Actions guide! This documentation provides an overview and detailed instructions on how to use our Templated GitHub Actions. Whether you're looking to build or deploy IaC configurations, we've got you covered.

## Table of Contents

1. [Build Terraform Configuration](docs/build-tf.md)
2. [Deploy Terraform Configuration](docs/deploy-tf.md)
3. [Deploy Bicep Configuration](docs/deploy-bicep.md)

## Overview

Our Template GitHub Actions are designed to streamline the process of building and deploying IaC configurations. With clear instructions and best practices, you can ensure a smooth and efficient workflow.

### [Build Terraform Configuration](docs/build-tf.md)

This action helps you build Terraform configurations. It sets up the specified version of Terraform, initializes your Terraform working directory, formats your Terraform code, and generates an execution plan.

[Read more...](docs/build-tf.md)

### [Deploy Terraform Configuration](docs/deploy-tf.md)

This action facilitates the deployment of Terraform configurations. It initializes the Terraform working directory and applies the Terraform plan, allowing you to deploy your infrastructure changes seamlessly.

[Read more...](docs/deploy-tf.md)

### [Deploy Bicep Configuration](docs/deploy-bicep.md)

This action assists in deploying Bicep configurations. It logs into Azure, deploys the specified Bicep template, and captures the Bicep outputs.

[Read more...](docs/deploy.md)
