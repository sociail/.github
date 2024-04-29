# GitHub Actions Workflows

This README provides detailed information about the GitHub Actions workflows configured in our repository. These workflows are designed to streamline our development processes, ensure consistency across multiple repositories, and enhance security and workflow management.

## Workflows Overview

We have two main workflows configured in our `.github/workflows` directory:

### 1. Apply Repository Settings (`apply_settings.yml`)

#### Description
This workflow automatically synchronizes repository settings from a designated source repository to the `.github` directory of the current repository. It ensures that our repository settings remain consistent and up-to-date with our organizational standards.

#### Triggers
- **Push to `dev` Branch**: This workflow runs whenever changes are pushed to the `dev` branch.
- **Manual Dispatch**: It can also be triggered manually through the GitHub UI, allowing for flexibility in managing settings application as needed.

#### Actions
- **Checkout**: Fetches the latest code from the repository.
- **Sync Settings**: Uses `repo-sync/github-sync@v2` to synchronize `.github` directory contents from the source repository.

### 2. Apply Select Repository Settings (`apply_settings_select.yml`)

#### Description
This manually triggered workflow provides granular control over applying repository settings across multiple repositories. It is ideal for situations where selective updates are necessary, avoiding the blanket application of settings.

#### Triggers
- **Manual Dispatch with Input**: Triggered manually via GitHub UI. It includes an input to decide whether to apply settings to all listed repositories or selectively based on other criteria.

#### Actions
- **Checkout**: Fetches the latest code from the repository.
- **Conditional Application**: A custom script checks the input and applies settings to either all listed repositories or selectively, based on the specified condition.

#### Input Options
- `apply_to_all`: Set to `yes` to apply settings to all repositories listed in the workflow file. Set to `no` to apply selectively.

## General Information

These workflows are integral to maintaining the operational integrity and consistency of our development practices. They are regularly updated to adapt to new requirements and improvements in our workflow processes.

For any modifications or suggestions regarding these workflows, please consult with the DevOps team or open an issue in the repository to discuss potential changes.


