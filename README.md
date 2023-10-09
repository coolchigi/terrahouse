# Terraform Beginner Bootcamp 2023

## Semantic Versioning :mage:

This project is going to utilize semantic versioning for its tagging
[semver.org](https://semver.org)

Given a version number **MAJOR.MINOR.PATCH**, increment the:

- **MAJOR** version when you make incompatible API changes
- **MINOR** version when you add functionality in a backward cmpatible manner
- **PATCH** version when you make backcompatible bug fixes


## Install the Terraform CLI

### Considerations with the Terraform CLI changes
The terraform CLI installation instructions have changed due to gpg keyring changes. Need to refer to the latest install CLI insturctions via Terraform Docs and change the scripting for install

[Install Terraform CLI](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli)


### Refactoring into Bash Scripts
While fixing the Terraform CLI gpg depreciation issues, noticed that bash scrips steps were a considerable amount more code. Solution was to create a bash script to install the Terraform CLI
- Tidy the Gitpod Task File ([.gitpod.yml](.gitpod.yml))
- Bash script is located here [./bin/install_terraform_cli](./bin/install_terraform_cli)