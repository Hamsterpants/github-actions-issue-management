# GitHub Actions Workflows

This repository contains two GitHub Actions workflows designed to automate issue management tasks based on branch creation events. These workflows help streamline the development process by automatically assigning the branch creator to the related issue and labeling the issue as "In Progress".

## Workflows Overview

### 1. Assign Branch Creator to Issue

This workflow triggers on the creation of new branches (excluding `main`, `master`, and `develop`). It automatically assigns the GitHub user who created the branch to the corresponding issue. The issue number is expected to be the leading digits in the branch name.

#### Trigger Conditions
- Branch creation, excluding `main`, `master`, and `develop`.

#### Main Actions
- Extracts the issue number from the branch name.
- Assigns the branch creator to the extracted issue number.

### 2. Label Issue as In Progress

Similar to the first workflow, this one also triggers on the creation of new branches, with the same exclusions. It labels the corresponding issue as "In Progress", facilitating workflow management and visibility into the issue's current status.

#### Trigger Conditions
- Branch creation, excluding `main`, `master`, and `develop`.

#### Main Actions
- Extracts the issue number from the branch name.
- Adds the "In Progress" label to the extracted issue number.

## Setup Instructions

1. **Ensure GitHub CLI is Available**: These workflows require the GitHub CLI (`gh`) to be installed on the runner. The workflows include steps to install `gh` if it's not already present.

2. **GitHub Token**: The workflows use the `GITHUB_TOKEN` secret for authentication. This token is automatically provided by GitHub Actions and does not require manual setup.

3. **Branch Naming Convention**: For these workflows to function correctly, branches should be named with the issue number as the leading digits, followed by a descriptive name. For example, `123-add-new-feature`.

4. **Add Workflows to Your Repository**: To use these workflows, add them to your repository under the `.github/workflows/` directory. Each workflow should be in its own `.yml` file.

5. **Label Setup**: Ensure the "In Progress" label exists in your repository's issues labels for the second workflow to function correctly.

## Customization

You can customize these workflows to fit your project's needs. This includes adjusting the branch naming conventions, modifying the excluded branches, and changing the labels applied to issues.
