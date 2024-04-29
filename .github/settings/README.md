# Repository Configuration Guide

This document outlines the configuration settings for our GitHub repository. These settings are essential for maintaining an organized, secure, and efficient workflow.

## Repository Settings

- **Wiki Enabled**: A Wiki is available for documenting project details and guides.
- **Issue Tracking Enabled**: Issue tracking is used to manage tasks and bugs.
- **Projects Enabled**: GitHub Projects are utilized for visual task management and workflow organization.
- **Visibility**: The repository is set to `internal` visibility, restricting access to our organization members only.
- **Forking Disabled**: Forking of the repository is disabled to control the distribution of the codebase.
- **License**: The codebase is protected under an all rights reserved license. Please see the LICENSE file for more details.

## Team Permissions

- **DevOps Team**
  - **Role**: Admin
  - **Permissions**: Full control over repository settings and code management.

## Branch Protection Rules

### Development Branch (`dev`)
- **Protection Enabled**: Yes
- **Required Status Checks**: Must pass CI build and tests.
- **Enforce Rules on Admins**: Yes
- **Required Approvals**: 1 approval required for merging.
- **Force Pushes**: Disabled
- **Branch Deletions**: Disabled

### Staging Branch (`stag`)
- **Protection Enabled**: Yes
- **Required Status Checks**: Must pass CI build and tests.
- **Enforce Rules on Admins**: Yes
- **Required Approvals**: No approvals required; additional scrutiny is assumed.
- **Force Pushes**: Disabled
- **Branch Deletions**: Disabled

### Production Branch (`prod`)
- **Protection Enabled**: Yes
- **Required Status Checks**: Must pass CI build and tests.
- **Enforce Rules on Admins**: Yes
- **Required Approvals**: 1 approval required.
- **Force Pushes**: Disabled
- **Branch Deletions**: Disabled

## Merge Settings

- **Squash Merging**: Enabled
- **Merge Commits**: Disabled
- **Rebase Merging**: Enabled
- **Delete Branch on Merge**: Enabled

## Security and Analysis Settings

- **Dependabot Alerts**: Enabled
- **Code Scanning Alerts**: Enabled

## Additional Workflow Settings

- **Force Pull Before Commit**: True
- **Suggest Existing Branches**: True

These settings are configured to enhance our workflow, ensure code quality, and protect the integrity of our codebase. For any changes or suggestions, please contact the repository administrators or raise an issue.
